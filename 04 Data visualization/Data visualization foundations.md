---
title: "Data visualization foundations"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [data-viz, foundation]
llm_priority: high
---

# Data visualization foundations

Matcha Man data visualization is quiet, editorial, and data-first.

## General rules

- Use 1–4 semantic/categorical `data/series/*` colors from the approved jazz palette.
- Category color does **not** imply good/bad.
- Status colors and series colors are distinct concepts.
- Numeric labels SHOULD use tabular numerals when alignment matters.
- Keep gridlines quiet and only as dense as needed.
- Do not build a fake “dynamic chart engine” in Figma; use reusable supporting primitives and representative compositions.
- Chart Tooltip is richer than the simple contextual [[Tooltip]].

## Axis rules

Line/scatter axes do not always need to start at zero. Bar/column charts generally do.

## Motion

Charts should not rely on animation for meaning.
