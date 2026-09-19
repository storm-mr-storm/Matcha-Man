---
title: "Navigation"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, navigation]
llm_priority: high
---

# Navigation

**Figma page:** 21 — Navigation

Navigation represents persistent destinations.

## Mobile

Approved direction is a compact horizontal floating bottom navigation, approximately 64px high with five-item examples. Preserve the existing audited geometry and dark nested selected surface.

## Desktop

Navigation structurally changes to a compact vertical rail:

- Rail ~72px wide
- 8px padding
- 4px gap
- Item target ~56×56
- Selected tile ~48×48, ~16px radius / 60% smoothing
- Icons 32×32

The structural difference justifies a viewport property on the parent Navigation.

## Rules

- Icon-only by default; provide accessible labels/tooltips.
- Selected state remains a dark nested surface, not a bright Matcha fill.
- Do not treat Navigation Items as Buttons or List Items.
