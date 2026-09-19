---
title: "ADR-012 Accessible Select listbox implementation"
type: decision
scope: product
status: accepted
date: 2026-09-19
last_reviewed: 2026-09-19
release_status: unreleased
change_level: minor
tags: [decision, adr, select, accessibility]
llm_priority: high
---

# ADR-012 Accessible Select listbox implementation

## Status

Accepted; Unreleased. The current released specification remains [[06 Decisions/VERSION|v0.1.0]].

## Area

Matcha Man Product Design System → Select implementation and adoption.

## Context

The Select documentation described the trigger and named option states but omitted the full popup geometry. Precision OS had an unused Base UI Select primitive alongside 39 native Select declarations. Native operating-system menus could not reproduce the designed Figma listbox or consistent chevron clearance.

Figma inspection on 2026-09-19 confirmed the 58px trigger, 16px trigger/menu radii, 16px chevron and inset, 8px menu padding/offset, 8px option radius, 16/12px option padding, and 48px option height. The opened master swaps to ChevronUp. [[Select]] records the exact nodes and token bindings.

## Decision

Implement Select through a shared, accessible custom listbox primitive. Reuse an installed headless library where available. Preserve the canonical trigger/menu/option geometry and semantic theme tokens. Support labelled form fields and value-only filters through composition; preserve non-color selection feedback and visible keyboard focus.

Preserve form contracts and product behavior during migration, including empty values, required/disabled fields, pending states, reset, and programmatic prefill. Keep popup positioning and keyboard/focus behavior owned by the accessible library.

## Rationale

Native option menus cannot reliably reproduce the design. A shared implementation corrects all consumers and prevents page-specific patches. The Figma option radius is 8px; inventing a 12px fallback would create drift. Existing application overlay layers and accessible interactions are preferable to new dependencies or hand-written keyboard logic.

## Consequences and implementation

- Precision OS reuses `@base-ui/react/select`; no dependency is added.
- The existing low-level Select exports remain available. An additive `SelectControl` composition accepts explicit options and string-valued change callbacks, optional internal labels, and form metadata.
- Native consumers migrate from DOM ChangeEvent callbacks to value callbacks without changing their filter/mutation logic or submitted values.
- Native field-prefill integrations need a small state bridge; form reset and required validation must be checked.
- JavaScript is required for Select interaction. Searchable combobox and multiselect patterns remain separate work.
- The web implementation retains the existing check indicator and adds a quiet hover stroke because the Figma Light hover and overlay tokens resolve to the same white. This is an explicit accessibility adaptation, not a new palette.
- Figma was inspected without modification. Product adoption is recorded separately from this accepted specification.

## Version classification

**MINOR candidate under Unreleased:** an additive shared component API and meaningful interaction/adoption refinement. The existing Select API is not removed, so this is not a breaking published component replacement; the product's native markup migration is completed internally. Per [[01 Rule strength and source of truth#Versioning and change records]], meaningful refinements receive an ADR and an Unreleased record. No release is being published by this implementation pass, so `VERSION.md` remains unchanged. Earlier decisions and release records are preserved.

## Canonical defaults clarification — 2026-09-19

The accepted decision applies to **all Matcha Man Select implementations**, not only Precision OS. A Select includes both its trigger and the designed, rounded opened listbox. Where the platform supports custom styling with accessible behavior, a native OS popup is non-canonical; implementation convenience is not an exception. A platform/accessibility constraint may justify a locally documented product exception, without altering the canonical specification. See [[Product design philosophy#Opinionated defaults]].

The 16px chevron edge clearance, 16px menu radius, 8px menu padding/offset, and 8px rounded option treatment are defaults, alongside the complete geometry and accessible behavior in [[Select]]. Base UI and Precision OS's component API are adoption evidence rather than required dependencies. The rationale is consistent visual anatomy and usable, predictable interaction across products. Preserve keyboard/focus behavior, form contracts, and semantic selected/hover/focus/disabled states during adoption.

## Related tokens

Use `select/height` (58px), `radius/control` (16px trigger/menu), `radius/chip` (8px options), `control/height` (48px option minimum), and `space/8`, `space/12`, `space/16`. Semantic roles are `surface/sunken`, `surface/overlay`, `surface/selected`, `surface/interactive`, `surface/disabled`, the documented border roles, and primary/secondary/disabled text. Exact bindings and typography remain in [[Select]]. No new raw token or generic 12px option radius is introduced.
