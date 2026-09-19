---
title: "Search"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, search]
llm_priority: high
---

# Search

**Figma page:** 33 — Search

Search finds content/entities.

## Search Field

- 58px height
- 16px radius, 60% smoothing
- 16px horizontal padding
- Leading Search icon ~20px
- Icon/text gap ~12px
- Optional clear control

Unlike Text Input/Select, Search does not use a persistent internal label by default.

## States

Default, Hover, Focus, Typing, Disabled.

## Results

Content/entity results should generally reuse [[List]]. Command results should generally reuse [[Menu]].

## Behavior

- Local search may update instantly.
- Remote typeahead SHOULD debounce roughly 200–300ms.
- Expensive AI/research actions should use explicit Submit rather than pretending to be instant search.
- Preserve the query while loading.
- Distinguish empty results from system errors.
