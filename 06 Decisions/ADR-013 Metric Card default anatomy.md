---
title: "ADR-013 Metric Card default anatomy"
type: decision
scope: product
status: accepted
date: 2026-09-19
last_reviewed: 2026-09-19
release_status: unreleased
change_level: minor
tags: [decision, adr, metric, anatomy]
llm_priority: high
---

# ADR-013 Metric Card default anatomy

## Status

Accepted on 2026-09-19; Unreleased, MINOR candidate. Current released specification: [[06 Decisions/VERSION|v0.1.0]].

## Area

Matcha Man Product Design System → Metric and Metric Card anatomy; system-wide implementation defaults.

## Context

Precision OS supplied decorative top-right icons through its shared Metric primitive even though the canonical note and inspected Figma Basic, Delta, Sparkline, and Delta + Sparkline cards did not define that slot. Removing it restored the intended hierarchy. The existing guidance should make that outcome an explicit default for future products and implementation agents, not merely record a local cleanup.

## Decision

Standard Metric Cards do not include decorative top-right icons or reserve layout space for them. Core anatomy is label, primary value, supporting text, and optional meaningful metric content: delta, sparkline, comparison, or secondary metric. Typography, spacing, data, and semantic context carry the hierarchy.

Preserve the 40px Card radius, 24px padding, semantic surface/border, and component-specific content rhythm in [[Metric]]. Keep real delta arrows, status/context, and chart content. A future variant requiring a meaningful corner control or semantic indicator must define and document that anatomy separately through existing governance. Do not add an icon simply to fill empty space.

## Rationale

Decorative corner symbols compete with numeric hierarchy and suggest actions or semantics that the card may not have. Removing their slot gives the content a coherent full-width axis. Meaningful metric content remains valuable and is not equivalent to icon garnish. This supports the quiet, data-first principles in [[Product design philosophy#Opinionated defaults]].

## Consequences

- Implement shared Metric Card anatomy first, then remove obsolete decorative icon props/metadata from consumers. Do not hide icons with page-specific CSS.
- Preserve labels, values, support, calculations, accessibility, and meaningful content variants during migration.
- Document intentional product exceptions locally while preserving the canonical component; new system variants still require a separate definition and decision.
- Precision OS's earlier implementation validation covered 24 Basic cards and 11 grouped metrics. It currently has no runtime Delta/Sparkline/Comparison variants; their canonical definitions remain supported.
- This pass changes documentation/governance only. It does not certify migration of every product or alter Figma.

## Relevant tokens and canonical references

Reuse [[Card]] geometry (40px radius, 24px padding), existing semantic surface/border roles, [[Typography]] metric roles (default 32/36 bold tabular value), and [[Spacing and layout]] roles. [[Metric]] owns the 8px metric rhythm and 24px metric-to-sparkline gap; dense comparison content follows its defined composition rather than an invented icon column. [[Sparklines and Microcharts]] owns chart content.

## Version impact

Recorded under [[06 Decisions/CHANGELOG|Unreleased]] as a **MINOR candidate** under the existing policy for meaningful component/design-guidance refinements. This formalizes default anatomy and downstream adoption expectations; no released package API or release history is changed in this documentation pass. Do not change `VERSION.md` until an explicit release is cut. The earlier implementation correction is evidence; this record is the formal system-wide acceptance.
