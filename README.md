# Portfolio

My personal portfolio for project showcase — built with [MkDocs](https://www.mkdocs.org/)
and [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

**Live site:** <https://joshuaohyq.github.io/Portfolio/>

## Running it locally

```bash
pip install -r requirements.txt
mkdocs serve
```

Then open <http://127.0.0.1:8000/Portfolio/>.

To check the site the way CI does, which fails on broken links and orphaned pages:

```bash
mkdocs build --strict
```

## Layout

```text
mkdocs.yml                  site config, nav, theme and palette
docs/
  index.md                  home — hero, featured project cards, skills
  about.md                  bio, skills, education
  contact.md                email, GitHub, resume
  projects/
    index.md                project grid + comparison table
    smart-waste-segregation.md
    piper.md
    solar-irrigation.md
  assets/img/<project>/     figures extracted from the source reports
  assets/img/site/          logo and favicon
  stylesheets/extra.css     palette, cards, hero, tech pills
.github/workflows/deploy.yml
```

Project figures were extracted from the source PDF reports in the repository root and
resized for web. Source reports are kept alongside them for reference.

## Deployment

Every push to `main` triggers `.github/workflows/deploy.yml`, which builds with
`mkdocs build --strict` and publishes via the native GitHub Pages Actions deployment.

### One-time setup (must be done in the browser)

Go to **Settings → Pages** on this repository and set **Source** to
**GitHub Actions**. Without that, the workflow will build successfully but the deploy
step will fail. There is no `gh-pages` branch — the artifact is uploaded directly, so
nothing else needs configuring.
