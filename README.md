# Torelli website backup (Adobe Muse export)

Static export of the Torelli: Furniture & Interiors website, built in Adobe Muse (2018.1) by Studio Aaviz.

## Layout

- `site/` is the full static site, served as-is. Open `site/index.html` locally or deploy the folder.
- `_source/` holds the `.psd` / `.ai` working files from the export. No page uses them, so they are kept out of the live site. The export's `assets/.htpasswd` password file is deliberately not in this repo.
- `netlify.toml` points Netlify at `site/` with no build step.
- `site/_headers` sends `X-Robots-Tag: noindex` so the backup stays out of search results. Delete it to allow indexing.

## Hosting

**Netlify:** Add new site > Import an existing project > GitHub > this repo. Settings are picked up from `netlify.toml`.

**Cloudflare Pages:** Create > Pages > Connect to Git > this repo. Framework preset: None, build command: blank, output directory: `site`.

## Notes

- 13,461 site files, about 845 MB (images 712 MB).
- jQuery loads from the local `site/scripts/` fallback over HTTPS. The old Business Catalyst CDN is gone.
- Proxima Nova web fonts in `site/fonts/` are commercially licensed (Mark Simonson).
