# JavaScript Notes — Staff Engineer Level

## Q1) What is the Critical Rendering Path (CRP), and why is it important?

The Critical Rendering Path is the browser's sequence for converting HTML, CSS, and JavaScript into visible pixels. At Staff level, CRP matters not just as a concept but as an architectural constraint that drives decisions around asset loading strategy, build pipeline design, and performance budgets across a product org.

Poor CRP hygiene compounds — 

render-blocking resources delay first paint,
large JS bundles delay interactivity,
and unoptimized images delay LCP.
  
   A Staff engineer owns the systems that prevent these regressions at scale, not just fixes them case by case.

### Quick recall
- CRP directly affects FCP, LCP, and INP.
- Frontend perf = network + parse + render + interaction cost.
- Staff responsibility: define org-wide standards, enforce via CI, monitor via RUM.

---

## Q2) What are the stages of CRP?

`DOM → CSSOM → Render Tree → Layout → Paint → Composite`

Each stage has measurable cost. Delays cascade: a late CSS file blocks Render Tree construction; a synchronous script blocks DOM parsing; an unoptimized paint causes jank on scroll.

At Staff level, you architect around these stages — for example, inlining critical CSS to unblock early paint, or enforcing compositor-safe animation properties in a design system so 60fps is guaranteed by convention, not by individual developer discipline.

### Quick recall
- Layout is expensive; avoid triggering it in loops.
- `transform`/`opacity` are compositor-only — no layout recalc.
- `will-change` hints compositor but has memory cost; use sparingly.

---

## Q3) Why does CSS block rendering and JavaScript block parsing?

CSS blocks rendering because the browser needs a complete CSSOM before it can construct the Render Tree — painting unstyled content would require a repaint. JS blocks HTML parsing (for classic scripts) because scripts can call `document.write` or modify the DOM, making parsing state unpredictable.

`async` decouples script download from parsing but executes as soon as downloaded — order not guaranteed. `defer` executes after parsing completes, in order — better default for most app scripts. Module scripts (`type="module"`) defer by default.

### Quick recall
- `defer`: parse first, execute in order after. Best for most scripts.
- `async`: parallel download, execute immediately on load. Good for analytics/beacons.
- Classic sync script: blocks parser. Avoid in critical path.

---

## Q4) What is Critical CSS and when should it be used?

Critical CSS is the minimum style subset needed to render above-the-fold content without a flash of unstyled content. Inlining it in `<head>` allows an early meaningful paint while the full stylesheet loads asynchronously.

At Staff level, you'd automate Critical CSS extraction in the build pipeline (tools like `critical` or `critters`), integrate it into your SSR/SSG output, and validate it doesn't drift as the design system evolves. Manual critical CSS is a maintenance liability at scale.

### Quick recall
- Inline critical, async-load the rest.
- Automate extraction — manual doesn't scale.
- Re-audit when design tokens or layout structure changes.

---

## Q5) Is an image part of CRP?

Images don't block initial text/layout paint like CSS does, but they are critical to user experience metrics. The Largest Contentful Paint (LCP) is often dominated by a hero image — so while images aren't render-blockers in the strict CRP sense, they are LCP-blockers in practice.

Missing explicit `width`/`height` on images causes Cumulative Layout Shift (CLS). Unoptimized images hurt LCP. Both are Core Web Vitals that affect SEO ranking and user experience.

### Quick recall
- Not a render-blocker like CSS.
- Critical for LCP (hero image) and CLS (missing dimensions).
- Use `loading="lazy"` for below-fold, `fetchpriority="high"` for LCP image.

---

## Q6) What is layout thrashing?

Layout thrashing occurs when code alternates between DOM writes and geometry reads in a loop, forcing the browser to recalculate layout synchronously on each read because pending writes have invalidated the previous layout state.

```js
// Bad — thrashing
elements.forEach(el => {
  el.style.width = el.offsetWidth + 10 + 'px'; // write then read in same loop
});

// Good — batch reads, then writes
const widths = elements.map(el => el.offsetWidth); // all reads
elements.forEach((el, i) => { el.style.width = widths[i] + 10 + 'px'; }); // all writes
```

### Quick recall
- Read all geometry first, then write all styles.
- `offsetWidth`, `getBoundingClientRect`, `scrollTop` etc. are layout-triggering reads.
- Use `requestAnimationFrame` to align writes with frame boundaries.

---

## Q7) How do we prevent layout thrashing at scale?

The micro-pattern is: batch reads before writes, use `requestAnimationFrame` for visual updates, and prefer `transform`/`opacity` for animations. At Staff level, you encode these rules into your design system and linting setup so individual engineers can't accidentally introduce thrashing — the architecture prevents the mistake.

