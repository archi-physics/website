## ADDED Requirements

### Requirement: News Post Listing
The site SHALL display a chronologically ordered list of news posts (newest first) on a dedicated News page, showing each post's title, date, and excerpt.

#### Scenario: Visitor browses news
- **WHEN** a visitor navigates to the News page
- **THEN** they see a list of posts ordered by date (newest first)
- **AND** each entry shows the title, publication date, and a short excerpt

### Requirement: News Post Detail
Each news post SHALL have its own page with the full content, rendered from Markdown with YAML front matter.

#### Scenario: Visitor reads a full post
- **WHEN** a visitor clicks a news post title
- **THEN** they are taken to the full post page with title, date, and complete content

### Requirement: Jekyll Posts Integration
News posts SHALL use Jekyll's `_posts/` directory convention with filenames in `YYYY-MM-DD-title.md` format and YAML front matter for metadata (title, date, author, excerpt).

#### Scenario: Author creates a new post
- **WHEN** a contributor adds a Markdown file to `_posts/` with correct naming and front matter
- **THEN** the post appears on the News page after the site is rebuilt
