---
title: "Feedback Banner"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, feedback-banner]
llm_priority: high
---

# Feedback Banner

**Figma page:** 27 — Feedback

Feedback Banner communicates information the user should notice because it affects understanding or next action.

## Geometry

- Fill width / Hug height
- 16px padding
- 16px radius, 60% smoothing
- ~12px internal gap
- Leading semantic icon ~20px
- No colored signal rail
- Dismiss uses the small transparent X treatment from Modal/Dialog, not a large contained Icon Button

## Tones

Neutral, Info, Positive, Warning, Critical using subtle semantic surfaces.

## Agentic compositions

- Agent update
- Working
- Action required
- Blocked
- Recovered
- Important change

## Rules

- Tone is communicated primarily through semantic surface + icon.
- Banner itself is not interactive; actions reuse [[Button]].
- Dismiss remains visually secondary and neutral across tones.
- Feedback is not the same as Status, Progress, or Activity.
