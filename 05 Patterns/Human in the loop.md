---
title: "Human in the loop"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [pattern, agentic, human-in-loop]
---

# Human in the loop

Human-in-the-loop moments are explicit decision boundaries, not generic warnings.

## Structure

1. State what requires a decision.
2. Explain the concrete constraint.
3. Offer a small number of meaningful actions.
4. Preserve progress/context if the task is paused.

Example:

**Robot 04 needs a decision.** Recipe calls for oat milk, but inventory is insufficient.

Actions:

- Use whole milk
- Pause orders

Use [[Feedback Banner]] Warning/Action Required styling unless the situation is genuinely critical.

Do not promote every uncertainty to Critical. Severity and need-for-human-decision are separate concepts.
