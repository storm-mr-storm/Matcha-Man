---
title: "Select"
type: component
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [component, select]
llm_priority: high
---

# Select

**Figma page:** [12 — Select](https://www.figma.com/design/gYVK5MVOYSMWgTjdKiO0Yf/Matcha-Man?node-id=6-53). Inspected 2026-09-19: Select master `119:1070`, Select Option master `117:51`, and open composition `762:199` / menu `762:207`.

Select is for choosing **one value from a predefined set when options are hidden until opened**.

> Matcha Man Select includes both the trigger and the opened listbox surface. Native operating-system option menus are not considered a faithful implementation of the component.

**Implementation requirement:** Where the platform permits custom styling and accessible interaction, use a designed Select/Listbox implementation and style its trigger, popup, and options together. Prefer an established accessible headless primitive. Do not substitute a native OS popup because it is easier to implement: native `<option>` CSS cannot reliably control its geometry, states, or theme. These are Matcha Man defaults across products, not an optional Precision OS skin.

If platform or accessibility requirements necessitate native behavior, document that product-specific exception locally, including its reason and scope. Preserve the canonical component and do not claim the native popup is visually equivalent. See [[Product design philosophy#Opinionated defaults]] and [[ADR-012 Accessible Select listbox implementation]].

## Trigger

- Height: **58px**, `select/height`, in both responsive modes.
- Radius: **16px**, `radius/control`; Figma uses 60% corner smoothing. Web implementations use standard CSS corners.
- Horizontal content inset: **16px**, `space/16`. Nominal vertical padding: **12px**, `space/12`; vertically center the label/value group within the fixed height.
- Default surface: `surface/sunken`; border: `border/default`. Hover/open use `border/strong`; keyboard focus uses `border/focus` with a clearly visible focus outline.
- Persistent internal label + value + trailing chevron for form fields. Label uses 13/18 typography (`type/label`); value uses 16/24 (`type/body`).
- Value-only filters omit the internal label and provide an accessible name. Precision OS retains 14/20 value typography for these compact compositions, while preserving the same 58px height, insets, radius, popup, and interaction model.
- Fill the available form width. Allocate enough width for readable text, the fixed chevron, and both insets; stack or reflow a parent grid instead of compressing the icon clearance.

### Chevron

- A **16px** Lucide chevron, using `text/secondary` as bound in the Figma master.
- Its icon box sits **16px from the physical right boundary**, vertically centered; use an auto trailing margin in a flex row or an equivalent inset anchor.
- Down when closed; **up when open**, matching Figma's icon swap. No decorative rotation animation is required.
- Reserve the icon's space when truncating long values. Border/stroke implementation must not consume the specified physical inset; an inset stroke is suitable on the web.

> Icons inside form controls respect the control's horizontal content inset and should never sit directly against the physical boundary.

## Floating menu

- Distinct custom popup, portaled above parent Cards and tables through the application's existing overlay layer.
- **16px radius**, `radius/control` (the menu radius role is equivalent).
- **8px internal padding**, `space/8`.
- Surface: `surface/overlay`; border: `border/default`.
- **8px offset** from the trigger, aligned to its left edge where viewport space permits. Do not overlap the selected option with the trigger.
- Width at least the trigger width; it may grow for option text, constrained to the viewport. Long labels wrap inside the popup.
- Use viewport collision handling, available-height limits, and scrolling for longer lists. Rounded ancestors must not clip the popup. Use the existing overlay layer rather than an arbitrary z-index.

## Select Option

The canonical option radius is **8px** (`radius/chip`), as confirmed in the inspected Figma master. This existing token takes precedence over a generic 12px fallback; the separate [[Menu]] item radius is not a Select Option token.

- Horizontal padding: **16px**, `space/16`.
- Vertical padding: **12px**, `space/12`.
- Minimum height: **48px**, `control/height`; allow wrapping content to increase height.
- Body typography: **16/24**, `type/body`.
- No persistent border on every option; default options blend into `surface/overlay`.
- Option count is composition-driven; do not create `Options=3/5/8` variants.

### Option states

- **Default:** overlay surface, primary text.
- **Selected:** `surface/selected` — warm cream in Light and its semantic selected surface in Dark. Preserve an existing check indicator as a second selection cue; never substitute browser blue or a saturated brand fill.
- **Hover:** `surface/interactive`. In Figma's Light mode this resolves to the same white as the overlay; a quiet, inset `border/default` hover stroke provides a perceptible web affordance without adding borders to every resting option.
- **Keyboard focus:** clearly visible inset `border/focus` outline on the highlighted option. Pointer hover and keyboard focus are separate states; selection remains visible while focus moves.
- **Disabled:** `surface/disabled` / `text/disabled` and reduced emphasis. Expose the disabled state to assistive technology and prevent selection. Headless libraries may keep a disabled option keyboard-focusable for announcement.

## Accessibility and form behavior

Support Tab focus, Enter/Space to open, Up/Down navigation, Enter to select, Escape to close and return focus, and typeahead supplied by the accessible primitive. Expose combobox/listbox/option semantics, an accessible name, expanded state, selected state, and disabled/required/error state where applicable.

Keep labels, values, field names, empty/none choices, default values, controlled updates, form submission, validation, and reset behavior intact when adopting the custom implementation. Programmatic prefill must update both the displayed value and submitted form value. A custom Select requires JavaScript for interaction; do not silently fall back to an OS option popup and claim visual equivalence.

## Distinctions

- Arbitrary user text → [[Text Input]]
- Few visible mutually exclusive choices → [[Radio]]
- Searchable long set → future Combobox
- Contextual commands → [[Menu]]
- Querying entities → [[Search]]

## Adoption and governance

See [[ADR-012 Accessible Select listbox implementation]] and [[06 Decisions/CHANGELOG|Unreleased]]. Precision OS uses its already-installed Base UI Select with shared value-only and internally labelled compositions. Existing low-level Select exports are retained; product consumers migrate native controls to an additive value-based composition. Figma was inspected, not edited. Acceptance of this guidance does not claim adoption in every product.

The component geometry and behavior are canonical; Base UI, `SelectControl`, and the 14/20 compact-filter typography noted above record one product's adoption choices. The system does not require that dependency or API. Future implementations use the canonical rules and record any product-specific composition exceptions under the same policy.
