---
title: "ADR-002 All Inter typography"
type: decision
scope: product
status: accepted
last_reviewed: 2026-09-16
tags: [decision, adr]
llm_priority: high
---

# ADR-002 All Inter typography

## Context

The system originally explored Satoshi Black for headings and Inter for body. Tooling, consistency, and redistribution concerns made that split less attractive.

## Decision

Use Inter throughout the product system, with hierarchy expressed through weight, scale, and tracking.

## Rationale

A single family simplifies Figma, implementation, licensing, and LLM instructions while preserving strong hierarchy.

## Consequences

Display uses Inter Black 900; headings step through 800/700/600; UI labels use 500; body uses 400.
