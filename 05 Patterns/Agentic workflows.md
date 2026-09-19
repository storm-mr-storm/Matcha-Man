---
title: "Agentic workflows"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [pattern, agentic]
---

# Agentic workflows

Agentic workflows should make autonomy legible.

## Goal → plan → work → artifact

A useful high-level model is:

Goal → Plan → Agents → Artifacts

The UI should help users understand where work currently sits in this chain.

## Useful surfaces

- Activity stream for current work
- Feedback for important changes/blocks
- Badge for status
- Progress for bounded completion
- List for agent/task rosters
- Card for coherent summaries

## Agent handoff

Handoffs SHOULD name the source and destination when useful, e.g. Matcha Unit 04 hands milk prep to Foambot 03.

## Avoid

- Animated “thinking” everywhere
- Fake confidence theater
- Hiding blockages behind generic spinners
- Automatic action when human judgment is explicitly required