Also useful: `ResizeObserver` for element size changes (avoids polling), `IntersectionObserver` for viewport-relative logic (avoids scroll event + `getBoundingClientRect` loops).

### Quick recall
- Read → write, never interleaved.
- `transform`/`opacity` stay in compositor thread.
- `ResizeObserver` / `IntersectionObserver` for reactive measurement without thrashing.
- Enforce via design system conventions and ESLint rules where possible.

---

## Q8) Why does JavaScript bundle size affect performance so much?

Bundle size is a three-part cost: download, parse, and execution. Download scales with network speed; parse and execution scale with device CPU. On mid-range Android devices (which represent a large global user segment), CPU cost often dominates — a 1MB JS bundle can take 3–5 seconds to parse and execute even after it's downloaded.

Large bundles also worsen INP (Interaction to Next Paint) because long tasks block the main thread and delay response to user input.

### Quick recall
- Cost = download + parse + execute. All three matter.
- Mobile CPU is the real bottleneck for many users.
- INP degrades when main thread is blocked by large JS evaluation.

---

## Q9) What are practical ways to reduce bundle size — at Staff scale?

Individual techniques: ES module tree shaking, dynamic `import()` for route/feature splitting, lazy loading non-critical modules, production minification, dead-code elimination.

At Staff scale, you also: enforce bundle budgets in CI (`bundlesize`, Webpack `performance.maxAssetSize`, Vite `build.chunkSizeWarningLimit`), run `webpack-bundle-analyzer` or `vite-bundle-visualizer` as part of build output, track bundle size trends over time in your observability stack, and audit third-party dependencies for size/cost before adoption (e.g., `moment` vs `date-fns` vs `Temporal`).

Module federation enables shared dependencies across microfrontends so common libraries (React, design system) aren't duplicated in every app bundle.

### Quick recall
- Ship less, split smartly, monitor continuously.
- Enforce budgets in CI — don't rely on manual review.
- Module federation for microfrontend shared dep deduplication.
- Measure third-party cost before adoption.

---

## Q10) How does the event loop prioritize microtasks and macrotasks?

After synchronous stack completes, the runtime drains **all** microtasks (Promises, `queueMicrotask`, MutationObserver callbacks) before processing the next macrotask (setTimeout, setInterval, I/O callbacks, requestAnimationFrame).

Browser rendering checkpoints generally occur between macrotasks. So a microtask flood — e.g., a long Promise chain — can delay rendering just as a long sync task can. React 18's scheduler uses `MessageChannel` (a macrotask) to yield to the browser between chunks of work, specifically to avoid this problem.

```
Sync → all Microtasks → [render opportunity] → one Macrotask → all Microtasks → repeat
```

### Quick recall
- Microtasks drain completely before next macrotask.
- Promise chains = microtasks — can starve rendering if abused.
- `queueMicrotask()` for scheduling work before next macrotask without setTimeout overhead.
- React 18 scheduler yields via `MessageChannel` to unblock rendering.

---

## Q11) Why is `setTimeout(fn, 0)` not immediate?

The callback enters the macrotask queue. It must wait for: current sync stack to complete, all queued microtasks to drain, and then its turn in the macrotask queue. Under load, this delay can be hundreds of milliseconds.

For scheduling work that should run soon but not block the current frame, `queueMicrotask` is lower overhead than setTimeout. For scheduling visual work, `requestAnimationFrame` is aligned with the browser's render cycle. React's own scheduler uses `MessageChannel` posts to stay in the macrotask queue but yield between units of work.

### Quick recall
- "0ms" = earliest possible future turn, not now.
- `queueMicrotask` for sub-macrotask scheduling.
- `requestAnimationFrame` for visual work.
- `MessageChannel` for scheduler-grade cooperative yielding.

---

## Q12) Why are Promises preferred over raw callbacks?

Promises provide structured async flow, centralized error propagation, and composability via `async/await`. They eliminate callback nesting and make concurrent patterns (race, all, allSettled) first-class.

More importantly: Promise rejections are catchable at a boundary and can be monitored globally via `unhandledrejection` events — critical for production error tracking.

### Quick recall
- Better structure, error flow, and composition.
- `unhandledrejection` event for global Promise error monitoring.
- `Promise.allSettled` when you need all results regardless of failures.
- `Promise.any` when you need first success from multiple attempts.

---

## Q13) When are callbacks/events still better than Promises?

When a source emits multiple values over time — WebSocket messages, DOM events, streams — event-based or observable models are more natural. A Promise resolves once and is done. For multi-emission sources, consider the Streams API or RxJS Observables, which model ongoing async sequences with backpressure and cancellation.

