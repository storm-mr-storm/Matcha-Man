---
title: "Forms and field composition"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [pattern, forms]
---

# Forms and field composition

Matcha Man forms should be built from existing field primitives rather than a separate generic “form control” visual.

## Common composition

Card or page section
→ field stack
→ Text Input / Select / Date / Time / Radio / Checkbox
→ Button group

## Spacing

The field component owns internal geometry. The form owns:

- Gap between fields (often ~12–16px)
- Section separation (~24px)
- Gap before primary CTA (~24px when appropriate)

## Field semantics

Use the actual component matching the data model. Do not make all controls look identical just for visual symmetry.

## Future field wrapper

Helper text, error message, character count, and external label MAY justify a future Field wrapper if repeated patterns demand it. Do not add one preemptively.
