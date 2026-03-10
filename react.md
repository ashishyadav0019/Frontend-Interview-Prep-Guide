# React Notes — Staff Engineer Level

## Q1) What exactly happens when state changes in React?

When state changes, React runs two major phases: **render** and **commit**.

In the **render phase**, React re-runs component functions to compute the next UI tree, then reconciles (diffs) it against the previous tree using the Fiber architecture. This phase is interruptible — React can pause low-priority renders to service urgent updates (e.g., user typing). It operates on a *work-in-progress* Fiber tree, leaving the current (committed) tree untouched until done.

The **commit phase** is synchronous and has three sub-phases:
1. **Before-mutation** — reads DOM state before changes, runs `getSnapshotBeforeUpdate`.
2. **Mutation** — applies DOM insertions, updates, deletions.
3. **Layout** — runs `useLayoutEffect` and `componentDidMount/Update` synchronously after DOM update but before paint.

`useEffect` runs asynchronously after paint — outside the commit phase entirely.

### Quick recall
- Render phase: interruptible, computes what changes.
- Commit phase (3 sub-phases): synchronous, applies changes.
- `useLayoutEffect` → before paint (use for DOM measurements).
- `useEffect` → after paint (use for side effects).
- Double buffering: work-in-progress tree vs current tree.

---

## Q2) What is automatic batching in React 18, and why does it matter?

React 18 batches all state updates — including those inside setTimeout, Promises, and native event handlers — into a single re-render. Before React 18, only updates inside React event handlers were batched; async updates each triggered separate renders.

This matters for performance (fewer renders = less work) but also for correctness when building concurrent features. Updates triggered within `startTransition` are batched together and can be interrupted if higher-priority updates arrive.

If you need to opt out of batching (rare), use `flushSync` from `react-dom`.

### Quick recall
- React 18: async updates are batched automatically.
- Fewer renders, better responsiveness.
- `flushSync` to force synchronous render when truly needed.
- Use functional updates when next value depends on previous state.

---

## Q3) Why should we use functional updates like `setCount(prev => prev + 1)`?

In concurrent mode, React may process multiple queued state updates before committing. If you derive next state from a captured variable (`setCount(count + 1)`), you risk computing from a stale snapshot. The updater function receives the most recent committed state as its argument, guaranteeing correctness regardless of how many updates are queued.

```js
// Risky in concurrent mode — `count` may be stale
setCount(count + 1);

// Safe — always operates on latest state
setCount(prev => prev + 1);
```

### Quick recall
- Use functional update whenever next state depends on current state.
- Critical in concurrent mode where updates may be queued and batched.
- Also applies to `useReducer` dispatch — reducers are pure and receive current state.

---

## Q4) Why is using array index as key considered risky?

React keys represent **identity**, not position. When you use index as key and list order changes (sort, filter, insert at non-end), React sees the same key at a position and reuses the existing component instance — carrying over internal state that now belongs to a different data item. This causes subtle bugs with input fields, focus state, animations, and uncontrolled components.

Index keys also cause unnecessary re-renders and remounts during reordering because reconciliation can't distinguish a reorder from full replacement.

### Quick recall
- Key = identity. Index = position. They diverge when list changes.
- Causes state/UI attached to wrong item on reorder.
- Index key acceptable only for truly static, never-reordered lists.
- Use stable data IDs from your backend/domain model.

---

## Q5) What problem did React Fiber solve?

The pre-Fiber "stack reconciler" processed the entire component tree synchronously in one pass. Long trees blocked the main thread, causing dropped frames and unresponsive UI during large updates.

Fiber reimplemented reconciliation as a linked list of work units ("fibers") that can be scheduled, paused, resumed, and prioritized. Each fiber represents one component's work. React can process a few fibers, yield to the browser for input/paint, then resume — making rendering cooperative rather than blocking.

This is the foundation for all of React's modern concurrency features: transitions, Suspense, Server Components, and concurrent rendering.

### Quick recall
- Old: synchronous, can't interrupt.
- Fiber: cooperative, scheduled, prioritized work units.
- Render interruptible; commit is not.
- Enables: Suspense, transitions, concurrent features, Server Components.

---

## Q6) What are lanes and where does `startTransition` fit in?