### Quick recall
- One-shot async → Promise.
- Multi-emission async → EventEmitter / Streams / Observable.
- WebSocket, SSE, file streams → events/streams, not Promises.

---

## Q14) What is a closure, in practical terms?

A closure is a function that retains access to variables from its enclosing lexical scope even after that scope has returned. It's the mechanism behind private state, factory patterns, and much of React's hook model.

```js
function createCounter() {
  let count = 0;
  return {
    increment: () => ++count,
    value: () => count
  };
}
```

At Staff level: closures are also a source of memory leaks when they inadvertently hold large objects in scope longer than needed. Event listeners that close over large state, or factory functions in hot render paths, are common culprits.

### Quick recall
- Function retains outer scope variables.
- Foundation of private state, factories, React hooks.
- Watch for unintended retention of large objects → memory leaks.

---

## Q15) What is currying and why use it?

Currying transforms `f(a, b, c)` into `f(a)(b)(c)` — a chain of unary functions. It enables partial application, where you fix some arguments upfront and reuse the resulting function.

```js
const multiply = a => b => a * b;
const double = multiply(2);
const triple = multiply(3);

[1, 2, 3].map(double); // [2, 4, 6]
```

Practically useful in functional pipelines and when composing middleware or transformers. In React, curried event handlers or selector factories are common patterns.

### Quick recall
- `f(a,b,c)` → `f(a)(b)(c)`.
- Enables partial application and reusable function factories.
- Used in middleware pipelines, Redux selectors, event handler factories.

---

## Q16) What is the difference between `call`, `apply`, and `bind`?

All three control `this` binding explicitly:
- `call` — invoke immediately, args as comma-separated values.
- `apply` — invoke immediately, args as array (useful when arg count is dynamic).
- `bind` — return a new function with `this` and optionally some args pre-bound, invoked later.

```js
const user = { name: "Ashish" };
function greet(greeting, punctuation) {
  return `${greeting}, ${this.name}${punctuation}`;
}

greet.call(user, "Hi", "!");          // invoke now
greet.apply(user, ["Hello", "."]);    // invoke now, array args
const greetUser = greet.bind(user, "Hey"); // returns new fn
greetUser("?");                        // invoke later
```

In modern code, arrow functions and class fields largely replace explicit `bind` for event handlers in React components.

### Quick recall
- `call` → now, spread args.
- `apply` → now, array args.
- `bind` → later, pre-bound context.
- Arrow functions capture `this` lexically — no binding needed.

---

## Q17) What happens when we enter a URL in the browser, from request to rendering?

**Network layer:**
URL parsing → cache checks (browser cache, DNS cache, Service Worker) → DNS resolution → TCP connection (3-way handshake: SYN → SYN-ACK → ACK) → TLS handshake for HTTPS (certificate verification, session key negotiation) → HTTP request sent.

With HTTP/2, connection is multiplexed — multiple requests share one TCP connection, eliminating head-of-line blocking at the HTTP layer. HTTP/3 (QUIC) eliminates TCP head-of-line blocking at the transport layer as well.

**Server layer:**
Load balancer → app server → DB/cache queries → HTTP response with status, headers, body. Cache headers on the response (`Cache-Control`, `ETag`) determine how browser and CDN store it.

**Rendering layer:**
HTML parsed → DOM built → CSS fetched/parsed → CSSOM built → Render Tree → Layout → Paint → Composite. JS execution can trigger additional layout/paint passes.

**Staff-level additions:**
- Observability: instrument TTFB, FCP, LCP with Real User Monitoring (RUM). Connect frontend Web Vitals to backend SLOs.
- CDN topology: response path varies based on PoP proximity; CDN cache hit rate is a first-class metric to own.
- Service Worker can intercept at cache-check stage — enabling offline support and cache-first strategies.

### Quick recall
- URL parse → cache/SW check → DNS → TCP → TLS → HTTP request → server → response → CRP.
- HTTP/2 multiplexing, HTTP/3 QUIC remove connection bottlenecks.
- Staff adds: RUM instrumentation, CDN strategy, Service Worker architecture.

---

## Q16) What is type coercion and what are the two kinds?

Coercion is JavaScript automatically converting a value from one type to another. There are two kinds:

**Implicit coercion** — triggered by operators or language constructs without you asking:
```js
"5" + 1        // "51"  — number coerced to string (+ prefers concatenation)
"5" - 1        // 4     — string coerced to number (- has no string meaning)
true + 1       // 2     — boolean coerced to number
null + 1       // 1     — null coerces to 0
undefined + 1  // NaN   — undefined coerces to NaN
[] + {}        // "[object Object]"
{} + []        // 0     — {} parsed as empty block, +[] is unary plus on array
```

