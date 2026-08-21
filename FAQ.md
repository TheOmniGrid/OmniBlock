# Frequently asked questions

Short, direct answers. If your question isn't here, [open an
issue](https://github.com/TheOmniGrid/OmniBlock/issues/new/choose).

## Why isn't this on the stores?

OmniBlock is donationware, not store-ware. The Chrome Web Store and
addons.mozilla.org exist to distribute software for free; asking people to
pay somewhere else for something the store hands out at no cost doesn't
work as a model. So builds go directly to supporters instead, through
Ko-fi or Patreon, and installation takes one extra step: "Load unpacked"
on Chromium, an `.xpi` on Firefox once signing is in place. See
[INSTALLATION.md](INSTALLATION.md).

## Is it really free software if I donate for it?

Yes. OmniBlock is GPL-3.0-or-later. Anyone who has a copy — donor or not —
gets the full source and every right the GPL grants: use it, study it,
modify it, share it. The donation buys convenience and continuity, not
permission. Nothing you agree to when supporting the project takes those
rights away, and if anything anywhere ever contradicts that, the GPL wins.
Full detail: [LICENSING.md](LICENSING.md).

## Can I share my copy?

Yes — the GPL guarantees it, and doing so will not be contested. The
project simply asks that you don't, because donationware only works while
the people who benefit from it choose to support it. If you can't afford
to contribute, ask instead of quietly passing a copy around. You'll get
one.

## How is it different from uBlock Origin?

On **Chromium**, no Manifest V3 extension — OmniBlock included — can match
what MV2-era uBlock Origin could do, because Chrome removed the API that
made its dynamic filtering possible. OmniBlock's real competitors there
are uBO Lite and ABP, and it aims to beat both on filter-list depth,
protection-level ergonomics, and per-site control, while running with zero
JavaScript in the request path.

On **Firefox**, OmniBlock uses full request blocking, same as uBO does,
and plays in uBO's own league.

On top of that, OmniBlock adds six protection levels instead of an on/off
switch, an independent always-on Security Shield, and one interface across
five languages. It doesn't claim to beat uBlock Origin everywhere, because
on Chromium that would not be true — see "Positioning, honestly" in the
[README](README.md).

## Does it slow my browser?

No, by construction. On Chromium, OmniBlock runs no JavaScript in the
request path at all — blocking is handled by the browser's own native
filtering engine from precompiled rulesets. On Firefox, it uses a
benchmarked matching engine over full request blocking.

Engine memory, deserialize time, cosmetic-pass cost and package size are
measured against the real filter lists on a weekly job; three of them —
engine size, deserialize time and packaged output size — are hard
thresholds that fail that job if they regress. Two budgets that need a
real browser profile, popup open time and cold-start engine load, are
not yet measured; the harness says so rather than pretending otherwise.

## What data do you collect?

None. No telemetry, no analytics, no crash reporting, no accounts, no
servers of OmniBlock's own. Network contact is limited to three things:
the filter-list hosts, any custom list URL you add yourself, and the
extension's own packaged files. Statistics are computed and stored only on
your machine.

That isn't a policy that could quietly change — it's structural. There is
no server for data to go to, and no code path that sends anything
anywhere. Full detail: [PRIVACY.md](PRIVACY.md).

## Does it work on mobile?

Not officially, and it hasn't been tested there. Chrome for Android
doesn't support desktop-style extensions at all; Edge and Brave on Android
support only a small, separate set. Firefox for Android can technically
install a signed self-distributed add-on from a file, but OmniBlock has
not been verified on it, so treat it as unsupported until that changes.

## What if a site breaks?

Start with **per-site trust** — one click in the popup — since it's
scoped to exactly the site that's broken and leaves every other site
untouched. If that isn't enough, drop the protection level; level 1 is
close to ad-blocking alone. The **element picker** is for hiding things
you don't want to see, not for fixing breakage — reach for it only after
the site works again.

## How do I add my own lists?

Dashboard → Lists → **Add custom list**, then paste a URL in adblock or
hosts syntax. Subscribed lists refresh automatically, with the previous
good copy kept if a refresh ever fails.

Two limits worth knowing before you rely on a large list: each subscribed
list is capped at 50,000 domains, and the dashboard tells you when a list
was truncated. On Chromium, only domain-style rules (`||example.com^`)
and cosmetic rules from a subscribed list take effect — rules carrying
options or paths need Firefox's engine, which has no such restriction. If you'd rather write rules
yourself, use **My Filters** — a free-text editor with uBO-style syntax,
validated line by line as you type.

## Is my configuration portable?

Yes. Dashboard → Settings → **Export** writes your whole configuration —
protection level, trusted sites, custom list subscriptions, My Filters —
to a single JSON file. **Import** it on another machine or browser to
bring it all back. Nothing syncs automatically, because there's no server
to sync through; export/import is the whole mechanism, by design.

## What happens if the project stops?

The GPL means the source doesn't stop existing along with the project —
anyone who has a copy keeps every right to it, including the right to fork
it under a new name and icon (see [TRADEMARK.md](TRADEMARK.md)).
Subscribed filter lists keep updating from their own upstream hosts
independent of OmniBlock's own maintenance. What would stall is the
compiled rulesets and the scriptlet library bundled into new releases —
without active maintenance, those age rather than vanish. There's no
guarantee beyond what the license already gives you, and nothing here
promises otherwise.
