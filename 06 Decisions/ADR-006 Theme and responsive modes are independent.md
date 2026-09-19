---
title: "ADR-006 Theme and responsive modes are independent"
type: decision
scope: product
status: accepted
last_reviewed: 2026-09-16
tags: [decision, adr]
llm_priority: high
---

# ADR-006 Theme and responsive modes are independent

## Context

Theme and viewport changes solve different problems, but design systems often accidentally couple them into duplicated components.

## Decision

Light/Dark lives in Theme variables; Desktop/Mobile lives in Responsive variables. Use separate dimensions.

## Rationale

This prevents combinatorial component duplication and makes theme switching independent from layout behavior.

## Consequences

Only components with genuine structural responsive changes, such as Navigation, should expose viewport structure differences.
