# Change: Initialize Archi project website

## Why
Archi needs a professional, modern project website to replace the outdated WordPress site at ppc.mit.edu/a2/. The site must represent the project's institutional affiliations (MIT, CERN, Fermilab) and serve as the central hub for project news, talks, team information, and links to source code and documentation. GitHub Pages provides free, low-maintenance hosting with version-controlled content.

## What Changes
- Initialize a Jekyll-based static site for GitHub Pages deployment
- Create a responsive, minimal site layout with global navigation and footer
- Build a homepage with project overview, key capabilities, and institutional branding
- Add a news/blog section using Jekyll posts
- Add a talks page for linking to presentations, recordings, and slides
- Add a team page with member profiles, roles, and institutional affiliations
- Configure GitHub Pages deployment from the `main` branch

## Impact
- Affected specs: `site-layout`, `homepage`, `news`, `talks`, `team` (all new)
- Affected code: Entire repository (greenfield)
- No breaking changes (new project)
