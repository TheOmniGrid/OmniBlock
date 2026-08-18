# OmniBlock Privacy Policy

**Effective date:** 2026-08-18
**Contact:** andre.hetzl@gmail.com

## Summary

OmniBlock collects **zero** data. It has no telemetry, no analytics, no
crash reporting, no account, no sign-in, and no server of its own.
Everything the extension knows about you or your browsing stays on your
device, in your browser's own storage. Nothing you do inside OmniBlock —
which sites you trust, which level you run, what you block, what shows up
on the Stats page — is ever transmitted anywhere by the extension.

The only network activity OmniBlock ever initiates is fetching filter-list
*text* (the block/hide rules themselves) from the public list maintainers
listed below, and — only if you choose to use it — a filter list URL you
supply yourself.

## What is stored locally, and where

All of the following lives in your browser's own local extension storage
(`browser.storage.local`, and — on Firefox only — a local IndexedDB
database). None of it is synced to any OmniBlock server, because no such
server exists.

| Data | Purpose | Where |
|---|---|---|
| Your protection level (0–5) and Security Shield on/off | Remembers your chosen blocking level between sessions | `storage.local` |
| Trusted sites (sites you've chosen to exempt from blocking entirely) | Remembers sites you've trusted | `storage.local` |
| Custom list subscriptions (URL, title, last-fetched time, rule count) | Remembers filter lists you've subscribed to | `storage.local` |
| My Filters (your own custom filter rules, if you write any) | Remembers rules you've authored yourself | `storage.local` |
| Blocked-request totals and 30-day history / top blocked domains | Powers the Stats dashboard page (Firefox only — see note below) | `storage.local` |
| The compiled filtering engine, serialized for fast startup | Avoids re-parsing filter lists on every browser start (Firefox only) | IndexedDB (local) |
| Cached text of subscribed filter lists | Avoids re-fetching a list on every use; used to rebuild the engine | IndexedDB (local) |

**Chromium note:** on Chrome/Edge/Brave and other Chromium browsers,
OmniBlock uses the browser's native `declarativeNetRequest` API, which
does not expose per-request match data to extensions. The Stats page is
honest about this — it does not fabricate Chromium block counts it cannot
actually see. Only the toolbar badge (backed by the browser's own count)
and dynamic-rule usage are shown there.

Nothing in the table above is ever read by anyone but you: there is no
"send diagnostics," no crash reporter, and no remote logging anywhere in
OmniBlock's code.

## What leaves your device, and why

OmniBlock fetches **filter-list text** — adblock-syntax network-blocking
and cosmetic-hiding rules — from the following public sources, so it can
keep your blocklists current:

- `easylist.to` — EasyList, EasyPrivacy
- `secure.fanboy.co.nz` — the Fanboy cookie-notice list (part of the
  EasyList family)
- `raw.githubusercontent.com` — uBlock Origin's `uAssets` filter lists,
  its scriptlet/redirect resource library, and HaGeZi's DNS blocklists

**When this happens differs by platform.** On Chromium (Chrome, Edge,
Brave, and similar), these built-in lists are compiled into the extension
at build time — OmniBlock's own code never re-fetches them at runtime;
only a **custom list** you subscribe to yourself is fetched by the running
extension. On Firefox, the extension additionally re-fetches these same
built-in sources itself, on a periodic timer, so its filter engine can
stay current between releases. Either way, **which of these source URLs
get fetched depends on your protection level** — a higher level enables
more filter-list components, each with its own source URL(s) — so the
*set* of URLs your browser requests is a weak but real signal to those
list-hosting servers about which protection level you run. No stronger
signal than that is ever sent: no identifier tied to you, no browsing
history, no query parameters describing your settings or activity.

These requests otherwise carry no information about you beyond what any
plain HTTP request to a public file necessarily includes (your IP address,
as seen by that server — the same as visiting any website).

If you subscribe to a **custom list** (Dashboard → Lists → "Add custom
list") or write **My Filters**, OmniBlock will also fetch whatever URL
*you* supply, on the same basis. That is a request you've explicitly asked
for; OmniBlock does not fetch any list URL you haven't added yourself.

**On scriptlets specifically:** some filter-list lines (`##+js(name,
args)`) invoke a named scriptlet from a small helper-script library,
rather than embedding code directly. That library is fetched over the
network exactly once, at **build time** (never by the running extension),
from a specific pinned source-code commit, with its contents checksummed
against a value recorded in OmniBlock's own build tooling — an unexpected
change to it fails the build rather than silently shipping. The library
that results ships packaged inside the extension; nothing
scriptlet-related is ever fetched at runtime. As a further safeguard, any
scriptlet-invoking line in a **custom list you subscribe to** is stripped
out before either of OmniBlock's blocking engines ever sees it, so a
subscribed list cannot introduce scriptlet behavior at all, regardless of
what it contains.

No other network requests originate from OmniBlock. In particular:

- No usage analytics, telemetry, or crash reports are ever sent, to us or
  anyone else.
- No remotely hosted code is ever executed at runtime, on either browser —
  the only network fetch of scriptlet code happens at build time,
  described above.
- Filter-list fetches never include your settings, your browsing activity,
  or any identifier tied to you (beyond the list-URL-selection signal
  described above).

## Permissions

OmniBlock requests broad host permissions (`<all_urls>`) on every
platform, so it can evaluate and block or hide content on any page you
visit. Beyond that, the exact permission set is platform-specific (both
request `storage`, `scripting`, and `alarms`):

- **Chromium:** `declarativeNetRequest` — the native Manifest V3 blocking
  API.
- **Firefox:** `webRequest` + `webRequestBlocking` — OmniBlock's own
  matching engine runs over this path on Firefox instead of
  `declarativeNetRequest`, for full uBlock-Origin-class filtering (see
  "Positioning, honestly" in the [README](../README.md)) — plus
  `webNavigation`, used only to reset the per-tab blocked-request counter
  when a new page navigation commits.

None of these are used to collect or transmit data about you — see "What
is stored locally" and "What leaves your device" above for the complete,
honest account of what OmniBlock actually does with them.

## Changes to this policy

If OmniBlock's data practices ever change, this document will be updated
and the "Effective date" above will change accordingly. Given that "zero
data collection" is a stated project goal, not an incidental current
state, no such change is currently planned.

## Contact

Questions about this policy: **andre.hetzl@gmail.com**
