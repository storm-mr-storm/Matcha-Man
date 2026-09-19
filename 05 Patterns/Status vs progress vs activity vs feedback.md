---
title: "Status vs progress vs activity vs feedback"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [pattern, semantics]
llm_priority: highest
---

# Status vs progress vs activity vs feedback

These concepts are intentionally separate.

## Status

“What condition is it in?”  
Typical primitive: [[Badge]] or plain text.

Example: `Brewing`

## Progress

“How far along is it?”  
Primitive: [[Progress]].

Example: `60% complete`

## Activity

“What is it doing right now?”  
Primitive/pattern: [[Activity and Reasoning]].

Example: `Steaming milk`

## Feedback

“What does the user need to notice or act on?”  
Primitive/pattern: [[Feedback Banner]].

Example: `Robot 04 needs a decision.`

## Combined example

Batch #184  
Badge: Brewing  
Progress: 60%  
Activity: Steaming milk

This can be valid because each layer communicates different information. Most UI should still avoid showing all four concepts unless each materially helps.
