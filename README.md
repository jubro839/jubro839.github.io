# juyeong.ai portfolio site

Static academic-style site (sidebar profile on the left, plain sections on the right), no JavaScript. Pages: `index.html` (About: biography, work experience, academic background, teaching, certifications, skills), `experience.html`, `research.html`, `presentations.html` (with first-page thumbnails in `assets/thumbs/`). Shared `styles.css`, plus `assets/` (photo, CV PDF, company logos in `assets/logos/`) and `docs/` (decks, paper summaries, thesis, certificates linked from the pages).

## Preview locally
    python3 -m http.server 8766
    # open http://localhost:8766

## Deploy (GitHub Pages)
Live at https://jubro839.github.io/ from the `main` branch of `jubro839/jubro839.github.io` (user site, served from the repo root). Every push to `main` redeploys in about a minute.

### Custom domain (juyeong.ai), when ready
As of 2026-09-27 the domain is not registered yet, so keep `CNAME.pending` as it is until the DNS records exist; a live `CNAME` file without DNS takes the site offline.
1. At the DNS provider add `A` records for `@` → 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 and a `CNAME` for `www` → `jubro839.github.io`.
2. Rename `CNAME.pending` to `CNAME` and push (the file already contains `juyeong.ai`).
3. In the repo → Settings → Pages, confirm the domain and tick "Enforce HTTPS" once the certificate is issued.

## Updating content
- The four pages and `styles.css` are generated: edit the text in `../deck-sources/site-design/build.py`, then run `python3 site_build.py <this folder>` from that folder. The same content feeds the Claude Design canvas boards.
- New CV → replace `assets/JuyeongLee_CV.pdf`.
- Updated deck → export the PPTX to PDF and overwrite the same-named file in `docs/` (links stay unchanged); regenerate its thumbnail with `pdftoppm -jpeg -f 1 -l 1 -scale-to 480 -singlefile docs/<name>.pdf assets/thumbs/<name>`.
- New deck or paper → drop the PDF in `docs/`, add a `[slides]`/`[paper]` link (`<a class="ref" href="docs/…">`) on the Experience or Research page and a row on the Presentations page.