Lanes are React's internal priority model — a bitmask system that classifies updates by urgency. Synchronous input events (typing, clicking) use high-priority lanes. Background rendering (data loading, large list updates) uses low-priority lanes.

`startTransition` marks an update as non-urgent (low-priority lane), allowing React to interrupt it if a high-priority update arrives. This is what keeps typing responsive even while React is computing a large filtered list.

`useDeferredValue` is the consumer-side complement — it lets a component subscribe to a value that may lag behind the latest state, rendering with the deferred (previous) value until React has time to commit the new one.

```js
// Mark as non-urgent — can be interrupted
startTransition(() => setSearchQuery(input));

// Render with deferred value — won't block urgent updates
const deferredQuery = useDeferredValue(searchQuery);
```

A key nuance: transitions don't just defer renders — React can **abandon** a transitional render entirely if a newer update supersedes it, avoiding wasted work.

### Quick recall
- Lanes = priority bitmask (sync > input > transition > idle).
- `startTransition` → low priority, interruptible, abandonable.
- `useDeferredValue` → consumer-side deferral, renders with stale value until ready.
- Both keep urgent interactions (typing/clicking) snappy.

---

## Q7) What is the practical difference between `useMemo` and `useCallback`?

`useMemo` memoizes a **computed value** and recomputes only when dependencies change. `useCallback` memoizes a **function reference** (identity) and returns a stable reference across renders unless dependencies change.

```js
const filtered = useMemo(() => items.filter(fn), [items, fn]);    // value
const handleSave = useCallback(() => save(id), [id]);              // function
```

Both serve referential stability — preventing downstream `React.memo` wrapped components from re-rendering when props haven't semantically changed.

### Quick recall
- `useMemo` → stable value.
- `useCallback` → stable function reference.
- Only useful when passed to memoized children or used as `useEffect` dependency.
- React 19: `React.memo` is being deprecated in favor of `use` and compiler optimizations — the React Compiler (Forget) automates most memoization.

---

## Q8) Why can overusing memoization hurt?

Every `useMemo`/`useCallback` call adds: dependency array allocation, comparison work on each render, and cached value retention in memory. For cheap computations or non-memoized children, this overhead exceeds any benefit.

More importantly, premature memoization can mask structural problems — if a component re-renders too often, the right fix is often better state colocation or component splitting, not adding memo hooks to paper over it.

Profile with React DevTools Profiler first. Optimize proven bottlenecks.

With the **React Compiler** (in production at Meta, available as opt-in), much of this manual memoization becomes unnecessary — the compiler automatically inserts stable references where beneficial.

### Quick recall
- Memoization has real cost: memory + comparison per render.
- Profile before optimizing — don't blanket-apply.
- React Compiler will automate most of this; write clean code first.

---

## Q9) What problem does Suspense solve in data-heavy UIs?

Without Suspense, every async operation requires imperative loading state: `if (loading) return <Spinner>`. In deeply nested trees, this creates scattered, inconsistent loading UI and makes coordinated loading states hard to manage.

Suspense provides **declarative loading boundaries** — components declare what they need, and the nearest `<Suspense>` boundary handles the pending state. This enables:
- Coordinated loading UI without per-component flags.
- Progressive rendering — show shell immediately, fill in sections as they load.
- Integration with streaming SSR (React 18) — server streams HTML progressively as Suspense boundaries resolve.

### Quick recall
- Declarative loading boundary — replaces scattered `if (loading)` checks.
- Enables progressive rendering and streaming SSR.
- Pair with Error Boundary for complete async state handling.

---

## Q10) How does Suspense work internally at a high level?

When a component attempts to read data that isn't ready yet (via a Suspense-compatible data source), it throws a Promise during render. React catches it at the nearest `<Suspense>` boundary, shows the fallback, and subscribes to the Promise. When the Promise resolves, React retries rendering the suspended subtree from the boundary.

This retry model integrates with Fiber lanes — the retry is scheduled at the appropriate priority so it doesn't block urgent updates.

Libraries that integrate with Suspense (React Query, SWR, Relay, Next.js `use()`) implement this throw-Promise contract internally. The new `use()` hook in React 19 exposes this directly.

### Quick recall
- Pending read throws Promise during render.
- Boundary catches → shows fallback → retries on resolve.
- Libraries wrap this contract (`use()`, React Query, Relay).
- Retry is prioritized — won't block urgent interactions.

