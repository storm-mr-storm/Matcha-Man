---
title: "Design review checklist"
type: llm-checklist
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [llm, checklist]
---

# Design review checklist

Use this checklist when reviewing a Matcha Man screen or component.

## Semantics

- Is each control the correct component for the job?
- Are Status, Progress, Activity, Feedback, and Metric kept distinct?
- Is the interaction model clear without relying on color alone?

## Component reuse

- Are connected components used instead of raw local copies?
- Could a repeated composition be built from existing primitives before adding a new component?
- Are parent-owned width/layout decisions mistakenly encoded as variants?

## Visual system

- Inter only?
- Sentence case?
- Semantic color variables?
- Correct radius family?
- Relationship-based spacing?
- No unnecessary shadows/glows/rails?

## Opinionated defaults

- Are the rules in [[Product design philosophy#Opinionated defaults]] applied, with deliberate product exceptions documented locally?
- Do major Card surfaces retain 40px radius and 24px boundary clearance, with 16px nested padding, 12px dense internal spacing, and 4–8px related-content gaps as appropriate?
- Do direct siblings share a primary content axis, and is each inset owned only once? See [[Spacing and layout]].
- Does [[Table]] add clearance at exposed rounded boundaries while retaining normal interior density?
- Does [[Select]] include an accessible designed listbox, 16px chevron edge clearance, rounded menu/options, and intentional interaction states?
- Does [[Metric]] omit decorative top-right icons while preserving meaningful delta, sparkline, comparison, and semantic content?
- Are accepted defaults kept distinct from release publication and product/Figma adoption status?

## Theme and responsive

- Does Light/Dark come from Theme variables?
- Does responsive behavior come from layout or `MM / Responsive`?
- Is a structural viewport variant used only when the component truly changes shape?

## Agentic behavior

- Is work concrete and observable?
- Is waiting distinguished from working?
- Are human decision boundaries explicit?
- Is motion restrained and reduced-motion safe?

## Accessibility

- Visible focus?
- Icon-only controls named by action?
- Color not the only status signal?
- Long content and narrow layout tested?
