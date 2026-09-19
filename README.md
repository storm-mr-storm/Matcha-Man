---
title: "Matcha Man product design system"
type: index
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [matcha-man, design-system, index]
llm_priority: highest
---

# Matcha Man product design system

This vault is the semantic and decision-making companion to the **Matcha Man product design library** in Figma. It documents the product-side visual language, component rules, interaction semantics, rationale, and the decisions that shaped the system.

The goal is not merely to describe what the components look like. The goal is to preserve enough **opinionated context** that a designer, engineer, Codex workflow, or LLM can infer how Matcha Man should behave when a new screen or component is created.

## What this vault covers

- Product UI foundations and principles
- Component anatomy and usage rules
- Semantic distinctions between similar patterns
- Responsive and theme behavior
- Agentic-interface patterns
- Data visualization rules
- Decision records and rationale
- Known gaps and future component candidates

## What this vault does not cover

This vault intentionally excludes the separate **Matcha Man brand / marketing library**. Marketing page patterns, social assets, campaign compositions, and brand-expression rules belong in a different knowledge base.

## Source of truth model

- **Figma** is the implementation source of truth for the current visual/component artifact.
- **This vault** is the reasoning, semantics, and decision source of truth.
- If the two disagree, treat that as **design-system drift that needs review**. Do not silently invent a reconciliation.

## Governance

- [[06 Decisions/VERSION|VERSION]] — current tracked release (**v0.1.0**)
- [[06 Decisions/CHANGELOG|CHANGELOG]] — dated system changes
- [[Decision log]] — accepted decisions and rationale

The system and ADR history predate formal version tracking. See [[01 Rule strength and source of truth#Versioning and change records|versioning rules]] for how changes are recorded.

## Rule strength

The vault uses a simple hierarchy:

- **MUST** — approved invariant; do not change without an explicit design-system decision.
- **SHOULD** — preferred default; exceptions are possible when the context genuinely requires one.
- **MAY** — supported option.
- **AVOID** — usually wrong; use only with clear justification.
- **DO NOT** — incompatible with the current Matcha Man product system.

Start with [[00 System map]], [[01 Rule strength and source of truth]], and [[02 LLM usage guide]]. For a compressed model-ready summary, use [[Matcha Man canonical context]].
