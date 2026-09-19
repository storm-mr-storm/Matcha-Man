---
title: "Spacing and layout"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [foundation, spacing, layout]
---

# Spacing and layout

Matcha Man uses relationship-based spacing rather than a flat one-gap system.

## Common rhythm

- Tight relationship — ~8px
- Standard relationship — ~16px
- Major separation — ~24px

These values are defaults, not an instruction to put one `gap=16` on every Auto Layout.

## Principle

Tighter spacing indicates one thought. Larger spacing indicates a new relationship or region.

## Ownership

Components own internal spacing. Parents own external spacing.

Examples:

- Button owns icon/text gap and horizontal padding.
- Card owns 24px edge padding.
- In a [[Table]] shell, cells and section bands supply that edge inset; the shell itself has zero padding. Boundary clearance and normal row density are separate roles, as accepted in [[ADR-011 Radius-aware table spacing]].
- Form layout owns the gap between fields and the Button.
- Grid owns the gap between Cards.

Avoid embedding margins into components simply to reproduce one composition.

Use component-specific spacing roles where relationships differ: Table uses a 4px primary title/supporting gap and 12px internal cell inline padding within the existing spacing rhythm. Reuse shared spacing primitives and the card-padding role rather than duplicate raw values in each product. See [[Table]] for the full spacing model and exposed-edge rules.
