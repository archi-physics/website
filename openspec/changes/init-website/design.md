## Context
Archi is an open-source RAG framework for scientific computing, developed by a multi-institutional team (MIT, CERN, Fermilab, UChicago, UW-Madison). The project needs a public website to replace an outdated WordPress site. The site must be maintainable by researchers (not web developers), hostable for free, and visually appropriate for the institutions it represents.

## Goals / Non-Goals
- **Goals:**
  - Professional, minimal static website hosted on GitHub Pages
  - Easy content updates (Markdown + YAML, no HTML knowledge needed for posts/talks/team)
  - Responsive design that works on all devices
  - Fast page loads, no JavaScript frameworks
- **Non-Goals:**
  - CMS or dynamic backend
  - User authentication or interactive features
  - Blog comments or analytics (can be added later)
  - Replicating the full Archi documentation (that lives at archi-physics.github.io/archi/)

## Decisions
- **Static site generator: Jekyll** — Native GitHub Pages support, no CI pipeline needed, Markdown-first, mature ecosystem. Alternatives considered: Hugo (faster builds but requires CI for GH Pages), plain HTML (harder to maintain), Docusaurus (too heavy for a project page).
- **No theme gem — custom minimal layout** — Academic sites need a distinctive look, not a generic blog theme. A small custom layout (~200 lines CSS) keeps the design clean and institutional. Alternative: minima theme (too blog-focused), academic-pages (too opinionated).
- **YAML data files for structured content** — Talks and team members are structured data, not prose. `_data/talks.yml` and `_data/team.yml` let non-developers add entries without touching HTML. Alternative: Markdown collections (more overhead for tabular data).
- **Jekyll `_posts/` for news** — Standard Jekyll convention. Gives us date-based URLs, chronological ordering, and RSS for free. Alternative: custom collection (unnecessary complexity).
- **CSS-only responsive design** — No JavaScript framework. A hamburger menu with a CSS checkbox hack keeps the site dependency-free. Alternative: Bootstrap (too heavy), Tailwind (requires build step).
- **MIT color palette** — Primary: MIT Cardinal Red (#A31F34), accents: dark gray (#8A8B8C), near-black (#1E1E1E) for text, white (#FFFFFF) background. The red is used sparingly for headings, nav highlights, and links to avoid overwhelming the minimal design.
- **Archi logo: PNG** — Downloaded from the source repo (`archi-physics/archi`). Stored at `assets/images/archi-logo.png` (520×536).

## Risks / Trade-offs
- **GitHub Pages Jekyll version lag** — GH Pages runs an older Jekyll. Mitigation: stick to features supported by the GH Pages gem; test with `github-pages` gem locally.
- **No search** — Static site has no built-in search. Acceptable for a small project site; can add lunr.js later if needed.
- **Manual content updates** — Adding talks/team requires editing YAML and pushing to git. Acceptable for an academic team comfortable with git.

## Domain Setup
GitHub Pages supports two options:
1. **Default**: The site is published at `https://<org>.github.io/<repo>/` (e.g., `archi-physics.github.io/archi-website/`). No configuration needed beyond enabling Pages in repo settings.
2. **Custom domain**: Purchase a domain (e.g., `archi.mit.edu` or `archi-physics.org`), then:
   - Add a `CNAME` file to the repo root containing the domain name
   - Configure DNS: add a CNAME record pointing to `archi-physics.github.io`
   - Enable "Enforce HTTPS" in the repo's Pages settings
   - GitHub provisions a free TLS certificate automatically

The `_config.yml` will use a `baseurl` variable so the site works with either option. When a custom domain is ready, just add the `CNAME` file and update `_config.yml`.

## Page Layout & Visual Design

```
┌──────────────────────────────────────────────────────────┐
│  NAVIGATION BAR                                          │
│  [Archi Logo]  Home   News   Talks   Team   Docs  GitHub │
│  ─────────────────────────────────────────────────────── │
├──────────────────────────────────────────────────────────┤
│                                                          │
│                     PAGE CONTENT                         │
│              (varies per page, see below)                │
│                                                          │
├──────────────────────────────────────────────────────────┤
│  FOOTER                                                  │
│  MIT · CERN · Fermilab          MIT License · Contact    │
└──────────────────────────────────────────────────────────┘
```

### Homepage Layout
```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│                    [Archi Logo]                           │
│              AI Augmented Research                        │
│               Chat Intelligence                          │
│                                                          │
│   A retrieval-augmented generation framework for         │
│   research and education teams.                          │
│                                                          │
│        [ View Docs ]    [ GitHub ]                        │
│                                                          │
├──────────────────────────────────────────────────────────┤
│                                                          │
│  KEY CAPABILITIES                                        │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐                 │
│  │ AI       │ │ Data     │ │ Multiple │                 │
│  │ Pipelines│ │ Ingest   │ │ Interfaces│                │
│  └──────────┘ └──────────┘ └──────────┘                 │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐                 │
│  │ LLM      │ │ Modular  │ │ Container│                 │
│  │ Support  │ │ Design   │ │ Deploy   │                 │
│  └──────────┘ └──────────┘ └──────────┘                 │
│                                                          │
├──────────────────────────────────────────────────────────┤
│  LATEST NEWS                                             │
│  • Mar 2026 — New website launched                       │
│  • Mar 2026 — CERN EP-IT Seminar ...                     │
│                                     [ All News → ]       │
├──────────────────────────────────────────────────────────┤
│  MIT · CERN · Fermilab                                   │
└──────────────────────────────────────────────────────────┘
```

### News Page
```
┌──────────────────────────────────────────────────────────┐
│  NEWS                                                    │
│                                                          │
│  March 27, 2026                                          │
│  ── Post Title ──────────────────────────────────────    │
│  Excerpt text here...                     [ Read → ]     │
│                                                          │
│  March 17, 2026                                          │
│  ── Another Post ────────────────────────────────────    │
│  Excerpt text here...                     [ Read → ]     │
└──────────────────────────────────────────────────────────┘
```

### Talks Page
```
┌──────────────────────────────────────────────────────────┐
│  TALKS & PRESENTATIONS                                   │
│                                                          │
│  Mar 17, 2026 · CERN EP-IT Data Science Seminar          │
│  Agents for Scientific Computing                         │
│  Jason Mohoney (MIT)                                     │
│  [ Slides ]  [ Recording ]  [ Event Page ]               │
│                                                          │
│  ─────────────────────────────────────────────────────   │
│  (next talk entry...)                                    │
└──────────────────────────────────────────────────────────┘
```

### Team Page
```
┌──────────────────────────────────────────────────────────┐
│  TEAM                                                    │
│                                                          │
│  ── MIT ─────────────────────────────────────────────    │
│  ┌────────┐  ┌────────┐  ┌────────┐                     │
│  │ [photo]│  │ [photo]│  │ [photo]│                     │
│  │ Name   │  │ Name   │  │ Name   │                     │
│  │ Role   │  │ Role   │  │ Role   │                     │
│  └────────┘  └────────┘  └────────┘                     │
│                                                          │
│  ── CERN ────────────────────────────────────────────    │
│  ┌────────┐  ┌────────┐                                  │
│  │ [photo]│  │ [photo]│                                  │
│  │ Name   │  │ Name   │                                  │
│  │ Role   │  │ Role   │                                  │
│  └────────┘  └────────┘                                  │
└──────────────────────────────────────────────────────────┘
```

### Typography & Color
- **Font**: System font stack (`-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif`) — fast, no external requests
- **Headings**: MIT Cardinal Red (#A31F34), uppercase for section labels
- **Body text**: Near-black (#1E1E1E) on white (#FFFFFF)
- **Links**: MIT Cardinal Red, underlined on hover
- **Cards/borders**: Light gray (#E0E0E0) borders, subtle shadow on hover
- **Nav bar**: White background, thin bottom border, red underline on active page
- **Max content width**: 960px centered, generous whitespace

### Responsive Behavior
- **Desktop (≥1024px)**: Full nav bar, 3-column card grids, side-by-side layouts
- **Tablet (768–1023px)**: 2-column grids, slightly reduced spacing
- **Mobile (<768px)**: Hamburger menu, single-column stack, full-width cards

## Open Questions
- Domain: TBD — site will work at the default GitHub Pages URL initially; custom domain can be added later via CNAME file
