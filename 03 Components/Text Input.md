---
title: "Text Input"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, text-input]
llm_priority: high
---

# Text Input

**Figma page:** 11 — Input

Text Input is for **single-line user-authored text**.

## Sizes

- Small — 50px height, 14px horizontal / 8px vertical padding, 16px radius
- Medium — 58px height, 16px horizontal / 12px vertical padding; default
- Large — 66px height, 20px horizontal / 14px vertical padding

All use 60% smoothing.

## Anatomy

Persistent internal label + value/placeholder. Helper/error text remains outside the fixed-height control.

## States

Default, Hover, Focus, Error, Disabled, Read only.

Empty/Filled are content conditions, not separate semantic states.

## Use for

Recipe name, Robot ID, Station name, custom label, short identifier.

## Do not use for

- Predefined choices → [[Select]]
- Search queries → [[Search]]
- Dates/times → [[Date and Time]]
- Multi-line text → future Textarea

## Rule

Use `Read only` when the control intentionally remains input-like but cannot be edited. Do not misuse Disabled for read-only data.
