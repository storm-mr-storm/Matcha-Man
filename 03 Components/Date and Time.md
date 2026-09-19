---
title: "Date and Time"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [component, date-and-time]
llm_priority: high
---

# Date and Time

**Figma page:** 35 — Date & Time

Date/Time controls are siblings of Text Input/Select with temporal semantics.

## Date Field / Time Field

- 58px height
- 16px horizontal / 12px vertical padding
- 16px radius, 60% smoothing
- Internal label + value + Calendar/Clock icon ~20px
- States: Default, Hover, Focus, Disabled, Error

## Date Range

Composition of two fields: side-by-side on desktop, MAY stack on mobile.

## Display patterns

- Timestamp: `Sep 2, 2026 · 8:42 AM`
- Relative time: `4 min ago`
- Last updated / Scheduled time patterns

## Principle

**Relative time for recency; absolute time for accountability.**

Relative-time guidance: just now; 1–59 min; 1–23 hr; Yesterday; 2–6 days; then absolute date. Use locale-aware formatting and avoid ambiguous numeric dates.
