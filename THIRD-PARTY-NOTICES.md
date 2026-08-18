# Third-party notices

OmniBlock stands on filter lists and libraries maintained by other people,
under their own licenses. This file credits every one of them. If you
redistribute OmniBlock, this file must travel with it — see
[LICENSING.md](LICENSING.md).

Each entry below was checked against the upstream project's own license
declaration, not assumed from reputation or a third-party summary — one
entry in an earlier draft of this list was wrong for exactly that reason
and had to be corrected (HaGeZi's DNS blocklists, noted below).

## Filter lists and rule data

| Component | License | Source |
|---|---|---|
| EasyList / EasyPrivacy | GPL-3.0-or-later, dual-licensed with CC BY-SA 3.0 (or later) | [easylist.to](https://easylist.to) |
| Fanboy's Cookie Monster list | Part of the EasyList family; same licensing as above | [secure.fanboy.co.nz](https://secure.fanboy.co.nz) |
| uBlock Origin's `uAssets` filter lists | GPL-3.0 | [github.com/uBlockOrigin/uAssets](https://github.com/uBlockOrigin/uAssets) |
| uBlock Origin's scriptlet and redirect resource library | GPL-3.0 | Obtained via a pinned commit of the `@ghostery/adblocker` project's own packaged mirror of uBlock Origin's resources; see [github.com/gorhill/uBlock](https://github.com/gorhill/uBlock) for the original |
| HaGeZi's DNS Blocklists | GPL-3.0 | [github.com/hagezi/dns-blocklists](https://github.com/hagezi/dns-blocklists), verified directly against the repository's own `LICENSE` file — some third-party summaries of this project describe it as CC BY-NC-SA, which does not match what the repository itself declares |

OmniBlock fetches, parses, and enforces this data — it never modifies or
redistributes the upstream lists on its own. `trusted-*` scriptlets from
uBlock Origin's resource library are deliberately stripped before
packaging; see [SECURITY.md](SECURITY.md) for why.

## Software components

| Package | License | Source |
|---|---|---|
| `@ghostery/adblocker`, `@ghostery/adblocker-webextension` | MPL-2.0 | [github.com/ghostery/adblocker](https://github.com/ghostery/adblocker) |
| `tldts` (and `tldts-core`, `tldts-experimental`) | MIT | [github.com/remusao/tldts](https://github.com/remusao/tldts) |

`@ghostery/adblocker` is the matching engine behind OmniBlock's Firefox
build and its Chromium cosmetic-filtering path. The `tldts` family handles
domain parsing for both.

## Why OmniBlock itself is GPL-3.0-or-later

OmniBlock bundles GPL-3.0 filter rules (uAssets, HaGeZi) and GPL-3.0
scriptlet resources directly into the extension package rather than
fetching them at runtime, and ships uBlock Origin's scriptlet library so
that `##+js(...)` rules actually run. Bundling GPL-3.0 code and data this
way makes the combined work GPL-3.0 as a whole. Full explanation:
[LICENSING.md](LICENSING.md).

## Corrections

If any license attribution here is wrong or has changed upstream, please
[open an issue](../../issues/new/choose) or email
**andre.hetzl@gmail.com** — this file is only as good as its last
verification, and getting it right matters more than getting it fast.
