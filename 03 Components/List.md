---
title: "List"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [component, list]
llm_priority: high
---

# List

**Figma page:** 30 — List

List is the structural primitive for repeated sibling content rows.

## List parent

Vertical layout, no default surface/radius/padding. The containing [[Card]] owns the surrounding surface when needed.

## List Item

- Minimum height: 56px
- Internal horizontal padding: 16px where the row owns a nested/internal boundary; follow the shell rules below when a row directly meets a major surface
- Vertical padding: 12px
- Leading → Content gap: ~12px
- Primary → Supporting gap: ~4px
- At least ~16px between Content and Trailing
- Fill width, Hug height

### Shell alignment

Direct rows in an unpadded 40px [[Card]] shell use **24px left/right clearance**, aligned with section headings and footer/action regions. Retain the normal compact 12px vertical padding independently. Review rows may use 16px vertical padding without changing the horizontal axis.

Those block-padding values govern interior density. At the exposed top/bottom shell boundary, the first/last owning region supplies 24px clearance; an existing heading/footer band may own it instead. Do not duplicate that spacing on the adjacent row. These are system defaults, not a Precision OS exception.

When the Card already supplies 24px padding, do not add a second shell inset to unframed rows. A nested bordered/filled surface instead uses **16px internally** while respecting its parent's 24px clearance. Plain wrappers and horizontal dividers do not create nested surfaces. See [[Spacing and layout#Surface hierarchy]] for ownership and [[ADR-011 Radius-aware table spacing]] for the accepted system rule.

## States

Default, Hover, Focus, Selected, Disabled. Static lists generally use Default only.

## Slots

Leading and Trailing SHOULD reuse actual primitives such as Avatar, Icon, Badge, Progress, Checkbox, Radio, or short metadata.

## Distinctions

Menu Item = commands. Select Option = value choices. Navigation Item = destinations. Table Row = columnar data. Do not collapse them into generic List Item.
