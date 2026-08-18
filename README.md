<div align="center">

<img src="assets/icon-128.png" width="96" alt="OmniBlock">

# OmniBlock

**A cleaner web. Two browsers. No telemetry.**

A content blocker for Chromium and Firefox — six protection levels, an always-on
security shield, custom lists, and per-site control.
Part of the [OmniVex](#the-omnivex-suite) suite.

![Version](https://img.shields.io/badge/version-0.12.0-3B82F6?style=flat-square)
![License](https://img.shields.io/badge/license-GPL--3.0--or--later-3B82F6?style=flat-square)
![Browsers](https://img.shields.io/badge/browsers-Chromium%20%C2%B7%20Firefox-3B82F6?style=flat-square)
![Languages](https://img.shields.io/badge/languages-EN%20DE%20ES%20FR%20RO-3B82F6?style=flat-square)
![Telemetry](https://img.shields.io/badge/telemetry-none-4ADE80?style=flat-square)

[**Get OmniBlock**](#get-omniblock) · [Features](#what-it-does) · [Install](docs/INSTALL.md) · [FAQ](docs/FAQ.md) · [Changelog](CHANGELOG.md)

</div>

---

<div align="center">
<img src="assets/screenshots/popup-hero.png" width="340" alt="The OmniBlock popup">
</div>

## What it does

OmniBlock blocks **660,916 domains** out of the box and **761,672** at its
highest level — ads, trackers, malware, phishing, scam and fake-shop domains,
compiled from fourteen maintained filter sources.

It is built around one idea: blocking should be something you *tune*, not
something you fight. One dial, six levels, and a security shield that stays on
even when you turn everything else off.

### Six protection levels

| Level | | What it blocks | Domains |
|---|---|---|---:|
| 0 | **Off** | Blocking disabled — the shield stays on | 389,588 |
| 1 | **Light** | Ads only, maximum compatibility | 474,518 |
| 2 | **Balanced** | Ads, trackers and privacy — the default | 660,916 |
| 3 | **Strict** | Adds annoyances and cookie banners | 705,714 |
| 4 | **Aggressive** | Broader blocking, some sites may need trusting | 731,466 |
| 5 | **Fortress** | Maximum blocking — expect breakage | 761,672 |

### The Security Shield

Malware, phishing, scam and fake-shop domains are handled on a **separate,
always-on axis** — including at level 0. Turning ads down should never turn
phishing protection off. That is a deliberate design decision, not a default
you have to remember to set.

### Everything else

- **Per-site trust** — one click in the popup, and the site is left alone.
- **Element picker** — point at anything on a page and hide it for good.
- **Custom lists** — subscribe to any filter list by URL, in adblock or hosts syntax.
- **My Filters** — write your own rules, validated line by line as you type.
- **Statistics** — computed and stored **only on your machine**. On Firefox that includes a 30-day history and your most-blocked domains; on Chromium the browser keeps per-request detail to itself unless an extension asks for an extra permission, which OmniBlock deliberately does not, so you get totals and the live count on the toolbar badge.
- **Import / export** — your whole configuration as a single JSON file.
- **Five languages** — see below.
- **A dark, deliberate interface** — part of the OmniVex design language, not a template.

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
</table>

## Fast by construction

On Chromium, OmniBlock runs **no JavaScript in the request path at all**. Blocking
is handled by the browser's own native filtering engine from precompiled rulesets,
which is why it cannot slow your browsing the way a callback-based blocker can.

On Firefox, it uses full request blocking with the Ghostery matching engine —
unlimited rules and live list updates.

Both paths ship with measured budgets rather than promises: engine memory, cache
growth, cold-start time and per-navigation cost are benchmarked, and the build
fails if they regress.

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

## Privacy by construction

**No telemetry. No analytics. No accounts. No servers.**

OmniBlock contacts exactly three kinds of address, and nothing else:

1. The filter-list hosts, to download public block lists.
2. Any custom list URL **you** add yourself.
3. Its own packaged files inside the extension.

Your browsing history never leaves your machine, because nothing ever sends it
anywhere. Statistics are computed and stored locally. There is no opt-out,
because there is nothing to opt out of.

Full detail: [Privacy Policy](docs/PRIVACY.md).

## Five languages

English, Deutsch, Español, Français and Română — the complete interface, not just
the menus. OmniBlock follows your browser's language automatically, and you can
override it at any time in the settings.

## Get OmniBlock

OmniBlock is **donationware**. It is not on the Chrome Web Store or on
addons.mozilla.org, and it is not sold. It is supported by the people who use it.

<div align="center">

### [☕ Support on Ko-fi](KOFI_LINK) · [★ Become a patron](PATREON_LINK)

</div>

Supporters get the packaged, ready-to-install build for both browsers, the
complete source, and new releases as they land.

What you are paying for is the convenience and the ongoing work — **not**
exclusivity. OmniBlock is GPL-3.0-or-later: everyone who receives a build
receives the source with it, along with every freedom that licence grants.
[LICENSING.md](LICENSING.md) explains exactly what that means.

If you cannot afford to give anything, that is genuinely fine — say so and you
will get a copy anyway.

**Installation takes about a minute:** [docs/INSTALL.md](docs/INSTALL.md).

## The OmniVex suite

OmniBlock is one of a family of tools sharing a design language and a philosophy
— modern, fast, privacy-respecting, no telemetry:

**OmniTheme** · **OmniBlock** · **OmniAPO** · **OmniEQ** · **OmniPlay** · **OmniScale** · **OmniShade**

## Support and bugs

Found something broken? [Open an issue](../../issues/new/choose) — bug reports
are welcome from everyone, supporter or not.

Security vulnerabilities: read [SECURITY.md](SECURITY.md) first; please do not
open a public issue for those.

## Licensing at a glance

- **The software** is GPL-3.0-or-later. You get the source, and you may study, modify and share it.
- **The name, logo and OmniVex identity** are not covered by that licence. Fork the code freely; give the fork its own name.

Full text: [LICENSING.md](LICENSING.md) · [TRADEMARK.md](TRADEMARK.md) · [Third-party notices](THIRD-PARTY-NOTICES.md)

---

<div align="center">
<sub>Built by <b>OmniVex</b> · No telemetry, no tracking, no compromise</sub>
</div>
