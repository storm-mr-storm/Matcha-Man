---
title: "Shape and geometry"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-18
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
