## ADDED Requirements

### Requirement: Global Navigation
The site SHALL provide a persistent navigation bar on every page with links to Home, News, Talks, Team, Documentation (external), and GitHub (external).

#### Scenario: Visitor navigates between sections
- **WHEN** a visitor is on any page
- **THEN** the navigation bar is visible at the top of the page
- **AND** all navigation links are functional

#### Scenario: External links open in new tab
- **WHEN** a visitor clicks Documentation or GitHub links
- **THEN** the link opens in a new browser tab

### Requirement: Responsive Layout
The site SHALL render correctly on desktop (≥1024px), tablet (768–1023px), and mobile (<768px) viewports.

#### Scenario: Mobile viewport
- **WHEN** a visitor views the site on a mobile device
- **THEN** the navigation collapses into a hamburger menu
- **AND** all content is readable without horizontal scrolling

### Requirement: Institutional Footer
The site SHALL display a footer on every page with institutional logos or names (MIT, CERN, Fermilab), copyright notice, and the MIT License reference.

#### Scenario: Footer visibility
- **WHEN** a visitor scrolls to the bottom of any page
- **THEN** the footer displays affiliated institution names and a link to the project license

### Requirement: Minimal Professional Theme
The site SHALL use a clean, minimal visual design with a consistent color palette and typography appropriate for academic/research institutions.

#### Scenario: Visual consistency
- **WHEN** a visitor navigates across pages
- **THEN** the typography, colors, spacing, and layout structure remain consistent
