# Track 4: Digital Reading Room Brief

## Source and intent

This brief is derived from the July 2026 intern work-plan document, specifically
"Plan 4: Digital Reading Room." The source document is useful for capturing
program intent, but it should be treated as an informal reference rather than a
binding specification.

The original draft correctly identifies the core opportunity: archival material
held by the WWII Pacific War Memorial Hall, the U.S. National Archives and
Records Administration (NARA), and university partners is currently fragmented.
Researchers, students, and staff do not have a single interface for discovery,
context, and access review.

## Project goal

Create a digital reading room that brings together three archival source lines
under one interface:

- memorial hall holdings
- NARA-derived records
- university archive materials

The first release should let users browse, filter, and search structured
archive records while clearly distinguishing:

- the source institution
- whether a description is original or AI-assisted
- whether the underlying asset is publicly viewable

This is both a practical research-access project and a demonstrable program
asset for future grants, partnerships, and student-facing digital history work.

## What from the original plan is worth keeping

- Start with structured inventory work before UI implementation.
- Use a consistent record template for all sources.
- Keep original text alongside AI-assisted Chinese summaries or descriptions.
- Separate public access status from internal-only or pending-review material.
- Build iteratively: browse first, then search, then filtering.
- Reuse a common design system across related public-facing projects where that
  reduces maintenance cost.

## What should be corrected from the original plan

### 1. "Vibe coding" is a method, not a product requirement

The original document frames natural-language prototyping as a core project
feature. That may be a teaching method for interns, but it is not part of the
system's user-facing requirements. This repository should describe the product
in terms of capabilities, data rules, and operational safeguards.

### 2. The original field list is useful but incomplete

The draft field set is a strong start, but it does not yet cover:

- rights or access status in a precise, enforceable way
- record type and file format
- stable internal identifiers
- provenance notes
- linked asset locations
- review status for records not yet approved for publication

Without those fields, the system would be hard to govern and risky to publish.

### 3. Search alone is not enough

The original brief says "support classification browsing and keyword search,"
which is right, but researchers also need contextual browse paths. The MVP
should support both:

- source-based navigation
- theme/topic navigation
- direct keyword search

### 4. AI-generated text must never blur into primary-source text

The original plan mentions keeping the original text, which is good. We should
make that a hard rule: AI-assisted summaries, translations, or normalized
descriptions must always be labeled as derived content and never replace the
source record.

## Recommended MVP scope

### In scope

- a unified record model for the three source lines
- a structured dataset that can be loaded from JSON or a spreadsheet export
- list view, detail view, search, and filtering
- public/private/review status on each record
- support for links to external files instead of immediate full DAMS ingestion
- bilingual-aware display where source text and Chinese derived text can coexist

### Out of scope for MVP

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

## Core operating principle

No record should be published to the public interface unless its access status
is explicitly known. Unknown rights status defaults to non-public.

## Delivery strategy

### Phase 1: metadata and access control foundation

- define the record schema
- inventory the first source collection
- label access and review status
- build a small but clean seed dataset

### Phase 2: reading room MVP

- implement browse/search/filter/detail workflows
- expose only approved records
- test with a small set of researchers or students

### Phase 3: scale-out

- add more collections and partners
- improve metadata normalization
- consider richer ingest and discovery capabilities

## Immediate next repository artifacts

This brief should be paired with:

- a product requirement document in `docs/requirements/`
- an initial archive record schema in `collections/schemas/`

Those documents should drive architecture and implementation decisions rather
than the original informal work-plan text.
