# Licensing

This page explains, in plain language, what you may do with OmniBlock. The
binding text is the [GNU General Public License, version 3](https://www.gnu.org/licenses/gpl-3.0.en.html)
or any later version, a copy of which is included with every build.

## The short version

**OmniBlock is free software.** Not free of charge — free as in you own what you
receive. If you have a copy, you may use it for anything, study how it works,
change it, and pass it on.

**OmniBlock is also donationware.** It is not on any extension store, and the
only way to get a build is from the people who make it, through Ko-fi or Patreon.

Those two facts are not in conflict, and it is worth being precise about why.

## Why OmniBlock is GPL

This is a deliberate choice, not an accident of copying a licence file.

OmniBlock bundles two kinds of GPL-licensed material:

- **uBlock Origin's scriptlet library**, which is what makes `##+js(...)` rules
  actually run. Without it, anti-adblock defences and a large class of
  annoyance filters simply do not work.
- **Filter rules from uAssets and HaGeZi**, compiled directly into the extension
  package rather than fetched at runtime.

Bundling GPL-3.0 code and data this way makes the combined work GPL-3.0 as a
whole. The alternative — dropping scriptlet support and the affected lists —
would leave a visibly worse blocker. That trade was considered and rejected.
It is the same trade uBlock Origin itself makes.

## What this means if you support the project

You receive the packaged build **and** the complete corresponding source, as the
licence requires. Concretely, you may:

- Install it on as many of your own machines as you like.
- Read the source and satisfy yourself that the privacy claims are true.
- Modify it for your own use.
- Give copies to other people, including for free.

You do **not** owe anyone permission to do these things, and nothing you agree to
when donating takes them away. If any statement anywhere — on Patreon, on Ko-fi,
or in this repository — appears to contradict the GPL, **the GPL wins**.

## Then what is the donation for?

For the work, and for the convenience.

Building OmniBlock yourself is possible and documented. It means installing the
toolchain, compiling the rulesets from fourteen upstream sources, producing both
browser targets, and getting the Firefox build signed. Supporting the project
means someone else has already done all of that, keeps doing it as the lists and
the browsers change, and answers you when something breaks.

That is what is being sold: **time and continuity, not permission.**

## What is not covered by the GPL

The GPL covers the software. It does not cover names and logos.

The name **OmniBlock**, the shield mark, the **OmniVex** identity, and the
associated visual design are not licensed to you by the GPL. You may fork the
code freely — but a fork must carry its own name and its own icon.

This is a normal and widely used arrangement. Mozilla does it with Firefox;
that is why Debian once shipped the same browser as Iceweasel. It exists so that
"OmniBlock" continues to mean the thing this project ships, and so that a
modified build cannot be mistaken for it. It restricts branding, never code.

Details: [TRADEMARK.md](TRADEMARK.md).

## A request, not a restriction

Because OmniBlock is GPL, nothing stops you from taking a build you received and
republishing it for free. That is your right and it will not be contested.

The project simply asks that you do not — not because it would be unlawful, but
because donationware only works while the people who benefit from it choose to
support it. If OmniBlock is worth using, it is worth keeping alive.

If you cannot afford to contribute, ask. You will get a copy. That is a better
outcome for everyone than a silent mirror.

## Third-party material

OmniBlock stands on filter lists and libraries maintained by other people, under
their own licences — EasyList, EasyPrivacy, Fanboy's lists, uAssets, HaGeZi's
DNS blocklists, and the Ghostery matching engine among them.

Every one of them is credited, with its licence, in
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md). If you redistribute OmniBlock,
those notices must travel with it.

## No warranty

OmniBlock is provided without warranty of any kind, as set out in sections 15
and 16 of the GPL. It is a content blocker, not a security product in the sense
of an antivirus: the Security Shield reduces exposure to known malicious domains,
it does not make you safe.

## A note on this document

This page is written to be understood, not to be airtight in court. It is a
summary of the GPL's effect and the project's intentions — it is not legal
advice, and it does not replace the licence text. If you are relying on the
details for anything consequential, read
[the licence itself](https://www.gnu.org/licenses/gpl-3.0.en.html), and if you
are the project maintainer publishing this commercially, have a lawyer in your
own jurisdiction review the arrangement before you launch.
