# Cartridge templates for Unraid

Unraid Community Applications templates for [Cartridge](https://github.com/BlizzHacker),
a set of tools for self-hosting a retro game library.

```
Move Weight
└─ Yarr.It ................ one front door for a self-hosted media library
   └─ Cartridge ........... you are here
      └─ ROMarr ........... the *arr for games: request it, get it, file it
         └─ ROM Hub ....... ROMarr's plugin factory
```

Each layer stands alone. These templates need nothing above them.

Unofficial. Not affiliated with RomM, Gaseous, Retrom or Lime Technology.

## What is listed here

| Template | What it is |
| --- | --- |
| [`templates/romarr.xml`](templates/romarr.xml) | **ROMarr** — the *arr for games. Request a title, ROMarr searches your indexers through Prowlarr, grabs the winner, and files the ROM into RomM, Gaseous, Retrom or a plain folder. |

Not every Cartridge project belongs in Community Applications. **ROM Hub** is
ROMarr's plugin layer and ships as a command-line tool with no web interface, so
a container listing would install something with nothing to click; it lives at
[BlizzHacker/rom-hub](https://github.com/BlizzHacker/rom-hub) instead.
**Cartridge for Xbox**, **Cartridge for Roku** and the **stream server** are
client apps rather than server containers.

## Installing

Search for **ROMarr** in Community Applications. Nothing here needs to be
cloned by hand.

## Three things that catch people out

These are in the template's own description too, but they are the entire
support load, so they are worth repeating.

**ROMarr reads its variables once.** On first start it copies them into its own
settings, and from then on the saved settings win — editing the variables in
this template does nothing. That is deliberate, and it is what lets you change
things on the Settings page without the template overriding you every restart,
but it is the opposite of how most Unraid containers behave. Get the values
right the first time; change them later on ROMarr's Settings page.

**The completed-downloads path must match what your client reports**, character
for character. ROMarr asks the download client where a finished download is and
then opens that path itself, so if qBittorrent says `/data/completed`, ROMarr
has to see `/data/completed`. Where they cannot be made to agree, add a remap
under Settings → Media Management.

**The WebUI is on port 6868.** ROMarr used to default to 7878, which is
Radarr's port — a guaranteed collision, since anyone running ROMarr is running
Radarr. Upstream moved to 6868 in v0.7.0, in the gap the \*arr family left
between Bazarr (6767) and Whisparr (6969), so host and container agree again
and there is no offset to remember.

## Adding a template

One XML file per app in `templates/`, `<Container version="2">`, and a
`<TemplateURL>` pointing at its own raw URL. `ca_profile.xml` is the Cartridge
maintainer profile and covers the whole repository, so a new app does not need
a new profile or a new repository.

After any change, re-run the scan at
[ca.unraid.net/submit](https://ca.unraid.net/submit) — that scanner, not this
README, is the authority on whether a template is valid.

## Support

GitHub issues on the project the template installs
([ROMarr](https://github.com/BlizzHacker/romarr/issues)). Problems with the
template itself — wrong default, bad path, broken icon — belong
[here](https://github.com/BlizzHacker/cartridge-unraid/issues).

## Licence

MIT, matching the projects it packages.
