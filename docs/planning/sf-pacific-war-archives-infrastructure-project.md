# SF Pacific War Archives Infrastructure Project

## Purpose

This is the umbrella framing document for the archives infrastructure program.
It defines overall scope, the four program tracks, the architectural lens, and
the cross-track principles. Detailed requirements belong in track-level
planning documents rather than here.

## Scope

The program covers four kinds of work:

- collection inventory, digitization, and preservation readiness
- collections metadata, archival description, and governance
- external archival interoperability and cross-institution discovery
- discovery, retrieval, and AI-assisted access through a digital reading room

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
records after inventory, including metadata, provenance, bilingual handling,
authority control, and review workflows.

Representative concerns:

- how a record should be described
- what fields are required
- how original text and AI-assisted text are distinguished
- how rights, review, and public-display status are tracked

### Track 3 — External Archives Metadata Aggregation & Interoperability

**Chinese label:** 外部档案元数据聚合与互操作

This track covers metadata aggregation and mapping for materials held by outside
institutions such as NARA and university archives. The goal is structured
discovery and context across systems, not immediate ownership transfer.

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

## Architecture lens

The same program can also be read through four connected architectural
concerns:

- `Preservation`: files, fixity, storage evidence, preservation metadata, and
  durable stewardship
- `Collections`: canonical metadata, hierarchy, provenance, rights, review
  status, and governed descriptive truth
- `External archival interoperability and cross-discovery`: mappings,
  identifiers, APIs, partner-held records, and cross-institution retrieval
- `Discovery and AI`: search, multilingual access, hybrid retrieval, and
  AI-assisted enrichment built on the layers below

This is a planning lens, not a requirement to implement one literal diagram or
one exact software decomposition. Some of these concerns may later live in the
same software system; they still need to remain conceptually distinguishable.

## Cross-track principles

- the canonical record remains the source of truth
- provenance, rights, and review state must remain explicit
- discovery and AI outputs must remain derived, replaceable, and distinguishable
  from source truth
- LLMs may interpret or enrich records, but must not rewrite original records
- public access must be built on structured records rather than ad hoc pages
