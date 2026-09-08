# improve — Aim Training Hub

**🎮 [Visit the website](https://nkbigmoney.github.io/improve/)**

A single-page site with Aimlabs + Kovaaks training plans per game, and a manual stats tracker for current vs. goal rank.

## What's in here

- `index.html` — the whole site (HTML, CSS, and JS in one file). No build step, no dependencies to install.

## Tabs

- **Home** — overview of the four games covered.
- **CS2 / Valorant / Marvel Rivals / Overwatch 2** — each has a training plan broken into 3 skill blocks (precision, tracking, target switching/reaction), with named Aim Labs and Kovaaks scenarios.
- **Lineups** — placeholder tab. Not built yet.
- **My Stats** — enter your current rank/stat and goal rank/stat per game. Saved and reloaded automatically.

## Adding more games

Open `index.html` and find the `plans` object in the `<script>` section. Copy one of the existing entries (e.g. `cs2`), rename the key, and fill in the intro and cards. Then:

1. Add a new tab button in the `<nav>` block: `<button class="tabbtn" data-view="yourkey">Your Game</button>`
2. Add an empty container in `<main>`: `<div class="view" id="view-yourkey"></div>`
3. Add `'yourkey'` to the array at the bottom of the plans script: `['cs2','valorant','rivals','ow2','yourkey'].forEach(renderPlan);`

## Stats and tracker networks

There's no way to pull live stats or rank from tracker.gg, Overwolf, or the games themselves into a third-party
site. Riot, Valve, Blizzard, and Marvel Rivals don't offer a public stats API, and tracker.gg's data access is a
paid, approved partner integration — not something you can just wire into a personal site.

The **My Stats** tab is built around manual entry instead: you type in your current rank/stat and your goal
rank/stat, and it's saved per game. If an official or licensed data source ever becomes available, the same tab
can be swapped to pull live numbers without changing the layout — the save/load logic is isolated in one place in
the script.

## Hosting

`index.html` is fully self-contained. Drop it on any static host (GitHub Pages, Netlify, Vercel, or just open it
locally in a browser) and it works as-is.

This site is hosted on **GitHub Pages** — no additional setup needed!
