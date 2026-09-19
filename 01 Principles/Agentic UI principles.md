---
title: "Agentic UI principles"
type: principle
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [principle, agentic]
llm_priority: high
---

# Agentic UI principles

Matcha Man is designed to support agentic and autonomous workflows without making the system feel magical or theatrical.

## Use observable work

Prefer specific activity language:

- Calibrating water temperature
- Comparing extraction results
- Handing milk prep to Foambot 03
- Reviewing the last five batches

Avoid vague language such as:

- AI thinking
- Agent reasoning deeply
- Magic analysis

## Separate the concepts

- **Activity** = what the system is doing
- **Status** = current condition
- **Progress** = how far along
- **Feedback** = what the user should know
- **Decision boundary** = where the user must intervene

## Human decision boundaries

Agentic UI SHOULD make the handoff explicit when the system cannot or should not decide alone.

Example:

> Robot 07 needs a decision. Milk inventory is below recipe requirement.

Then expose concrete actions such as `Use whole milk` or `Pause order`.

## Reasoning summaries

Product-level reasoning MAY explain observation → decision, but MUST NOT attempt to expose hidden chain-of-thought. Example: “Previous brews ran slow, so the grinder was adjusted one step coarser.”
