# Security and Caching Notes — Staff Engineer Level

## Q1) What is the practical difference between XSS and CSRF?

**XSS (Cross-Site Scripting)** is an injection attack where attacker-controlled script executes in your application's origin context. Once running in your origin, it can read DOM content, access cookies not marked HttpOnly, steal tokens from localStorage, and make authenticated requests — all as the current user. XSS is fundamentally a trust violation: the browser trusts your origin, so injected code inherits that trust.

**CSRF (Cross-Site Request Forgery)** abuses the browser's automatic cookie attachment. An attacker's page triggers a request to your backend; the browser attaches the victim's session cookie automatically, making the forged request appear authenticated. CSRF doesn't execute script — it forges requests that carry credentials the attacker doesn't need to know.

Key distinction: XSS gives script execution power; CSRF abuses authenticated request flow without needing script execution.

### Quick recall
- XSS: script runs in your origin → full origin access.
- CSRF: forged request with auto-attached cookies → authenticated action without user intent.
- XSS defense: output encoding, CSP, sanitization.
- CSRF defense: SameSite cookies, anti-CSRF tokens, origin validation.

---

## Q2) How do SameSite cookies reduce CSRF risk?

`SameSite` controls whether the browser sends cookies on cross-site requests:

- **`Strict`**: Cookie never sent on cross-site requests — even top-level navigations from external sites. Strongest CSRF protection; can break OAuth and external redirect flows.
- **`Lax`** (modern browser default): Cookie sent on top-level navigations (user clicks a link) but not on cross-site subrequests (fetch, XHR, form POST from external origin). Practical default that preserves most UX while blocking most CSRF vectors.
- **`None`**: Cookie sent cross-site. Must be combined with `Secure`. Required for third-party contexts (OAuth, embedded iframes, SSO). Needs explicit CSRF mitigation since cookie is cross-site accessible.

### Quick recall
- `Strict` → strongest, may break external redirect flows.
- `Lax` → good default, blocks most CSRF.
- `None` → cross-site; requires `Secure` and explicit CSRF controls.

---

## Q3) Why do anti-CSRF tokens still matter if SameSite is enabled?

Defense in depth. SameSite is a browser behavior — you can't control all browser versions, proxy behaviors, or future spec changes. Anti-CSRF tokens provide server-verifiable proof that a request originated from a page your server rendered, not from an attacker's origin.

An attacker cannot read the CSRF token from your page (same-origin policy blocks cross-origin reads), so forged requests fail server-side validation even if a cookie is somehow attached.

The combination — `SameSite=Lax` + anti-CSRF token + `Origin`/`Referer` header validation — is layered defense. Each layer covers gaps in the others.

### Quick recall
- SameSite: browser-enforced guardrail.
- CSRF token: server-verified proof of page origin.
- Origin/Referer header check: additional server-side validation.
- Never rely on a single control.

---

## Q4) Which security headers are high value in modern web apps?

**HSTS (`Strict-Transport-Security`)**: Forces HTTPS for the specified duration. `includeSubDomains` extends to all subdomains. `preload` submits to browser preload lists — protection before first visit. Blocks SSL-stripping attacks.

**CSP (`Content-Security-Policy`)**: Defines allowed sources for scripts, styles, images, fonts, and other resources. A well-configured CSP is one of the most effective XSS mitigations available. Start with `report-only` mode to find violations before enforcing. Use nonces or hashes instead of `unsafe-inline`.

**`X-Frame-Options` / CSP `frame-ancestors`**: Prevents clickjacking by blocking your page from being embedded in iframes on other origins. `frame-ancestors` in CSP supersedes `X-Frame-Options` and is more expressive.

**SRI (`Subresource Integrity`)**: Ensures third-party CDN resources haven't been tampered with. Browser verifies hash before executing. Critical for any externally hosted script.

**`Permissions-Policy`** (formerly Feature-Policy): Controls access to browser APIs (camera, geolocation, microphone) per-origin. Reduces attack surface if a script is compromised.

**`X-Content-Type-Options: nosniff`**: Prevents MIME-type sniffing attacks.

### Quick recall
- HSTS → HTTPS enforcement, preload for strongest protection.
- CSP → script/resource allowlist, use nonces, deploy in report-only first.
- `frame-ancestors` → clickjacking protection.
- SRI → CDN tamper detection.
- `Permissions-Policy` → API surface restriction.
- `nosniff` → MIME confusion prevention.

---

## Q5) Why is storing JWT in `localStorage` often considered risky?

