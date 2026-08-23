# CLAUDE.md

Guidance for Claude Code when working in this repository.

## What this repo is

`thorstenweberger.github.io` is Thorsten Weber's personal portfolio site, built
with Jekyll (`jekyll-theme-yat`) and hosted on GitHub Pages. It showcases his
projects as a scrolling list of posts on the homepage, each linking out to the
project's own GitHub repo.

## Adding a new project section

When asked to "add a new project", "add a section for repo X", or similar,
follow this recipe. Every existing project on the site is a single Jekyll
post under `_posts/` — there is no separate "projects" data file or template
system beyond that.

### 1. Gather the source material

Read the target repo's `README.md` (and skim its structure) to learn:
- What the project does, in one clear paragraph
- The tech stack / key tools involved
- 3-5 concrete highlights or capabilities worth bulleting
- Whether it has a hero/banner image worth reusing

If the repo isn't already attached to the session, use `add_repo` (or clone
read-only for public repos) before reading it.

### 2. Add a hero image (if available)

Site convention: one image per project at
`assets/images/projects/<slug>.png`, referenced at the top of the post.
If the source repo has a suitable banner/hero image, copy it in under that
path. If not, skip the image line entirely — not every existing post has one.

### 3. Create the post file

Add `_posts/YYYY-MM-DD-<slug>.md` (use today's date, `<slug>` matching the
repo name in kebab-case) with this exact front matter and structure, modeled
directly on existing posts (see `_posts/2026-01-25-generate-erd-automatically.md`):

```markdown
---
layout: post
title: "<Human-readable Project Title>"
subtitle: "<one-line pitch>"
categories: projects
tags: [tag1, tag2, tag3]
---

![<alt text>](/assets/images/projects/<slug>.png)

<1-2 paragraph description of what the project does and why it matters,
written in the same voice as existing posts — plain, concrete, no hype.>

**Tech Stack:** Tool A · Tool B · Tool C

**Highlights**

* Bullet 1
* Bullet 2
* Bullet 3

[View the code and full write-up on GitHub →](https://github.com/ThorstenWeberGER/<repo-name>)
```

Notes on tone: match the existing posts — short, factual, no marketing
adjectives. Lead with what the tool does, not why it's impressive. The image
line is omitted if there's no hero image to use.

### 4. Do not touch `projects.md` or `index.md`

`projects.md` just points at `layout: archives`, which auto-lists all
`categories: projects` posts. `index.md` is static bio copy. Neither needs
editing when adding a project — the new post appears automatically once it's
in `_posts/` with `categories: projects`.

### 5. Commit and push

Commit only the new post file (and new image, if added) with a concise
message like `Add <project> to projects`. Don't touch unrelated files.

## Site structure reference

- `_config.yml` — Jekyll config, theme (`jekyll-theme-yat`), header pages
- `_posts/` — one file per project, `categories: projects` makes it show up
  in the project archive/list
- `_data/social.yml` — social links shown via `_includes/social-links.html`
- `assets/images/projects/` — one hero image per project, `<slug>.png`
- `index.md` — homepage bio text
- `about.md` — longer bio page
- `projects.md` — archive listing (auto-populated, don't hand-edit)

## Working conventions

- This is a static Jekyll site — no build step is required to add a post,
  but if verifying rendering locally, `bundle exec jekyll serve` works given
  the `Gemfile`.
- Keep new posts self-contained: don't create new includes/layouts for a
  single project unless the existing `post` layout genuinely can't express it.
- Always link out to the actual GitHub repo rather than duplicating its docs
  here — this site is a showcase/index, not a mirror.
