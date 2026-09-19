---
title: "Checkbox"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, checkbox]
llm_priority: high
---

# Checkbox

**Figma page:** 13 — Checkbox

Checkbox supports independent selection and group-derived indeterminate state.

## Geometry

- Visual control: 20×20
- Radius: 6px
- Corner smoothing: 60%
- Label gap: 8px
- Labeled interaction target SHOULD be about 44px without enlarging the visible box

## Selection

Unchecked, Checked, Indeterminate.

## State

Default, Hover, Focus, Disabled.

Checked uses Matcha fill + check. Focus uses jazz-blue/info treatment while preserving selection semantics.

## Indeterminate

Indeterminate normally represents a derived group state (some children selected), not a third user-authored choice.
