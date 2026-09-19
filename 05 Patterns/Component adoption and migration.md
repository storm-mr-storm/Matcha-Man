---
title: "Component adoption and migration"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [pattern, migration]
decision: [[ADR-010 Masters-first component adoption]]
---

# Component adoption and migration

The Matcha Man file is being normalized through focused component-adoption passes.

## Migration order

1. Audit the file.
2. Update reusable component masters/patterns first.
3. Update documentation examples.
4. Update templates/playground/one-off compositions.
5. Run a final legacy-pattern audit.

## Principle

Do not chase 100% adoption at the cost of semantics or component integrity.

If a valid usage cannot migrate because the primitive is too rigid, record an **architecture observation** rather than detaching components or creating local hacks.

## Preserve previous migrations

Each pass should keep existing Button, Card, Icon, Input, Select, Badge, Progress, List, etc. connections intact.

## Goal

The file should converge toward a small set of well-used primitives rather than many visually similar local frames.
