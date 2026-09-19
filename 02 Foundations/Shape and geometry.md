---
title: "Shape and geometry"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [foundation, shape]
decision: [[ADR-005 Card geometry and soft shape hierarchy]]
---

# Shape and geometry

Soft geometry is a signature of Matcha Man. Use the approved hierarchy instead of inventing local radii.

## Canonical geometry

- Checkbox — 20×20, 6px radius, 60% smoothing
- Badge / chip / tooltip — 8px radius, 60%
- Filter chip — 12px radius, 60%
- Button / Text Input / Select — 16px radius, 60%
- Card — 40px radius, 60%
- Table shell — same 40px Card radius and applicable smoothing; [[Table]] owns boundary clearance rather than reducing the radius
- Modal — 40px radius, 60%

True circles are used for:

- Radio
- Avatar
- Circular Progress
- Toggle thumb

True capsules are valid for controls where the metaphor supports it, including Toggle tracks and Progress Bars.

## Rule

DO NOT normalize every component to one radius. Geometry should communicate component family and scale.

Large-radius geometry is a defining part of Matcha Man's visual personality and should not be reduced simply because conventional components are easier to lay out with smaller radii. Preserve the **40px** Card/major-shell radius and solve layout through boundary clearance.

> Radius changes edge clearance, not the density of the entire component.

Use [[Spacing and layout#Surface hierarchy]] for boundary ownership and [[Table]] for exposed row edges. This does not turn every rounded component into a 40px Card: controls, menus, and other families retain their documented geometry. See [[Product design philosophy#Opinionated defaults]] and [[ADR-011 Radius-aware table spacing]].