---

## Q11) Does Suspense also handle errors?

No. Suspense handles *pending* state. Rejected Promises and render errors require an **Error Boundary** (class component with `componentDidCatch` / `getDerivedStateFromError`, or `react-error-boundary` library).

A robust async architecture pairs them: Suspense for loading, Error Boundary for failure, together forming a complete async state machine for any subtree.

```jsx
<ErrorBoundary fallback={<ErrorUI />}>
  <Suspense fallback={<Skeleton />}>
    <DataDrivenComponent />
  </Suspense>
</ErrorBoundary>
```

### Quick recall
- Suspense → loading.
- Error Boundary → error.
- Always pair both for production-grade async UI.

---

## Q12) What is the difference between fetch-on-render and render-as-you-fetch?

**Fetch-on-render**: Component mounts, then triggers fetch inside `useEffect`. In nested component trees, this creates waterfall requests — each child waits for its parent to render before starting its own fetch.

**Render-as-you-fetch**: Data fetching is initiated *before* rendering begins — at the router/loader layer (Next.js `getServerSideProps`, React Router loaders, TanStack Router loaders). Components receive data that is already in-flight or resolved when they render. Combined with Suspense, components suspend if data isn't ready yet, but they never *initiate* fetches inside render.

```jsx
// Initiate fetch at route boundary (before render)
const userPromise = fetchUser(params.id);

function UserProfile() {
  const user = use(userPromise); // suspends if not ready
  return <h1>{user.name}</h1>;
}
```

### Quick recall
- Fetch-on-render → waterfall, slower perceived load.
- Render-as-you-fetch → parallel requests, faster perceived load.
- Modern routers (Next.js App Router, TanStack Router) implement this natively.

---

## Q13) What are React Server Components (RSC)?

RSC is a paradigm shift: components can render on the server and send serialized UI (not HTML strings) to the client. Server Components have **zero client-side JS footprint** — they don't ship to the browser bundle at all.

Key rules:
- Server Components can `async/await` directly — no `useEffect` fetching needed.
- Server Components cannot use hooks, event handlers, or browser APIs.
- `"use client"` boundary marks where client components begin.
- Client components can be *imported by* Server Components but not the reverse.

```jsx
// ServerComponent.tsx — runs only on server
async function UserData({ id }) {
  const user = await db.getUser(id); // direct DB access, no API layer needed
  return <ClientCard user={user} />;  // passes data to client component
}
```

Benefits: smaller client bundles, direct backend access, no API layer for data colocation, better security (sensitive logic never reaches client).

