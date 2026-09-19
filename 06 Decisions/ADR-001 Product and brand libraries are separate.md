---
title: "ADR-001 Product and brand libraries are separate"
type: decision
scope: product
status: accepted
last_reviewed: 2026-09-16
tags: [decision, adr]
llm_priority: high
---

# ADR-001 Product and brand libraries are separate

## Context

Matcha Man began as a foundation for product UI but also developed a separate marketing/brand expression with bento layouts, promotional templates, photography, and social assets.

## Decision

Maintain separate Product and Brand libraries. This vault documents Product only.

## Rationale

The shared visual DNA is useful, but component semantics and documentation needs diverge quickly between application UI and marketing surfaces.

## Consequences

Product components should not be created to satisfy one-off marketing needs. Brand patterns may borrow palette and typography without becoming product primitives.
