---
title: "Motion and active work"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [foundation, motion]
decision: [[ADR-009 Observable agentic UI]]
---

# Motion and active work

Motion in Matcha Man is restrained and functional.

## Signature active-work treatment

The working state in [[Activity and Reasoning]] MAY use moving gradient text.

Conceptual gradient:

`text/secondary → accent/info → text/primary → accent/info → text/secondary`

Guidance:

- Highlight band roughly 20–30%
- Left-to-right movement
- Approximately 2 seconds
- Linear loop
- No bounce
- No glow
- No rainbow

Use jazz blue / info semantics, not positive matcha green.

## Reduced motion

Fallback to static jazz-blue/info text or a subtle static gradient plus explicit status.

## Principle

Motion supplements state. It must never be the only way to understand what is happening.
