---
title: "ADR-005 Card geometry and soft shape hierarchy"
type: decision
scope: product
status: accepted
last_reviewed: 2026-09-16
tags: [decision, adr]
llm_priority: high
---

# ADR-005 Card geometry and soft shape hierarchy

## Context

The product needed a recognizable surface language without making every component equally pill-shaped.

## Decision

Cards use 40px radius, 60% smoothing, and 24px padding; other component families use smaller radii according to scale and function.

## Rationale

Large soft Cards provide the signature warmth while controls remain precise and usable.

## Consequences

Do not flatten the system to one radius or introduce Card sizes without a structural need.
