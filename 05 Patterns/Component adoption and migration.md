---
title: "Component adoption and migration"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [pattern, migration]
decision: [[ADR-010 Masters-first component adoption]]
---

# Component adoption and migration

The Matcha Man file is being normalized through focused component-adoption passes.

The same order applies to product code: correct shared primitives first, then their consumers. [[Product design philosophy#Opinionated defaults]] and accepted component specifications are the target behavior; a conventional platform pattern is not a substitute simply because it is easier to implement.

## Migration order

1. Audit the file.
2. Update reusable component masters/patterns first.
3. Update documentation examples.
4. Update templates/playground/one-off compositions.
5. Run a final legacy-pattern audit.

## Principle

Do not chase 100% adoption at the cost of semantics or component integrity.

If a valid usage cannot migrate because the primitive is too rigid, record an **architecture observation** rather than detaching components or creating local hacks.

Product validation may motivate an improved system rule. Propose it through [[01 Rule strength and source of truth#Versioning and change records|existing governance]], then update the canonical specification and adoption guidance once accepted. Until acceptance, record the product-specific exception locally; after acceptance, future implementations use the new default. Keep acceptance, release publication, and adoption status distinct.

## Preserve previous migrations

Each pass should keep existing Button, Card, Icon, Input, Select, Badge, Progress, List, etc. connections intact.

## Goal

The file should converge toward a small set of well-used primitives rather than many visually similar local frames.
