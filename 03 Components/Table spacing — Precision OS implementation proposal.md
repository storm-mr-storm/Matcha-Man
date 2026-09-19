---
title: "Table spacing — Precision OS implementation proposal"
type: implementation-note
scope: product
status: superseded
superseded_by: "[[ADR-011 Radius-aware table spacing]]"
last_reviewed: 2026-09-18
tags: [component, table, spacing, implementation]
llm_priority: low
---

# Table spacing — Precision OS implementation proposal

Historical implementation record, originally proposed and implemented in Precision OS on 2026-09-18. The spacing decision was subsequently accepted in [[ADR-011 Radius-aware table spacing]] and integrated into canonical [[Table]] in **v0.1.0** on the same date. The filename is retained to preserve existing links.

This note records the first implementation and its product-specific aliases/adaptations. It is superseded as a proposal: consult [[Table]] for current rules, not this implementation snapshot. Matcha Man remains canonical. No Figma components or variables were changed.

## Decision and rationale

> The 40px table radius is preserved. Radius clearance is handled at the outer boundary rather than by increasing the density of every table row.

Uniform 16px horizontal insets and conventional header heights placed content too close to the curved shell. Adding padding around the entire table would inset dividers and duplicate cell spacing. Instead, the shell owns its surface, border, clipping, and 40px radius; rows and section bands own spacing. The shell has zero padding.

## Spacing model

| Role | Value | Precision OS mapping |
| --- | --- | --- |
| Shell radius | 40px | Existing card radius |
| Shell padding | 0 | `TableShell` |
| Outer content inset | 24px | Existing card padding; `--mm-table-edge-inset` |
| Normal cell inline padding | 12px | Spacing scale × 3; `--mm-table-cell-padding-inline` |
| Normal row block padding | 16px top / 16px bottom | Spacing scale × 4; `--mm-table-row-padding-block` |
| Section/title region | 24px on all sides | Existing card padding; `TableSectionHeader` |
| Exposed top header | 24px top / 16px bottom | Card padding; `--mm-table-boundary-padding-block` |
| Exposed final data row | 16px top / 24px bottom | Same boundary alias |
| Title → supporting text gap | 4px | Spacing scale × 1; `--mm-table-primary-gap` |

The first cell in each header, body, and footer row gets 24px inline-start padding; the last gets 24px inline-end padding. Other inline cell padding is 12px, giving 24px between adjacent column contents. A single spanning cell receives both edge insets. Header and body column edges align. These aliases use the existing 4px spacing scale and card-padding token, not new raw spacing values.

## Two shell compositions

**With a title band:** `TableShell → TableSectionHeader + Table`. The title band uses 24px on all sides, clearing the top corners. Column headers beneath it retain 16px top and bottom padding. Do not add another 24px above these column headers.

**Standalone:** `TableShell → Table`. The first column-header row directly touches the shell, so it uses 24px top and 16px bottom padding. Subsequent header rows use 16px on both sides. A headerless table follows the same boundary rule for its first body row.

The final body row gets 24px bottom padding only when it reaches the bottom shell. If a table footer or bottom caption follows, that region receives the bottom clearance and the data row remains at 16px. A separate region following the table owns its own boundary clearance. A single-row headerless table receives both top and bottom boundary padding. Fixed 40px/44px row heights are not enforced in this implementation; content and padding determine height.

## Cell content, sizing, and dividers

- `TablePrimaryCell` groups title, optional provenance content, and supporting description with a shared 4px gap. It uses Inter and body-small typography (14px/20px), medium-weight title, and secondary supporting text. Optional provenance stays visible and follows the same gap rhythm.
- Cells default to vertical center. A multiline primary group centers as one block; badges and dates align to the same row center.
- Compact metadata columns use content-sized, nonwrapping cells. Descriptive and primary columns retain flexible space and wrapping. A shared 16rem primary-cell minimum keeps dense tables legible; overflow remains horizontally scrollable.
- Preserve subtle horizontal dividers, existing hover/selected states, and status semantics. Do not add vertical grid lines, row boxes, or zebra striping. Numeric values remain right aligned with tabular numerals where applicable.
- Retain the existing 640px table minimum and horizontal scroll container. Precision OS keeps the 24px edge inset at narrow widths; it does not introduce a new mobile spacing variant or conceal columns. Inline editing controls keep their existing minimum width.
- Standard CSS border-radius approximates the Figma geometry; no corner-smoothing dependency is introduced.

## Validation and adoption status

All 16 Precision OS tables use the shared shell: roadmap goals/initiatives/features, tasks, decisions, knowledge items/customer insights, agents, agent runs/generated outputs, app features, sales, competitors, notes, and email/social marketing.

The initial validation recorded 92 browser table checks across both themes and desktop/mobile layouts, plus checks for empty spanning rows, keyboard navigation, and footer/caption boundary ownership. Lint, TypeScript, and production build passed. Evidence is recorded in [Precision OS table refinement report](/Users/matthewstorm/Dev/pa-os/precision-os/docs/table-spacing-refinement.md); that report describes the implementation-time state before canonical promotion.

The former canonical fixed row heights and 16px cell padding have now been replaced in [[Table]]. The 640px table minimum, 16rem primary-cell minimum, and inline-control sizing above remain Precision OS implementation choices. CSS rounded corners remain an implementation approximation of Figma smoothing. Connected Figma masters/examples have not been updated or re-audited in this documentation pass; adoption must be verified separately.
