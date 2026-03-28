## ADDED Requirements

### Requirement: Talks Listing
The site SHALL display a list of talks and presentations on a dedicated Talks page, ordered by date (newest first), with each entry showing the title, speaker, event/venue, and date.

#### Scenario: Visitor browses talks
- **WHEN** a visitor navigates to the Talks page
- **THEN** they see a list of talks with title, speaker, event name, and date

### Requirement: Talk Resource Links
Each talk entry SHALL support optional links to slides, recordings, and event pages (e.g., Indico).

#### Scenario: Visitor accesses talk materials
- **WHEN** a talk has associated slides or a recording
- **THEN** the talk entry displays clickable links to those resources

#### Scenario: Talk without resources
- **WHEN** a talk has no slides or recording linked
- **THEN** the talk entry displays without resource links and no broken UI elements

### Requirement: Data-Driven Talks
Talks SHALL be defined in a YAML data file (`_data/talks.yml`) with fields for title, speaker, date, event, event_url, slides_url, and recording_url.

#### Scenario: Maintainer adds a new talk
- **WHEN** a contributor adds a new entry to `_data/talks.yml`
- **THEN** the talk appears on the Talks page after the site is rebuilt
