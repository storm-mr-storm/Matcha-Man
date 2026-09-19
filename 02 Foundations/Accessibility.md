---
title: "Accessibility"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [foundation, accessibility]
---

# Accessibility

Accessibility is part of component semantics, not a finishing pass.

## Core rules

- Interactive targets SHOULD be approximately 44px or larger where practical.
- Color MUST NOT be the only signal for status or error.
- Icon-only controls require meaningful accessible names based on the action, not the glyph name.
- Dynamic agentic updates should not flood assistive technology with low-value announcements.
- Motion must have a reduced-motion fallback.
- Focus should remain visible and semantically consistent, typically using the jazz-blue/info focus treatment.

## Examples

`X` icon in a dialog → accessible name: **Close dialog**, not “X”.

`Ellipsis` icon → accessible name: **More actions**, not “Ellipsis”.

Progress implementation should expose meaningful values such as “Batch preparation, 60% complete.”
