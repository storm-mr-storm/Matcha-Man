---
title: "Matcha Man changelog"
type: governance
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [governance, changelog]
---

# Matcha Man changelog

Meaningful changes to the accepted product design system are recorded here. Current release: [[06 Decisions/VERSION|VERSION]]. Rationale: [[Decision log]]. Version policy: [[01 Rule strength and source of truth#Versioning and change records]].

## [Unreleased]

No unreleased changes recorded.

## [0.1.0] — 2026-09-18

First formally tracked Matcha Man design-system version. The system existed before version tracking was introduced.

### Added

- Formal version tracking and this changelog, retaining the existing decision log and ADR history.
- Accepted [[ADR-011 Radius-aware table spacing]].

### Changed

- Standardized [[Table]] spacing around the preserved 40px shell: 24px outer inset / 12px cell inline padding / 16px normal row padding / 24px exposed-boundary clearance, plus a 4px primary-cell gap.
- Defined title-band and standalone-table boundary ownership separately from internal row density.

### Fixed

- Reconciled the canonical Table note and LLM summary with the accepted spacing decision; marked the earlier implementation proposal superseded.
