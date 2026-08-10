# Pacific War Digital Collections & Archives Program

## Updated scoping and requirements draft

This document translates the umbrella program framing into practical scope and
requirements language. It is intended to support stakeholder discussion,
requirements review, and later decomposition into implementation issues and
track-level plans.

## Scope statement

The program covers the workflows, metadata structures, interoperability rules,
and access products needed to support digital collections related to the WWII
Pacific War Memorial Hall and selected partner archives.

The program does **not** assume that all assets will be ingested into one
system, nor that the institution already operates a full preservation-grade
digital archive. This is a staged infrastructure program.

## Primary objectives

1. Create a coherent institutional framework for local digital collections work.
2. Enable structured description and governance of local and linked archival
   records.
3. Support discovery across local and external archival sources.
4. Deliver a public-facing reading-room experience for approved records.
5. Preserve the useful intent of the earlier intern work plan without inheriting
   its weaker design assumptions.

## Track-level scope and requirements

### Track 1 — Collection Inventory & Digitization

#### Scope

Track 1 covers local holdings and born-digital assets that need to be inventoried,
organized, assessed, and prioritized for digitization or cleanup.

This includes:

- exhibition materials
- photographs
- documents and scans
- oral-history materials
- video and audio assets
- born-digital website/history content where institutionally relevant

#### Requirements

- The program must maintain a structured inventory of local materials.
- Each inventory entry must support at least:
  - stable local identifier
  - title or working label
  - asset type/format
  - language
  - current storage location
  - digitization status
  - access/rights status
  - notes on condition or follow-up needs
- The inventory must distinguish:
  - already-digitized material
  - analog-only material
  - born-digital material
  - material pending rights review
- The program should support digitization prioritization based on research value,
  exhibition value, condition, and public-access potential.

#### Key outputs

- inventory worksheet or dataset
- digitization priority queue
- first set of normalized local records for downstream tracks

### Track 2 — Digital Collections Management & Archival Description

#### Scope

Track 2 covers how local records are described, governed, normalized, and made
usable across downstream systems.

#### Requirements

- The program must define a local archival record model.
- Record description must support:
  - stable identifiers
  - title and original title where relevant
  - source/provenance
  - date or date range
  - record type
  - descriptive summary
  - original/source text where available
  - rights/access status
  - review/publication status
  - tags/themes and named entities as appropriate
- The program must distinguish source text from AI-assisted translation,
  summary, or normalization.
- The program must support internal review before public release.
- The program should be able to model different local material types without
  forcing all of them into one over-simplified template.

#### Key outputs

- local description schema
- record templates and field guidance
- review workflow for publishable versus non-public records

### Track 3 — External Archives Metadata Aggregation & Interoperability

#### Scope

Track 3 covers representation of relevant materials from outside institutions
such as NARA and university archives.

The emphasis is on discoverability and contextual linkage, not on claiming local
custody over partner-held assets.

#### Requirements

- The program must preserve the identity of the source institution for each
  external record.
- External records must retain source identifiers or call numbers where
  available.
- The program must document how external fields map into the local discovery
  profile.
- The system must support link-out patterns for externally held materials.
- The program should be able to distinguish:
  - locally held digital objects
  - locally described but externally held objects
  - records included only for discovery context
- Interoperability work should begin with a small, auditable sample rather than
  a large opaque import.

#### Key outputs

- field crosswalks
- source-specific aggregation notes
- a small mapped external sample set

### Track 4 — Digital Reading Room: Discovery & Access

#### Scope

Track 4 covers the public- or researcher-facing access layer for approved
records.

#### Requirements

- Users must be able to browse by source and theme.
- Users must be able to search across structured descriptive fields.
- Users must be able to filter by at least source, type, and access-ready
  record status.
- Each record detail page must present:
  - title
  - identifier
  - source institution
  - source record identifier where relevant
  - date
  - type/format
  - descriptive text
  - original/source text where relevant
  - rights/access context
  - asset link or access reference
- The interface must clearly label AI-assisted content.
- Non-public or not-yet-approved records must not appear in the public release.
- The experience must remain usable on both desktop and mobile.

#### Key outputs

- reading-room prototype
- approved seed dataset powering the prototype
- public discovery rules for release readiness

## Cross-track requirements

### Rights and access governance

- Unknown rights status defaults to non-public.
- Rights review and editorial review must not be conflated.
- Public availability must be an explicit state, not an assumption.

### AI use and labeling

- AI may assist with translation, summary, normalization, or cleanup.
- AI-derived text must be labeled as derived.
- Original or source-supplied text should remain visible when available.

### Bilingual and multilingual handling

- The program should assume at least Chinese and English descriptive needs.
- The first release does not need to fully solve every multilingual workflow,
  but the schema and interface must not block that future.

### Lightweight-first technical approach

- The first release may use JSON, CSV export, or spreadsheet-backed structured
  data.
- A complex database or DAMS is not required for the first working version.

## Coverage of the earlier intern plan

This section shows how the earlier intern plan is preserved, transformed, or
excluded.

| Earlier intern-plan item | Updated treatment |
| --- | --- |
| Historical website content archive | Included, but redistributed across Track 1, Track 2, and selected Track 4 public outputs. |
| AI voice guide | Not a core track in the current archives-program scope. Treated as a downstream interpretation product enabled by better collections data. |
| Volunteer mobile platform | Not included as a core archives-program track. Should be reconsidered as a separate operations/workflow project unless scope is intentionally expanded. |
| Digital reading room | Included directly as Track 4, with enabling work moved into Tracks 1 to 3. |
| Three-source integration | Preserved and strengthened through Track 3 plus Track 4 discovery requirements. |
| Structured archival record fields | Preserved and expanded through Track 2 and the schema drafts. |

## Out of scope for the current program draft

- full preservation-storage architecture implementation
- enterprise DAMS selection
- volunteer operations tooling as a core program requirement
- QR voice-guide production as a core program requirement
- large-scale automated harvesting before metadata rules are stable
- public release of materials with unclear rights

## Revisit items from the original design

The original design ideas were useful, but the following items should remain
explicit discussion points rather than implicit assumptions:

1. Whether the historical website archive is a collections problem, a web
   publishing problem, or both.
2. Whether the voice-guide project should be formally attached as a later public
   interpretation track.
3. Whether volunteer-generated content should feed archival ingest and, if so,
   through what workflow.
4. Whether the institution needs a separate preservation/storage roadmap before
   public access expands.
5. How much external metadata aggregation should be manual curation versus
   automated interoperability in the first year.
6. Whether the reading room should initially emphasize curated collections over
   general search breadth.
7. Which parts of the original intern plan were framed as implementation method
   rather than actual product requirement.

## Recommended next steps

1. Review and approve the umbrella program name and four-track structure.
2. Confirm which earlier intern-plan items are core, adjacent, or out of scope.
3. Continue drafting track-specific requirements beginning with Track 1 and
   Track 2, while retaining the existing Track 4 requirement draft.
4. Convert approved requirements into GitHub Issues, ADRs, schema tasks, and
   prototype work.