`localStorage` is synchronously accessible to any JavaScript running on your origin. A single XSS vulnerability — even in a third-party script — can exfiltrate tokens immediately and silently. The attacker doesn't need CSRF-style tricks; they just read `localStorage.getItem('token')`.

HttpOnly cookies are not readable by JavaScript at all, removing this theft vector. The trade-off shifts risk to CSRF, which must then be explicitly mitigated.

For Staff-level consideration: neither storage mechanism is universally "safe" — the right choice depends on your threat model, your XSS risk surface, and your operational ability to enforce CSRF controls.

### Quick recall
- `localStorage` → JS-accessible → XSS exfiltration is trivial.
- HttpOnly cookie → not JS-readable → removes token theft via XSS.
- HttpOnly cookie still needs CSRF mitigation.
- Memory storage (in-app variable) → safest against XSS, lost on refresh, impractical for most apps.

---

## Q6) What is a safer authentication cookie setup?

Baseline: `HttpOnly; Secure; SameSite=Lax` on session/auth cookies. This combination blocks JS reads, enforces HTTPS transport, and prevents most cross-site request abuse.

For sensitive write operations: add CSRF token validation and `Origin`/`Referer` header checks server-side.

For high-security applications, consider the **BFF (Backend for Frontend) pattern**: the BFF server handles authentication and token storage entirely server-side. The browser only holds a session cookie to the BFF; access tokens never reach the client at all. This removes the entire token storage question from the frontend.

Refresh token rotation: issue short-lived access tokens and long-lived refresh tokens. On refresh, invalidate the old refresh token and issue a new one. Detect token reuse (replay attacks) by tracking rotation lineage server-side.

### Quick recall
- Cookie baseline: `HttpOnly + Secure + SameSite=Lax`.
- Write endpoints: add CSRF token + Origin header validation.
- BFF pattern: keep tokens server-side entirely.
- Refresh token rotation: detect replay, short-lived access tokens.

---

## Q7) What does "defense in depth" mean in frontend/backend security collaboration?

Defense in depth is the principle that security posture should not depend on any single control. Each layer assumes others may fail.

