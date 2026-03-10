# Testing Pyramid and Tooling — Staff Engineer Level

## Q1) What is the Testing Pyramid and why does it still matter?

The Testing Pyramid balances confidence, speed, and maintenance cost across three layers: a large base of fast unit tests, a middle layer of integration tests, and a narrow top of E2E tests.

At Staff level, the pyramid is not just a personal practice — it is a **team and org-level strategy** you own and defend. The two failure modes you prevent are: teams that write only brittle slow E2E suites (slow CI, high flakiness, low trust), and teams that write only isolated unit tests that miss real user behavior (false confidence, production surprises).

Staff framing: you define the strategy, establish tooling standards, set coverage expectations per domain, and make the case to engineering leadership for the right investment at each layer.

### Quick recall
- Unit: many, fast, cheap to maintain.
- Integration: verifies collaboration between parts.
- E2E: fewer, high business value, reserved for critical journeys.
- Staff owns the strategy, not just the tests.

---

## Q2) What ratio should I target, and how do I defend it?

A common starting point is roughly 70% unit, 20% integration, 10% E2E. This is a heuristic, not a law.

At Staff level you adjust based on **risk profile**:
- Payment, auth, compliance, and data-loss flows justify heavier E2E coverage because failures are expensive and hard to catch in lower layers.
- Pure utility logic (formatters, validators, calculators) should be almost entirely unit tested — E2E adds no value there.
- Component libraries warrant heavy RTL integration coverage because their consumers are broad and accessibility correctness matters.

How to make the case to leadership: frame test investment in terms of **mean time to detect** (MTTD) and **CI cycle time**. A suite dominated by E2E tests might have high confidence on paper but 40-minute CI runs, which slows every engineer's feedback loop and reduces deployment frequency.

### Quick recall
- Start near 70/20/10. Shift based on risk and cost of failure.
- Frame test strategy in terms of MTTD and CI cycle time to leadership.

---

## Q3) Which Jest functions are used most often?

Structure: `describe`, `test`/`it`, `beforeEach`, `afterEach`, `beforeAll`, `afterAll`.

Assertions: `expect` with matchers — `toBe`, `toEqual`, `toStrictEqual`, `toThrow`, `resolves`/`rejects` for async.

Test doubles: `jest.fn()`, `jest.spyOn()`, `mockReturnValue`, `mockResolvedValue`, `mockRejectedValue`, `mockImplementation`.

Cleanup: always call `jest.clearAllMocks()` in `beforeEach` — prevents state leaking between tests.

```ts
describe("user service", () => {
  beforeEach(() => jest.clearAllMocks());

  test("returns user on success", async () => {
    const api = { getUser: jest.fn().mockResolvedValue({ id: 1, name: "Ashish" }) };
    await expect(api.getUser(1)).resolves.toEqual({ id: 1, name: "Ashish" });
  });

  test("throws on failure", async () => {
    const api = { getUser: jest.fn().mockRejectedValue(new Error("Not found")) };
    await expect(api.getUser(99)).rejects.toThrow("Not found");
  });
});
```

Staff note: enforce `jest.config` standards across repos — consistent `testEnvironment`, coverage thresholds, and transform config prevent cross-team inconsistency.

### Quick recall
- Structure: `describe`, `test`, lifecycle hooks.
- Assertions: `expect` + matchers.
- Mocks: `jest.fn`, `spyOn`, resolved/rejected helpers.
- Always clear mocks in `beforeEach`.

---

## Q4) How do module mocks and fake timers work in Jest?

`jest.mock('module-path')` replaces the entire module. For partial mocking, combine with `jest.requireActual`:

```ts
jest.mock('./analytics', () => ({
  ...jest.requireActual('./analytics'),
  trackEvent: jest.fn(), // override only this
}));
```

Fake timers (`jest.useFakeTimers()`) make time-dependent logic deterministic — essential for debounce, throttle, retry with backoff, and polling:

```ts
jest.useFakeTimers();

triggerRetry(); // starts 3s retry timer
jest.advanceTimersByTime(3000);

expect(mockFn).toHaveBeenCalledTimes(2);
```

