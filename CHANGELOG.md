# Changelog

All notable changes to OmniBlock are recorded here, most recent first.

## 0.12.0

An internal cleanup and hardening pass following a full re-audit of the
codebase: dependencies pinned to exact versions, comment and dead-code
bloat trimmed across several modules, oversized files split along their
actual responsibilities, and a handful of duplicated helper functions
consolidated into one place. No user-facing feature changes.

## 0.11.0

A follow-up audit found further issues after 0.10.0; all were fixed in
this release.

### Security
- Pinned the scriptlet/redirect resource library to a specific upstream
  commit with a SHA-256 integrity check, and stripped all `trusted-*`
  scriptlets from the packaged resource set — nothing in this stack
  enforces uBlock Origin's own trust gating for them, so they're removed
  entirely rather than left reachable.
- Resolved a filter-compilation gap that had silently dropped included
  content from several upstream lists, recovering roughly 21,000 rules
  (about 2.25 MB) of blocking coverage that should have been there all
  along.
- Subscribed custom-list content now has scriptlet-injection syntax
  stripped before either blocking engine sees it, and a backtick-argument
  guard closes a template-literal injection independent of source — the
  combination closes a critical remote-code-execution path that a
  malicious or compromised custom list could otherwise have used.
- Custom-list fetches now reject non-HTTP(S) schemes and
  loopback/private/link-local hosts, and cap response size at 5 MB,
  streamed.
- The element picker's selector generator rejects characters that could
  otherwise inject broken or unsafe selectors, and refuses to produce an
  unsafe one rather than guessing.
- The settings-import confirmation dialog now shows the actual custom-list
  URLs and My Filters lines being added, not just a count — previously, a
  same-count list swap or a scriptlet addition produced no visible
  warning.
- Release pipeline hardened: GitHub Actions pinned to commit SHAs, no
  persisted release credentials, and both the typecheck and test gates now
  actually run before a release is built (they previously didn't).

### Fixed
- Firefox cosmetic hiding and scriptlet injection, which 0.10.0 had
  claimed were fixed and were not — the underlying library's only styling
  path relied on an API Firefox's Manifest V3 removed.
- Per-site trust and per-site cosmetic/scriptlet toggles on Firefox, fixed
  as a side effect of the same underlying repair.
- A brief window after the extension's background process woke from sleep
  during which requests could pass through unblocked, now closed with a
  readiness gate.
- Contrast and keyboard-accessibility issues across the popup and
  dashboard: WCAG AA color contrast, keyboard navigation on the
  protection-level dial, minimum 24px touch targets on toggle switches,
  and a visible, announced error message when a level/trust/shield save
  fails.
- The My Filters rule-limit error message now formats its number correctly
  in every supported language instead of always using English formatting.

## 0.10.0

### Added
- Full interface translation into English, German, Spanish, French, and
  Romanian, with automatic detection of your browser's language and a
  manual override in Settings.
- The OmniVex visual restyle: a blue accent color, a new toolbar icon, and
  a restyled popup and dashboard.

### Fixed
- Firefox's background blocking registration, which previously went dark
  after the browser suspended and revived the extension's background
  process instead of surviving it.
- Firefox cosmetic hiding, scriptlet delivery, and Chromium cosmetic-engine
  persistence across background-process restarts. (A related regression
  in the Firefox fix specifically was found and corrected in 0.11.0.)
- Replaced a broken, effectively empty upstream annoyances source with two
  working ones, and added a safeguard so a future empty-source problem
  fails the build loudly instead of silently shipping near-zero rules.
- A bug where per-site overrides could be computed at the wrong site
  granularity in one code path, causing a trust decision to apply more
  broadly — or narrowly — than intended.

## 0.9.0

The first release candidate: the ruleset compiler, the Chromium
`declarativeNetRequest` engine, the Firefox `webRequest` +
`@ghostery/adblocker` engine, cosmetic filtering and scriptlet injection,
the popup and dashboard interface, custom list subscriptions, the element
picker, the stats dashboard, and the CI/release pipeline.
