# Frontend Stage-2 Prep Playbook

This document is your Stage-2 frontend deep-prep guide.
It is designed for engineers who already know the basics and now need stronger interview depth, better system-level answers, and real-world debugging narratives.

Use this playbook with:
- `triviaQuestion.md` to sharpen concept recall
- `pragmaticUI.md` to improve coding-round execution
- `systemDesign.md` to practice architecture communication

By the end of this playbook, you should be able to:
- explain web fundamentals with practical production examples
- present a testing strategy beyond only unit tests
- discuss frontend architecture operations and scale tradeoffs
- narrate performance investigations with metrics, root cause, and impact

## 1. Web Fundamentals (Deep, Interview-Level)

### 1.1 Rendering Pipeline in Real Scenarios

Know the full path:
- Parse HTML -> build DOM
- Parse CSS -> build CSSOM
- Build render tree
- Layout
- Paint
- Composite

Example discussion prompt:
- "Why does a page visually freeze when opening a mega menu?"

Good answer:
- Large synchronous JS task blocks the main thread before paint.
- Heavy layout thrashing (`offsetHeight` reads mixed with style writes) causes repeated reflow.
- Fix with batched reads/writes, `requestAnimationFrame`, and reducing sync work.

### 1.2 Critical Rendering Path (CRP)

Interview expectation:
- Explain blocking resources and how to prioritize first meaningful content.

Example:
- Issue: Hero text appears late because CSS and large JS block initial render.
- Fixes:
- Inline critical CSS for above-the-fold.
- Mark non-critical scripts as `defer`.
- Delay low-priority widgets (chat, recommendations).
- Preload hero font/image with clear priority.

### 1.3 Event Loop and UI Bugs

Example bug:
- Spinner is set to `true`, but UI does not show spinner before heavy processing starts.

Reason:
- Heavy sync operation blocks render between state update and paint.

Improvement:
- Yield before heavy work (`setTimeout(..., 0)` or split tasks).
- Move heavy compute to Web Worker if possible.

### 1.4 Caching Layers

You should differentiate:
- Browser HTTP cache
- CDN edge cache
- App-level memory cache
- Service Worker cache (offline/stale strategy)

Example tradeoff:
- Product listing data cache TTL too long causes stale prices.
- Solution: `stale-while-revalidate` for list, but strict fresh fetch for checkout totals.

### 1.5 Network Fundamentals

Interview-ready points:
- Latency and throughput are different bottlenecks.
- HTTP/2 multiplexing reduces connection overhead.
- Brotli/gzip for text assets.
- Image formats (AVIF/WebP) and responsive sizes reduce transfer.

Mini metric example:
- Before: JS bundle 1.2 MB, LCP 4.1s on 4G.
- After splitting + image optimization: JS 420 KB critical path, LCP 2.3s.

## 2. Testing Maturity (What Senior Interviewers Probe)

### 2.1 Test Boundaries

Clear separation:
- Unit: pure functions, reducers, formatters.
- Integration: component + hooks + async data behavior.
- E2E: critical user journeys (signup, checkout, payment success/failure).

### 2.2 What To Test in Frontend

At component level:
- Rendering states (loading, empty, error, success).
- Interaction logic (click, keyboard nav, form validation).
- Accessibility semantics (role, label, focus order).

At page/workflow level:
- Multi-step flow correctness.
- Error recovery and retry behavior.
- URL state and back/forward navigation integrity.

### 2.3 Practical Example: Search Page

Must-have tests:
- Query updates URL params.
- Debounced API call triggers once for burst typing.
- Empty result state shows expected messaging.
- API 500 triggers retry CTA and telemetry event.

### 2.4 Contract Testing (Frontend-Backend)

Problem:
- UI expects `price.amount` but backend changes to `price.value`.

Fix:
- Add contract test on API adapter layer.
- Validate response shape before mapping to UI model.
- Fail early in CI when contract breaks.

### 2.5 CI Quality Gates

Add checks:
- Unit/integration pass threshold.
- E2E smoke for main flows.
- Lighthouse budget for key routes.
- Accessibility checks for critical pages.

## 3. Architecture Beyond Basic HLD

### 3.1 Module Boundaries and Ownership

Good architecture discussion includes:
- Domain modules (`catalog`, `checkout`, `orders`, `account`)
- Shared platform layer (`design-system`, `api-client`, `observability`)
- Ownership model by team, not by random file splits

Example:
- Checkout team owns `features/checkout/*`.
- Platform team owns shared request client and design tokens.

### 3.2 State Strategy (Interview Favorite)

Split state intentionally:
- Server state: fetched data with cache/invalidations.
- Domain state: business workflow data (cart, step progress).
- UI state: modal open/close, selected tab, hovered item.

Example anti-pattern:
- Putting server response snapshots into global store permanently.

Preferred:
- Keep server state in query/cache layer and derive UI from source-of-truth.

### 3.3 Progressive Delivery

Expected concepts:
- Feature flags for risky rollouts.
- Canary release by user percentage.
- Kill-switch for bad experiments.

Example:
- New search ranking rolled out to 5% users, compare CTR/conversion, rollback on regression.

### 3.4 Observability

Must track:
- UX metrics: LCP, INP, CLS, route transition latency.
- Business metrics: conversion drop after UI change.
- Errors: API failures by route, top JS exceptions.

Example narrative:
- "We correlated LCP regression on mobile PDP with image payload growth after new carousel release."

### 3.5 Resilience Patterns

Explain:
- Retry only safe/idempotent requests.
- Exponential backoff.
- Graceful fallback when partial backend dependencies fail.

