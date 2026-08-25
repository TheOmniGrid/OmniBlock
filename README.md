<p align="center">
  <img src="assets/banner-animated.gif?v=20260822-premium-motion-v3" alt="OmniBlock — Privacy-first blocking for Chromium and Firefox." width="100%">
</p>

<h1 align="center">OmniBlock</h1>
<p align="center"><b>A content blocker for Chromium and Firefox — six protection levels, an always-on security shield, custom lists and per-site control.</b></p>
<p align="center">Part of the <a href="#the-omnivex-suite">OmniVex</a> suite.</p>

<p align="center">
  <a href="https://www.patreon.com/TheOmniGrid"><img alt="Get it on Patreon" src="https://img.shields.io/badge/Get%20it%20on-Patreon-FF424D?style=for-the-badge&logo=patreon&logoColor=white"></a>
  &nbsp;
  <a href="https://ko-fi.com/theomnigrid"><img alt="Get it on Ko-fi" src="https://img.shields.io/badge/Get%20it%20on-Ko--fi-FF5E5B?style=for-the-badge&logo=kofi&logoColor=white"></a>
</p>

<!-- Suite metadata: Version · Platform · Languages · Telemetry · Distribution -->
<p align="center">
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-8A7BFF?style=flat-square">
  <img alt="Platform" src="https://img.shields.io/badge/platform-Chromium%20%C2%B7%20Firefox-57C7FF?style=flat-square">
  <img alt="Languages: 11" src="https://img.shields.io/badge/languages-11-8A7BFF?style=flat-square">
  <img alt="Telemetry" src="https://img.shields.io/badge/telemetry-none-00C66D?style=flat-square">
  <img alt="Distribution" src="https://img.shields.io/badge/distribution-docs%20only-969FAB?style=flat-square&labelColor=30363D">
</p>

<!-- Quick navigation. These are clickable: each chip jumps to a section of this
     page, or to the document it names. Anchors are GitHub's own slugs for the
     headings below -- if a heading is renamed, its chip has to be renamed too. -->
<p align="center">
  <a href="#get-omniblock"><img alt="Get OmniBlock" src="https://img.shields.io/badge/⬇%20Get%20OmniBlock-8A7BFF?style=for-the-badge"></a>
  <a href="#what-it-does"><img alt="Features" src="https://img.shields.io/badge/Features-2B2545?style=for-the-badge"></a>
  <a href="#six-protection-levels"><img alt="Levels" src="https://img.shields.io/badge/Levels-2B2545?style=for-the-badge"></a>
  <a href="#fast-by-construction"><img alt="Performance" src="https://img.shields.io/badge/Performance-2B2545?style=for-the-badge"></a>
  <a href="#see-it"><img alt="Screenshots" src="https://img.shields.io/badge/Screenshots-2B2545?style=for-the-badge"></a>
  <a href="#privacy-by-construction"><img alt="Privacy" src="https://img.shields.io/badge/Privacy-2B2545?style=for-the-badge"></a>
  <a href="INSTALLATION.md"><img alt="Installation" src="https://img.shields.io/badge/Installation-2B2545?style=for-the-badge"></a>
  <a href="FAQ.md"><img alt="FAQ" src="https://img.shields.io/badge/FAQ-2B2545?style=for-the-badge"></a>
  <a href="SUPPORT.md"><img alt="Support" src="https://img.shields.io/badge/Support-2B2545?style=for-the-badge"></a>
  <a href="CHANGELOG.md"><img alt="Changelog" src="https://img.shields.io/badge/Changelog-2B2545?style=for-the-badge"></a>
</p>

> [!IMPORTANT]
> **Documentation-only repository.** This public repository contains OmniBlock documentation, approved artwork, and screenshots—not the extension source tree, packaged builds, store payloads, signing material, or private build infrastructure. Official distribution remains outside GitHub.

<img src="assets/presentation/metrics.png" alt="OmniBlock verified snapshot: 623,896 default domains, 694,738 Fortress domains, 14 maintained sources, and zero usage telemetry" width="100%">

