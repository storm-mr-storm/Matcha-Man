---
title: "Activity and Reasoning"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, activity-and-reasoning]
llm_priority: high
---

# Activity and Reasoning

**Figma page:** 26 — Activity & Reasoning

Activity communicates what an autonomous system is doing now.

## States

- Queued — static quiet
- Working — moving gradient text
- Complete — static + check
- Failed — static negative

## Working treatment

Use the restrained jazz-blue/info moving-gradient treatment from [[Motion and active work]]. Only the current active line should animate in a stream.

## Content

Use short process labels such as:

- Calibrating water temperature
- Comparing extraction results
- Handing milk prep to Foambot 03

Reasoning summary should be an observation → decision explanation at product level, not hidden chain-of-thought.

Waiting is distinct from Working and may use static text plus indeterminate progress.