Example:
- Recommendation API failure should not block product details or add-to-cart.

## 4. Performance Storytelling (How to Answer Well)

Interviewers value structured communication as much as fixes.

Use this format:
1. Symptom: what users felt.
2. Evidence: which metrics/logs proved it.
3. Root cause: where time/CPU/network was spent.
4. Fixes: prioritized by impact.
5. Result: measurable improvements.
6. Tradeoffs: what you chose not to optimize yet.

Example:
- Symptom: slow first interaction on dashboard.
- Evidence: INP p95 = 420ms, CPU flame chart showed long task from chart library init.
- Fix: defer non-visible charts, code-split heavy widgets, precompute data.
- Result: INP p95 improved to 180ms, bounce reduced 6%.

## 5. Built-In Addendum (Detailed Notes Included Here)

This section folds the previous add-on topics into this same document so you can use one file as your Stage-2 master prep sheet.

### 5.1 Web Fundamentals Deep Dive

Key concepts to master:
- Parsing and rendering pipeline: DOM/CSSOM/render tree/layout/paint/composite
- Main thread scheduling and long tasks
- Browser storage behavior (cookies, localStorage, sessionStorage, IndexedDB)
- Same-origin policy, CORS, CSP, and secure-by-default frontend patterns
- CDN + browser caching strategy with clear invalidation rules

Common interview questions:
- "Why does this page feel janky after initial load?"
- "When would you use IndexedDB over localStorage?"
- "How do you avoid stale data when caching aggressively?"
- "What causes layout shift and how do you prevent it?"

Strong-answer example:
- Question: "Why is scrolling laggy in a data-heavy table?"
- Answer structure:
- Root cause: excessive DOM nodes + sync reflow from repeated layout reads/writes.
- Fix: virtualized rendering + batched style updates + sticky headers without forced reflow.
- Result: frame drops reduced and interaction became stable under large datasets.

Mini case study:
- Scenario: Dashboard had 10k-row table and delayed first interaction.
- Action: implemented virtualization and deferred heavy chart initialization.
- Outcome: interaction latency dropped significantly and CPU usage stabilized.

### 5.2 Frontend Testing Strategy

Testing stack expectations:
- Unit tests for pure logic and mappers
- Integration tests for component behavior + async flows
- E2E tests for revenue-critical journeys
- Contract tests for API shape compatibility

What to test first:
- User-visible state changes (loading, empty, error, success)
- Accessibility paths (keyboard flow, aria labels, focus handling)
- Async reliability (retry/failure timeout behavior)
- URL-driven state and navigation consistency

Common interview questions:
- "What should be unit-tested vs integration-tested?"
- "How do you avoid flaky frontend tests?"
- "How do you test debounced search and race conditions?"
- "How would you test checkout without over-mocking?"

Strong-answer example:
- Question: "How do you reduce test flakiness?"
- Answer:
- Use deterministic fixtures and stable selectors.
- Avoid timing assumptions by waiting on UI state, not arbitrary delays.
- Keep one source of truth for network mocks and isolate external dependencies.

Mini case study:
- Scenario: Search tests were flaky due to uncontrolled timers and network race.
- Action: switched to fake timers for debounce and deterministic mock server responses.
- Outcome: test pass stability improved and CI reruns reduced.

### 5.3 Frontend Architecture Operations

Operational architecture topics:
- Domain ownership model and module boundaries
- Dependency governance (shared package versioning and compatibility)
- Feature-flag lifecycle (introduce, monitor, cleanup)
- Release operations (canary, rollback, blast radius control)
- Observability operations (metrics dashboards + alert rules)

Common interview questions:
- "How do you scale a frontend codebase to multiple teams?"
- "When do you split modules vs keep a modular monolith?"
- "How do you prevent architecture drift over time?"
- "What would your rollback plan look like for a bad release?"

Strong-answer example:
- Question: "How do you structure ownership?"
- Answer:
- Organize by domain capabilities (checkout, catalog, account).
- Keep shared UI/platform boundaries strict with documented contracts.
- Introduce architecture decision records for major changes.

Mini case study:
- Scenario: Shared UI package changes repeatedly broke multiple teams.
- Action: introduced semantic versioning policy + compatibility checks in CI.
- Outcome: cross-team breakages dropped and release confidence increased.

### 5.4 Performance Debug Playbook

Debug sequence:
1. Confirm user symptom (what feels slow).
2. Map to metrics (LCP, INP, CLS, TTFB, route transition time).
3. Capture traces (DevTools, Lighthouse, RUM dashboards).
4. Identify top bottleneck (network, CPU, rendering, bundle size).
5. Apply targeted fix and measure before/after.
6. Document tradeoffs and follow-up items.

Common interview questions:
- "How would you improve LCP on a content-heavy page?"
- "What steps do you take when INP regresses?"
- "How do you choose between SSR and CSR for performance?"
- "What would you optimize first with limited time?"

Strong-answer example:
- Question: "LCP is high on mobile, what do you do?"
- Answer:
- Audit hero image and blocking resources.
- Preload hero asset, defer non-critical JS, reduce CSS blocking path.
- Recheck field metrics and ensure no CLS regression from asset changes.

Mini case study:
- Scenario: Product detail page had high LCP and INP in real-user metrics.
- Action: split non-critical bundles, optimized media delivery, delayed recommendations.
- Outcome: significant LCP/INP improvements and measurable conversion uplift.

## Outcome Target

After adding these detailed layers, you should be able to:
- Explain core browser/performance behavior with confidence.
- Design test strategy beyond just writing unit tests.
- Defend architecture choices with clear tradeoffs.
- Present real debugging/performance stories with measurable impact.
