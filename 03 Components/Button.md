---
title: "Button"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, button]
llm_priority: high
---

# Button

**Figma page:** 10 — Button

Button is the contained action primitive.

## Sizes

- Small — 40px height, 16px horizontal padding, icon ~16px
- Medium — 48px height, 24px horizontal padding; default application size
- Large — 56px height, 32px horizontal padding, icon ~20px

All use 16px radius and 60% smoothing. Icon/text gap is typically 8px.

## Hierarchy

Primary, Secondary, Tertiary/contained, Destructive.

Use one Primary action per local decision group when possible. Destructive is reserved for genuinely destructive actions, not negative status.

## States

Default, Hover, Pressed, Focus, Disabled, Loading.

## Rules

- Width is normally Hug; parent MAY set Fill container.
- DO NOT create `Width=Full` variants.
- Icon-only actions belong to Icon Button if available, not text Button with hidden label.
- Tabs, Menu Items, Navigation Items, Filter Chips, and Action Links are not Buttons.
- Loading is owned by Button; do not insert a one-off spinner.

## Examples

Primary: `Start brew`  
Destructive: `Delete recipe`  
Small feedback action: `Reconnect`
