---
title: "Responsive behavior"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [foundation, responsive]
decision: [[ADR-006 Theme and responsive modes are independent]]
---

# Responsive behavior

Responsive behavior is independent from theming.

## Variable collection

`MM / Responsive` contains Desktop/Mobile behavior. `MM / Theme` contains Light/Dark behavior.

## Rule

Use the same component across viewports unless the **structure genuinely changes**.

Examples:

- Button: same component; parent may change Hug → Fill or horizontal → stacked actions.
- Card: same component; radius/padding remain stable by default.
- Table: preserve semantics and horizontal scrolling; the 40px shell radius and 24px outer content inset remain stable by default. Use the boundary rules in [[Table]], not denser desktop rows or device-specific copies.
- List Item: same component; height may grow naturally as text wraps.
- Navigation: structural exception. Mobile uses horizontal bottom navigation; Desktop uses a vertical compact rail.

DO NOT create device-specific component copies merely because available width differs.
