---
title: "Card"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [component, card]
llm_priority: high
---

# Card

**Figma page:** 20 — Card

Card is the persistent content-surface primitive for one coherent content unit.

**Implementation requirement:** Use this anatomy and [[Spacing and layout#Surface hierarchy]] by default. Preserve the 40px radius; resolve large corners with edge clearance, not reduced radii or inflated interior density. See [[Product design philosophy#Opinionated defaults]].

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

Headings, direct list/queue rows, review content, and footer/action regions share the same 24px horizontal content axis. A sectioned Card may delegate that inset to each band or row with zero shell padding; do not mix a 24px heading with 16px direct body rows. A standard padded Card already owns the inset, so children must not add it again.

A nested bordered/filled panel sits at the Card's 24px content inset and uses 16px internal padding. It establishes a deliberate new axis. See [[Spacing and layout#Surface hierarchy]] and the accepted system guidance in [[ADR-011 Radius-aware table spacing]].

In an unpadded sectioned Card, the first and last content regions also own the 24px exposed top/bottom clearance. Interior row spacing remains component-specific; applying boundary clearance once does not make every row 24px padded on all sides.

## Rhythm

Use nested relationships: ~8px tight, ~16px standard, ~24px major. Do not apply one flat gap to the entire Card.

## Not a Card

Modal, Feedback Banner, Menu, Select menu, Tooltip, Navigation, Filter Panel, full-page surface, or arbitrary rounded frame.

Avoid Card-inside-Card unless the semantics genuinely justify nested content surfaces.
