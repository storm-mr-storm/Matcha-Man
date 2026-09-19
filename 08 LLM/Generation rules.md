---
title: "Generation rules"
type: llm-guide
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [llm, generation]
---

# Generation rules

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

## Default aesthetic choices

- Prefer quiet surfaces over shadows.
- Prefer sentence-case labels over all caps.
- Prefer a small number of strong accent signals.
- Prefer direct, specific process language.
- Prefer real component instances in documentation.

## Never infer

Do not invent exact token values not documented here or in Figma. If an exact jazz-blue value or unrecorded primitive is required, retrieve it from the design file rather than guessing.
