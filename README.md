# thorstenweberger.github.io

Personal portfolio page, built with [Jekyll](https://jekyllrb.com/) using the [jekyll-theme-yat](https://github.com/jeffreytse/jekyll-theme-yat) gem theme (see [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md)), hosted on [GitHub Pages](https://pages.github.com/).

Live at: https://thorstenweberger.github.io

## How it works

A GitHub Actions workflow (`.github/workflows/deploy.yml`) builds the site with Jekyll and Bundler and deploys it to GitHub Pages on every push to `main`. Requires the repo's **Settings → Pages → Build and deployment → Source** to be set to **"GitHub Actions"**.

To develop locally:

```bash
bundle install
bundle exec jekyll serve
```

## Structure

- `index.html` – homepage (shows the latest projects)
- `about.html` – about page
- `projects.html` – full project list, grouped by year
- `_posts/` – project case studies (each project is a dated post)
- `_config.yml` – Jekyll configuration (theme, site title, navigation, etc.)
