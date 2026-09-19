---
title: "ADR-011 Radius-aware table spacing"
type: decision
scope: product
status: accepted
date: 2026-09-18
last_reviewed: 2026-09-18
version: v0.1.0
tags: [decision, adr, table, spacing]
llm_priority: high
---

# ADR-011 Radius-aware table spacing

## Status

Accepted.

## Date

2026-09-18. Included in the first formally tracked release, [[06 Decisions/VERSION|v0.1.0]].

## Area

Matcha Man Product Design System → Table component.

## Context

Conventional table padding placed content too close to the large rounded corners of Matcha Man's 40px card/table shell. The previous Table specification used 40px headers, 44px minimum body rows, and uniform 16px horizontal cell padding without distinguishing exposed boundaries from interior rows.

## Decision

Preserve the **40px table shell radius** while introducing radius-aware edge spacing: **24px outer inset / 12px internal cell inline padding / 16px standard vertical row padding / 24px exposed-boundary padding**, with a **4px primary title/supporting gap**.

The shell has zero padding; cells and section bands supply clearance. A section/title band owns the top clearance when present; otherwise the first column-header row owns it. The final body row owns bottom clearance only when no following region supplies it. See [[Table]] for the full current specification and composition rules.

This refines the padding ownership described by [[ADR-005 Card geometry and soft shape hierarchy]] specifically for table shells. Standard Card padding and the approved shape hierarchy remain unchanged. It supersedes the former Table row-height and cell-padding defaults, and promotes [[Table spacing — Precision OS implementation proposal]] into the canonical Table specification.

## Rationale

The 40px radius is part of Matcha Man's identity and should not be weakened to accommodate conventional table geometry. Increasing clearance only where content approaches curved boundaries preserves efficient internal density.

> Radius changes edge clearance, not the density of the entire table.

## Consequences

- Preserves Matcha Man's personality and improves corner clearance.
- Aligns header/body columns consistently and avoids oversized interior rows.
- Establishes a reusable Table rule across products.
- First/last rows can have different block padding from interior rows; components must identify which region owns each boundary.
- Existing table implementations and Figma masters/examples need an adoption audit. Acceptance of this specification does not claim that every implementation has migrated.

## Implementation

[[Table]] is canonical. Precision OS was the first implementation validation, covering all 16 tables with shared primitives and spacing aliases. Its recorded browser validation included both themes, desktop/mobile layouts, titled and standalone tables, empty rows, and footer/caption boundary ownership.

Implementation evidence: [[Table spacing — Precision OS implementation proposal]]. Precision OS code was read for verification during this decision's documentation pass and was not modified. Figma adoption remains to be verified separately.

## Related tokens

Reuse the card-radius role in [[Shape and geometry]], the card-padding role in [[Card]], and spacing primitives described in [[Spacing and layout]]. Table aliases should point to these existing roles. The implementation record maps Precision OS aliases; those CSS identifiers and product-specific minimum widths are not new canonical Figma token names.
