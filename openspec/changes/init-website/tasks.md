## 1. Project Scaffolding
- [x] 1.1 Initialize Jekyll project (`Gemfile`, `_config.yml`, `.gitignore`)
- [x] 1.2 Configure `_config.yml` with site metadata (title, description, base URL, GitHub Pages settings)
- [x] 1.3 Set up GitHub Pages deployment configuration

## 2. Site Layout & Theme
- [x] 2.1 Create base layout (`_layouts/default.html`) with `<head>`, navigation, content area, and footer
- [x] 2.2 Create navigation partial (`_includes/nav.html`) with links to all sections
- [x] 2.3 Create footer partial (`_includes/footer.html`) with institutional affiliations and license
- [x] 2.4 Write the site stylesheet (`assets/css/main.css`) — typography, colors, spacing, responsive breakpoints
- [x] 2.5 Implement responsive hamburger menu for mobile viewports

## 3. Homepage
- [x] 3.1 Create homepage (`index.html`) with project overview text
- [x] 3.2 Add key capabilities section
- [x] 3.3 Add institutional affiliation display
- [x] 3.4 Add quick links to docs, GitHub, and news
- [x] 3.5 Add Archi logo

## 4. News Section
- [x] 4.1 Create news listing page (`news.html`) with layout that iterates over `site.posts`
- [x] 4.2 Create post layout (`_layouts/post.html`) for individual news posts
- [x] 4.3 Add seed news posts in `_posts/` (website launch + CERN seminar)

## 5. Talks Page
- [x] 5.1 Create `_data/talks.yml` with seed data (CERN EP-IT seminar, March 2026)
- [x] 5.2 Create talks page (`talks.html`) that renders entries from the YAML data file
- [x] 5.3 Support optional resource links (slides, recording, event page)

## 6. Team Page
- [x] 6.1 Create `_data/team.yml` with seed team member entries
- [x] 6.2 Create team page (`team.html`) that renders members grouped by institution
- [x] 6.3 Handle optional photos with placeholder/initials fallback

## 7. Final Polish
- [x] 7.1 Verify all internal and external links work
- [x] 7.2 Test responsive layout at desktop, tablet, and mobile breakpoints
- [x] 7.3 Verify local build with `bundle exec jekyll serve`
- [x] 7.4 Add a `README.md` with instructions for contributing content (adding posts, talks, team members)