**Explicit coercion** — you control it:
```js
Number("42")      // 42
String(42)        // "42"
Boolean(0)        // false
parseInt("42px")  // 42
+"42"             // 42 — unary plus, common shorthand
```

### Why this matters at Staff level
Coercion bugs are subtle and show up in comparison logic, form input handling (inputs are always strings), and API data parsing. At Staff level you should be able to read any coercion expression and explain the result, and enforce linting rules (`eqeqeq`, `no-implicit-coercion`) that prevent coercion bugs across the codebase.

### Quick recall
- `+` with a string = concatenation. All other arithmetic operators coerce to number.
- `null` → 0, `undefined` → NaN, `false` → 0, `true` → 1, `[]` → 0, `{}` → NaN.

---

## Q17) What is the difference between `==` and `===`, and what are the coercion rules for `==`?

`===` (strict equality) — no coercion, checks type AND value.
`==` (loose equality) — applies Abstract Equality Comparison algorithm, which coerces types.

Key rules for `==`:
```js
null == undefined   // true  — special rule, only these two are equal to each other
null == 0           // false — null only equals undefined under ==
NaN == NaN          // false — NaN is never equal to anything, including itself

"1" == 1            // true  — string coerced to number
true == 1           // true  — boolean coerced to number first
false == 0          // true
[] == false         // true  — [] -> "" -> 0, false -> 0
[] == ![]           // true  — one of JS's most famous wtf results
```

**The `[] == ![]` breakdown:**
```js
// Step 1: ![] is false ([] is truthy, negated = false)
// Step 2: [] == false
// Step 3: boolean false coerces to 0 → [] == 0
// Step 4: [] coerces to string "" → "" == 0
// Step 5: "" coerces to number 0 → 0 == 0 → true
```

**Rule:** Always use `===`. The only acceptable use of `==` is `x == null` as a shorthand for `x === null || x === undefined`.

### Quick recall
- `===` never coerces. Use it always.
- `x == null` catches both null and undefined — the one accepted `==` idiom.
- `NaN !== NaN` — use `Number.isNaN()` to check for NaN.

---

## Q18) What are falsy and truthy values, and where do they cause bugs?

**Falsy values** (coerce to false in boolean context): `false`, `0`, `-0`, `0n`, `""`, `null`, `undefined`, `NaN`.

Everything else is truthy — including `[]`, `{}`, `"0"`, `"false"`.

**Common bugs:**
```js
// Bug: 0 is a valid count but falsy
const count = 0;
if (count) showBadge(count); // never shows — 0 is falsy

// Fix: explicit check
if (count !== undefined && count !== null) showBadge(count);
// Or: if (count != null) showBadge(count);

// Bug: empty array is truthy
const items = [];
if (items) render(items); // always renders — [] is truthy!
// Fix: check length
if (items.length > 0) render(items);

// Bug: "0" string from form input is truthy
const value = "0"; // comes from <input>
if (value) doSomething(); // runs — "0" is truthy

// JSX rendering bug — 0 renders as text node
const count = 0;
return <div>{count && <Badge />}</div>; // renders "0" not nothing!
// Fix: use ternary or explicit boolean
return <div>{count > 0 && <Badge />}</div>;
return <div>{Boolean(count) && <Badge />}</div>;
```

### Quick recall
- `0`, `""`, `null`, `undefined`, `NaN` are falsy. `[]` and `{}` are truthy.
- `{count && <X />}` in JSX renders `0` when count is 0 — use `count > 0 &&` or ternary.
- Null-ish checks: use `?? ` (nullish coalescing) instead of `||` to not swallow `0` and `""`.

---

## Q4) What is the difference between `||`, `&&`, and `??`?

```js
// || returns first truthy value, or last value
0 || "default"      // "default" — 0 is falsy, swallowed
"" || "default"     // "default" — "" is falsy, swallowed
null || "default"   // "default"

// ?? (nullish coalescing) returns first non-null/undefined value
0 ?? "default"      // 0   — 0 is not nullish
"" ?? "default"     // ""  — "" is not nullish
null ?? "default"   // "default"

// && returns first falsy value, or last value
null && doSomething()  // null — short circuits, doSomething not called
user && user.name      // user.name if user is truthy
```

**Rule:** Use `??` instead of `||` when you want to preserve `0`, `false`, and `""` as valid values. This is critical for form state, numeric config values, and feature flags.