Staff note: fake timers are one of the most common sources of test confusion in shared codebases. Enforce `jest.useRealTimers()` in `afterEach` in shared test setup to prevent cross-test contamination.

### Quick recall
- `jest.mock` for dependency isolation. `requireActual` for partial mocks.
- Fake timers for deterministic time-dependent logic.
- Always restore real timers in `afterEach`.

---

## Q5) What are the most important React Testing Library (RTL) functions?

RTL tests behavior the way users experience it — not implementation details.

**Query priority (most to least preferred):**
1. `getByRole` — maps directly to accessibility tree. Use this first, always.
2. `getByLabelText` — for form fields associated with labels.
3. `getByPlaceholderText` — fallback for unlabeled inputs.
4. `getByText` — for non-interactive content.
5. `getByTestId` — last resort only; avoid coupling tests to implementation.

**Async queries:** Use `findBy...` (returns Promise) or `waitFor` for UI that updates asynchronously after an event.

**Interactions:** Use `userEvent` over `fireEvent` — it simulates the full browser event chain (pointerdown, focus, input, keyup, etc.) for realistic behavior.

```tsx
const user = userEvent.setup();
render(<LoginForm onSuccess={mockOnSuccess} />);

await user.type(screen.getByLabelText(/email/i), "a@b.com");
await user.type(screen.getByLabelText(/password/i), "secret");
await user.click(screen.getByRole("button", { name: /sign in/i }));

expect(await screen.findByText(/welcome/i)).toBeInTheDocument();
expect(mockOnSuccess).toHaveBeenCalledTimes(1);
```

Staff note: `getByRole` doubles as an accessibility audit. If you cannot query by role, the component likely has an a11y problem — missing ARIA role, label, or semantic element. This is a valuable signal to catch in code review.

### Quick recall
- Query priority: `role` > `label` > `placeholder` > `text` > `testId`.
- `findBy`/`waitFor` for async UI updates.
- `userEvent` for realistic interactions.
- `getByRole` failures often signal a11y issues.

---

## Q6) Which Jest-DOM matchers are most practical?

Core daily matchers:
- `toBeInTheDocument()` — element exists in DOM.
- `toBeVisible()` — element is visible to user (not hidden by CSS).
- `toHaveTextContent('...')` — text content check.
- `toHaveValue('...')` — form input value.
- `toBeDisabled()` / `toBeEnabled()` — interactive state.
- `toHaveAttribute('aria-expanded', 'true')` — for ARIA state assertions.
- `toHaveFocus()` — focus management in keyboard navigation tests.

Staff note: `toBeVisible()` is more meaningful than `toBeInTheDocument()` for user-facing assertions — an element can be in the DOM but hidden. Prefer the more specific matcher.

### Quick recall
- Prefer `toBeVisible` over `toBeInTheDocument` for UX assertions.
- Add `toHaveAttribute` for ARIA state and `toHaveFocus` for keyboard nav tests.

---

## Q7) Which Playwright functions should I know, and what is the locator strategy?

Core API:
- Navigation: `page.goto(url)`, `page.reload()`, `page.goBack()`.
- Locators (preferred over selectors): `getByRole`, `getByLabel`, `getByText`, `getByTestId`.
- Actions: `click()`, `fill()`, `check()`, `uncheck()`, `selectOption()`, `hover()`, `press()`.
- Assertions: `expect(page).toHaveURL(...)`, `expect(locator).toBeVisible()`, `toHaveText()`, `toHaveValue()`.

```ts
import { test, expect } from "@playwright/test";

test("checkout flow", async ({ page }) => {
  await page.goto("/cart");
  await page.getByRole("button", { name: /proceed to checkout/i }).click();
  await page.getByLabel("Card number").fill("4242424242424242");
  await page.getByRole("button", { name: /pay now/i }).click();
  await expect(page).toHaveURL(/confirmation/);
  await expect(page.getByRole("heading", { name: /order confirmed/i })).toBeVisible();
});
```

Staff note: Playwright locators are **auto-retrying** — they poll until the element matches or timeout. This is different from a DOM query and eliminates most explicit wait boilerplate. Teach your team this mental model to prevent unnecessary `waitFor` spam.

