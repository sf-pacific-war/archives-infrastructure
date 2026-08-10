# Track 4: Digital Reading Room Requirements

## Status

Drafted on August 10, 2026 from the July 2026 intern planning document and
aligned to this repository's institutional-architecture goals.

## Problem statement

Archival materials relevant to the WWII Pacific War Memorial Hall are spread
across at least three source lines:

- memorial hall holdings
- NARA records
- university archive materials

Potential readers do not currently have one place to discover what exists,
understand provenance, read contextual metadata, and determine whether an item
is available for public viewing.

## Product objective

Deliver a first working digital reading room that allows users to:

- browse records by source and theme
- search by keyword, title, or person name
- filter by source, format, era/date, and access status where appropriate
- open a detail page with structured context for each record
- distinguish original source text from AI-assisted derived text

## MVP success criteria

The MVP is successful if a user can do the following from one interface:

1. Find records from all three source lines without switching systems.
2. Tell where a record came from and whether it is approved for public access.
3. Read a structured summary without losing sight of the original source text.
4. Retrieve records through both browsing and search.
5. Use the experience on desktop and mobile without layout or navigation
   failure.

## Functional requirements

### 1. Record browsing

The system must provide browse paths for:

- source institution
- theme/topic
- optionally format type if enough data exists

### 2. Search

The system must provide keyword search over at least these fields:

- title
- Chinese summary/description
- original title/description
- tags
- names when present in structured fields or searchable text

### 3. Filtering

The system must allow filtering by:

- source institution
- record format/type
- access status
- era/date range when the date field is available in normalized form

### 4. Record detail view

Each record detail page must display structured metadata and clearly labeled
content sections. At minimum the page must support:

- title
- stable record identifier
- source institution
- source call number or original identifier where available
- normalized or display date
- format/type
- access status
- review/publication status
- Chinese summary or description
- original title or original description
- tags/topics
- asset link or location reference

### 5. Access and publication control

Each record must carry a publication/access state. Minimum supported states:

- `public`
- `internal_only`
- `restricted`
- `pending_rights_review`
- `pending_editorial_review`

Public UI must exclude records that are not explicitly approved for public
display.

### 6. AI-derived content labeling

If a record contains AI-assisted translation, summary, normalization, or
description, the interface must label that content as derived. Original text
must remain separately visible when available.

### 7. Data source model

The MVP may read structured record data from a simple source such as:

- JSON
- exported CSV
- Google Sheets export

The MVP does not require a complex database if a flat structured source is
sufficient for the first release.

## Non-functional requirements

### 1. Governance and safety

- Unknown rights status must default to non-public.
- AI-derived text must never overwrite source text.
- The schema must support audit-friendly review fields.

### 2. Usability

- The interface must work on both desktop and mobile browsers.
- Search and browse should remain understandable for non-technical users.

### 3. Maintainability

- Record fields must map cleanly to a documented schema.
- The application should be able to add new source collections without
  redesign.

### 4. Performance

- Typical record list and detail pages should load quickly on ordinary consumer
  connections.
- The first release should prefer lightweight linked assets over heavy embedded
  viewers.

## Data requirements

The MVP requires a normalized archive record schema with:

- mandatory core identity fields
- provenance/source fields
- rights and review fields
- descriptive fields
- display/support fields

The initial schema draft is stored separately under `collections/schemas/`.

## Recommended first-release dataset strategy

Do not start by mixing all three sources at once.

Recommended order:

1. memorial hall holdings with the cleanest available metadata
2. a small NARA sample set
3. university partner material after rights and metadata conditions are clearer

This sequencing reduces risk and helps validate the schema before scale.

## Explicit exclusions for MVP

The following are intentionally excluded unless requirements change:

- automated OCR/transcription pipelines
- user accounts and researcher workspaces
- public comments or annotations
- complex media streaming or preservation workflows
- advanced linked-data interoperability

## Acceptance checklist

- Records from all intended source lines can appear in one interface.
- Public records are clearly distinguished from non-public or pending items.
- Search returns relevant records from structured fields.
- Detail pages show both context and provenance.
- AI-derived content is visibly labeled and separated from original text.
- Mobile browsing is functional and readable.

## Open decisions

- exact theme taxonomy
- final access-status vocabulary
- whether dates need one field or both display and normalized variants
- whether person/place entities should be modeled now or later
- whether the first implementation will read JSON directly or use a generated
  export from a spreadsheet workflow
