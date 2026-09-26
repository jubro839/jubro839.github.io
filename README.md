# juyeonglee.ai — portfolio site

Static academic-style site (Minimal-Mistakes-like layout: sidebar profile + plain sections), no build step and no JavaScript. Pages: `index.html` (About — biography, work experience, academic background, teaching, certifications, skills), `research.html`, `projects.html`, `presentations.html`. Shared `styles.css`, plus `assets/` (photo, CV PDF) and `docs/` (decks, paper summaries, thesis, certificates linked from the pages).

## Preview locally
    python3 -m http.server 8766
    # open http://localhost:8766  — add ?theme=light or ?theme=dark to force a theme

## Deploy (GitHub Pages)
Live at https://jubro839.github.io/ from the `main` branch of `jubro839/jubro839.github.io` (user site, served from the repo root). Every push to `main` redeploys in about a minute.

### Custom domain (juyeonglee.ai), when ready
1. At the DNS provider add `A` records for `@` → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 and a `CNAME` for `www` → `jubro839.github.io`.
2. Rename `CNAME.pending` to `CNAME` and push (the file already contains `juyeonglee.ai`).
3. In the repo → Settings → Pages, confirm the domain and tick "Enforce HTTPS" once the certificate is issued.

## Updating content
- New CV → replace `assets/JuyeongLee_CV.pdf`.
- New deck or paper → drop the PDF in `docs/` and add a link (`<a class="doc" href="docs/…">`) in `index.html`.
- Each project block in `index.html` follows the same pattern: `.proj-head` → `.lead` → `.cols` (Description | Impact) → `.kv` chip rows → `.links`.
