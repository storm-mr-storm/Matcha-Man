---
title: "Iconography"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [foundation, icons]
decision: [[ADR-004 Local Lucide icon component]]
---

# Iconography

Matcha Man uses a local **Icon** component whose glyphs are derived from Lucide.

## Architecture

- One component set: `Icon`
- One main variant property: `Name`
- Canonical Lucide names are preserved, e.g. `House`, `Search`, `Settings`, `CircleCheck`, `Trash2`.
- Source grid: 24×24
- Default Lucide stroke: 2px
- Round caps and joins
- No Size variants
- No Color variants

Consumers resize Icon instances to fit context, commonly 16, 20, 24, or 32px.

## Naming rationale

Preserving Lucide canonical names keeps Figma and implementation aligned:

`Icon → Name=CircleCheck` maps cleanly to a Lucide code component with the same canonical glyph name.

## Color

The Icon primitive represents shape. The consuming component/context owns semantic color.

## Brand icons

Brand logos are separate. Do not mix company logos into the general Lucide Icon set without reviewing their own licensing/trademark rules.

## Distribution

Keep Lucide attribution and current third-party license requirements with distributed system assets.
