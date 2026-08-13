# Track 4: Digital Reading Room

## Purpose

This document defines the track-level requirements for the digital reading
room. Unlike the umbrella program document, this file is intended to carry the
detail needed for planning and implementation.

## Scope

Create a digital reading room that brings together three archival source lines
under one discovery interface:

- memorial hall holdings
- NARA-derived records
- university archive materials

The first release should let users browse, filter, and search structured
archive records while clearly distinguishing:

- the source institution
- whether text is original or AI-assisted
- whether the underlying asset is publicly viewable

### In scope

- a unified record model for the three source lines
- a structured dataset that can be loaded from JSON, CSV export, or spreadsheet
  export
- list view, detail view, search, and filtering
- public/private/review status on each record
- support for links to external files instead of immediate full DAMS ingestion
- bilingual-aware display where source text and Chinese derived text can
  coexist

### Out of scope for the first release

- full-text OCR indexing across all scans
- complex role-based user accounts
- bulk ingest automation from every source system
- IIIF manifests, viewers, or preservation packaging
- citation export, annotation, or collaborative research tools
- automatic publication of unreviewed records

## Primary users

- internal staff preparing exhibitions, grant materials, and programming
- student researchers in digital/oral history contexts
- external researchers using public, approved records
- editors or reviewers checking metadata quality and access rights

## Success criteria

The first release is successful if a user can:

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

The first release may read structured record data from a simple source such as:

- JSON
- exported CSV
- Google Sheets export

The reading room does not require a complex database if a flat structured source
is sufficient for the first release.

## Non-functional requirements

### Governance and safety

- Unknown rights status must default to non-public.
- AI-derived text must never overwrite source text.
- The schema must support audit-friendly review fields.

### Usability

- The interface must work on both desktop and mobile browsers.
- Search and browse should remain understandable for non-technical users.

### Maintainability

- Record fields must map cleanly to a documented schema.
- The application should be able to add new source collections without
  redesign.

### Performance

- Typical record list and detail pages should load quickly on ordinary consumer
  connections.
- The first release should prefer lightweight linked assets over heavy embedded
  viewers.

## Open questions

- exact theme taxonomy
- final access-status vocabulary
- whether dates need one field or both display and normalized variants
- whether person/place entities should be modeled now or later
- whether the first implementation will read JSON directly or use a generated
  export from a spreadsheet workflow

## Dependencies

This track depends on:

- local record schema work under `collections/schemas/`
- Track 1 inventory work
- Track 2 description/governance work
- Track 3 external metadata mapping where partner records are involved
