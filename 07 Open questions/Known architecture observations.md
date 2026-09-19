---
title: "Known architecture observations"
type: open-question
scope: product
status: open
last_reviewed: 2026-09-16
tags: [open, architecture]
---

# Known architecture observations

These are areas to watch during future migration and QA work.

## Card slots

If legitimate Card use repeatedly requires detaching content because the primitive cannot host connected nested components, improve the Card architecture rather than creating local surfaces.

## Select flexibility

Watch for long values, large option sets, and reusable open-menu composition. Repeated problems may indicate a need for Combobox rather than more Select variants.

## List slots

Leading/Trailing should remain flexible enough to host connected Avatar, Icon, Badge, Progress, Checkbox, Radio, and short metadata without override fragility.

## Badge semantics

Warning vs indeterminate may need clearer semantic separation if product usage repeatedly demonstrates both.

## Progress semantics

Do not let Metric/score use cases pull Progress into being a generic percentage visual.

## Field wrapper

Repeated helper/error/character-count patterns may justify a Field composition later.
