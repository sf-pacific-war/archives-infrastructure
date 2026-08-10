# Archives Infrastructure

Institutional repository for the digital archives, metadata standards, research infrastructure, and technical planning of the WWII Pacific War Memorial Hall.

## Purpose

This repository is intended to serve as the long-lived institutional home for:

- program planning and requirements
- architecture and implementation decisions
- metadata and description standards
- collection schemas and controlled vocabularies
- external integrations and ingest workflows
- research notes that inform infrastructure design

## Repository Structure

```text
docs/
  program/         Program framing, strategy, and roadmap materials
  requirements/    Product, platform, and operational requirements
  architecture/    System architecture, diagrams, and technical design
  standards/       Metadata, preservation, and interoperability standards
  decisions/       Decision records and governance history
  meetings/        Meeting notes and working-session documentation
  research/        Background research, benchmarking, and references

collections/
  schemas/         Collection data models and field definitions
  authorities/     Authority files and identity control
  vocabularies/    Controlled vocabularies and taxonomies
  crosswalks/      Field mappings between systems and standards

integrations/
  nara/            National Archives-related integration notes and scripts

scripts/           Utility scripts for validation, transformation, and ingest
```

## Working Principles

- Treat this repository as institutional memory rather than personal scratch space.
- Prefer documenting decisions in writing before implementation becomes hard to reverse.
- Keep standards, mappings, and schemas versioned alongside the code that depends on them.
- Use plain-language README files so new volunteers, interns, and collaborators can onboard quickly.

## Suggested Next Milestones

1. Add the current program requirement/design document into `docs/program/`.
2. Draft an initial metadata and interoperability outline in `docs/standards/`.
3. Define the first collection schema in `collections/schemas/`.
4. Create the GitHub organization profile repository `.github` under `sf-pacific-war`.
