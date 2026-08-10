# Pacific War Digital Collections & Archives Program

*Chinese working title: 太平洋战争数字馆藏与档案计划*

## Purpose of this document

This document reframes the earlier intern project planning material into a
program-level scoping brief that is suitable for stakeholder discussion,
repository planning, and future requirements work.

It intentionally treats the earlier intern plan as source material, not as a
final design specification. The intern plan surfaced several useful needs, but
it mixed together:

- archival infrastructure work
- public-facing access products
- interpretation and education features
- internal operational tooling

This updated scoping document separates those concerns into a cleaner program
structure.

## Recommended umbrella name

**Primary recommendation**

`Pacific War Digital Collections & Archives Program`

This is the strongest umbrella name for the current phase because it:

- is broad enough to cover all four tracks
- does not reduce the entire effort to the digital reading room alone
- does not overstate the current maturity of the institution's archival system
- works for technical planning, stakeholder communication, and future scaling

**Formal institutional variant**

`WWII Pacific War Memorial Hall Digital Collections & Archives Program`

This variant is appropriate when the institution name should be explicit in
formal or external-facing contexts.

**Alternative grant-oriented naming**

- `Pacific War Digital Archives & Research Infrastructure Initiative`
- `Pacific War Digital History & Archives Initiative`

These may be stronger in future grant or university-collaboration settings, but
for the current repository and scoping phase, `Digital Collections & Archives
Program` is the clearest choice.

## Program statement

The program's purpose is to build the institutional foundations needed to
inventory, describe, connect, and responsibly provide access to digital
collections related to the WWII Pacific War Memorial Hall and its surrounding
research ecosystem.

The program is not just a website project. It is a multi-track effort combining
collection preparation, metadata design, interoperability planning, and public
access delivery.

## Program tracks

### Track 1 — Collection Inventory & Digitization

**Chinese label:** 馆藏盘点与数字化

This track covers the identification, inventory, prioritization, and
digitization of local collection materials and born-digital assets.

Representative concerns:

- what the institution actually holds
- what has already been digitized
- what is still analog or poorly organized
- what can be publicly shown and what cannot
- which materials should be digitized first

### Track 2 — Digital Collections Management & Archival Description

**Chinese label:** 数字馆藏管理与档案著录

This track covers the structured management and description of local digital
records after inventory. It includes metadata, descriptive practice, authority
control, provenance, bilingual handling, and review workflows.

Representative concerns:

- how a record should be described
- what fields are required
- how original text and AI-assisted text are distinguished
- how rights, review, and public-display status are tracked

### Track 3 — External Archives Metadata Aggregation & Interoperability

**Chinese label:** 外部档案元数据聚合与互操作

This track covers metadata aggregation and mapping for materials held by outside
institutions such as NARA and university archives. The goal is not immediate
ownership transfer, but structured discovery and context across systems.

Representative concerns:

- how to represent external holdings in a local discovery layer
- how to preserve source identifiers and provenance
- how to map external metadata into a local profile
- when to link out versus copy or ingest

### Track 4 — Digital Reading Room: Discovery & Access

**Chinese label:** 数字阅览室：检索、发现与访问

This track covers the user-facing discovery interface where approved records can
be browsed, searched, filtered, and opened through structured detail pages.

Representative concerns:

- public discovery and research access
- record detail views
- multilingual presentation
- search and filtering
- clear distinction between source text and derived text

## Why this is better than using "Digital Reading Room" as the whole project name

The original project language leaned heavily on the "digital reading room"
concept. That is useful, but only for the fourth track.

If the entire program is called a digital reading room, it blurs several
important distinctions:

- inventory and digitization work look optional when they are actually
  foundational
- metadata and archival-description work disappear behind the interface
- external interoperability work gets treated as part of one app feature rather
  than a separate data problem
- internal governance and review workflows become invisible

The reading room should be treated as a public-facing product enabled by the
first three tracks, not as the whole program.

## Relationship to the earlier intern plan

The earlier intern plan contained four project ideas:

1. historical website content archive
2. AI voice guide
3. volunteer mobile platform
4. digital reading room

Those ideas remain useful, but they need to be redistributed across the updated
program model.

### What is directly incorporated

**Historical website content archive**

This requirement is still valid, but it is no longer treated as a standalone
website-only project. Its useful components now live across:

- Track 1: inventory of born-digital and exhibition-history materials
- Track 2: structured description of those materials
- Track 4: possible public discovery or showcase surfaces for approved records

**Digital reading room**

This remains fully in scope, but it is now correctly positioned as Track 4
rather than as the umbrella concept for the whole program.

**Three-source archival integration**

The original intent to bring together memorial hall, NARA, and university
materials is preserved, but split more cleanly:

- Track 2 handles local description standards
- Track 3 handles external metadata aggregation and mapping
- Track 4 delivers discovery and access

### What is only partially incorporated

**AI voice guide**

This is still a strong future-facing use case, but it is better treated as a
dependent interpretation product rather than a core archival-infrastructure
track.

The archives program should support it by making assets, descriptions, and
multilingual metadata easier to manage. But QR workflows, TTS production, and
onsite visitor experience design are not core requirements of the present
archives-program scope.

### What is currently outside the core program scope

**Volunteer mobile platform**

This appears to be an internal operations and workflow tool rather than a core
digital-collections track. It may become an adjacent project or integration
later, especially if volunteer-created content contributes to collections
capture, but it should not sit inside the core archives-program umbrella unless
the scope is intentionally expanded.

## Program goals

### Near-term goals

- establish a shared program structure for stakeholders
- define the difference between local collections work and public access work
- create initial schemas, requirements, and sample data
- produce an MVP path for the digital reading room without skipping metadata and
  governance foundations

### Medium-term goals

- inventory and normalize a first tranche of local materials
- model selected external holdings for unified discovery
- ship a lightweight reading-room MVP using structured records

### Long-term goals

- support future grant applications and university collaboration
- create sustainable institutional memory around digital collections work
- enable future interpretation products, research tools, and public history
  initiatives

## Suggested program sequencing

### Phase 0 — Scope and standards

- confirm track boundaries
- approve naming
- define high-level requirements and governance principles

### Phase 1 — Local collections foundation

- inventory local holdings
- establish descriptive schema and review workflow
- prepare a seed dataset of publishable records

### Phase 2 — External metadata and access prototype

- map a small external sample set
- document crosswalk assumptions
- build a reading-room prototype using approved records

### Phase 3 — Controlled public release

- expand source coverage
- refine search, browse, and bilingual presentation
- test with researchers, students, and institutional stakeholders

## Core program principles

- No record is public by default.
- Unknown rights status defaults to non-public.
- AI-derived text must never silently replace source text.
- Public access should be built on structured records, not ad hoc page copying.
- The repository documents how the program works; it is not the preservation
  storage system itself.

## Revisit list

The following questions should be carried forward explicitly rather than buried
inside implementation:

1. Should historical exhibitions be modeled as records, collections, web
   features, or a mix of all three?
2. Should the AI voice guide become a separate interpretation track later?
3. Should volunteer data capture become a separate operational systems project?
4. What level of bilingual support is required in the first release versus
   later phases?
5. How formal does the rights-review workflow need to be before any public
   launch?
6. Should external archives start with manual curated aggregation or more
   automated interoperability work?
7. When should preservation-storage architecture become its own explicit track
   rather than an implicit background concern?

## Recommended next repository documents

- a program-level scoping and requirements document under `docs/requirements/`
- track-specific requirement documents, starting with Track 4
- standards documents for description, rights, and digitization
- ADRs when major architecture or governance decisions are made
