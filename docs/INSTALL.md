# Installing OmniBlock

OmniBlock is not on the Chrome Web Store or on addons.mozilla.org — see
["Why isn't this on the stores?"](FAQ.md#why-isnt-this-on-the-stores) if you
want the reasoning. Supporters get a packaged, ready-to-install build
directly: a `.zip` for Chromium browsers and an `.xpi` for Firefox (see the
signing-status note below). Installing either takes about a minute.

Haven't got a build yet? See [Get OmniBlock](../README.md#get-omniblock) in
the main README.

## Chromium — Chrome, Edge, Brave, Vivaldi, Opera

This is the supported install route on Chromium, not a workaround. Because
OmniBlock isn't on the Web Store, "Load unpacked" through Developer mode is
how every Chromium install works — including the maintainer's own.

1. **Unzip** the build you received (something like
   `omniblock-0.12.0-chrome.zip`) into a folder you intend to keep. Don't
   extract it somewhere temporary — the folder's location is part of how
   Chrome identifies the extension (see "Updating" below).
2. Open `chrome://extensions` — `edge://extensions` on Edge,
   `brave://extensions` on Brave, `vivaldi://extensions` on Vivaldi,
   `opera://extensions` on Opera.
3. Turn on **Developer mode**, top right corner of the page.
4. Click **Load unpacked** and select the folder you unzipped — the one
   that directly contains `manifest.json`, not a parent folder.
5. OmniBlock appears in your extensions list, and its shield icon appears
   in the toolbar. Pin it via the puzzle-piece icon if it doesn't show up
   there automatically.

**About the developer-mode notice.** Chromium browsers may show a notice
about developer-mode extensions while Developer mode is on. That's
expected, not a sign anything is wrong — it's the same notice Chrome shows
for any unpacked extension, including ones under active development
elsewhere on your machine. It doesn't mean OmniBlock is unsafe; it means
Chrome can't vouch for it the way it vouches for a Web Store listing,
because there is no Web Store listing.

### Updating (Chromium)

1. Unzip the new release **over the same folder** you used originally.
2. Go to `chrome://extensions` and click the circular **reload** icon on
   OmniBlock's card.

Chrome derives an unpacked extension's identity from the absolute path of
its folder. As long as that folder stays put, reloading picks up the new
version and keeps every setting — protection level, trusted sites, custom
lists, My Filters. If you extract a new release into a *different* folder
instead, Chrome treats it as an unrelated extension with no memory of your
settings; use **Export**/**Import** on the dashboard's Settings page to
carry your configuration across (see
["Is my configuration portable?"](FAQ.md#is-my-configuration-portable) in
the FAQ).

## Firefox

Firefox requires add-ons to be signed by Mozilla. OmniBlock uses **unlisted
(self-distribution) signing** — the same signing pipeline Mozilla uses for
add-ons listed on addons.mozilla.org, just without a public listing. Once a
build is signed, the `.xpi` installs in ordinary release Firefox exactly like
any add-on from the store: no developer mode, no flag to flip, no separate
Firefox channel. This is verified against Mozilla's own Extension Workshop
documentation on self-distribution and signing.

> **Signing status.** Signing is not yet set up. Until it is, the Firefox build
> ships unsigned and installs only in Firefox Developer Edition, Nightly or ESR,
> with `xpinstall.signatures.required` set to `false` in `about:config`. Check
> what you received: an `.xpi` is signed, a `.zip` is not yet.

Requires Firefox 128 or later.

1. **Download** the `.xpi` you received (e.g. `omniblock-0.12.0-firefox.xpi`)
   and save it somewhere you can find it.
2. In Firefox, open the menu and go to **Add-ons and themes** (or open
   `about:addons` directly).
3. Click the **gear icon**, then **Install Add-on From File…**.
4. Browse to the `.xpi` you downloaded and open it.
5. Firefox shows a permissions prompt. Click **Add**.

OmniBlock now appears under **Extensions** in the Add-ons Manager, and its
icon appears in the toolbar.

**A note on unsigned builds.** If you ever end up with an *unsigned* `.xpi`
— from building OmniBlock from source yourself, for instance — it will
only install in Firefox Developer Edition, Nightly, or ESR, and only after
flipping `xpinstall.signatures.required` to `false` in `about:config`.
That is **not** the route supporters need: the `.xpi` you receive is
already signed and installs in ordinary release Firefox with no
configuration changes at all. If normal Firefox refuses your file with a
"could not be verified" error, you most likely have an unsigned build or a
corrupted download — re-download rather than reaching for the signature
flag.

### Updating (Firefox)

Repeat the install steps above with the new `.xpi`. Firefox recognizes the
same add-on ID and updates OmniBlock in place — your settings carry over.

## Verifying the install worked

Click the shield icon in your toolbar. You should see the OmniBlock popup:
your current protection level and the Security Shield toggle.

Now visit a page with ads or trackers. On **Chromium**, a number appears on
the toolbar icon itself — that is the browser's own count of what OmniBlock
blocked on this page, and it climbs within a second or two. The popup's
"This page" tile shows an em dash there, because Chromium does not hand
per-request detail to extensions without a permission OmniBlock declines to
request. On **Firefox**, that same count also appears inside the popup.

## Where the dashboard lives

Click **Open Dashboard** inside the popup, or right-click the toolbar icon
and choose the extension's **Options** (Chromium) or
**Manage Extension → Extension Options** (Firefox). The dashboard is where
protection levels, custom lists, My Filters, statistics, and settings all
live — the popup is deliberately minimal.

## Uninstalling

- **Chromium:** right-click the toolbar icon and choose
  **Remove from [browser]**, or remove it from `chrome://extensions`.
- **Firefox:** open `about:addons` → **Extensions**, find OmniBlock, and
  choose **Remove**.

Uninstalling deletes OmniBlock's local storage — settings, statistics,
cached lists — along with it. Export your configuration first (dashboard →
Settings → Export) if you might want it back.

## Troubleshooting

**"Load unpacked" is greyed out.** Developer mode is off — turn it on
first (top right of `chrome://extensions`).

**Chrome disabled OmniBlock after a restart or profile sync.** The
unzipped folder was moved, renamed, or deleted. Re-extract the build
somewhere permanent and load it again.

**Firefox says the file "could not be verified" or "appears to be
corrupt."** You most likely have a partial download or an unsigned build.
Re-download the `.xpi` and try again.

**The popup opens but looks blank or stuck.** Click the reload icon for
OmniBlock on the extensions page and try again. If that doesn't help,
remove and reinstall — your settings survive as long as you haven't
cleared browsing data for the extension in between.

**A site is broken.** That's a filtering side effect, not necessarily a
bug — see
["What if a site breaks?"](FAQ.md#what-if-a-site-breaks) in the FAQ before
anything else: lower the protection level, or trust the site from the
popup.

**Still stuck?** [Open an issue](../../../issues/new/choose) with your
browser, browser version, and OmniBlock version — the bug report template
asks for exactly what's useful here.
