# Archi Project Website

Public website for [Archi](https://github.com/archi-physics/archi) — an open-source AI agent for CMS computing operations at CERN, built at MIT.

Built with [Jekyll](https://jekyllrb.com/) and deployed via [GitHub Pages](https://pages.github.com/).

## Local Development

Requires Ruby 3.3+ (recommend installing via Homebrew on macOS: `brew install ruby`).

```bash
# Install dependencies
bundle install

# Serve locally (http://localhost:4000)
bundle exec jekyll serve
```

The site auto-rebuilds when you edit files. Press Ctrl+C to stop.

## Site Structure

```
_config.yml          # Site settings (title, description, plugins)
_data/
  team.yml           # Team members grouped by institution
  talks.yml          # Conference talks and presentations
  publications.yml   # Academic publications
_includes/
  nav.html           # Top navigation bar
  footer.html        # Site footer
_layouts/
  default.html       # Base layout (head, nav, footer)
  post.html          # Blog post layout
_posts/              # News articles (Markdown)
assets/
  css/main.css       # All styles (single file)
  images/            # Logos, screenshots, team photos
index.html           # Homepage
news.html            # News listing page
talks.html           # Talks & Publications page
team.html            # Team page
404.html             # Error page
```

## Adding Content

### News Posts

Add a Markdown file to `_posts/` named `YYYY-MM-DD-slug.md`:

```yaml
---
layout: post
title: "Your Post Title"
date: 2026-04-01
image: /assets/images/news/optional-image.png  # optional, for social sharing
---

Post content in Markdown. Use [links](https://example.com) and images:

![Alt text](/assets/images/news/your-image.png)
```

Posts appear automatically on the homepage (latest 3) and the news listing page.

### Talks

Add an entry to `_data/talks.yml`:

```yaml
- title: "Talk Title"
  speaker: "Speaker Name"
  institution: "MIT"
  date: 2026-04-01
  event: "Conference Name"
  event_url: "https://..."        # optional
  slides_url: "https://..."       # optional
  recording_url: "https://..."    # optional
```

Talks are sorted by date (newest first). Future talks automatically get an "Upcoming" label.

### Publications

Add an entry to `_data/publications.yml`:

```yaml
- title: "Paper Title"
  authors: "A. Author, B. Author, C. Author"
  venue: "Conference or Journal Name"
  year: 2026                      # optional
  upcoming: true                  # optional, shows "Upcoming" label
  arxiv_url: "https://..."        # optional
  doi_url: "https://..."          # optional
  event_url: "https://..."        # optional
```

### Team Members

Add an entry to `_data/team.yml`:

```yaml
- name: "Full Name"
  role: "Role Title"              # optional
  institution: "MIT Physics"      # groups members on the page
  github: "username"              # optional, links to GitHub profile
  photo: "/assets/images/team/username.jpg"  # optional, 400x400+ recommended
  pi: true                        # optional, shows in PI section with large card
```

**Institutions used:** MIT Physics, MIT CSAIL, CERN, Fermilab, Collaborators.

For collaborators from other universities, also add:
```yaml
  affiliation: "Brown University"  # shown below name
```

Team photos go in `assets/images/team/`. Members without photos get an initials placeholder.

### Images

Place images in the appropriate subfolder:
- `assets/images/` — logos, site-wide images
- `assets/images/news/` — images for blog posts
- `assets/images/team/` — team member photos

## Deployment

Deployment is **manual** — pushing to `main` does not auto-deploy. To deploy:

1. Go to the **Actions** tab on GitHub
2. Select the **Deploy Jekyll site to Pages** workflow
3. Click **Run workflow**

This lets collaborators review changes before they go live.

## License

[MIT License](https://github.com/archi-physics/archi/blob/main/LICENSE)
