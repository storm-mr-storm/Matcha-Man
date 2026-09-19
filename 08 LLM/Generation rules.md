---
title: "Generation rules"
type: llm-guide
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [llm, generation]
---

# Generation rules

**Implementation requirement:** [[Product design philosophy#Opinionated defaults]] and the linked component specifications define normal Matcha Man behavior. Follow documented geometry, spacing, anatomy, interactions, and composition; do not replace them with conventional platform defaults for convenience. Retrieve only the rules relevant to the task. If an implementation deliberately diverges, document the product requirement and exception locally while preserving the canonical component.

When generating new Matcha Man product UI, follow this order:

1. State the user task.
2. Select existing components by semantics.
3. Build the hierarchy with Card/List/Table/etc. only where needed.
4. Apply parent-owned layout and spacing.
5. Use semantic Theme variables.
6. Validate Light/Dark.
7. Validate Desktop/Mobile.
8. Validate accessibility and long-content behavior.
9. Add agentic Activity/Feedback only if they materially improve understanding.
10. Propose a new component only after showing why existing primitives cannot express the need cleanly.

For surfaces, explicitly identify who owns each physical boundary and content axis using [[Spacing and layout]]. For [[Table]], distinguish exposed edges from interior row density. For [[Select]], implement the opened listbox as well as the trigger. For [[Metric]], omit decorative corner slots while retaining meaningful metric content. Accepted Unreleased guidance applies by default; check [[Decision log]] and [[06 Decisions/CHANGELOG|CHANGELOG]] for its status.

## Default aesthetic choices

- Prefer quiet surfaces over shadows.
- Prefer sentence-case labels over all caps.
- Prefer a small number of strong accent signals.
- Prefer direct, specific process language.
- Prefer real component instances in documentation.

## Never infer

Do not invent exact token values not documented here or in Figma. If an exact jazz-blue value or unrecorded primitive is required, retrieve it from the design file rather than guessing.
