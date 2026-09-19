---
title: "ADR-004 Local Lucide icon component"
type: decision
scope: product
status: accepted
last_reviewed: 2026-09-16
tags: [decision, adr]
llm_priority: high
---

# ADR-004 Local Lucide icon component

## Context

Lucide was already the working icon library, but external instances and one-off vectors created dependency and consistency issues.

## Decision

Detach the included Lucide glyphs into one local `Icon` component set with `Name` variants and canonical Lucide names.

## Rationale

Canonical names map cleanly to implementation and avoid local semantic renaming. A single 24px source prevents size-variant explosion.

## Consequences

Consumers resize instances as needed. Brand logos remain separate. Third-party attribution/license requirements remain part of distribution hygiene.
