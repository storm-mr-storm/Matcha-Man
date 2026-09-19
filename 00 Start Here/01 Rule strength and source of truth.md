---
title: "Rule strength and source of truth"
type: governance
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [governance, rules]
llm_priority: highest
---

# Rule strength and source of truth

Matcha Man is intentionally opinionated. The system should be interpreted as a set of defaults with clear semantics, not as a bag of visual ingredients.

## Precedence when instructions conflict

Use the following order:

1. **Accepted decision records** in `06 Decisions/`
2. **Canonical component/foundation notes** in this vault
3. **Pattern guidance**
4. **Examples and QA compositions**
5. Historical or deprecated artifacts

Figma remains the latest implementation artifact. If Figma contradicts an accepted rule, surface the conflict rather than treating the Figma state as a new unrecorded decision.

## Stable invariants

The following are especially important:

- Product UI uses **Inter** throughout.
- Product copy uses **sentence case**.
- Light/Dark theming is independent from Desktop/Mobile responsive behavior.
- Cards use the approved **40px radius / 60% smoothing / 24px padding** system. In a [[Table]] shell, cells and section bands supply the 24px edge inset while shell padding is zero, as refined by [[ADR-011 Radius-aware table spacing]].
- General UI icons use the local **Icon** component sourced from Lucide canonical glyphs.
- Status, progress, activity, and feedback are semantically distinct.
- Agentic UI should expose observable work rather than magical anthropomorphic “thinking.”
- Do not create variants merely to encode layout decisions that belong to the parent.

## When to propose a new variant

A new variant is justified only when the component itself owns a durable semantic or structural difference. It is not justified simply because a parent needs a different width, gap, screen size, or one-off color.

## Versioning and change records

Use the existing `06 Decisions/` governance structure. [[06 Decisions/VERSION|VERSION]] identifies the current release; [[06 Decisions/CHANGELOG|CHANGELOG]] records when it changed; [[Decision log]] indexes why meaningful decisions were made. Component and foundation notes describe how the system works now. Cross-link these records instead of repeating full specifications.

Versions use **MAJOR.MINOR.PATCH**, interpreted for the design system:

- **MAJOR:** breaking changes requiring meaningful product migration, such as component removal, replacement of core token architecture, breaking component APIs, or a major visual-system rewrite.
- **MINOR:** new components, variants, tokens, documented patterns, or meaningful behavioral/design refinements such as new table layout behavior.
- **PATCH:** corrections that do not materially change component usage, such as typos, clarified wording, incorrect token references, or small accessibility corrections without API changes.

The initial tracked release is **v0.1.0**. Matcha Man and its accepted decision history predate release tracking; do not fabricate earlier releases or reassign historical decisions to invented versions.

For a meaningful change, update the canonical specification, add the next sequential ADR to [[Decision log]], and record the change under Unreleased. When releasing, move that entry into a dated release and update [[06 Decisions/VERSION|VERSION]] in the same pass. Preserve earlier accepted records; explain any superseded rule in the new ADR. Record implementation/Figma adoption separately from acceptance of the specification.
