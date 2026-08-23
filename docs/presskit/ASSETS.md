# Brand assets — what goes where

Every image in `../../assets/` and the slot it was sized for. All of them are
rendered from the product's own icon geometry and the README's own numbers,
so they stay in step with what the software actually does.

## Platform slots

| File | Size | Use it for |
|---|---|---|
| `avatar-512.png` | 512×512 | Ko-fi profile picture, Patreon avatar, GitHub org avatar, Discord icon |
| `kofi-cover.png` | 1200×300 | Ko-fi page cover banner |
| `patreon-cover.png` | 1600×400 | Patreon page cover banner |
| `social-preview.png` | 1280×640 | GitHub **Settings → Social preview** (must be uploaded by hand — GitHub has no API for it), and as the link-preview card anywhere else |
| `banner-animated.gif` | 1600×500 | **The README hero.** Looping. Hand-managed — not produced by the generator; the README cache-busts it with a `?v=` query, so bump that when it changes |
| `banner-1600x500.png` | 1600×500 | Static version of the hero, for anywhere animation is unwanted or unsupported. Hand-managed, same as above |
| `banner-1400x560.png` | 1400×560 | Older wide hero — blog posts, forum headers |
| `tile-440x280.png` | 440×280 | Compact promo tile where a squarer crop is wanted |
| `icon-128.png` | 128×128 | Small inline logo |

## In-page graphics

| File | Size | Shows |
|---|---|---|
| `presentation/metrics.png` | 1600×270 | The four headline numbers |
| `presentation/capabilities.png` | 1600×720 | Six core capabilities in the shared OmniVex presentation system |
| `presentation/levels.png` | 1600×520 | The six protection levels and the domain count at each |
| `presentation/engines.png` | 1600×540 | Chromium vs Firefox, and the honest positioning |
| `support-patreon.svg` | 520×116 | **The donation button.** Vector, used in the README at `height="64"`. Same construction OmniShade ships, so the suite reads as one family |
| `support-kofi.svg` | 520×116 | As above, Ko-fi |
| `btn-kofi.png` | 440×104 | Raster fallback, for donation platforms that will not accept an SVG upload |
| `btn-patreon.png` | 440×104 | Raster fallback, as above |

## Screenshots

`assets/screenshots/` holds ten captures from a real build at 2560px wide
(popups at 680px). They are produced by the capture harness in the source
repository, not hand-edited — a UI change makes them stale, so re-run it and
re-sync rather than touching them.

<sub>The two `support-*.svg` buttons deliberately keep each platform’s OWN brand colour — Patreon coral, Ko-fi cyan — rather than the OmniVex violet. They are other people’s marks; recolouring them would misrepresent them.</sub>

## Regenerating

Two kinds of asset live here, and the difference matters:

- **Generator-owned** — `social-preview.png`, `avatar-512.png`, `kofi-cover.png`,
  `patreon-cover.png`, `btn-*.png`, `support-*.svg`. Rendered by a generator in
  the source repository (this one deliberately ships no code), into a local
  folder there. `pnpm brand --sync` copies exactly this list across. Anything
  else is never touched from there.
- **Hand-managed** — the two banners and everything under `presentation/`.
  Edited directly in this repository. The generator does not know about them
  and will not overwrite them.

Screenshots are a third thing -- see the section above.