```js
// Bug: disables a valid port number of 0
const port = config.port || 3000; // always 3000 if port is 0

// Fix:
const port = config.port ?? 3000; // 0 is preserved
```

### Quick recall
- `||` swallows all falsy values including `0` and `""`.
- `??` only swallows `null` and `undefined`.
- Use `??` for defaults when `0`, `false`, `""` are meaningful values.

---



## Q5) How does JavaScript memory management work?

JavaScript uses automatic garbage collection — you allocate memory by creating values, and the engine reclaims memory when values are no longer reachable.

**Allocation:** happens automatically on variable/object/function creation.

**Reachability:** the GC starts from roots (global variables, current call stack, closures) and traverses all references. Anything reachable is kept alive. Anything unreachable is eligible for collection.

**Mark-and-sweep algorithm (V8):**
1. Mark all roots as live.
2. Traverse all references from roots, mark everything reachable.
3. Sweep (collect) everything not marked.
4. Compact heap to reduce fragmentation (optional, costly).

V8 uses a generational approach:
- **Young generation (Scavenge):** Short-lived objects. GC runs frequently and fast.
- **Old generation (Mark-Sweep/Compact):** Long-lived objects promoted from young gen. GC is less frequent but more expensive.

### Quick recall
- GC = reachability, not reference counting (no circular reference bugs like old IE).
- V8: young generation (fast) + old generation (expensive).
- GC pauses are the enemy of smooth 60fps — minimize long-lived object allocation in hot paths.

---

## Q6) What are memory leaks in JavaScript and how do you find them?

A memory leak occurs when memory that is no longer needed remains reachable and cannot be collected.

**Common sources:**

**1. Forgotten event listeners:**
```js
// Leak — listener holds reference to element and closure scope
window.addEventListener("resize", heavyHandler);

// Fix — always remove when done
window.removeEventListener("resize", heavyHandler);

// In React — clean up in useEffect return
useEffect(() => {
  window.addEventListener("resize", handler);
  return () => window.removeEventListener("resize", handler);
}, []);
```

**2. Closures holding large objects:**
```js
function createHandler() {
  const largeData = new Array(1_000_000).fill("data"); // captured in closure
  return function handler() {
    console.log("handled"); // largeData never released even if unused
  };
}
```

**3. Detached DOM nodes:**
```js
// Node removed from DOM but still referenced in JS
const removed = document.getElementById("modal");
document.body.removeChild(removed);
// If `removed` stays in a variable/map, the entire subtree leaks
```

**4. Unbounded caches and maps:**
```js
const cache = new Map();
// Items added but never evicted — grows forever
// Fix: use WeakMap for object keys, or implement LRU eviction
```

**5. Timers and intervals never cleared:**
```js
const id = setInterval(poll, 5000);
// If component unmounts without clearInterval(id), poll runs forever
```

**Finding leaks with Chrome DevTools:**
1. Open Memory tab → take Heap Snapshot.
2. Perform the suspected leaking action.
3. Take second snapshot.
4. Use "Comparison" view — look for growing object counts.
5. Retainer tree shows what is keeping objects alive.

Also use "Allocation instrumentation on timeline" to see what allocates during an interaction.

### Quick recall
- Top leak sources: forgotten listeners, closure captures, detached nodes, unbounded maps, uncleaned timers.
- DevTools: Heap Snapshot comparison + retainer tree to find what holds reference.
- `WeakMap`/`WeakSet` for caches keyed by objects — keys are not held strongly, GC can collect them.

---

## Q7) What are WeakMap and WeakSet, and when should you use them?

`WeakMap` and `WeakSet` hold **weak references** — they do not prevent garbage collection of their keys/values.

```js
const cache = new WeakMap();

function processNode(node) {
  if (cache.has(node)) return cache.get(node);
  const result = expensiveCompute(node);
  cache.set(node, result);
  return result;
}

// When `node` is removed from DOM and no other references exist,
// it is GC'd and its WeakMap entry is automatically cleaned up.
// A regular Map would keep node alive forever.
```

**Use cases:**
- DOM node metadata without preventing GC of removed nodes.
- Private instance data in class patterns.
- Memoization caches keyed by objects.

**Limitations:** Not iterable, no `.size` property — you cannot inspect contents or iterate, by design.

### Quick recall
- `WeakMap`: object keys held weakly — entry auto-removed when key is GC'd.
- Use for: DOM caches, per-object metadata, object-keyed memoization.
- Not iterable — cannot list all entries. That is intentional.

---

## Q8) How do you write memory-efficient code in hot paths?

Hot paths are code that runs thousands of times per second — event handlers, animation frames, data processing loops.

