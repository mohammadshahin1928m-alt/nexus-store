# NEXUS — Computer Hardware Store

A bilingual (English / Persian) hardware storefront and magazine. Static HTML, CSS and vanilla JS — no build step, no framework, no backend.

**فروشگاه سخت‌افزار دو زبانه (انگلیسی / فارسی) — کاملاً استاتیک، بدون فریم‌ورک و بدون بک‌اند.**

---

## Pages · صفحه‌ها

| File | Description |
|---|---|
| `index.html` | Store: hero, 5 shelf groups, 21 subcategories, 26 product cards, filters, compare, cart, AI assistant. **Self-contained** — all CSS, fonts, images and video inlined as `data:` URIs. |
| `magazine.html` | NEXUS MAG: 13 news cards + 9 briefs, Persian/English switch. |
| `story.html?id=<slug>` | Article reader. Slugs: `zen6`, `socket`, `ddr6`, `handheld`, `lpddr6`, … |
| `404.html` | Redirects unknown paths back to the store. |
| `index.source.html` | Editable source of the store (linked assets instead of inlined). Edit this, then rebuild. |

## Run locally · اجرای محلی

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

Opening `index.html` directly from disk also works, but a local server is recommended so the magazine/article links resolve.

## Editing · ویرایش

`index.html` is a generated bundle (~6 MB). To change the store:

1. Edit `index.source.html` and/or `assets/store.css`.
2. Rebuild the single-file bundle:
   ```bash
   python3 ../build_single2.py
   ```
3. Copy the result over `index.html`.

`magazine.html` and `story.html` are hand-written and can be edited directly.

## Features · امکانات

- Full EN/FA interface with RTL layout, Persian digits and a `B Yekan` type stack.
- 21 subcategories across 5 shelving groups; every category has at least one product card.
- Cart persisted in `localStorage`, compare tray, price converter (USD → toman), light/dark theme.
- "Nexus" AI shopping assistant panel (rules-based, runs entirely in the browser).
- Responsive down to 320 px; no horizontal overflow at 320 / 360 / 390 / 768 / 1440.

## Deploy · انتشار

Served by GitHub Pages from the `main` branch root. Push to `main` and the site is live.
Static hosting anywhere else (Netlify, Cloudflare Pages, S3) works the same way — no configuration needed.

## License

Code and content in this repository are the property of the repository owner.
Product names and trademarks belong to their respective owners; images are placeholders for demonstration.
