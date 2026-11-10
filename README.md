# Free Kodi Setup - vSeeBox 6 Plus

A curated, free and legal Kodi setup: live TV with a real channel guide, plus on-demand movies and shows. No paid accounts, no debrid services.

Everything installs from add-ons maintained by their own authors. This repo is a guide and configuration kit - it does not re-host anyone's add-ons, so your add-ons keep auto-updating from their official sources. Nothing runs on (or streams from) a computer you own: video comes straight from each service to your box, and this kit itself lives on GitHub.

**About the recommendations:** each add-on below is present in its repository today and its capabilities come from the add-on author's own current documentation (the SlyGuy add-ons are actively maintained code). That is documented capability, not a playback test - the final check happens on your box as you install each one.

---

## Step 1 - Install or update Kodi

- Easiest: install **Kodi** from the Google Play Store on the box - it automatically picks the right build.
- Or sideload from [https://kodi.tv/download/android](https://kodi.tv/download/android) (offers ARMV7A 32-bit and ARMV8A 64-bit APKs; the Play Store route avoids having to know which your box needs).

This guide targets **Kodi 21 "Omega"** (current stable, v21.3 per kodi.tv). The in-app repository automatically serves the right add-on versions.

## Step 2 - Free TV Hub (the included installer/menu add-on)

This kit includes **Free TV Hub** (`plugin.program.freetvhub-0.2.0.zip`), a small custom add-on written for this setup - it contains no third-party code and no content. Install it first: **Add-ons > Install from zip file** and pick the zip (Kodi will ask you to allow unknown sources once). Then open it from **Add-ons > Program add-ons**:

- **Step 1** downloads the SlyGuy repository zip from the author's site and opens the installer for you.
- **Step 2** installs all the recommended add-ons from their own repositories (Kodi resolves dependencies and keeps them auto-updated from the original sources).
- After that, the hub shows simple entries: **Live TV guide**, **Live TV channels**, each service, **Search movies and shows**, and **Trakt: sign in and settings** (Trakt sign-in happens on the box - no password is typed anywhere else).

Pin Free TV Hub to Kodi's Favourites (context menu > Add to favourites) so it's always one click from the home screen.

Note: this hub is statically checked (valid Python, valid add-on structure) but built without a Kodi test rig - the first run on your box is its real test, and the manual steps below remain as the fallback for anything that misbehaves.

## Step 3 - The SlyGuy repository (the backbone of this setup)

The SlyGuy repo by developer Matt Huisman (actively maintained; source mirror: [https://github.com/matthuisman/slyguy.addons](https://github.com/matthuisman/slyguy.addons)) carries the free services below. If you used Free TV Hub Steps 1-2, this is already done - this section is the manual route and reference. To install by hand:

1. **Settings > File manager > Add source**, enter `https://slyguy.uk/.repo`
2. **Add-ons > Install from zip file**, pick that source, install the SlyGuy repository.
3. **Install from repository > SlyGuy Repository** > Video add-ons, and install the ones you want.

Install SlyGuy add-ons only from this repo URL - the author notes copied zips break because of dependencies.

## Step 4 - Free live TV (SlyGuy add-ons)

Per the author's own add-on documentation:

| Add-on | What you get | Login? |
|---|---|---|
| **Samsung TV Plus** | Free live TV, browse by region and genre | No login or subscription per the author; some channels geo-locked |
| **Plex Live** | 200+ free live channels, per the author | No subscription required per the author |
| **Pluto TV** | Free live TV channels | No login or subscription per the author; some channels geo-locked |
| **PBS Live** | Live streams of local PBS stations | None indicated |

Each of these offers **"Setup IPTV Merge"** in its settings: that automatically installs the IPTV Merge and IPTV Simple Client add-ons and wires the channels and program guide into Kodi's **TV** section, so you get a cable-style guide.

Note: the older official-repo Pluto TV add-on is marked broken/deprecated in the Kodi wiki ([https://kodi.wiki/view/Add-on:Pluto_TV](https://kodi.wiki/view/Add-on:Pluto_TV)) - use the SlyGuy one above instead.

## Step 5 - On-demand movies and shows

- **Roku** (SlyGuy repo, optional - not installed by the hub; install it from the SlyGuy repository yourself if you want it): third-party reviews report it carries The Roku Channel's free live channels (300+) plus on-demand movies and shows, with no login indicated ([https://troypoint.com/roku-kodi-addon/](https://troypoint.com/roku-kodi-addon/)). The Roku Channel itself is a free ad-supported service. The author's own page doesn't detail this one, so treat it as worth trying rather than guaranteed.
- **Documentary Heaven** (official Kodi repository): free documentaries; the site it pulls from ([https://www.documentaryheaven.com/](https://www.documentaryheaven.com/)) is live.
- **YouTube** (official repository, optional): full YouTube in Kodi, but requires creating personal Google API keys - a fiddly one-time setup documented at [https://github.com/anxdpanic/plugin.video.youtube/wiki/Personal-API-Keys](https://github.com/anxdpanic/plugin.video.youtube/wiki/Personal-API-Keys).

Free services rotate their catalogs, so specific titles come and go.

## Step 6 (optional) - A bigger community live-TV playlist

For channels beyond the services above: install **PVR IPTV Simple Client** from the official repo (**PVR clients** category; [https://kodi.wiki/view/Add-on:IPTV_Simple_Client](https://kodi.wiki/view/Add-on:IPTV_Simple_Client)) and point it at a playlist from the iptv-org project ([https://github.com/iptv-org/iptv](https://github.com/iptv-org/iptv)) plus its EPG link.

Heads-up from the project's own Legal note: the playlists are user-submitted links to publicly reachable streams, believed to be intentionally public and removed on a copyright holder's request, but the maintainers have no control over the stream sources. Treat it as a broad but mixed-reliability bonus, not the backbone.

## Step 7 - A clean, simple home screen and search

**Cleaner home screen:** Kodi's default skin (Estuary) lets you hide main-menu items you don't use - **Settings > Interface settings > Configure skin > Main menu items** - so the box opens to just the sections you want. Your live channels and guide live under **TV**; your streaming services under **Add-ons**. (Fancier layouts - service shortcuts on the home screen, custom widgets - depend on the skin and are a good second pass once the basics are working.)

**Direct play inside each service:** the add-ons above play their own service's stream when you pick something - one click, one official stream, no picking through lists of links.

**One discovery layer across services (approximate, optional):** **TheMovieDb Helper** (present in the official repo; the author recommends installing his repo, [https://jurialmunkey.github.io/repository.jurialmunkey/](https://jurialmunkey.github.io/repository.jurialmunkey/), for current modules - [https://github.com/jurialmunkey/plugin.video.themoviedb.helper](https://github.com/jurialmunkey/plugin.video.themoviedb.helper)) adds Netflix-style browsing and search of TMDb/Trakt catalogs - trending, popular, your watchlist. When you pick a title, it offers playback through installed add-ons via "player" files. Honest limit: players for the free services above are community-made (e.g. [https://github.com/slrwin/tmdbh.players](https://github.com/slrwin/tmdbh.players)) and vary in quality, and a title no free service carries simply won't play. It finds what *exists*; it can't create a free stream where none exists. Note Kodi's Global Search (and SlyGuy's Global Search+) searches only your local library, not the add-ons - TMDb Helper is the discovery layer, not that.

**Trakt (watch history and watchlist sync):** install **Trakt** from the official repo and sign in with your free trakt.tv account ([https://kodi.wiki/view/Add-on:Trakt](https://kodi.wiki/view/Add-on:Trakt)) - sign-in happens on the box itself, so no password goes anywhere else. It scrobbles what you watch and syncs watchlists and collections. One caveat: scrobbling depends on each add-on reporting playback properly, so watched-status syncing may be patchy for some services - the Trakt account and lists work regardless, and TMDb Helper can show your Trakt lists.

## Step 8 (optional) - Torrent playback for authorized content

**Elementum** (actively maintained - commits as recent as November 2026; install via the repository zip at [https://elementum.surge.sh/](https://elementum.surge.sh/); source: [https://github.com/elgatito/elementum](https://github.com/elgatito/elementum)) is Kodi's torrent-streaming engine. Torrents are a distribution technology, not a content source: include it if you have authorized torrent content (public-domain and Creative Commons releases, your own files). This kit does not preconfigure index providers - the popular provider packs point at unlicensed catalogs, and without a debrid service, torrent playback also shares pieces from your home IP while you watch.

## About this repo

- Hosted on GitHub, readable from your phone or the box's browser. Nothing runs on your computer; no files to babysit.
- Kodi add-ons install one at a time from their repositories inside the app - there is no official one-click way to install a whole list, so this guide walks you through each step.
- If this repo ever grows into a true Kodi repository (hosting add-on files), the files must be reachable over the internet without a login, because Kodi fetches them directly - a public GitHub repo with GitHub Pages does that for free ([https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages)); the long-running Netflix add-on repo at [https://castagnait.github.io/repository.castagnait/](https://castagnait.github.io/repository.castagnait/) is hosted exactly that way.

## Troubleshooting

- An add-on fails to install: confirm you're on Kodi 21 (**Settings > System information**); update via Play Store if not.
- A stream won't play: free services rotate catalogs and channels; try another add-on for the same title.
- Keep auto-update for add-ons on (the default) so everything stays current.