**Avoid allocation in loops:**
```js
// Bad — allocates new array every frame
function update() {
  const positions = elements.map(el => el.getBoundingClientRect()); // allocation
  // ...
  requestAnimationFrame(update);
}

// Better — reuse pre-allocated array
const positions = new Array(elements.length);
function update() {
  for (let i = 0; i < elements.length; i++) {
    positions[i] = elements[i].getBoundingClientRect(); // reuse
  }
  requestAnimationFrame(update);
}
```

**Object pooling for frequently created/destroyed objects:**
```js
class ParticlePool {
  #pool = [];

  acquire() {
    return this.#pool.pop() ?? { x: 0, y: 0, vx: 0, vy: 0, active: false };
  }

  release(particle) {
    particle.active = false;
    this.#pool.push(particle);
  }
}
```

**Avoid string concatenation in loops:** Use arrays + `.join("")` or template literals.

**Typed arrays for numeric data:** `Float32Array`, `Int32Array` are more memory-efficient than regular arrays for large numeric datasets (WebGL, audio, canvas).

### Quick recall
- No allocation in animation frames or tight loops.
- Object pooling for frequently created/destroyed objects.
- Typed arrays for numeric-heavy data.
- Profile with Chrome Performance tab — look for GC pauses (grey bars) in flame chart.

---

# PART 3: PROMISE CHAINING, ASYNC/AWAIT, COMPLEX ASYNC FLOWS

---

## Q9) How does Promise chaining work and what are the rules?

Every `.then()` returns a new Promise. The value returned from a `.then()` callback becomes the resolved value of that new Promise. This is what enables chaining.

```js
fetch("/api/user")
  .then(res => res.json())           // returns Promise<data>
  .then(data => transform(data))     // receives data, returns transformed
  .then(result => render(result))    // receives transformed result
  .catch(err => handleError(err));   // catches any rejection in the chain
```

**Rules:**
- Returning a value from `.then()` wraps it in a resolved Promise.
- Returning a Promise from `.then()` flattens it — the chain waits for that inner Promise.
- Throwing inside `.then()` rejects the returned Promise.
- `.catch()` at the end catches any rejection from any step above it.
- `.finally()` runs regardless of resolve/reject — good for cleanup.

```js
// Returning a Promise inside .then() — chain waits for it
fetch("/api/user")
  .then(res => res.json())
  .then(user => fetch(`/api/orders/${user.id}`)) // returns Promise — chain waits
  .then(res => res.json())
  .then(orders => render(user, orders)); // ❌ user not in scope here

// Fix: use closure or async/await
```

This scope issue is why `async/await` is preferred for multi-step flows — it keeps all variables in the same scope.

### Quick recall
- `.then()` always returns a new Promise.
- Returned Promise is flattened (no Promise<Promise<T>>).
- `.catch()` covers all rejections above it.
- Scope access across steps → use `async/await`.

---

## Q10) What are the common async/await pitfalls and how do you avoid them?

**Pitfall 1: Sequential awaits when parallel is possible:**
```js
// Bad — sequential, total time = A + B
const user = await fetchUser(id);
const orders = await fetchOrders(id);

// Good — parallel, total time = max(A, B)
const [user, orders] = await Promise.all([fetchUser(id), fetchOrders(id)]);
```

**Pitfall 2: Missing await — floating Promise:**
```js
async function save() {
  db.save(data); // ❌ no await — errors are swallowed, function returns before save completes
  return "saved";
}

// Fix:
await db.save(data);
```

**Pitfall 3: try/catch swallowing errors silently:**
```js
// Bad — catches everything, hides bugs
try {
  const data = await riskyOperation();
} catch (e) {
  // silence...
}

// Good — catch what you can handle, re-throw what you cannot
try {
  const data = await riskyOperation();
} catch (e) {
  if (e instanceof NetworkError) return showOfflineMessage();
  throw e; // unknown errors should propagate
}
```

**Pitfall 4: await inside forEach — does not work:**
```js
// Bad — forEach does not await, all run simultaneously without coordination
items.forEach(async item => {
  await process(item); // forEach ignores returned Promise
});

// Fix for sequential:
for (const item of items) {
  await process(item);
}

// Fix for parallel:
await Promise.all(items.map(item => process(item)));
```

### Quick recall
- Independent async ops → `Promise.all`, not sequential awaits.
- Never forget `await` on Promises — use `no-floating-promises` ESLint rule.
- `forEach` + `async` is broken. Use `for...of` or `Promise.all(map(...))`.
- Catch to handle, re-throw the rest.

---

