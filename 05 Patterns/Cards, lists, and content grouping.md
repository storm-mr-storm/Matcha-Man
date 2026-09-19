---
title: "Cards, lists, and content grouping"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [pattern, card, list]
---

# Cards, lists, and content grouping

Use Card and List together intentionally.

## Card

One coherent persistent content unit; owns surface, radius, padding.

For columnar data, follow the [[Table]] composition: the shell retains Card geometry with zero shell padding, while section bands and cells supply the edge inset. Do not add a second padded Card around the table.

## List

Repeated sibling rows; owns row anatomy, states, and dividers; no default surrounding surface.

## Preferred composition

Card
→ optional Header
→ List
   → List Item
   → List Item
   → List Item

Avoid:

Card
→ Card
→ Card

when the inner units are simple repeated rows.

Avoid adding a second Card-like background around List inside Card unless a real semantic surface exists.
