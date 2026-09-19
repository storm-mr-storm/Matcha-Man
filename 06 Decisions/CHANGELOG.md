---
title: "Matcha Man changelog"
type: governance
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [governance, changelog]
---

# Matcha Man changelog

Meaningful changes to the accepted product design system are recorded here. Current release: [[06 Decisions/VERSION|VERSION]]. Rationale: [[Decision log]]. Version policy: [[01 Rule strength and source of truth#Versioning and change records]].

## [Unreleased]

Accepted canonical guidance; **MINOR candidate** under the existing policy for meaningful design/component refinements. The released version remains **v0.1.0** until an explicit release is cut. Implementation adoption and acceptance are recorded separately.

### Changed

- 2026-09-19: Formalized [[Product design philosophy#Opinionated defaults|Opinionated defaults]] as implementation requirements for products and agents; deliberate product exceptions are documented locally rather than silently changing the system.
- 2026-09-19: Expanded [[ADR-011 Radius-aware table spacing]] to canonically accept **24px major boundary / 16px nested surface / 12px dense internal / 4–8px relational spacing** and shared content-axis behavior. Preserved the intentional 40px radius and efficient Table interiors with additional clearance only at exposed boundaries. See [[Spacing and layout]], [[Shape and geometry]], and [[Table]].
- 2026-09-19: Clarified [[ADR-012 Accessible Select listbox implementation]] as the system-wide [[Select]] default: designed trigger + rounded listbox, 16px chevron edge clearance, 16px menu radius, 8px menu padding/offset, and the existing **8px option radius** with intentional selected/hover/focus/disabled states. Native OS option presentation is non-canonical where custom accessible styling is feasible.
- 2026-09-19: Accepted [[ADR-013 Metric Card default anatomy]]: standard [[Metric]] Cards omit decorative corner icons and prioritize label, value, support, and optional meaningful metric content. Preserve 40px radius, 24px padding, and legitimate delta/sparkline/comparison content.
- 2026-09-19: Aligned component notes, high-level indexes, generation/review guidance, and the file manifest with the accepted defaults. Retained historical release records and the superseded Table proposal as implementation evidence.

### Fixed

- 2026-09-19: Corrected Precision OS queue, review, list, and detail-surface alignment through shared surface primitives; retained 40px shells and existing table spacing. Nested filter/action panels now distinguish their internal padding from the parent's edge clearance.
- 2026-09-19: Earlier Precision OS adoption replaced native Select menus with Base UI's rounded listbox and an additive `SelectControl` API, retaining low-level exports and form/filter behavior. Standardized selected, hover, keyboard-focus, disabled, and chevron down/up treatments.
- 2026-09-19: Earlier Precision OS adoption removed decorative Metric corner icons and their unsupported internal prop/metadata. This restored the existing Figma anatomy; ADR-013 now formally records the system-wide default. The current documentation/governance pass changes neither product code nor Figma.

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
