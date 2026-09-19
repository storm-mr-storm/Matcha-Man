---
title: "LLM usage guide"
type: llm-guide
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [llm, governance]
llm_priority: highest
---

# LLM usage guide

This vault is designed to be useful as retrieval context for an LLM.

## Recommended behavior for an LLM

When generating or reviewing Matcha Man product UI:

1. Identify the component or pattern being used.
2. Read [[Product design philosophy#Opinionated defaults]], then retrieve the relevant foundation/component note and linked accepted decision.
3. Prefer existing primitives and compositions before proposing a new component.
4. Preserve semantic distinctions even when two patterns look visually similar.
5. Treat MUST/DO NOT statements as constraints and documented geometry, spacing, anatomy, and behavior as the implementation defaults—not optional examples.
6. Treat examples as demonstrations, not as hard-coded product content.
7. Use robot-café examples only when a concrete example is helpful; documentation language should remain generic and professional.

## Important reasoning rule

Do not infer a new system rule from a single screenshot or one-off specimen. Repeated rules documented here take precedence over incidental composition details.

**Implementation requirement:** Do not substitute conventional platform defaults merely because they are easier to generate. Accepted Unreleased guidance is canonical; implementation evidence does not need to be copied verbatim. If a product must diverge, document the requirement, affected canonical rule, and local exception while preserving the canonical component. Do not turn an undocumented local workaround into a system default.

## Good model output

A good Matcha Man recommendation should explain:

- Which existing component is appropriate
- Which variant/state is appropriate
- Which parent owns width/layout
- Which semantic tokens should be used
- Any accessibility or responsive implications
- Why an adjacent-looking component is not the right choice

## Avoid

- Inventing extra variants
- Reintroducing title case or all caps
- Hard-coding colors that should be semantic
- Treating all rounded surfaces as Card
- Treating all clickable rows as Button or List Item
- Treating confidence/score values as Progress
- Using green/red to imply “good/bad” when the value is merely magnitude or direction