## Q11) What is the difference between Promise.all, Promise.allSettled, Promise.race, and Promise.any?

```js
// Promise.all — resolves when ALL resolve, rejects on FIRST rejection
const [a, b] = await Promise.all([fetchA(), fetchB()]);
// Use when: all results are needed and one failure should abort everything

// Promise.allSettled — waits for ALL, never rejects, gives status per item
const results = await Promise.allSettled([fetchA(), fetchB(), fetchC()]);
results.forEach(result => {
  if (result.status === "fulfilled") use(result.value);
  if (result.status === "rejected") log(result.reason);
});
// Use when: partial success is acceptable, you want all outcomes

// Promise.race — resolves/rejects with FIRST settled Promise
const data = await Promise.race([fetchWithTimeout(), timeoutAfter(5000)]);
// Use when: implementing timeouts, taking fastest response

// Promise.any — resolves with FIRST fulfilled, rejects only if ALL reject
const fastest = await Promise.any([mirror1(), mirror2(), mirror3()]);
// Use when: redundant sources, want first success (CDN fallback pattern)
```

**Timeout pattern with Promise.race:**
```js
function withTimeout<T>(promise: Promise<T>, ms: number): Promise<T> {
  const timeout = new Promise<never>((_, reject) =>
    setTimeout(() => reject(new Error(`Timed out after ${ms}ms`)), ms)
  );
  return Promise.race([promise, timeout]);
}

const data = await withTimeout(fetchUser(id), 5000);
```

### Quick recall
- `all`: all-or-nothing. `allSettled`: all outcomes, never throws.
- `race`: first to settle wins. `any`: first to succeed wins.
- Timeout = `Promise.race([operation, rejectAfterMs(n)])`.

---

## Q12) How do you handle complex async flows: retry, cancellation, and throttling?

**Retry with exponential backoff:**
```js
async function fetchWithRetry(url, { retries = 3, baseDelay = 300 } = {}) {
  for (let attempt = 0; attempt <= retries; attempt++) {
    try {
      return await fetch(url).then(r => r.json());
    } catch (err) {
      if (attempt === retries) throw err;
      const delay = baseDelay * 2 ** attempt + Math.random() * 100; // jitter
      await new Promise(resolve => setTimeout(resolve, delay));
    }
  }
}
```

**Cancellation with AbortController:**
```js
function fetchUser(id) {
  const controller = new AbortController();

  const promise = fetch(`/api/users/${id}`, { signal: controller.signal })
    .then(r => r.json());

  return { promise, cancel: () => controller.abort() };
}

// In React:
useEffect(() => {
  const { promise, cancel } = fetchUser(userId);
  promise.then(setUser).catch(err => {
    if (err.name !== "AbortError") setError(err);
  });
  return cancel; // cancel on unmount or userId change
}, [userId]);
```

**Request deduplication — prevent duplicate in-flight requests:**
```js
const inFlight = new Map();

async function deduplicatedFetch(url) {
  if (inFlight.has(url)) return inFlight.get(url);

  const promise = fetch(url).then(r => r.json()).finally(() => {
    inFlight.delete(url);
  });

  inFlight.set(url, promise);
  return promise;
}
```

**Async queue — process items with concurrency limit:**
```js
async function processWithConcurrency(items, handler, concurrency = 3) {
  const results = [];
  const executing = new Set();

  for (const item of items) {
    const promise = handler(item).then(result => {
      executing.delete(promise);
      return result;
    });
    executing.add(promise);
    results.push(promise);

    if (executing.size >= concurrency) {
      await Promise.race(executing); // wait for one to finish before adding more
    }
  }

  return Promise.all(results);
}
```

### Quick recall
- Retry: exponential backoff + jitter prevents thundering herd.
- Cancellation: `AbortController` — always handle `AbortError` separately.
- Deduplication: `Map` of in-flight Promises.
- Concurrency limit: `Promise.race` on active set.

---

# PART 4: RENDERING BOTTLENECKS AND BROWSER PERFORMANCE

---

## Q13) How do you identify and fix rendering bottlenecks?

**Identify with Chrome DevTools Performance tab:**
- Record a trace during the problematic interaction.
- Look for: long tasks (>50ms, shown as red), forced synchronous layouts (yellow warning triangles), frequent style recalculations, paint flashes.
- Flame chart shows call stack — find which function dominates time.

**Common bottlenecks and fixes:**

**Forced synchronous layout (layout thrashing):**
```js
// Bad — forces layout in loop
elements.forEach(el => {
  const h = el.offsetHeight;  // read — forces layout
  el.style.height = h + 10 + "px"; // write
});

// Fix — batch reads, then writes
const heights = elements.map(el => el.offsetHeight); // all reads
elements.forEach((el, i) => el.style.height = heights[i] + 10 + "px"); // all writes
```