### Quick recall
- Locators auto-retry — no need for manual waits in most cases.
- Accessibility-first locator strategy mirrors RTL query priority.

---

## Q8) How should you handle waits and network behavior in Playwright?

**Auto-wait first:** Playwright automatically waits for elements to be actionable (visible, stable, enabled) before acting. Trust this before adding explicit waits.

**Explicit waits when needed:**
- `page.waitForURL(/pattern/)` — after navigation triggers.
- `page.waitForResponse(urlPattern)` — after actions that trigger API calls.
- `expect(locator).toBeVisible({ timeout: 10000 })` — for slow async UI.

**Network control — the Staff-level tool:**
```ts
// Intercept and mock API response
await page.route('**/api/orders', route =>
  route.fulfill({ json: { orders: mockOrders } })
);

// Simulate failure
await page.route('**/api/payment', route =>
  route.fulfill({ status: 500, body: 'Server error' })
);
```

Network mocking makes E2E tests deterministic and eliminates flakiness from real API variability. At Staff level, define a shared `fixtures` pattern so teams mock consistently rather than ad-hoc.

**CI strategy at scale:**
- Use Playwright's built-in **sharding** to parallelize across CI workers: `--shard=1/4`, `--shard=2/4`, etc.
- Store test results with `--reporter=blob` and merge with `playwright merge-reports` for unified HTML report.
- Quarantine flaky tests to a separate suite with a flakiness label — do not let them block main CI, but track and fix them on a SLA.

### Quick recall
- Trust auto-wait. Add explicit waits only at clear state boundaries.
- Use `page.route` to mock network for deterministic tests.
- Shard Playwright in CI for parallelism. Quarantine flaky tests rather than ignoring them.

---

## Q9) How do you own testing strategy as a Staff engineer?

This is what separates a Staff answer from a Senior answer. Staff engineers do not just write good tests — they define and defend the strategy across teams.

**Setting standards:**
- Define test coverage thresholds per domain in `jest.config` — not a blanket 80% line coverage (meaningless), but meaningful branch coverage on critical paths.
- Write a testing guide for the org: when to use unit vs RTL vs Playwright, query priority rules, mock standards, async patterns.
- Add automated checks: bundle size budgets, accessibility linting (`jest-axe`, `axe-playwright`), and visual regression (Chromatic or Percy) as appropriate.

**Managing CI health:**
- Track test suite runtime trends — a suite that grows from 3 min to 15 min over 6 months kills developer velocity.
- Shard and parallelize. Own the CI configuration as infrastructure.
- Define a flakiness SLA: any test that fails intermittently 3+ times in 30 days gets quarantined and prioritized for fix.

**Advocating upward:**
- Frame test investment in terms of MTTD (mean time to detect regression), deployment frequency, and on-call burden.
- A well-tested codebase reduces P0 incidents and accelerates feature velocity — make that case with data.

### Quick recall
- Set coverage thresholds on critical paths, not blanket line %.
- Own CI runtime as infrastructure — shard, parallelize, monitor trends.
- Flakiness SLA: quarantine and fix, don't ignore.
- Frame testing ROI in MTTD, deploy frequency, and incident reduction.

---

## Q10) What are common mistakes teams make and how do you fix them as Staff?

| Mistake | Fix |
|---|---|
| All-E2E strategy — slow, flaky CI | Rebalance to pyramid. Write RTL for component behavior. |
| Testing implementation details (state, class names) | Enforce semantic query-first RTL approach in code review. |
| Fragile CSS selectors in Playwright | Ban `page.$('.btn-primary')`. Enforce `getByRole`/`getByLabel`. |
| Non-deterministic async tests | Shared jest setup with fake timers pattern. `waitFor` guidelines. |
| Coverage theater (100% lines, 0% confidence) | Switch to meaningful branch coverage on critical flows only. |
| Flaky tests ignored in CI | Introduce quarantine suite + flakiness SLA. |
| No accessibility testing | Add `jest-axe` to RTL suite. Add axe checks to Playwright smoke tests. |

### Quick recall
- Test behavior, not internals.
- Semantic selectors everywhere.
- Deterministic async. Flakiness SLA.
- Coverage on critical branches, not line count.
- Accessibility testing is not optional at Staff level.