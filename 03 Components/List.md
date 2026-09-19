---
title: "List"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
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
- Horizontal padding: 16px
- Vertical padding: 12px
- Leading → Content gap: ~12px
- Primary → Supporting gap: ~4px
- At least ~16px between Content and Trailing
- Fill width, Hug height

## States

Default, Hover, Focus, Selected, Disabled. Static lists generally use Default only.

## Slots

Leading and Trailing SHOULD reuse actual primitives such as Avatar, Icon, Badge, Progress, Checkbox, Radio, or short metadata.

## Distinctions

Menu Item = commands. Select Option = value choices. Navigation Item = destinations. Table Row = columnar data. Do not collapse them into generic List Item.
