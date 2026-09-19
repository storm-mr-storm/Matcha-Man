---
title: "Select"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, select]
llm_priority: high
---

# Select

**Figma page:** 12 — Select

Select is for choosing **one value from a predefined set when options are hidden until opened**.

## Trigger

- 58px height
- 16px horizontal / 12px vertical padding
- 16px radius, 60% smoothing
- Persistent internal label + value + trailing chevron
- Fill container in form layouts

## Trigger states

Default, Hover, Focus, Open, Error, Disabled.

## Select Option

States: Default, Hover, Selected, Disabled. Option count is composition-driven; do not create `Options=3/5/8` variants.

## Distinctions

- Arbitrary user text → [[Text Input]]
- Few visible mutually exclusive choices → [[Radio]]
- Searchable long set → future Combobox
- Contextual commands → [[Menu]]
- Querying entities → [[Search]]

## Long content

Protect the chevron. Long values should truncate/wrap according to the approved component behavior without colliding with the trailing icon.
