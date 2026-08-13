# SF Pacific War Archives Infrastructure Project Repository

Institutional repository for the WWII Pacific War Memorial Hall's SF Pacific
War Archives Infrastructure Project.

This repository is not for code (not an app product repo). It is the version-controlled workspace for program documentation, technical planning, metadata models, schema decisions, and the institutional history of how the digital archives program progresses.

## What This Repository Is For

This repository is intended to serve as the long-lived institutional home for:

- program planning and scope definition
- requirements, architecture, and standards
- decision history and meeting notes
- collection schemas, vocabularies, authorities, and crosswalks
- sample data and validation artifacts
- scripts and lightweight technical utilities
- app boundary definitions, interface notes, and prototype references

## What This Repository Is Not For

This repository should not be treated as the archival storage system itself.
Do not use GitHub as the default home for:
- TIFF masters
- WAV oral-history masters
- large MP4 preservation files
- restricted donor materials
- sensitive records
- copyrighted source files without a clear publication basis

GitHub stores how the project works. Preservation and access systems store the
archival objects themselves.

## Program Tracks

## Repository Structure

```text
docs/
  planning/        Program scope, track definitions, requirements, and setup notes
  architecture/    System architecture, models, and technical design
  standards/       Metadata, digitization, rights, and interoperability standards
  decisions/       ADRs and governance history
  meetings/        Meeting notes and working-session documentation
  research/        Benchmarking, source-system notes, and background research

collections/
  schemas/         Collection data models and schema drafts
  authorities/     Authority control assets
  vocabularies/    Controlled vocabularies and taxonomies
  crosswalks/      Field mappings between local and external systems
  sample-data/     Small non-sensitive example datasets

apps/
  collections-management/  App boundary and integration notes
  digital-reading-room/    Public access application notes and references

integrations/
  nara/            National Archives-related integration notes and scripts

scripts/           Utility scripts for validation, transformation, and ingest
tests/             Validation and fixture-oriented checks for repo-managed assets
.github/           Repository workflow templates and collaboration defaults
```

## How To Use This Repository

A new volunteer or intern should be able to enter through:

1. this README
2. the relevant planning document under `docs/planning/`
3. related standards, decisions, and research notes
4. an assigned GitHub Issue or pull request

The goal is to prevent project knowledge from living only in chat threads,
meeting memory, or scattered Google Docs.

## Working Principles

- Treat this repository as institutional memory rather than personal scratch
  space.
- Prefer written requirements and ADRs before implementation becomes hard to
  reverse.
- Keep schemas, mappings, and standards versioned alongside the scripts and
  documentation that depend on them.
- Separate meeting notes from decisions: meetings record discussion; ADRs record
  the final choice.
- Keep public-facing app ideas documented here even when the production app
  later lives in another repository.

## Current Focus

The repository now has initial scoping artifacts at both the umbrella-program
and track-specific levels:

- an umbrella planning document for the overall program
- a Track 4 planning document
- a scope-boundaries note mapping this project against the earlier intern plan
- a record-schema draft under `collections/schemas/`
- organization/repository setup guidance under `docs/planning/`

Key current documents:

- `docs/planning/sf-pacific-war-archives-infrastructure-project.md`
- `docs/planning/track-4-digital-reading-room.md`
- `docs/planning/archives-infrastructure-scope-boundaries.md`
- `docs/planning/github-organization-setup.md`
