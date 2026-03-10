# JavaScript & Browser Performance (Staff Level)

## Q1) How does the Event Loop impact Interaction to Next Paint (INP)?
The event loop processes synchronous code, then exhausts the entire microtask queue before moving to the next macrotask or rendering opportunity. Senior engineers must identify "Long Tasks" (>50ms); if microtasks (like recursive Promises) or heavy synchronous logic flood the loop, the browser cannot render a frame or process user input, leading to a degraded INP.

### Quick recall
- Sync -> All Microtasks -> Render -> Macrotask.
- Microtask "starvation" blocks the UI; use `scheduler.yield()` or `setTimeout` to break up work.

## Q2) How do you architect a site to minimize Layout Thrashing?
Thrashing occurs when code repeatedly alternates between writing styles and reading layout geometry (like `offsetWidth`), forcing the browser into synchronous reflow loops. Beyond batching reads and writes, Staff engineers use CSS `contain` to isolate layout boundaries and move animations to the **Compositor thread** (using `transform`/`opacity`) to bypass Layout and Paint stages entirely.

### Quick recall
- Read first, write later.
- Offload animations to the Compositor.

## Q3) Why is JS Bundle Size a proxy for device-specific performance?
Bundle size isn't just a network problem; it’s a CPU problem. On lower-end devices, the time spent on **parsing and compiling** JavaScript can exceed the download time. This delays the "Time to Interactive" and can cause significant main-thread contention during the hydration phase.

### Quick recall
- JS Cost = Download + Parse + Execute.
- Use Code Splitting and Tree Shaking to ship the minimum viable script.

# React Architecture & Patterns (Staff Level)

## Q1) What is the architectural significance of React 18’s Concurrent Mode?
Concurrent React moves rendering from a blocking, synchronous process to an **interruptible** one. React can now prepare a new UI in the background (Render phase) without blocking the main thread, allowing high-priority events like user typing to interrupt low-priority renders.

### Quick recall
- Render phase: Interruptible and "pure".
- Commit phase: Synchronous and applies DOM changes.

## Q2) How do you choose between Context, Zustand, and Redux Toolkit?
The choice hinges on **re-render scope** and **traceability**. Context API lacks a selector mechanism, meaning every consumer re-renders when the value changes—ideal for low-frequency data like themes. Zustand offers a "bottom-up" approach with fine-grained selectors. Redux Toolkit is the standard for enterprise scale where complex async flows and strict state-action traceability are required for large teams.

### Quick recall
- Context: Simple/Static.
- Zustand: Pragmatic/Selector-based.
- Redux: Complex/Scale-oriented.

## Q3) What is the "Render-as-you-fetch" pattern?
Unlike "fetch-on-render" (which creates waterfalls), "render-as-you-fetch" starts network requests parallel to component initialization, often at the router or loader level. Components "suspend" if data isn't ready, allowing for a declarative loading state via `<Suspense>`.

### Quick recall
- Avoid waterfalls by fetching early.
- Use Suspense for coordinated loading UI.

# Security & Caching (Staff Level)

## Q1) How does the BFF (Backend-for-Frontend) pattern improve security?
While `HttpOnly` cookies reduce XSS risk compared to `localStorage`, the BFF pattern takes it further by moving token management to a server-side proxy. The frontend never "sees" the JWT; it only communicates with the BFF via an encrypted session cookie, virtually eliminating token exfiltration risk.

### Quick recall
- localStorage = XSS vulnerability.
- HttpOnly + Secure + SameSite = Industry baseline.

## Q2) What is the ideal caching strategy for a high-traffic SPA?
A "Defense in Depth" cache strategy uses **long-term immutable** headers for hashed assets (JS/CSS) and a **short-term or revalidation-based** header (like `ETag` or `no-cache`) for the HTML entry point. This ensures that when a new version is deployed, the browser detects the change in the HTML immediately and fetches the new bundles.

### Quick recall
- Hashed assets: Long-term cache.
- HTML/Entry: Revalidate per request.

## Q3) Why are Security Headers (CSP, HSTS) non-negotiable?
CSP acts as a secondary layer of defense; even if an attacker finds an XSS vulnerability, a strict CSP can prevent the execution of unauthorized inline scripts or data exfiltration to unknown domains. HSTS prevents protocol downgrade attacks by forcing the browser to only communicate via HTTPS.

### Quick recall
- CSP: Mitigates XSS impact.
- HSTS: Ensures transport security.

# Testing Strategy & Tooling (Staff Level)

## Q1) Why move from the "Testing Pyramid" to the "Testing Trophy"?
The Pyramid emphasizes many unit tests, but Staff engineers often favor the **Testing Trophy**, which prioritizes **Integration tests**. Testing how components collaborate (using RTL) provides higher confidence and lower maintenance than testing implementation details in isolation.

### Quick recall
- Unit: Logic.
- Integration: User Behavior (Highest ROI).
- E2E: Critical Journeys.

## Q2) How do you prevent "Flakiness" in Playwright E2E tests?
Flakiness usually stems from non-deterministic async states. Staff engineers use **auto-waiting** and accessible locators (like `getByRole`) rather than arbitrary timeouts. Additionally, mocking unstable network responses via `page.route` ensures that tests focus on the UI logic rather than third-party API reliability.

### Quick recall
- Use semantic selectors.
- Intercept and mock unstable network calls.

## Q3) When should you mock vs. spy in Jest?
Mocking (`jest.mock`) is for isolating the system from external dependencies (like APIs), while spying (`jest.spyOn`) is for asserting that internal side effects happened without replacing the original implementation. Over-mocking leads to tests that pass even when the real system is broken.

### Quick recall
- Mock for isolation.
- Spy for observation.