Trade-offs: new mental model, serialization constraints (can't pass functions/classes to client), hydration complexity, framework dependency (currently Next.js App Router, or custom RSC setups).

### Quick recall
- Server Components: zero client JS, can access DB/FS directly, no hooks.
- `"use client"` marks client boundary — everything below is client bundle.
- Passes *serializable* props to client components only.
- Enables drastic bundle reduction for data-heavy pages.

---

## Q14) How do I explain state management choices: Context vs Redux vs Zustand?

State management choice maps to problem shape:

**Context API** — best for low-frequency, cross-tree state: auth user, theme, locale, feature flags. Simple, zero dependency. Pitfall: all consumers re-render on any context value change unless carefully split or memoized. Not suitable for high-frequency state (mouse position, form state, real-time data).

**Zustand** — lightweight global store with selector-based subscriptions. Components only re-render when their selected slice changes. Low boilerplate, easy adoption, great middle ground. Trade-off: fewer architectural guardrails than Redux — teams must enforce consistency themselves.

**Redux Toolkit** — best for complex state domains with strict predictability requirements: multi-team, large apps, complex async workflows, time-travel debugging, audit requirements. Strong conventions, excellent devtools, RTK Query for server state. Trade-off: more setup and conceptual overhead.

**React Query / TanStack Query** — treat server state (async data) separately from UI state. Handles caching, background refetch, optimistic updates, and stale-while-revalidate out of the box. Often the right answer for "how do we manage API data" — separate from UI state management entirely.

At Staff level: define which category of state (server state, global UI state, local component state, URL state) lives where, and document it as an architectural decision. This prevents state management sprawl.

### Quick recall
- Local state → `useState`/`useReducer`.
- Server state → React Query / SWR.
- Simple global UI state → Context or Zustand.
- Complex, predictable, multi-team state → Redux Toolkit.
- URL state → router params/search params.

---

## Q15) What is the difference between CSR, SSR, and SSG — and when to use each?

**CSR (Client-Side Rendering)**: Minimal HTML shell, all rendering in browser via JS. Best for authenticated apps where SEO is less important and interactivity is high. Slower first meaningful paint; LCP depends on JS execution.

**SSR (Server-Side Rendering)**: HTML generated per-request on server, hydrated on client. Best for SEO-critical dynamic pages with user-specific content. Faster first paint, better LCP — but higher server cost and hydration complexity. React 18 streaming SSR allows progressive HTML delivery before full data is ready.

**SSG (Static Site Generation)**: Pages pre-rendered at build time, served from CDN. Best for content that changes infrequently (docs, blogs, marketing). Fastest delivery, lowest cost. Freshness requires ISR (Incremental Static Regeneration) or rebuild pipelines.

**ISR (Incremental Static Regeneration)**: Next.js feature that regenerates static pages in the background after a revalidation interval. Combines SSG performance with SSR freshness — strong default for many content pages.

Real systems use all four at the route level: marketing → SSG, product pages → ISR, user dashboard → SSR or CSR, realtime features → CSR with WebSocket/SSE.

### Quick recall
- CSR: rich interactivity, weaker first-load/SEO.
- SSR: better first paint + SEO for dynamic content.
- SSG: fastest/cheapest for static content.
- ISR: SSG freshness without full rebuild.
- Choose per route, not per application.

---

---

## Q14) How do you improve state management efficiency to prevent rendering bottlenecks?

State management performance problems are usually one of: too many components re-rendering, too much state in one place, or derived state recomputed on every render.

**Context over-rendering — the most common React perf issue:**
```js
// Bad — every consumer re-renders when ANY field in context changes
const AppContext = createContext({ user, theme, notifications, cart });

// Fix — split contexts by update frequency
const UserContext = createContext(user);         // changes rarely
const ThemeContext = createContext(theme);       // changes rarely
const CartContext = createContext(cart);         // changes often
// Components only subscribe to what they need
```

**Selector pattern with Zustand:**
```js
// Bad — component re-renders on any store change
const store = useStore();

// Good — re-renders only when count changes
const count = useStore(state => state.count);
const increment = useStore(state => state.increment); // stable function ref
```

**Derived state — compute once, not on every render:**
```js
// Bad — recomputed every render
function OrderList({ orders }) {
  const total = orders.reduce((sum, o) => sum + o.amount, 0); // every render
  const sorted = [...orders].sort((a, b) => b.date - a.date); // every render
}

// Fix — memoize
const total = useMemo(() => orders.reduce((sum, o) => sum + o.amount, 0), [orders]);
const sorted = useMemo(() => [...orders].sort((a, b) => b.date - a.date), [orders]);
```

**Virtualization for long lists:**
```js
// Rendering 10,000 DOM nodes is always slow regardless of framework
// Use react-window or react-virtual — only render visible rows

import { FixedSizeList } from "react-window";

<FixedSizeList height={600} itemCount={10000} itemSize={50} width="100%">
  {({ index, style }) => <Row style={style} item={items[index]} />}
</FixedSizeList>
```

### Quick recall
- Split context by update frequency — coarse context is the #1 React perf killer.
- Selectors: subscribe to slices, not full store.
- `useMemo` for expensive derived state that depends on stable inputs.
- Virtualize lists beyond ~100 items.
___

## Staff-only Topics (not in original notes)

### Accessibility at Scale
Own axe-core in CI (via `jest-axe` for unit, `@axe-core/playwright` for E2E). Define ARIA authoring patterns in the design system. Run periodic WCAG 2.1 AA audits. Staff engineers often own a11y compliance org-wide — including the process, not just the implementation.

### Design System Architecture
At Staff level, you define component API contracts, token architecture, versioning strategy, and the boundary between primitive components and composed patterns. The design system is a product with its own roadmap and consumers.

### Performance Budget Governance
Define bundle size budgets, Web Vitals SLOs, and automated regression detection. Connect deploy pipeline to Lighthouse CI or RUM alerts. When a PR degrades INP or LCP, the build should fail or require explicit sign-off.

