---
title: "Matcha Man canonical context"
type: llm-context
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [llm, canonical]
llm_priority: highest
---

# Matcha Man canonical context

This is the compressed canonical brief for the Matcha Man **product** design system.

**Implementation requirement:** These are opinionated defaults, not optional examples. Use [[Product design philosophy#Opinionated defaults]] and the relevant canonical specifications when generating or refactoring UI. Do not substitute conventional platform defaults for convenience. Preserve the canonical component and document deliberate product-specific exceptions locally. Accepted Unreleased guidance applies now; release publication and implementation adoption are separate.

## Character

Editorial, calm, slightly unconventional, jazz-influenced, serious product software with subtle playfulness. Soft geometry, restrained color, strong typography, and observable agentic behavior.

## Typography

Inter only. Display 900, H1 800, H2 700, H3/H4 600, UI 500, body 400. Sentence case. Tabular numerals for aligned metrics/data.

## Color

Use primitives → semantic Theme aliases → components. Matcha positive `#9DAF62`, jazz red `#C36C5F`, jazz yellow `#C2A256`. Dark tail: 800 `#242722`, 850 `#1A1E18`, 900 `#121611`, 950 `#0B0E0A`, 1000 `#050705`. Dark should feel black coffee + matcha + cream.

## Shape

60% smoothing where applicable. Checkbox 6px; badge/tooltip 8px; filter chip 12px; button/input/select 16px; Card and Modal 40px. Circles remain true circles. Toggle/progress tracks may be capsules.

Large Card/surface radius is intentional: do not shrink it to accommodate conventional layouts. Radius changes edge clearance, not the density of the entire component. See [[Shape and geometry]].

## Spacing

Relationship-based rhythm: ~8 tight, ~16 standard, ~24 major. Components own internal spacing; parents own external spacing and width.

Canonical hierarchy: **24px major boundary / 16px nested surface / 12px dense internal / 4–8px relational spacing**. Major Card shells use 24px physical edge clearance; nested bordered/filled panels respect that inset and use 16px internally; dense/table cells use 12px internal inline padding. Exposed top/bottom regions own boundary clearance while interior rows keep component-specific density. Direct siblings share a primary content axis; nested panels deliberately establish a new one. Apply each inset once. Surface padding describes a physical boundary; internal spacing describes content relationships. Other families retain explicit component rules, such as Modal padding and Select popup padding. See [[Spacing and layout#Surface hierarchy]].

## Icons

Local `Icon` component from Lucide. Canonical names. 24×24 source, 2px round strokes. No Size or Color variants.

## Component invariants

- Button: 40/48/56 heights; Primary/Secondary/Tertiary/Destructive.
- Text Input: 50/58/66 heights; persistent internal label.
- Select: 58px height; 16px trigger/menu radius and chevron inset; 8px menu padding/offset; custom listbox with 8px-radius, 16x/12y options (48px minimum). Chevron swaps down/up. Optional internal form label; value-only filters keep an accessible name. Native OS popups are not faithful implementations. See [[Select]] and [[ADR-012 Accessible Select listbox implementation]] (Unreleased MINOR candidate).
- Checkbox: 20×20, 6px radius; indeterminate is usually group-derived.
- Radio: 20×20 with 8px dot.
- Toggle: 44×24 track, 18px thumb.
- Tabs: underline style, 40px height, 2px Matcha indicator.
- Badge: 32px, 8px radius; status/category only, noninteractive.
- Tooltip: 8px radius, 12x/8y padding, noninteractive.
- Avatar: 24/32/40.
- Card: 40px radius, 24px padding, no default shadow. A Table shell delegates edge spacing to cells/bands and has zero shell padding.
- Navigation: mobile horizontal; desktop compact vertical rail with 32px icons.
- Table: preserve the 40px shell radius; zero shell padding; 24px outer inset / 12px internal cell inline padding / 16px standard row block padding / 24px exposed-boundary clearance; 4px primary title/supporting gap. Title bands use 24px on all sides, with normal headers below. Standalone first headers use 24px top / 16px bottom; exposed final body rows use 16px top / 24px bottom. A following footer/caption owns lower clearance instead. Content determines row height; horizontal dividers only. See [[Table]] and [[ADR-011 Radius-aware table spacing]].
- Progress: circular 24px/2px; bar 8px; progress is not a score.
- Feedback Banner: 16px radius/padding; semantic surface + icon; no left rail; small transparent dismiss X.
- Modal: 40px radius, ~32px padding, ~440–480 desktop width.
- Menu: 16px surface radius; 44px items; commands only.
- List: 56px min rows, 12px compact vertical padding; repeated content entities. Direct rows against a 40px shell use 24px horizontal clearance; 16px belongs to internal/nested spacing. Do not duplicate padding already owned by a parent.
- Metric: direction and tone are separate. Standard cards use label, value, support, and optional metric-specific content; no decorative top-right icon slot or icon added to fill empty space. Preserve meaningful delta arrows, sparklines, comparison values, and agentic context. A future corner control/semantic indicator requires separately defined anatomy. See [[Metric]] and [[ADR-013 Metric Card default anatomy]].
- Search: 58px, no persistent internal label.
- Filter chip: 36px, 12px radius; neutral applied constraints.
- Date/Time fields: 58px, 16px radius.

## Semantic distinctions

Button = contained action.  
Menu = contextual command.  
Navigation = persistent destination.  
List = repeated content entities.  
Select = one predefined value.  
Search = query.  
Filter = narrow an existing set.  
Badge = current condition/category.  
Progress = completion.  
Activity = current work.  
Feedback = what the user should notice/act on.  
Metric = measured value, not necessarily progress.

## Agentic UI

Use concrete observable work such as “Calibrating water temperature.” Working activity may use restrained jazz-blue moving-gradient text (~2s linear, 20–30% highlight band). Only active work animates. Reasoning summaries are observation → decision, not hidden chain-of-thought.

## Example world

Documentation prose is generic. Examples use the autonomous robot café. Core robots: Matcha Unit 04, Brewbot 07, Tea Unit 02, Foambot 03. Humor is dry and sparse.

## Governance

Prefer existing primitives and composition. Do not create variants for parent layout decisions. Light/Dark and Desktop/Mobile are independent. When Figma and the vault conflict, flag drift rather than guessing.

Current tracked specification: **v0.1.0**; see [[06 Decisions/VERSION|VERSION]], [[06 Decisions/CHANGELOG|CHANGELOG]], and [[Decision log]]. Existing ADR history is retained; formal version tracking begins on 2026-09-18. Radius changes edge clearance, not the density of the entire table. Figma adoption of ADR-011 remains to be verified separately.

The 2026-09-19 canonical-defaults pass amends ADR-011 and ADR-012 and accepts ADR-013. It is tracked under Unreleased as a **MINOR candidate**, with v0.1.0 unchanged. The principles index states what to follow; component notes specify how; decisions explain why; the changelog records when.