In practice for a Staff engineer:
- **Frontend**: Framework output encoding (React's JSX escapes by default), strict CSP, SRI for third-party scripts, `dangerouslySetInnerHTML` review gates in code review.
- **Backend**: Input validation and sanitization *server-side* regardless of frontend validation, parameterized queries, auth checks on every endpoint, not trusting request origin headers alone.
- **Infrastructure**: WAF for known attack patterns, dependency scanning (Dependabot, Snyk, npm audit in CI), secrets scanning in git hooks, principle of least privilege for service accounts.
- **Process**: Security review as part of design docs for auth/data flows, incident response runbook, regular penetration testing.

### Quick recall
- Multiple independent layers — one failure doesn't collapse the system.
- Frontend can't be the last line of defense; server must validate independently.
- Supply chain: audit dependencies, lockfile integrity, automated scanning in CI.
- Process: security in design phase, not as an afterthought.

---

## Q8) What is the difference between browser cache and CDN cache?

**Browser cache** is private to one user's device. Reduces repeat load cost for that user. Hard to remotely invalidate — you can't force a user's browser to clear its cache unless you change the URL (cache-busting via content hash) or use `Clear-Site-Data` header (limited support).

**CDN cache** is shared across all users at edge locations. Dramatically reduces origin server load and improves global latency. Centrally purgeable — CDN APIs allow cache invalidation on deploy. Cache hit rate is a first-class metric (CDN miss = origin request = higher latency and cost).

**Service Worker cache** is a programmable, origin-controlled cache in the browser. Unlike HTTP cache, it's fully controlled by JavaScript — you define caching strategies (cache-first, network-first, stale-while-revalidate) explicitly. Enables offline support, background sync, and push notifications.

### Quick recall
- Browser cache: per-user, private, hard to remotely invalidate.
- CDN cache: shared edge, centrally purgeable, hit rate is a KPI.
- Service Worker cache: programmable, strategy-based, enables offline.

---

## Q9) What cache strategy works best for modern SPAs?

**Hashed static assets (JS/CSS/fonts/images)**: Content hash in filename → `Cache-Control: public, max-age=31536000, immutable`. File name changes on every build, so stale content is impossible. Browser and CDN cache indefinitely. This is the foundation of modern asset caching.

**HTML entry point**: Short TTL or `Cache-Control: no-cache` (forces revalidation on each request, but uses cached copy if ETag matches). Ensures users always get the latest app shell pointing to correct asset hashes. Never cache HTML with a long TTL — it becomes the bottleneck to deploying updates.

**API responses**: Depends on data sensitivity and freshness requirements. Public, stable data: `public, max-age=N, s-maxage=M`. User-specific data: `private, no-store` or `private, max-age=N`. Sensitive state: `no-store`. Use `stale-while-revalidate` for non-critical data where showing slightly stale data while refreshing is acceptable.

**CDN-specific**: Use `s-maxage` to control CDN TTL independently of browser TTL. Use `Vary` header carefully — incorrect `Vary` can cause CDN cache fragmentation and poor hit rates.

### Quick recall
- Hashed assets: `immutable, max-age=1yr` — never stale.
- HTML: `no-cache` or short TTL — always fresh app shell.
- User data: `private` — never shared cache.
- Sensitive: `no-store` — never cached.
- `s-maxage` for CDN-specific TTL.

---

## Q10) Why do teams use both `max-age` and `s-maxage`?

`max-age` controls browser (private) cache lifetime. `s-maxage` controls shared cache (CDN, proxy) lifetime and overrides `max-age` for shared caches.

This separation allows independent tuning: you might want CDN to cache an API response for 5 minutes (`s-maxage=300`) to reduce origin load, while telling browsers to revalidate on every request (`max-age=0, must-revalidate`) to ensure users always see fresh data. Without `s-maxage`, you'd have to choose one TTL for both caching tiers.

```
Cache-Control: public, max-age=0, s-maxage=300, stale-while-revalidate=60
```

This says: browsers always revalidate, CDN serves for 5 min, then can serve stale for 60s while refetching.

### Quick recall
- `max-age` → browser TTL.
- `s-maxage` → CDN/shared cache TTL (overrides max-age for shared caches).
- Use both for independent per-tier cache control.

---

## Q11) How should I explain secure token architecture trade-offs in interviews?

The framing matters: there is no storage strategy that eliminates risk — each shifts the risk profile. The job is to understand the threat model and choose accordingly.

| Strategy | XSS Risk | CSRF Risk | Notes |
|---|---|---|---|
| `localStorage` JWT | High — JS-readable | Low — not auto-sent as cookie | Suitable only if XSS surface is very tightly controlled |
| HttpOnly cookie | Low — not JS-readable | High — auto-sent cross-site | Requires strong CSRF controls |
| HttpOnly + SameSite=Lax | Low | Low-Medium | Good default; gaps remain |
| BFF (server-side token) | Very Low | Very Low | Best security, higher complexity |
| Memory only (in-app variable) | Very Low | Low | Lost on refresh, poor UX |

Staff answer: "I'd start by defining our threat model — what's our XSS risk surface, do we have third-party scripts, what's our session lifetime, are we on subdomain boundaries that affect SameSite? Then I'd design to that, not to a generic recommendation. For most production apps I'd advocate for HttpOnly + SameSite + CSRF token + BFF if we handle particularly sensitive data."

### Quick recall
- No perfect answer — trade-offs, not solutions.
- Define threat model first, then choose.
- BFF pattern is strongest for high-security requirements.
- Layer controls: cookie attributes + CSRF tokens + origin checks.

---

## Q12) What quick checklist should I run before release?

**Security:**
- [ ] Auth cookies: `HttpOnly`, `Secure`, `SameSite` set correctly
- [ ] CSRF tokens active on all state-mutating endpoints
- [ ] CSP configured and tested (start in report-only, then enforce)
- [ ] HSTS with `includeSubDomains` and `preload` on production domain
- [ ] `frame-ancestors` / `X-Frame-Options` set
- [ ] SRI hashes on all externally-hosted scripts
- [ ] `Permissions-Policy` restricts unneeded browser APIs
- [ ] `npm audit` / Dependabot scan clean
- [ ] No secrets in client bundle (env var audit)

**Caching:**
- [ ] Static assets have content-hashed filenames + `immutable` cache headers
- [ ] HTML entry point has short TTL or `no-cache`
- [ ] User-specific API responses have `private` directive
- [ ] Sensitive responses have `no-store`
- [ ] CDN purge process tested and documented

**Process:**
- [ ] CDN rollback procedure documented and tested
- [ ] Error monitoring (Sentry) capturing auth/session errors
- [ ] Incident runbook updated

### Quick recall
- Cookie flags → headers → dep scan → secrets → cache directives → CDN purge.
- Security is a process, not a checklist — but checklists prevent the obvious misses.