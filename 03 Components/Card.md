---
title: "Card"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [component, card]
llm_priority: high
---

# Card

**Figma page:** 20 — Card

Card is the persistent content-surface primitive for one coherent content unit.

## Geometry

- Radius: 40px
- Corner smoothing: 60%
- Padding: 24px
- Quiet semantic border
- No default shadow
- Width controlled by parent
- Height typically Hug contents

When used as a [[Table]] shell, retain the 40px radius and surface treatment but use zero shell padding. Table cells and section bands own the 24px edge inset so dividers reach the shell and padding is not doubled. This composition-specific rule is accepted in [[ADR-011 Radius-aware table spacing]]; standard Card padding remains 24px.

## Content

Card MAY expose a simple heading. Complex headers containing Avatar, Badge, actions, metadata, or multi-column layout remain composition-owned.

## Rhythm

Use nested relationships: ~8px tight, ~16px standard, ~24px major. Do not apply one flat gap to the entire Card.

## Not a Card

Modal, Feedback Banner, Menu, Select menu, Tooltip, Navigation, Filter Panel, full-page surface, or arbitrary rounded frame.

Avoid Card-inside-Card unless the semantics genuinely justify nested content surfaces.