<p align="center">
  <img src="assets/screenshots/popup-hero.png" width="340" alt="The OmniBlock popup: one dial, six levels, and a security shield">
</p>

---

## What it does

OmniBlock blocks **623,896 distinct domains** at its default setting and
**694,738** at its highest level — ads, trackers, malware, phishing, scam and
fake-shop domains, compiled from fourteen maintained filter sources.

It is built around one idea: blocking should be something you *tune*, not
something you fight. One dial, six levels, and a security shield that stays on
even when you turn everything else off.

<img src="assets/presentation/capabilities.png?v=20260825-symbol-number-v4" alt="OmniBlock capability map covering tunable protection, the always-on Security Shield, fine control, and native browser performance" width="100%">

### Six protection levels

<img src="assets/presentation/levels.png?v=20260825-symbol-number-v4" alt="OmniBlock protection levels from Off through Fortress, including the distinct domain count at each level" width="100%">

| Level | | What it blocks | Distinct domains |
|---|---|---|---:|
| 0 | **Off** | Blocking disabled — the shield stays on | 439,389 |
| 1 | **Light** | Ads only, maximum compatibility | 508,560 |
| 2 | **Balanced** | Ads, trackers and privacy — the default | 623,896 |
| 3 | **Strict** | Adds annoyances and cookie banners | 645,103 |
| 4 | **Aggressive** | Broader blocking, some sites may break | 669,328 |
| 5 | **Fortress** | Maximum blocking — expect breakage | 694,738 |

<sub>Counted from the compiled rulesets on 2026-08-19: unique domains across
every list active at that level, deduplicated — the same domain appearing in
three lists counts once. The upstream lists change daily, so read these as a
snapshot rather than a constant.</sub>

### The Security Shield

Malware, phishing, scam and fake-shop domains are handled on a **separate,
always-on axis** — including at level 0. Turning ads down should never turn
phishing protection off. That is a deliberate design decision, not a default
you have to remember to set.

### Everything else

- **Per-site trust** — one click in the popup, either permanently or only until the browser restarts.
- **Regional lists** — nine optional language-specific lists, disabled by default and free of rule-budget cost until enabled.
- **Element picker** — point at anything on a page, preview the generated cosmetic rule, then commit or revert it.
- **Element zapper** — remove page annoyances for the current visit without saving a rule.
- **Custom lists** — subscribe to any filter list by URL, in adblock or hosts syntax; Chromium converts safe `$redirect`, `$removeparam` and `$csp` rules to native DNR behavior.
- **My Filters** — write your own rules, validated line by line as you type.
- **Tracker neutralization** — packaged redirect stubs, tracking-parameter removal and CSP policies where each browser exposes a safe implementation path.
- **CNAME uncloaking on Firefox** — resolves disguised first-party tracker hosts through Firefox's own DNS API and blocks the real destination when it matches.
- **Statistics** — a running total, 30-day history and top blocked domains, computed and stored **only on your machine** on both browsers. Chromium's detailed feed is available because OmniBlock ships unpacked and feature-detects the native DNR debug event; unsupported store-packaged contexts show an explanation instead of invented data.
- **Import / export** — your whole configuration as a single JSON file.
- **Eleven languages** — see below.
- **A dark, deliberate interface** — part of the OmniVex design language, not a template.

## Fast by construction

<img src="assets/presentation/engines.png" alt="OmniBlock engine comparison: native declarativeNetRequest on Chromium and full webRequest blocking with Ghostery on Firefox" width="100%">

On Chromium, OmniBlock runs **no JavaScript in the request path at all**. Blocking
is handled by the browser's own native filtering engine from precompiled rulesets,
which is why it cannot slow your browsing the way a callback-based blocker can.

On Firefox, it uses full request blocking with the Ghostery matching engine —
unlimited rules and live list updates.

Both paths ship with measured numbers rather than promises. A benchmark harness
parses the real packaged filter text and reports engine memory, deserialize time,
cosmetic-pass cost and on-disk size; three of those — engine size, deserialize
time and packaged output size — are hard thresholds checked on a weekly run
against every real upstream source, and a breach fails that run loudly. The
ruleset compiler additionally fails the build outright if a level overruns
Chromium's static rule budget.

