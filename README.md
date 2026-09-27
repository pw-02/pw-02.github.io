# Patrick Watters — personal website

This repository contains the source for **https://pw-02.github.io**.

The site is built with Jekyll/al-folio and intentionally keeps a small surface area:

- **About** — homepage and research positioning
- **Research** — current systems/ML research directions
- **Publications** — publications and preprints
- **CV** — academic and research profile

## Local development

### Option 1: Dev Container / Codespaces

Open the repository in a GitHub Codespace or VS Code Dev Container. The repository already includes a `.devcontainer` configuration.

### Option 2: Local Ruby

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000`.

## Publishing

The source lives on `master`. Pushing to `master` triggers `.github/workflows/deploy.yml`, which builds the Jekyll site and publishes the generated output to `gh-pages`.

Do not edit `gh-pages` manually.

## Where to edit

- Homepage: `_pages/about.md`
- Research: `_pages/projects.md`
- Publications page: `_pages/publications.md`
- Publication BibTeX: `_bibliography/papers.bib`
- CV page: `_pages/cv.md`
- CV data: `_data/cv.yml`
- Site-wide settings/social links: `_config.yml`
- Styling: `_sass/_base.scss`
