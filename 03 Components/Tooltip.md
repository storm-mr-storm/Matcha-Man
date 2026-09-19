---
title: "Tooltip"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, tooltip]
llm_priority: high
---

# Tooltip

**Figma page:** 18 — Tooltip

Tooltip is a transient, noninteractive explanation attached to a trigger.

## Geometry

- Radius: 8px, 60% smoothing
- Padding: 12px horizontal / 8px vertical
- Suggested max width: ~280px
- Body: ~12/16 Regular
- Caret: ~8×4
- Trigger gap: ~8px

Placements: Top, Right, Bottom, Left. Optional shortcut text may be included.

## Rules

- Tooltip itself has no hover/pressed state.
- Show on hover/focus as appropriate.
- Critical information MUST NOT exist only in a tooltip.
- If the floating surface contains actions or richer interaction, use a Popover pattern rather than Tooltip.