**Long tasks blocking main thread:**
```js
// Bad — processes 10k items synchronously, blocks for >100ms
function processAll(items) {
  return items.map(heavyTransform);
}

// Fix — chunk with scheduler.yield() or setTimeout
async function processInChunks(items, chunkSize = 100) {
  const results = [];
  for (let i = 0; i < items.length; i += chunkSize) {
    const chunk = items.slice(i, i + chunkSize);
    results.push(...chunk.map(heavyTransform));
    await scheduler.yield(); // yield to browser between chunks
  }
  return results;
}
```

**Expensive style recalculation:**
- Avoid querying or writing styles in `scroll` and `resize` handlers without throttling/debouncing.
- Use `will-change: transform` on elements that animate to promote them to compositor layer early — but use sparingly, it consumes GPU memory.
- Batch DOM mutations with `DocumentFragment` when inserting many nodes.

### Quick recall
- Profile first — do not guess bottlenecks.
- Layout thrashing: batch reads then writes.
- Long tasks: chunk + yield with `scheduler.yield()` or `setTimeout(0)`.
- Scroll/resize handlers: always debounce or use passive listeners.


---

## Q15) How do you measure and improve Core Web Vitals in production?

Core Web Vitals are Google's user-centric performance metrics and directly affect SEO ranking.

| Metric | Measures | Good threshold |
|---|---|---|
| LCP (Largest Contentful Paint) | Load performance — when main content is visible | < 2.5s |
| INP (Interaction to Next Paint) | Responsiveness — delay from input to visual response | < 200ms |
| CLS (Cumulative Layout Shift) | Visual stability — unexpected layout shifts | < 0.1 |

**Improving LCP:**
- Preload the LCP resource: `<link rel="preload" as="image" href="/hero.webp">`.
- Serve images in modern formats (WebP, AVIF) with proper sizing.
- Use SSR or SSG to ship HTML content without waiting for JS hydration.
- Eliminate render-blocking resources above the fold.

**Improving INP:**
- Break long tasks — any task >50ms can contribute to poor INP.
- Move heavy computation off main thread to Web Workers.
- Use `startTransition` for non-urgent UI updates in React.
- Debounce expensive event handlers (resize, input, scroll).

**Improving CLS:**
- Always set explicit `width` and `height` on images and video.
- Reserve space for async-loaded content (ads, embeds) with CSS aspect-ratio.
- Avoid inserting DOM content above existing content.
- Font loading: use `font-display: optional` or `swap` with size-adjusted fallback to minimize FOFT.

**Measuring in production:**
```js
import { onLCP, onINP, onCLS } from "web-vitals";

onLCP(metric => sendToAnalytics({ name: "LCP", value: metric.value, rating: metric.rating }));
onINP(metric => sendToAnalytics({ name: "INP", value: metric.value }));
onCLS(metric => sendToAnalytics({ name: "CLS", value: metric.delta }));
```

At Staff level: own a Web Vitals dashboard, set SLOs (e.g. "p75 LCP < 2.5s"), alert on regressions, and build performance budgets into CI so new code cannot ship if it would degrade scores.

---

### Quick recall
- LCP: preload, SSR, modern image formats, no render-blocking above fold.
- INP: break long tasks, Web Workers, `startTransition`.
- CLS: explicit image dimensions, reserve space for async content.
- Measure in production with web-vitals library + RUM dashboard.
- Staff: own SLOs and enforce budgets in CI.

## Staff-only Topics (not in original notes)

### Web Vitals Ownership
Know the metrics deeply — LCP (load), INP (interaction), CLS (visual stability) — but more importantly, own the *system* for improving them: RUM tooling (web-vitals.js + analytics pipeline), CrUX data for field data, alerting on regression, and a playbook for investigation. Staff engineers connect frontend metric regressions to deploys automatically.

### Microfrontend Architecture
Module federation (Webpack 5 / Vite) allows independent teams to deploy UI slices that compose at runtime. Key trade-offs: shared dependency version conflicts, cross-app communication (custom events vs shared store vs URL state), independent deployability vs integration testing complexity. Staff engineers define the federation contract and governance model.

### Observability
Frontend observability = error tracking (Sentry), RUM (Datadog RUM, New Relic), distributed tracing (OpenTelemetry for frontend-to-backend trace correlation), and synthetic monitoring (Playwright-based checks running in production). Staff engineers define what "healthy frontend" means in dashboards and alerts.