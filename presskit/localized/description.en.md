# OmniBlock — Store Listing Copy

Source of truth for both stores' listing forms. Copy exact strings from the
fenced blocks below directly into the CWS Developer Dashboard / AMO
Developer Hub — don't retype them, so the character-count comments here
stay honest.

## Name

```
OmniBlock
```

## Category

- **Chrome Web Store:** Productivity (secondary option: Tools) — CWS's
  closest fit for a content-blocking utility extension as of this writing;
  re-check the current category list in the Developer Dashboard at
  submission time, since CWS has changed its taxonomy before.
- **AMO:** Privacy & Security → Ad Blockers

## Short description (Chrome Web Store, ≤132 characters)

122 characters:

```
Ad, tracker and threat blocker: 6 protection levels, Security Shield, custom lists, per-site controls. No telemetry, ever.
```

## Summary (AMO, ≤250 characters)

185 characters:

```
Blocks ads, trackers and known-malicious sites across 6 protection levels plus an independent Security Shield. Custom lists, per-site trust, element picker. Zero telemetry, fully local.
```

## Full description (both stores)

```
OmniBlock is a multi-browser content blocker: ads, trackers, cookie
banners, and known-malicious sites, with a 0-5 protection-level dial,
an independent always-on Security Shield, per-site controls, custom
filter-list subscriptions, and a point-and-click element picker.

HONEST ABOUT PLATFORM DIFFERENCES

On Chrome, Edge, Brave, and other Chromium browsers, OmniBlock runs on
Manifest V3's native declarativeNetRequest API. No Manifest V3
extension — OmniBlock included — can match what MV2-era uBlock Origin
could do, because Chrome removed the dynamic-filtering API that made
it possible. OmniBlock's real competition on Chromium is uBO Lite and
ABP-MV3, and we aim to beat both on filter-list depth, protection-level
ergonomics, and per-site control, while running at native DNR speed —
zero JavaScript in the request path, which is strictly faster than any
MV2-style blocker's JS-evaluated matching ever was.

On Firefox, OmniBlock uses full blocking webRequest with its own
filtering engine, putting it genuinely in uBlock Origin's class:
complete filter-list syntax support, unlimited rules, and a matcher
that, per Ghostery's own published benchmarks, is faster than uBO's.

We'd rather tell you this up front than let you find out the hard way.

FEATURES

- 6 protection levels (Off through Fortress), each cumulative and
  precompiled — switching levels is instant, no restart
- Independent Security Shield: threat-intelligence blocklists (malware,
  phishing, scam, fake shops) that stay on even at protection level Off,
  because security isn't an ad-blocking preference
- Custom filter-list subscriptions — subscribe to any adblock- or
  hosts-syntax list URL
- My Filters — write your own filter rules by hand, validated line by
  line
- Element picker — point and click to hide anything a filter list
  missed
- Per-site controls — trust a site entirely, exempting it from blocking
  with one click
- Local stats dashboard — blocked-request history and top blocked
  domains (Firefox; see the platform note in the Stats page about why
  Chromium can't expose this data to any extension)
- Import/export your settings as a single file
- Dark-only Rift interface (OmniVex design system, OmniBlock's signature
  blue) designed for a fast, low-friction popup

PRIVACY

Zero data collection. No telemetry, no analytics, no accounts, no
server. Filter lists are fetched as adblock-syntax filter text from
their public maintainers (EasyList, uBlock Origin's filter lists,
HaGeZi's DNS blocklists). The scriptlet library those rules can
reference ships packaged inside the extension itself, pinned to a
specific verified version — and any list you subscribe to yourself
has scriptlet-invoking lines stripped out before OmniBlock's blocking
engines ever see them. Full policy: see the Privacy tab on this
listing.
```

## Data-collection disclosure

Both stores now ask developers to explicitly declare what user data an
extension collects.

- **Chrome Web Store (Privacy practices tab):** select **"This item does
  not collect user data."** OmniBlock genuinely collects nothing — see
  [`privacy-policy.md`](./privacy-policy.md).
- **AMO `data_collection_permissions`** — required as of Mozilla's
  November 3, 2025 built-in data-collection consent system for all new
  extensions (verified 2026-08-16 against Mozilla's own
  [Extension Workshop docs](https://extensionworkshop.com/documentation/develop/firefox-builtin-data-consent/)
  and the [MDN `browser_specific_settings` reference](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_specific_settings)).
  **This is a `manifest.json` key, not just a submission-form question** —
  `wxt.config.ts`'s Firefox manifest branch already declares it:
  ```json
  "browser_specific_settings": {
    "gecko": {
      "data_collection_permissions": { "required": ["none"] }
    }
  }
  ```
  (confirmed present in a real build's `.output/firefox-mv3/manifest.json`).
  This manifest key is the authoritative, validator-checked declaration —
  Mozilla's docs describe it as what gets shown to users at install time,
  on the listing page, and in `about:addons`. Whether the Developer Hub
  submission flow additionally surfaces a confirmation step reflecting it
  wasn't independently confirmed here (that's a live-UI detail, not
  something the public docs describe) — check the current upload flow at
  first-submission time; if it asks anything about data collection, it
  should already match what's declared here. Nothing in OmniBlock's
  manifest or code path collects, transmits, or stores any personal-data
  category anywhere but the user's own local browser storage — see the
  privacy policy for exactly what's stored locally and why.

## Screenshots checklist

Chrome Web Store wants 1280×800 (or 640×400) PNG/JPEG screenshots, 1-5 of
them; AMO accepts the same images. Capture all of these, at 1280×800, from
a real built extension (not a mockup) with a non-empty, realistic-looking
state (a handful of custom lists, some blocked-request history, a couple of
trusted sites) rather than a brand-new empty install:

1. **Popup, default level** — the level control (a 6-way pill row, active
   pill accent-filled) on Balanced, site domain shown, Trust toggle,
   Security Shield status pill, blocked counters visible.
2. **Popup, level control mid-interaction** — focused on a non-default
   pill, to show all 6 protection levels clearly.
3. **Dashboard — Lists page** — the catalog of built-in components with
   per-list rule counts, plus at least one subscribed custom list.
4. **Dashboard — Stats page** — the 30-day blocked-over-time chart and top
   blocked domains (capture this on a Firefox build — see the honesty note
   above about why Chromium can't populate this page the same way; if a
   Chromium screenshot is needed too, capture its honest
   "not available on this platform" explanation rather than an empty
   chart).
5. **Dashboard — Security Shield page** — the always-on threat-feed
   toggle and its own description.
6. **Element picker in action** — mid-selection on a real page, showing
   the picker's highlight/selection UI.

## Promo tiles

Already generated by `pnpm icons` (`tools/icon-generator/generate.mjs`'s
`MARKETING_TILES`) — do not hand-design new ones, just re-run `pnpm icons`
if the icon/brand mark ever changes:

- `docs/store/assets/440x280.png` — Chrome Web Store small promo tile
- `docs/store/assets/1400x560.png` — Chrome Web Store marquee-style promo
  tile (also reusable as AMO's larger listing header image if needed)

## Support / homepage URL

Use the repository URL once a GitHub remote exists (none as of Task 16 —
see `submission-runbook.md`'s account-setup section). Support contact in
the meantime: andre.hetzl@gmail.com.
