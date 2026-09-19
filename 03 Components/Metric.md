---
title: "Metric"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [component, metric]
llm_priority: high
---

# Metric

**Figma page:** [31 — Metric](https://www.figma.com/design/gYVK5MVOYSMWgTjdKiO0Yf/Matcha-Man?node-id=6-72). Inspected 2026-09-19: Metric `514:53`, Metric Card set `516:4091`, and its Basic / Delta / Sparkline / Delta + Sparkline variants.

Metric presents a primary quantitative value and optional trend/context.

**Implementation requirement:** Use the anatomy below by default when generating or refactoring Matcha Man metric surfaces. Preserve it across products; document deliberate exceptions locally under [[Product design philosophy#Opinionated defaults]]. The formal decision is [[ADR-013 Metric Card default anatomy]].

## Metric value

Default approximately 32/36 Bold 700 with tabular numerals.

## Label/support

Label ~13–14 Medium, secondary. Supporting text is smaller/tertiary.

Typical rhythm:

- Label → value: 8px
- Value → delta: 8px
- Delta → support: 8px
- Metric block → sparkline: 24px

## Metric Delta

**Direction** and **Tone** are separate concepts.

Direction: Up / Down / Flat.  
Tone: Positive / Negative / Neutral.

A value moving down can be positive (e.g. brew time). Do not encode direction as meaning.

## Metric Card

Uses [[Card]] as the surface and MAY include Delta and [[Sparklines and Microcharts]].

> Standard Matcha Man metric cards prioritize numeric hierarchy and supporting context. Decorative corner icons are not part of the default metric-card anatomy.

**Standard Matcha Man metric cards do not include decorative top-right icons.** Do not add an icon simply to fill empty card space. Metric-card hierarchy should come from typography, spacing, data, and semantic context rather than decorative iconography.

Core anatomy is a label, primary value, supporting text when useful, and optional metric-specific content such as a delta, sparkline, or comparison/secondary metric. The inspected Figma variants have no decorative/action-style top-right icon slot. Keep the label/value/support stack full-width; do not reserve a second column for an absent icon.

Preserve the Card's **40px radius / 24px padding**, semantic surface and border, typography hierarchy, and 8px internal metric rhythm. Standard CSS rounded corners remain the web adaptation for Figma corner smoothing.

Basic, Delta, Sparkline, and Delta + Sparkline remain distinct content compositions. A delta's directional arrow is meaningful metric content, not a decorative corner icon. Preserve meaningful deltas, status, comparison values, sparklines, and agentic context when present; this rule does not suppress icons or SVGs inside legitimate metric content or unrelated card headers.

A future variant with a meaningful corner control or semantic indicator must define and document that anatomy separately through the existing variant/decision process. It is not an implicit icon slot on Basic or the other standard variants. Comparison/secondary metrics may provide useful context; this permission does not create an undocumented new variant or justify fabricated trends.

## Precision OS adoption

Precision OS uses Basic `MetricCard` and grouped `Metric` compositions. Its unsupported decorative `icon` prop and caller metadata were removed to restore the existing Figma anatomy; labels, values, support, calculations, and surface tokens are unchanged. No current Precision OS consumer implements Delta or Sparkline variants, so that cleanup did not add or remove those capabilities. The implementation correction preceded this explicit system-wide acceptance in [[ADR-013 Metric Card default anatomy]]; both are recorded under [[06 Decisions/CHANGELOG|Unreleased]]. Product code and Figma were not changed by this documentation/governance pass.