### Positioning, honestly

OmniBlock will not tell you it beats uBlock Origin everywhere, because that
would not be true.

On **Chromium**, Google removed the API that made uBlock Origin's dynamic
filtering possible. No extension can match MV2-era uBO there — not this one, not
any other. OmniBlock's real competitors on Chromium are uBO Lite and ABP, and it
aims to beat them on list depth, level ergonomics and per-site control, at
native speed.

On **Firefox**, full request blocking is still available, and OmniBlock plays in
uBO's own league.

Anyone claiming otherwise is selling something.

## Eleven languages

English, Deutsch, Español, Français, Română, Русский, Türkçe, 简体中文, 繁體中文,
日本語 and 한국어 — the complete interface, not just the menus. OmniBlock follows
your browser's language automatically, and you can override it at any time without
restarting the browser. Plural forms follow each locale's CLDR rules.

## See it

<table>
<tr>
<td width="50%"><img src="assets/screenshots/dashboard-lists.png" alt="Filter list management"><br><sub><b>Lists</b> — every built-in list, what it costs, and whether it is active at your level.</sub></td>
<td width="50%"><img src="assets/screenshots/dashboard-shield.png" alt="The Security Shield"><br><sub><b>Security Shield</b> — threat protection on its own switch, on even at level zero.</sub></td>
</tr>
<tr>
<td><img src="assets/screenshots/picker.png" alt="Element picker"><br><sub><b>Element picker</b> — click anything, and it stays gone.</sub></td>
<td><img src="assets/screenshots/dashboard-myfilters.png" alt="My Filters"><br><sub><b>My Filters</b> — uBlock-Origin-style syntax, validated as you type.</sub></td>
</tr>
<tr>
<td><img src="assets/screenshots/dashboard-stats.png" alt="Statistics dashboard"><br><sub><b>Statistics</b> — local-only, and honest about what each engine can actually see.</sub></td>
<td><img src="assets/screenshots/popup-de.png" alt="The popup in German"><br><sub><b>Eleven languages</b> — the complete interface, not just the menus.</sub></td>
</tr>
</table>

## Privacy by construction

**No telemetry. No analytics. No accounts. No servers.**

OmniBlock contacts exactly three kinds of address, and nothing else:

1. The filter-list hosts, to download public block lists.
2. Any custom list URL **you** add yourself.
3. Its own packaged files inside the extension.

Your browsing history never leaves your machine, because nothing ever sends it
anywhere. Statistics are computed and stored locally. There is no opt-out,
because there is nothing to opt out of.

Full detail: [Privacy Policy](PRIVACY.md).

## Get OmniBlock

OmniBlock is **donationware**. It is not on the Chrome Web Store or on
addons.mozilla.org, and it is not sold. It is supported by the people who use it.

<p align="center">
  <a href="https://www.patreon.com/TheOmniGrid"><img src="assets/support-patreon.svg" height="64" alt="Support OmniBlock on Patreon"></a>
  &nbsp;&nbsp;
  <a href="https://ko-fi.com/theomnigrid"><img src="assets/support-kofi.svg" height="64" alt="Support OmniBlock on Ko-fi"></a>
</p>

Supporters get the packaged, ready-to-install build for both browsers, the
complete source, and new releases as they land.

What you are paying for is the convenience and the ongoing work — **not**
exclusivity. OmniBlock is GPL-3.0-or-later: everyone who receives a build
receives the source with it, along with every freedom that licence grants.
[LICENSING.md](LICENSING.md) explains exactly what that means.

If you cannot afford to give anything, that is genuinely fine — say so and you
will get a copy anyway.

**Installation takes about a minute:** [INSTALLATION.md](INSTALLATION.md).

> **Note:** this repository is the showcase, not the delivery mechanism. It
> deliberately contains no source code and no builds — those go directly to
> supporters, with the complete source alongside every build, as the GPL
> requires.

## Documentation

