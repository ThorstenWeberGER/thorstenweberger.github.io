# thorstenweberger.github.io

Personal portfolio page, built with [Jekyll](https://jekyllrb.com/) using the [Jekyll Serif theme](https://github.com/zerostaticthemes/jekyll-serif-theme) (see [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md)), hosted on [GitHub Pages](https://pages.github.com/).

Live at: https://thorstenweberger.github.io

## How it works

A GitHub Actions workflow (`.github/workflows/deploy.yml`) builds the site with Jekyll and Bundler and deploys it to GitHub Pages on every push to `main`.

**One-time setup required:** in the repo's **Settings → Pages → Build and deployment → Source**, select **"GitHub Actions"** (instead of "Deploy from a branch"). This theme needs a modern Jekyll version and plugins that GitHub's legacy branch-based build doesn't support, so the Actions workflow takes care of the build instead.

To develop locally:

```bash
bundle install
bundle exec jekyll serve
```

## Structure

- `index.md` – homepage
- `about.md` – about page
- `contact.md` – contact page
- `projects.md` + `_projects/` – project case studies (a Jekyll collection)
- `_layouts/`, `_includes/`, `_sass/`, `assets/`, `images/` – theme files
- `_data/` – site data (navigation menus, contact details, social links, SEO settings)
- `_config.yml` – Jekyll configuration
