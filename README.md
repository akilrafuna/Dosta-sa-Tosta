# Dosta #sa Tosta — Website

A single-page site for **Dosta #sa Tosta**, a street-food toast spot in Ulpiana, Prishtina.
Static HTML/CSS/JS — no build step, no dependencies. Ready for GitHub Pages.

**Albanian by default**, with an SQ / EN switch in the navbar (the choice is
remembered in `localStorage`).

## Files
```
index.html          → the whole site (both languages live in data-sq / data-en attributes)
style.css           → styles ("Warm Deli" theme, 8pt spacing scale)
assets/
  exterior.jpg      → storefront photo (compressed; ⚠ see "Photos" below)
  menu/*.jpeg       → menu item photos (from Wolt)
scrape n info/      → research: brand scrape + original source images
```

## Editing the text
Every translatable element carries both languages:
```html
<span data-sq="Porosit në" data-en="Order on">Porosit në</span>
```
Edit **both** attributes to change a string. The visible text between the tags is
just the Albanian fallback shown before JavaScript runs.

## Host it on GitHub Pages (free)

> ⚠️ **Before pushing:** GitHub repo names can't contain `#` or spaces.
> Use a clean name like `dosta-sa-tosta` for the repository. The site files
> themselves are fine — they only use relative links.

1. Create a new repo on GitHub, e.g. **`dosta-sa-tosta`**.
2. Upload everything in this folder (at minimum `index.html`, `style.css`, `assets/`).
   Easiest way: on the repo page → **Add file → Upload files** → drag them in → **Commit**.
3. Go to **Settings → Pages**.
4. Under **Build and deployment → Source**, pick **Deploy from a branch**.
5. Branch: **main**, folder: **/ (root)** → **Save**.
6. Wait ~1 min. Your site is live at:
   `https://<your-username>.github.io/dosta-sa-tosta/`

### Custom domain (optional)
In **Settings → Pages → Custom domain**, add e.g. `dostasatosta.com` and point your
domain's DNS to GitHub Pages. GitHub gives you free HTTPS.

## Edit content
- **Prices / items:** edit the `.card` blocks in `index.html`.
- **Wolt link:** search `wolt.com` in `index.html` (appears on every Order button).
- **Colors:** the `:root` variables at the top of `style.css`
  (`--espresso`, `--paper`, `--brick`, `--ochre`, `--wolt`).
- **Spacing:** use the `--s1`…`--s8` 8pt scale rather than ad-hoc pixel values.
- **Fonts:** Fraunces (display) + Karla (body), loaded from Google Fonts.

## Built in

- **Local SEO** — a `Restaurant` JSON-LD block in `<head>` feeds Google the address,
  phone, opening hours and all 11 menu items. Test it with
  [Google's Rich Results tool](https://search.google.com/test/rich-results).
  *Rating is deliberately left out:* Google disallows marking up ratings collected on
  other sites (Wolt/Google) as your own page's `aggregateRating`.
- **Live open/closed badge** — computed in `Europe/Belgrade`, so it stays correct for
  visitors abroad. Change the hours via `OPEN_H` / `CLOSE_H` in `index.html`.

## ⚠ Photos

`assets/exterior.jpg` is a **Google Street View capture and carries visible
"© 2026 Google" watermarks** — it should be replaced with an original photo of the
shop before this goes live commercially. Any decent phone photo will look better too.

## Credits
Menu photos & data sourced from the venue's [Wolt page](https://wolt.com/en/xkx/pristina/restaurant/dosta-sa-tosta-1).
Fonts: Anton + Space Grotesk (Google Fonts).
