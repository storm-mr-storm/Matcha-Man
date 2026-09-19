---
title: "Component selection guide"
type: pattern
scope: product
status: canonical
last_reviewed: 2026-09-16
tags: [pattern, selection]
llm_priority: highest
---

# Component selection guide

Choose components by semantics, not visual similarity.

| Need | Use | Do not substitute |
|---|---|---|
| Contained action | [[Button]] | Tab, Menu Item, Link |
| Arbitrary single-line text | [[Text Input]] | Select |
| One hidden predefined choice | [[Select]] | Text Input |
| Few visible exclusive choices | [[Radio]] | Select by default |
| Independent boolean/multi-select | [[Checkbox]] | Radio |
| Immediate on/off state | [[Toggle]] | Checkbox when the model is a setting switch |
| Sibling view switch | [[Tabs]] | Button |
| Compact status/category | [[Badge]] | Filter Chip |
| Repeated content entities | [[List]] | Menu Item |
| Contextual commands | [[Menu]] | List Item |
| Persistent destinations | [[Navigation]] | Menu/List |
| Columnar data | [[Table]] | List |
| Process completion | [[Progress]] | Metric/Badge |
| Current work | [[Activity and Reasoning]] | Progress alone |
| Important user-facing update | [[Feedback Banner]] | Badge alone |
| Search/query | [[Search]] | Text Input alone |
| Narrow existing set | [[Filter]] | Tabs |

When in doubt, describe the semantic job in one sentence before choosing the component.
