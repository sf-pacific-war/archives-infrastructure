# GitHub Organization Setup

This document captures the initial GitHub organization structure for the WWII
Pacific War Memorial Hall digital archives program.

## Organization

- GitHub organization handle: `sf-pacific-war`
- Intended display name: `WWII Pacific War Memorial Hall`
- Ownership model: organization-owned repositories managed by
  institution-affiliated contributors using their personal GitHub accounts

## Recommended Organization Profile

Set the GitHub organization profile to the following baseline values:

- Name: `WWII Pacific War Memorial Hall`
- Description: `Digital archives, collections, research infrastructure, and public history projects of the WWII Pacific War Memorial Hall in San Francisco.`
- Location: `San Francisco, California`
- Website: official museum website
- Logo: institution logo or memorial hall mark

## Organization Profile README Draft

Create a public repository named `.github` under the organization and place the
following content in `.github/profile/README.md`.

```md
# WWII Pacific War Memorial Hall

The WWII Pacific War Memorial Hall develops digital archives, historical
collections, and public-history resources related to the Pacific War and
Chinese American historical memory.

## Digital Archives & Research Infrastructure

Our digital archives program supports collection digitization, archival
description, preservation, cross-institutional discovery, and public research
access.

## Projects

- SF Pacific War Archives Infrastructure Project
- Digital Reading Room
```

## Initial Repository Plan

Recommended first-phase repositories:

1. `.github`
2. `archives-infrastructure`
3. `digital-reading-room` when public application development begins

The current local repository is structured to serve as the starting point for
`archives-infrastructure`.

## Rationale

- institutional repositories preserve organizational memory beyond any single
  volunteer or staff member
- permissions can be delegated through organization membership, teams, and
  repository roles
- public-facing documentation can remain stable even as contributors change
- standards, decisions, and architecture documents become institutional assets
  instead of personal notes

## Immediate Next Steps

1. Create `sf-pacific-war/archives-infrastructure` on GitHub.
2. Add this local repository as the remote for that organization-owned
   repository.
3. Commit the initial structure and push the first version.
4. Create the `.github` organization profile repository and publish the profile
   README.
