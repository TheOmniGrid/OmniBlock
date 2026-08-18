# Security Policy

OmniBlock is a content blocker: it parses and enforces third-party filter
lists (EasyList, EasyPrivacy, uBlock Origin's uAssets, HaGeZi's DNS
blocklists, and any custom list a user subscribes to) and injects CSS and
scriptlets into every page a user visits. That combination — untrusted
input, broad page access, and code execution — is exactly the kind of
thing that produces vulnerabilities, and it already has, once. This file
exists so a report has somewhere to go.

## Scope

In scope:

- The extension itself, on both build targets — the Chromium
  `declarativeNetRequest` engine and the Firefox `webRequest` /
  `@ghostery/adblocker` engine.
- The ruleset compiler and its supply-chain integrity checks (pinned
  source commits, SHA-256 verification of fetched resources).
- The build and release pipeline.

Out of scope:

- The upstream filter lists themselves (EasyList, HaGeZi, etc.) — report
  issues with list content to their own maintainers.
- The `@ghostery/adblocker` engine's own internals, unless the issue is
  specifically how OmniBlock uses it (e.g. a bypassed sanitization layer).
  Report engine-level bugs upstream.
- Denial-of-service via a pathologically large or slow-to-parse filter
  list a user chose to subscribe to themselves — this is a known-accepted
  risk of the subscription model, not a vulnerability in OmniBlock's
  handling of it, unless it's exploitable *without* the user opting in.

## How to report

Email **andre.hetzl@gmail.com** with a description of the issue, the
affected browser/build target (Chromium, Firefox, or both), and, if
possible, steps to reproduce or a proof-of-concept filter list line.
Please do not open a public GitHub issue for a vulnerability that isn't
already public — this is currently a single-maintainer project with no
dedicated security mailing list or bug-bounty program, so a direct email
is the fastest path to a fix.

## What to expect

There's no SLA — this is a single-maintainer, unpaid project — but a
genuine security report will get a response acknowledging receipt, and a
fix will be prioritized over feature work once confirmed. If you don't
hear back within a couple of weeks, it's fine to follow up; it does not
mean the report was ignored on purpose.

## Trust model

Being explicit about what OmniBlock treats as trusted versus untrusted,
since getting this distinction wrong is exactly how the project's one
confirmed critical vulnerability happened:

- **Packaged filter lists**, compiled from pinned upstream sources at
  build time, and **the local user's own "My Filters" text** are treated
  as trusted — curated by this project or typed by the user into their own
  browser. Scriptlets from either source are allowed to resolve and run.
- **Subscribed third-party custom lists** are treated as **untrusted,
  attacker-controlled input**. Any scriptlet-injection syntax in a custom
  list is stripped before either blocking engine ever sees it, independent
  of whether the custom list's publisher is malicious or was themselves
  compromised.
- **Scriptlets only ever come from the packaged, `trusted-*`-stripped
  resource set**, fetched from a pinned upstream commit with a SHA-256
  integrity check at compile time. uBlock Origin's own `trusted-*`
  scriptlets (which that project gates behind its own trust model,
  unenforced anywhere in this stack) are stripped from the packaged
  resource set entirely, not merely left ungated.
- **A second, independent defense** patches the one place in the installed
  `@ghostery/adblocker` library that resolves a scriptlet's arguments into
  runnable code, refusing any argument containing a backtick — closing a
  specific upstream template-literal injection this project found and
  reported against `@ghostery/adblocker@2.18.2`. The patch asserts its
  target methods exist at startup and fails loudly if a dependency update
  renames them, rather than silently no-op-ing.
- **The packaged extension never fetches or evaluates remote code at
  runtime**, on either browser. All scriptlet execution happens on code
  that was already resolved from the packaged, compile-time-verified
  resource set or the local user's own text — never fetched over the
  network at runtime.

If you find a gap in any of the above — a case where untrusted input
reaches code execution, or a place this document's claims don't match what
OmniBlock actually does — that is exactly the kind of report this policy
exists for.
