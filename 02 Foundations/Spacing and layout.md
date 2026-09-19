---
title: "Spacing and layout"
type: foundation
scope: product
status: canonical
last_reviewed: 2026-09-19
tags: [foundation, spacing, layout]
---

# Spacing and layout

Matcha Man uses relationship-based spacing rather than a flat one-gap system.

**Implementation requirement:** The hierarchy below is the canonical default for Matcha Man surface composition across products. Apply it when generating or refactoring UI; document deliberate exceptions locally under [[Product design philosophy#Opinionated defaults]].

## Common rhythm

- Tight relationship — ~8px
- Standard relationship — ~16px
- Major separation — ~24px

More specific component relationships use 4px for title/supporting copy and 12px for dense internal cell spacing. Use existing spacing roles rather than arbitrary intermediate values.

These values are defaults, not an instruction to put one `gap=16` on every Auto Layout.

## Principle

Tighter spacing indicates one thought. Larger spacing indicates a new relationship or region.

> Surface padding describes distance from a component's physical boundary. Internal spacing describes relationships between content. Do not substitute one for the other.

> Direct siblings inside the same surface should normally share a common primary content axis.

Components sharing the same parent surface should share the same primary content axis unless there is a deliberate hierarchy change.

## Surface hierarchy

| Context | Spacing ownership |
| --- | --- |
| Major 40px rounded shell | Direct content uses **24px physical boundary clearance**; headings, direct rows, and footers share the 24px horizontal axis |
| Nested bordered/filled surface | The panel respects its parent's **24px** inset; its own content uses **16px** internal padding |
| Dense/table cell | Internal inline padding is **12px**; first/last table cells still respect the major shell's 24px edge inset |
| Closely related content | Use **4–8px** between related elements: 4px title/support in dense cells, 8px label/value/support in metrics |

This hierarchy applies to headings, list and queue rows, review bodies, action/footer regions, and standalone Card content. At exposed top/bottom boundaries, the owning region supplies the major-shell clearance; interior rows keep their own density. Compact list rows may retain 12px block padding and standard review rows 16px away from those exposed edges; tables follow [[Table]]. Do not increase every row's padding or reduce the 40px radius.

The intended nesting is **40px shell → 24px → nested surface → 16px → content**. A nested surface establishes a new content axis; its text need not align with the outer heading. A plain structural wrapper or row divider does not establish a new padded surface.

Apply each inset once. A standard padded Card already supplies 24px; its unframed children must not add another shell inset. In an unpadded sectioned shell, the heading, rows, and footer each supply the same 24px horizontal inset, and the first/last region owns exposed block-edge clearance. When an inset panel already supplies 16px, avoid duplicating it on its unframed children. Controls retain their own documented internal padding.

This surface hierarchy does not replace explicit geometry for other component families: for example, [[Modal and Overlay]] keeps its documented ~32px padding and [[Select]] its 8px popup padding. A distinct component specification is a deliberate system rule, not permission to silently substitute 16px for a major Card boundary.

Keep the 24px major-shell inset across viewports under the current [[Responsive behavior]] defaults. There is no blanket 16px mobile-shell exception. Preserve explicit component-specific responsive rules where documented.

### Shared content axis

Direct siblings normally align as follows:

```text
24px → Section title
24px → Row title
24px → Supporting copy
24px → Next row
```

Do not pair a 24px section-title inset with 16px direct row/support insets. Use a new axis only when a deliberately nested surface establishes one: **24px → nested panel → 16px → content**.

The full **24 / 16 / 12 / 4–8** hierarchy and shared-axis rule are accepted in the dated extension to [[ADR-011 Radius-aware table spacing]].

## Ownership

Components own internal spacing. Parents own external spacing.

Examples:

- Button owns icon/text gap and horizontal padding.
- Card owns 24px edge padding.
- In a [[Table]] shell, cells and section bands supply that edge inset; the shell itself has zero padding. Boundary clearance and normal row density are separate roles, as accepted in [[ADR-011 Radius-aware table spacing]].
- Form layout owns the gap between fields and the Button.
- Grid owns the gap between Cards.

Avoid embedding margins into components simply to reproduce one composition.

Use component-specific spacing roles where relationships differ: Table uses a 4px primary title/supporting gap and 12px internal cell inline padding within the existing spacing rhythm. Reuse shared spacing primitives and the card-padding role rather than duplicate raw values in each product. See [[Table]] for the full spacing model and exposed-edge rules.
