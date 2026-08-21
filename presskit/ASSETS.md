# Brand assets — what goes where

Every image in `../assets/` and the slot it was sized for. All of them are
rendered from the product's own icon geometry and the README's own numbers,
so they stay in step with what the software actually does.

## Platform slots

| File | Size | Use it for |
|---|---|---|
| `avatar-512.png` | 512×512 | Ko-fi profile picture, Patreon avatar, GitHub org avatar, Discord icon |
| `kofi-cover.png` | 1200×300 | Ko-fi page cover banner |
| `patreon-cover.png` | 1600×400 | Patreon page cover banner |
| `social-preview.png` | 1280×640 | GitHub **Settings → Social preview** (must be uploaded by hand — GitHub has no API for it), and as the link-preview card anywhere else |
| `banner-1400x560.png` | 1400×560 | Wide hero banner — README top, blog posts, forum headers |
| `tile-440x280.png` | 440×280 | Compact promo tile where a squarer crop is wanted |
| `icon-128.png` | 128×128 | Small inline logo |

## In-page graphics

| File | Size | Shows |
|---|---|---|
| `stats-strip.png` | 1400×190 | The four headline numbers |
| `feature-grid.png` | 1400×712 | Six features as cards |
| `levels.png` | 1400×660 | The six protection levels and the domain count at each |
| `engines.png` | 1400×600 | Chromium vs Firefox, and the honest positioning |
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

The generator is **not in this repository**. It lives in the source repo,
because this one deliberately ships no code:

```
pnpm brand          # rewrites every graphic above into ../OmniBlock-Public/assets/
pnpm screenshots    # re-captures the screenshots from a real build
```

The numbers baked into `stats-strip.png` and `levels.png` come from a single
`FACTS` block in that generator, mirroring the table in [the README](../README.md).
If the upstream filter lists move, change both together — otherwise the
graphics start making claims the software no longer backs.
