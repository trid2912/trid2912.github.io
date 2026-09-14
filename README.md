# trid2912.github.io

Personal academic page for Duc Tri Tran, built on
[Jekyll Now](https://github.com/barryclark/jekyll-now).

## Publishing

1. Create a GitHub repository named exactly **`trid2912.github.io`** (User Pages repo).
2. From this directory:

   ```bash
   git init
   git add .
   git commit -m "Initial personal page"
   git branch -M main
   git remote add origin https://github.com/trid2912/trid2912.github.io.git
   git push -u origin main
   ```

3. In the repo: **Settings → Pages → Source = Deploy from a branch → `main` / `(root)`**.
   The site appears at <https://trid2912.github.io> within a minute or two.
   GitHub builds the Jekyll site for you — nothing to install locally.

## Previewing locally (optional)

```bash
bundle install
bundle exec jekyll serve
# → http://localhost:4000
```

## Editing

| What | Where |
|---|---|
| Name, tagline, avatar, footer links | `_config.yml` |
| Bio + Updates list | `index.md` |
| Publication list | `_data/publications.yml` |
| Experience / education / skills | `experience.md` |
| CV page | `cv.md` |
| Nav bar items | `_layouts/default.html` |
| Colors and type | `_sass/_variables.scss`, `style.scss` |

### Photos

- `images/tran-duc-tri.jpg` — 400x400 head crop, shown as the circular header avatar
  (set via `avatar:` in `_config.yml`).
- `images/milan.jpg` — the full photo, 900px wide. Unused by default; uncomment
  the `<img>` line at the top of `index.md` to float it beside the bio.

Both are cropped from the original in `../cv/`.

### Updating the CV

The LaTeX source is in `cv-source/`:

```bash
cd cv-source
latexmk -pdf resume.tex
cp resume.pdf ../assets/Duc-Tri-Tran-CV.pdf
latexmk -c
```
