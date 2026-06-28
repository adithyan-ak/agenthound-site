# agenthound.io

Source for the AgentHound landing page at <https://agenthound.io>.

Single-file static site, no build step. Deployed via GitHub Pages with a custom domain (`CNAME`).

## Local preview

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

1. Push to `main` on the GitHub repo backing the site.
2. In repo Settings -> Pages: set source to `main` / root.
3. In Settings -> Pages -> Custom domain: enter `agenthound.io`.
4. Add DNS records (at your registrar):
   - `A` records for `agenthound.io` -> GitHub Pages IPs (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153)
   - `CNAME` for `www` -> `<user>.github.io`
5. Wait for HTTPS provisioning, then enable "Enforce HTTPS".

## Files

- `index.html` - the page (HTML, CSS, JS inline)
- `404.html` - fallback that redirects to `/`
- `og.png` - Open Graph / Twitter card (1200×630)
- `og-template.html` - source for `og.png` (re-render with headless Chrome at 1200×630)
- `robots.txt` - crawler rules + sitemap pointer
- `sitemap.xml` - single-URL sitemap
- `site.webmanifest` - PWA / install manifest
- `favicon.ico`, `favicon-16x16.png`, `favicon-32x32.png`,
  `apple-touch-icon.png`, `android-chrome-192x192.png`,
  `android-chrome-512x512.png` - favicon set
- `CNAME` - custom domain
- `.nojekyll` - disables Jekyll processing

## License

Apache 2.0 (matches the AgentHound project).
