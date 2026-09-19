---
title: "System restraint and component economy"
type: principle
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [principle, architecture]
---

# System restraint and component economy

Matcha Man favors **fewer strong primitives** over a large catalog of narrowly scoped variants.

## Parent-owned decisions

The parent layout SHOULD own:

- Width
- Fill vs Hug behavior
- Grid placement
- External spacing
- Horizontal vs vertical action grouping
- Responsive stacking

Do not create variants such as `Width=Full`, `Desktop`, or `Mobile` when the component structure itself does not change.

## Component-owned decisions

A component SHOULD own durable semantic or structural states such as:

- Button hierarchy
- Input validation state
- Select open/closed state
- Badge tone
- List Item selected state

## Reuse before invention

Before proposing a new component, ask whether the need can be expressed with existing primitives such as Card + List + Badge + Button.
