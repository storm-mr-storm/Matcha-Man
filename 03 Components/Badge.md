---
title: "Badge"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, badge]
llm_priority: high
---

# Badge

**Figma page:** 17 — Badge

Badge is compact, noninteractive status/category metadata.

## Geometry

- Height: 32px
- Radius: 8px, 60% smoothing
- Horizontal padding: 8px
- Icon: ~16px
- Icon gap: ~6px
- Width: Hug contents

## Tone

Preserve the existing semantic Tone architecture. Examples may include Positive, Negative, and Indeterminate/warning-like treatments.

Reference colors include Matcha positive `#9DAF62`, jazz red `#C36C5F`, jazz yellow `#C2A256` via semantic variables.

## Examples

Ready, Working, Queued, Calibrating, Needs attention.

## Rules

- Badge is not interactive; no hover/pressed/focus variants.
- Applied filters are [[Filter]] chips, not Badge.
- Percent completion is usually [[Progress]], not Badge.
- Sentence case only.
