# Forest — a Jellyfin theme

Deep pine + burnt orange. Netflix-style layout: transparent top bar that
solidifies on scroll, hover-zoom cards, hero banner on detail pages.

## Install

Dashboard > General > Custom CSS, paste one line, save, hard-refresh twice:

```
@import url('https://cdn.jsdelivr.net/gh/USER/REPO@main/theme.css');
```

Replace `USER/REPO`. Swap `@main` for a tag (`@v1`) once you're happy, so
in-progress commits don't hit the living room mid-movie.

Note: jsDelivr caches aggressively. While iterating, use `@main` and append
`?v=2` (bump the number) to bust the cache, or work from a local paste.

## Modules

Everything lives in `modules/`. `theme.css` imports them in order; comment out
a line to drop that piece.

| File | What it does |
|---|---|
| `tokens.css` | All colors. Edit here to retheme. |
| `base.css` | Page surfaces, scrollbars, font stack |
| `header.css` | Top nav layout + text wordmark |
| `drawer.css` | Side drawer |
| `hero.css` | Detail-page hero banner |
| `buttons.css` | Buttons, focus rings |
| `cards.css` | Rows, hover zoom, progress bars |
| `forms.css` | Inputs, dialogs, lists, links |
| `player.css` | Video OSD |
| `login.css` | Login screen |
| `mediabar.css` | Tints Jellyfin Media Bar (no-op without the plugin) |

## Customizing

Change the wordmark: `modules/header.css`, the `content:` string.

Change the accent: `modules/tokens.css`, `--accent` and `--accent-hot`.

## Home page hero

Needs the Jellyfin Media Bar plugin (IAmParadox27's fork adds it without
editing your Jellyfin install files). `mediabar.css` tints it to match.

## Reverse proxy

If you later put this behind nginx using the config from the Jellyfin docs,
its Content-Security-Policy blocks external stylesheets and the theme silently
won't load. Add `https://cdn.jsdelivr.net` to `style-src`.

## Credits

Two rules borrowed from [CTalvio/Ultrachromic](https://github.com/CTalvio/Ultrachromic) (MIT).
