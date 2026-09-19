---
title: "ADR-003 Sentence case"
type: decision
scope: product
status: accepted
last_reviewed: 2026-09-16
tags: [decision, adr]
llm_priority: high
---

# ADR-003 Sentence case

## Context

The file accumulated all-caps and Title Case labels such as MATCHA MAN / LAB and 01 / FOUNDATIONS.

## Decision

Use sentence case for product and documentation UI. Preserve acronyms and proper nouns.

## Rationale

The typography already provides hierarchy. Sentence case feels more editorial and reduces enterprise-dashboard visual noise.

## Consequences

Text-case transforms should be Original where possible; capitalization is carried by the actual string.
