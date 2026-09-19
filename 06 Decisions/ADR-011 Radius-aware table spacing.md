---
title: "ADR-011 Radius-aware table spacing"
type: decision
scope: product
status: accepted
date: 2026-09-18
last_reviewed: 2026-09-19
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

## Implementation guidance refinement — 2026-09-19

Clarify the existing boundary-ownership principle across table, list, queue, and review compositions: **24px major-shell clearance / 16px nested-surface padding / 12px dense cell inline padding**. Preserve the 40px radius. Components sharing a parent surface share its primary content axis; a deliberately nested bordered/filled panel establishes a new one. Apply each boundary inset once and keep vertical row density independent. The full guidance lives in [[Spacing and layout#Surface hierarchy]], [[Card]], and [[List]].

This is an implementation/guidance refinement of the accepted spacing decision, not a replacement architecture or new decision ID. It is recorded under [[06 Decisions/CHANGELOG|Unreleased]]; the released version remains **v0.1.0**. The original 2026-09-18 decision and release attribution above remain intact.

Precision OS validates the clarification through shared `SurfaceSection` and `SurfaceInset` primitives, reusing its existing card-padding token and adding an inset alias to the spacing scale. The Marketing queues, Reviews/Inbox, dashboard lists, and related detail/agent surfaces adopt the shared spacing; the existing Table rules remain unchanged. Product code is implementation evidence, not the canonical source. Figma adoption is still a separate verification step.

## Canonical defaults acceptance — 2026-09-19

**Status:** Accepted; this extension is **Unreleased, MINOR candidate**. The original v0.1.0 Table decision above remains unchanged. **Affected area:** Card, Table, List, queue/review compositions, nested surfaces, and shared layout foundations.

**Context:** Product validation showed that correct spacing numbers alone are insufficient when teams confuse a surface boundary with a relationship between children. The prior implementation guidance needs explicit system-level force so future products and agents reproduce the same hierarchy.

**Decision:** Promote **24px major boundary / 16px nested surface / 12px dense internal / 4–8px relational spacing** and the shared-primary-content-axis rule to normal Matcha Man implementation defaults. Major Card content keeps 24px clearance from physical boundaries; interior density remains component-specific. Nested panels respect the parent's 24px inset, then use 16px internally. Preserve the intentional 40px radius. Follow [[Spacing and layout]], [[Card]], [[List]], and [[Table]] for ownership and existing component-specific distinctions.

**Rationale:** The hierarchy expresses containment and relationships while protecting the soft outer geometry. Direct siblings should read as one coherent surface. Smaller conventional radii, inconsistent row axes, and uniformly inflated padding weaken that intent. Radius changes edge clearance, not the density of the entire component.

**Consequences:** Future implementations use these rules automatically under [[Product design philosophy#Opinionated defaults]]. Apply each boundary inset once; document deliberate product exceptions locally. Reuse the existing spacing and Card radius/padding roles described under Related tokens rather than introducing new values. This broadens the accepted guidance within the existing decision; it does not rewrite the original release or certify adoption in every product/Figma master.
