---
title: "Future component candidates"
type: open-question
scope: product
status: open
last_reviewed: 2026-09-16
tags: [open, future-components]
---

# Future component candidates

The following candidates have been intentionally deferred until repeated product needs justify them.

## Textarea

Needed if multi-line authored input repeats enough to deserve a component. Do not force multi-line content into Text Input.

## Combobox / searchable select

Needed for large predefined option sets where users type to filter. Do not stretch plain Select into a 50-option picker.

## Multi-select

Needed when several values may be selected from a constrained set and Checkbox/Filter patterns are insufficient.

## Stepper

Potentially useful for explicit multi-step workflows. Current Progress primitives should not be expanded into a full Stepper without repeated evidence.

## Full labeled desktop sidebar

Current Navigation uses a compact vertical rail on desktop. A larger labeled sidebar is a future pattern, not part of the current primitive.

## Popover

Use if repeated rich, interactive floating content appears. Tooltip remains noninteractive.

## Specialized list compositions

Activity Row, Agent Row, Source Row, and Settings Row should only be introduced if generic List Item repeatedly fails to express their anatomy cleanly.
