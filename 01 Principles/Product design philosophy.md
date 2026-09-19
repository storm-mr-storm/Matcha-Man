---
title: "Product design philosophy"
type: principle
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [principle, visual-language]
llm_priority: high
---

# Product design philosophy

Matcha Man should feel like **modern jazz album art translated into serious product software**: editorial, calm, tactile, slightly unconventional, and quietly expressive.

## Core principles

### Quiet confidence

The system SHOULD use typography, proportion, spacing, and hierarchy before adding decorative signals. Avoid stacking color, border, icon, glow, shadow, and motion when one or two signals already communicate the meaning.

### Soft geometry without softness of intent

Rounded geometry is a signature, but the product must not feel toy-like. Large Card radii are balanced by restrained color, strong type, and disciplined layout.

### Relationship-based spacing

Spacing SHOULD express meaning. Content that belongs together sits tighter; distinct concepts receive more space. Avoid flattening a composition into one uniform gap.

### Data-first, not dashboard-generic

Data visualization and metric surfaces should remain editorial and legible. Avoid “enterprise dashboard” tropes such as heavy shadows, over-gridding, excessive color, and decorative chrome.

### Observable autonomy

When agents work, show what they are doing, what changed, and where human judgment is required. Do not simulate mystical cognition.

### Component economy

Prefer a strong primitive plus composition over a proliferation of narrowly named components.

## Opinionated defaults

Matcha Man is intentionally opinionated. Component documentation describes the preferred implementation, not merely an example. When the documentation defines geometry, spacing, anatomy, interaction behavior, or composition, implementations SHOULD use those rules by default. Do not weaken distinctive Matcha Man characteristics merely to reproduce conventional UI patterns.

Deviations must be intentional, justified by product requirements, and documented locally. Name the canonical rule, the product need, and the exception's scope; preserve the canonical component rather than silently redefining it. Changes to approved invariants still follow [[01 Rule strength and source of truth|governance]].

Implementation-specific validation may reveal better system rules. Once accepted into Matcha Man documentation and governance, those rules become canonical and should propagate to future implementations. Precision OS provides validation evidence, not a separate set of optional design-system rules.

| Default | Canonical specification |
| --- | --- |
| Geometry | **40px major Card/surface radius is intentional.** Solve corner clearance through spacing, not a smaller radius. [[Shape and geometry]], [[Card]] |
| Spacing | **24px major boundary → 16px nested surface → 12px dense internal → 4–8px relational spacing.** These are distinct roles, not interchangeable gaps. [[Spacing and layout#Surface hierarchy]] |
| Alignment | Direct siblings sharing a surface normally share a primary content axis; a deliberate nested surface establishes a new one. [[Spacing and layout#Shared content axis]], [[List]] |
| Table | Preserve efficient interior density; add radius-safe clearance at exposed boundaries. [[Table]] |
| Select | Design the trigger and rounded listbox together; native OS option presentation is not the default where custom styling is feasible. [[Select]] |
| Metric | No default decorative top-right icon; retain meaningful metric-specific content. [[Metric]] |

**Implementation requirement:** When generating or refactoring UI using Matcha Man, treat these specifications as default behavior. Do not substitute conventional platform defaults simply because they are easier to implement. Retrieve the linked component rules rather than copying a product screenshot or this summary as a full specification.
