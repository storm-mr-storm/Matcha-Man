---
title: "Matcha Man canonical context"
type: llm-context
scope: product
status: canonical
last_reviewed: 2026-09-18
tags: [llm, canonical]
llm_priority: highest
---

# Matcha Man canonical context

This is the compressed canonical brief for the Matcha Man **product** design system.

## Character

Editorial, calm, slightly unconventional, jazz-influenced, serious product software with subtle playfulness. Soft geometry, restrained color, strong typography, and observable agentic behavior.

## Typography

Inter only. Display 900, H1 800, H2 700, H3/H4 600, UI 500, body 400. Sentence case. Tabular numerals for aligned metrics/data.

## Color

Use primitives → semantic Theme aliases → components. Matcha positive `#9DAF62`, jazz red `#C36C5F`, jazz yellow `#C2A256`. Dark tail: 800 `#242722`, 850 `#1A1E18`, 900 `#121611`, 950 `#0B0E0A`, 1000 `#050705`. Dark should feel black coffee + matcha + cream.

## Shape

60% smoothing where applicable. Checkbox 6px; badge/tooltip 8px; filter chip 12px; button/input/select 16px; Card and Modal 40px. Circles remain true circles. Toggle/progress tracks may be capsules.

## Spacing

Relationship-based rhythm: ~8 tight, ~16 standard, ~24 major. Components own internal spacing; parents own external spacing and width.

## Icons

Local `Icon` component from Lucide. Canonical names. 24×24 source, 2px round strokes. No Size or Color variants.

## Component invariants

- Button: 40/48/56 heights; Primary/Secondary/Tertiary/Destructive.
- Text Input: 50/58/66 heights; persistent internal label.
- Select: 58px; one hidden predefined choice; Select Option for menu rows.
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
- List: 56px min rows, 16x/12y padding; repeated content entities.
- Metric: direction and tone are separate.
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
