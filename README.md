<p align="center">
  <img src="icon-512.png" width="120" alt="Fairgram logo">
</p>

<h1 align="center">Fairgram</h1>
<p align="center"><i>Because it's only fair they follow you back.</i></p>

<p align="center">
  A small, private tool for finding the Instagram accounts that don't follow you back —
  and working through them at your own pace, without automating a single click on your account.
</p>

---

## What it does

Fairgram reads the official data export you download from Instagram, compares your followers against who you follow, and builds a clean, working list of everyone who doesn't follow you back. From there it walks you through them one at a time so you can review and unfollow manually, at whatever pace you want.

Nothing in this tool ever logs into Instagram, automates a click, or touches your account directly — it only opens a profile link for you. Everything else is a normal, deliberate tap in the real Instagram app.

## Features

- **Focus mode** — one account at a time, with a direct link to their profile
- **Keyboard shortcuts** — `Space` to mark done, `S` to skip, `Backspace` to undo
- **Daily batch limits** — cap how many you review per day so it never feels like a chore
- **Progress that sticks** — your place is saved automatically between visits
- **Full list view** — searchable, filterable by pending / done / skipped
- **CSV export & restore** — back up your progress, or pick up on a different device
- **Installable** — add it to your phone's home screen and it opens like a native app

## Getting your data from Instagram

1. Open Instagram → your profile → menu (☰)
2. **Settings and privacy** → **Accounts Center** → **Your information and permissions**
3. **Download your information** → **Some of your information**
4. Select only **Followers and following**
5. Format: **JSON**, date range: **All time** → submit
6. Once it's ready, download and unzip it
7. Inside, find `followers_1.json` and `following.json` under `connections/followers_and_following/`

Fairgram walks you through this same checklist the first time you open it.

## How it works, technically

Everything runs client-side, in your browser:

- Your two export files are parsed locally with the `FileReader` API — they're never uploaded anywhere
- The "doesn't follow back" list is computed in-browser and saved to `localStorage` on your device
- A service worker and web manifest make it installable as a home-screen app
- No backend, no server, no account required

## Privacy

Your Instagram data never leaves your device. There's no server in this project at all — it's a static site, so whatever GitHub Pages (or wherever you host it) serves is the entire application.

## A note on Instagram's terms

Fairgram is a **manual review aid**, not an automation tool. It doesn't unfollow anyone for you, and it doesn't interact with Instagram's app or API in any way beyond opening a profile link, the same as tapping a link anywhere else on the web. The actual unfollow action always happens by hand, in the real Instagram app.

## Running it yourself

This is a static site — no build step, no dependencies.

1. Clone or download this repo
2. Open `index.html` in a browser, or host the whole folder anywhere that serves static files (GitHub Pages, Netlify, etc.)
3. On first load, upload your two export files and start reviewing

---

<p align="center"><sub>A personal project. Not affiliated with Instagram or Meta.</sub></p>
