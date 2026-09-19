---
title: "ADR-010 Masters-first component adoption"
type: decision
scope: product
status: accepted
last_reviewed: 2026-09-16
tags: [decision, adr]
llm_priority: high
---

# ADR-010 Masters-first component adoption

## Context

The Figma file contained many locally recreated controls and examples. Replacing them instance-by-instance would be slow and brittle.

## Decision

Perform focused adoption passes: reusable masters first, then documentation, then higher-level compositions, then a legacy audit.

## Rationale

Fixing the source propagates improvements and preserves component integrity.

## Consequences

Migration work should report architecture limitations rather than detaching components to force adoption.
