---
title: "Table"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [component, table]
decision: "[[ADR-011 Radius-aware table spacing]]"
version: v0.1.0
llm_priority: high
---

# Table

**Figma page:** 22 — Table

Table is for columnar data with headers and aligned fields. Data tables use this component; there is no separate Data Table specification.

**Implementation requirement:** Use the geometry, spacing, and boundary ownership below by default in every Matcha Man implementation. This is the accepted Table specification, not a product-specific example. Document deliberate product exceptions locally; see [[Product design philosophy#Opinionated defaults]].

## Primitives

Table shell, optional section/title band, Table, Table Row, Table Cell, Table Header Cell, and primary-cell content group. A footer or bottom caption may follow the body.

The shell owns the surface, border, clipping, and radius. Sections and cells own internal spacing. Preserve table semantics and shared column alignment.

## Geometry

- Shell radius: **40px**, preserving the Matcha Man large-radius treatment and applicable smoothing from [[Shape and geometry]]
- Shell padding: **0**; do not wrap the whole table in generic 24px padding
- Quiet semantic border and existing surface treatment
- Clip content to the rounded shell while allowing horizontal scrolling within it
- Row height grows with content and the padding below; do not enforce the former 40px header / 44px body geometry

### Spacing model

| Role | Spacing |
| --- | --- |
| Outer left/right content inset | **24px** |
| Standard internal cell inline padding | **12px** per side |
| Standard header/body row vertical padding | **16px** top / **16px** bottom |
| Section/title region | **24px** on all sides |
| First header directly touching the top shell | **24px** top / **16px** bottom |
| Final body row directly touching the bottom shell | **16px** top / **24px** bottom |
| Primary title → supporting text gap | **4px** |

The first cell in every header, body, and footer row receives 24px inline-start padding; the last receives 24px inline-end padding. Other cell edges use 12px, creating 24px between neighboring column contents. A single spanning cell receives both outer insets. Header and body content must align to the same column edges; do not add margins between cells.

Reuse existing card-radius, card-padding, and spacing primitives for these roles; see [[Shape and geometry]] and [[Spacing and layout]]. Component aliases should reference those primitives rather than introduce duplicate raw values.

### Core principle

> Matcha Man tables preserve efficient interior density while providing additional clearance only where content approaches the rounded shell.

> Radius changes edge clearance, not the density of the entire table.

This applies the system-wide rule in [[Shape and geometry]] and the boundary/relationship distinction in [[Spacing and layout]].

DO NOT reduce the 40px radius to solve table layout problems, or give every row boundary padding.

## Composition and boundary ownership

### Table with section header

Rounded shell → section/title band → column header → body rows.

The section/title band owns the radius-safe **24px padding on all sides**. The column-header row below uses normal **16px top / 16px bottom** spacing because it does not touch the top rounded boundary.

### Standalone table

Rounded shell → column header → body rows.

The first column-header row directly touches the top shell and uses **24px top / 16px bottom** padding. Any additional header rows use normal spacing. This extra top padding is conditional on touching the shell, not a global header default.

### Bottom edge and other compositions

The final body row uses **16px top / 24px bottom** when it touches the lower rounded boundary. When a footer or bottom caption follows, that region owns the 24px bottom clearance and the final body row retains normal 16px bottom padding. Do not stack redundant boundary spacing.

A headerless table applies top clearance to its first body row. A single-row headerless table receives both boundary paddings: 24px top and bottom. Empty spanning rows follow the same edge rules. If a separate region follows the table, that region owns its own boundary clearance.

## Dividers

- Horizontal dividers only by default
- No vertical grid lines
- No zebra stripes by default
- Last row typically has no divider
- Do not compensate for spacing with heavier borders or additional row boxes

## Row states

Default, Hover, Selected, Disabled.

## Cell types

Text, Numeric, Status. Numeric values align right and use tabular numerals. Status cells may contain [[Badge]].

Primary cells group a medium-weight title and secondary supporting text with a shared **4px gap**, using Inter and the body-small typography roles from [[Typography]]. Optional provenance stays visible and follows the same internal gap rhythm. Use a shared content primitive, not page-level margins or line-height adjustments.

Cells default to vertical center. A multiline primary group centers as one block; badges, dates, and compact metadata align with it. Keep descriptive/primary columns flexible and compact metadata columns close to their content requirements. Preserve all content and status semantics.

## Responsive

Preserve table semantics and allow horizontal overflow on narrow layouts rather than auto-converting into illegible equal-width columns or arbitrary Cards. Keep the 40px radius and 24px outer inset across themes and viewports by default. Do not compress normal desktop row density to solve narrow-screen overflow. Product-specific column/control minimums are implementation choices, not universal Matcha Man tokens.

## Decision and adoption

Accepted in [[ADR-011 Radius-aware table spacing]] and tracked in [[06 Decisions/CHANGELOG|CHANGELOG]] for **v0.1.0**. This component note describes the current rules; the ADR records why they changed.

Precision OS provided the first implementation validation. [[Table spacing — Precision OS implementation proposal]] is retained as a superseded implementation record, not the canonical specification. Matcha Man remains the source of truth.

Figma masters and connected examples have not been updated or re-audited as part of this documentation release. Verify and reconcile their spacing through [[Component adoption and migration]]; do not infer Figma adoption from this accepted specification.
