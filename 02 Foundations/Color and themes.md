---
title: "Color and themes"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [foundation, color, theme]
decision: [[ADR-007 Dark neutral tail]]
---

# Color and themes

Color is built as **primitives → semantic Theme aliases → components**.

## Variable collections

- `MM / Color Primitives`
- `MM / Theme`

Theme owns Light/Dark. Responsive mode is separate.

## Signature accents

The system uses a jazz-influenced matcha green, blue, red, and yellow. Known reference colors include:

- Positive / matcha: `#9DAF62`
- Negative / jazz red: `#C36C5F`
- Indeterminate / jazz yellow: `#C2A256`

Use semantic aliases in components rather than raw values.

## Dark neutral tail

Approved dark primitives:

- neutral/800 — `#242722`
- neutral/850 — `#1A1E18`
- neutral/900 — `#121611`
- neutral/950 — `#0B0E0A`
- neutral/1000 — `#050705`

Dark semantic surfaces:

- canvas → neutral/1000
- default → neutral/950
- subtle → neutral/900
- raised → neutral/850
- sunken → neutral/1000
- overlay → neutral/850

Desired dark feel: **black coffee + matcha + cream**, not generic gray dashboard + green accent.

## Rules

- MUST use semantic variables in components.
- DO NOT add ad hoc Light/Dark variants.
- DO NOT use category color to imply positive/negative meaning unless the semantics genuinely require it.
