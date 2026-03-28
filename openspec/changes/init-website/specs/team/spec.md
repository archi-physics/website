## ADDED Requirements

### Requirement: Team Member Listing
The site SHALL display team members on a dedicated Team page, showing each member's name, role, institutional affiliation, and optionally a photo and personal/profile URL.

#### Scenario: Visitor views the team
- **WHEN** a visitor navigates to the Team page
- **THEN** they see a grid or list of team members with names, roles, and affiliations

### Requirement: Institutional Grouping
The Team page SHALL organize members by institution or role category to make the collaborative nature of the project clear.

#### Scenario: Members grouped by institution
- **WHEN** a visitor views the Team page
- **THEN** members are visually grouped (e.g., by institution: MIT, CERN, Fermilab, etc.)

### Requirement: Data-Driven Team
Team members SHALL be defined in a YAML data file (`_data/team.yml`) with fields for name, role, institution, photo (optional), url (optional), and github (optional).

#### Scenario: Maintainer adds a new team member
- **WHEN** a contributor adds a new entry to `_data/team.yml`
- **THEN** the member appears on the Team page after the site is rebuilt

#### Scenario: Member without photo
- **WHEN** a team member entry has no photo specified
- **THEN** a placeholder or initials avatar is displayed
