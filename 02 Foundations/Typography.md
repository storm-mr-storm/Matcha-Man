---
title: "Typography"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [foundation, typography]
decision: [[ADR-002 All Inter typography]]; [[ADR-003 Sentence case]]
---

# Typography

Matcha Man product UI uses **Inter throughout**.

## Hierarchy

- Display — Inter Black 900
- H1 — Extra Bold 800
- H2 — Bold 700
- H3/H4 — Semi Bold 600
- UI labels/buttons — Medium 500
- Body — Regular 400

Large headings SHOULD use modest negative tracking.

## Numeric data

Financial/data-style numerals and product metrics SHOULD use **tabular numerals** where alignment matters.

## Capitalization

Sentence case is the default for headings, labels, buttons, statuses, and documentation sections.

Use:

- Agent activity
- Live brew
- Action required
- Data visualization foundations

Avoid:

- AGENT ACTIVITY
- LIVE BREW
- Action Required

Preserve proper nouns and acronyms such as Matcha Man, AI, API, QA, Lucide.

## Rationale

The typography already provides sufficient hierarchy. All caps is not needed as a substitute for structure or emphasis.
