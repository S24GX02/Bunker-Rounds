# Bunker Rounds – Android app guide

This folder is the game packaged as a **Progressive Web App (PWA)**: a website that Android can
install like a normal app (own icon, full screen, works offline).

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The game itself (same as the online version, plus 3 lines that make it installable) |
| `manifest.webmanifest` | Tells Android the app's name, icon, colours, and that it runs full screen in landscape |
| `sw.js` | The "service worker": saves a copy of the game on the phone so it runs without internet |
| `icons/` | App icons in the sizes Android and iPhone ask for |

> **Why it needs hosting:** Android only installs PWAs from an `https://` web address. Opening
> `index.html` straight from your phone's file manager will play the game, but won't offer
> "Install". The free option below takes about 10 minutes.

---

## Part 1 – Put it online for free with GitHub Pages

1. Go to **https://github.com** and create a free account (or sign in).
2. Click **+** (top right) → **New repository**.
   - Repository name: `bunker-rounds`
   - Set it to **Public** (GitHub Pages is free for public repositories)
   - Click **Create repository**.
3. On the new repository page, click **uploading an existing file**.
4. Drag in **everything from this folder**: `index.html`, `manifest.webmanifest`, `sw.js`,
   `README.md`, and the whole `icons` folder. Click **Commit changes**.
5. Go to **Settings** → **Pages** (left menu).
   - Source: **Deploy from a branch**
   - Branch: **main**, folder **/ (root)** → **Save**.
6. Wait 1–2 minutes and refresh. GitHub shows your address, which looks like
   `https://YOUR-USERNAME.github.io/bunker-rounds/`.

## Part 2 – Install it on your Android phone

1. Open that address in **Chrome** on your phone.
2. Tap the **⋮** menu (top right) → **Install app** (on some phones: **Add to Home screen** → **Install**).
3. The Bunker Rounds icon appears on your home screen. It opens full screen, in landscape, and keeps working without internet after the first launch.

Share the same link with colleagues and they can install it the same way.

## Part 3 (optional) – Make a real `.apk` file / Play Store package

1. Go to **https://www.pwabuilder.com** and paste your GitHub Pages address.
2. It checks the app (the manifest, icons and service worker in this folder are already set up for this).
3. Click **Package for stores** → **Android** → **Generate**.
4. You get a zip with:
   - an **`.apk`** you can copy to a phone and install directly ("install unknown apps" must be allowed for your file manager), and
   - an **`.aab`** for uploading to the Google Play Console (needs a Google Play developer account, one-time fee).
5. Keep the **signing key** file from that zip somewhere safe. You need the same key for every future update of the app.

---

## Updating the game later

1. Replace `index.html` in your GitHub repository with the new version (**Add file → Upload files**).
2. Open `sw.js` in GitHub (pencil icon to edit) and change `bunker-rounds-v1` to `bunker-rounds-v2`
   (then v3, v4 … each time). This tells installed phones to fetch the new version.
3. Commit. Phones pick up the update the next time the app is opened with internet (sometimes it takes two launches).

## Touch controls (quick reference)

- **Left thumb**: move (the stick appears wherever you touch the left half of the screen)
- **Right thumb**: aim. Your gun fires automatically when the red laser is on a zombie.
- **USE** (hold): buy, open doors, use machines and traps, rebuild windows
- **NADE**: throw a grenade in the direction you're aiming
- **Right edge**: round icons for Pause, Map, Swap weapon, Knife and Reload (Fullscreen and Cheats are in the pause menu)
- Tip: if it stutters on an older phone, turn on **Low graphics** on the start screen or in the pause menu.