| | |
|---|---|
| [Installation](INSTALLATION.md) | Install the packaged extension in Chrome or Firefox |
| [Privacy](PRIVACY.md) | Local data, network requests and telemetry boundaries |
| [FAQ](FAQ.md) | Common installation, filtering and browser questions |
| [Support](SUPPORT.md) | Useful reports, privacy redaction and contact routes |
| [Security](SECURITY.md) | Private vulnerability reporting |
| [Contributing](CONTRIBUTING.md) | Documentation and reproducible-report scope |
| [Changelog](CHANGELOG.md) | Release history |
| [Licensing](LICENSING.md) | GPL terms, distribution and source availability |
| [Third-party notices](THIRD-PARTY-NOTICES.md) | Upstream engines, lists and licences |

## The OmniVex suite

OmniBlock is one of a family of tools sharing a design language and a philosophy
— modern, fast, privacy-respecting, no telemetry:

**OmniTheme** · **OmniBlock** · **OmniCleaner** · **OmniAPO** · **OmniEQ** · **OmniPlay** · **OmniScale** · **OmniShade** · **OmniVisuals** · **OmniGPU** · **OmniWrappers**

<sub>**OmniWrappers** is four Direct3D compatibility installers — OmniDXVK, OmniDxWrapper, OmniVKD3D and OmniVoodoo2.</sub>

<sub>Tuned for framerate, mixed for headroom, sharp to the pixel. Donationware
tools for gamers and audiophiles — audio, graphics, and a bit of privacy too.</sub>

More at [github.com/TheOmniGrid](https://github.com/TheOmniGrid).

---

## Credit

OmniBlock stands on the filter lists and blocking engine maintained by others.

It bundles **[uBlock Origin's uAssets](https://github.com/uBlockOrigin/uAssets)** filter
rules and scriptlet/redirect resources (GPL-3.0), **EasyList** and **EasyPrivacy**
(GPL-3.0-or-later, dual CC BY-SA 3.0+), **Fanboy's Cookie Monster / EasyList Cookie List**
(CC BY 3.0), and **[HaGeZi's DNS Blocklists](https://github.com/hagezi/dns-blocklists)**
(GPL-3.0). Bundling GPL-3.0 rules and data into the package this way is what makes the
combined work GPL-3.0 as a whole.

Matching is done by **[Ghostery's adblocker engine](https://github.com/ghostery/adblocker)**
(MPL-2.0), alongside `tldts` (MIT), `webextension-polyfill` (MPL-2.0) and Svelte (MIT).

Full attribution in [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

**Licensing at a glance:** the software is GPL-3.0-or-later — you get the source, and you
may study, modify and share it. The name, logo and OmniVex identity are not covered by that
licence; fork the code freely, but give the fork its own name.
[LICENSING.md](LICENSING.md) · [TRADEMARK.md](TRADEMARK.md)

---

## Contact

Use public channels only for information that is safe to share. Remove usernames, local paths,
account identifiers, licence data, and other personal information from screenshots and logs.

| Channel | Use |
|---|---|
| [GitHub Issues](../../issues/new/choose) | Reproducible bugs, compatibility reports, and documentation corrections |
| [GitHub Discussions](../../discussions) | Questions, ideas, and community support |
| [Security](SECURITY.md) | Private vulnerability reporting — never use a public issue |
| [Email](mailto:omnivex@theomnigrid.biz) | Private support, delivery, or licensing questions |

Support is best-effort. See [SUPPORT.md](SUPPORT.md) and [CONTRIBUTING.md](CONTRIBUTING.md)
for repository scope and reporting guidance.

---

<p align="center">
  <strong>OmniBlock</strong><br>
  <a href="https://github.com/TheOmniGrid">The OmniGrid on GitHub</a> ·
  <a href="https://ko-fi.com/theomnigrid">Ko-fi</a> ·
  <a href="https://www.patreon.com/TheOmniGrid">Patreon</a><br><br>
  <sub>Copyright © 2026 OmniVex · GPL-3.0-or-later · <a href="LICENSING.md">Legal &amp; licensing</a></sub><br>
  <sub>The OmniVex name and logo are not covered by the GPL licence.</sub>
</p>
