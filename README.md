# juyeonglee.ai — portfolio site

Static academic-style site (Minimal-Mistakes-like layout: sidebar profile + plain sections), no build step and no JavaScript. Pages: `index.html` (About — biography, work experience, academic background, teaching, certifications, skills), `research.html`, `projects.html`, `presentations.html`. Shared `styles.css`, plus `assets/` (photo, CV PDF) and `docs/` (decks, paper summaries, thesis, certificates linked from the pages).

## Preview locally
    python3 -m http.server 8766
    # open http://localhost:8766  — add ?theme=light or ?theme=dark to force a theme

## Deploy (GitHub Pages)
1. `git init && git add -A && git commit -m "Portfolio site"` then push to a GitHub repo on `main`.
2. Repo → Settings → Pages → "Deploy from a branch" → `main` / root.
3. `CNAME` already contains `juyeonglee.ai`. At the DNS provider add:
   - `A` records for `@` → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - `CNAME` for `www` → `<github-username>.github.io`
4. Enable "Enforce HTTPS" once the certificate is issued.

## Updating content
- New CV → replace `assets/JuyeongLee_CV.pdf`.
- New deck or paper → drop the PDF in `docs/` and add a link (`<a class="doc" href="docs/…">`) in `index.html`.
- Each project block in `index.html` follows the same pattern: `.proj-head` → `.lead` → `.cols` (Description | Impact) → `.kv` chip rows → `.links`.
