```markdown
# Design System Specification: Digital Intelligence & Forensic Rigor

## 1. Overview & Creative North Star
**Creative North Star: "The Sentinel’s Lens"**

This design system moves away from the generic "SaaS Dashboard" look to embrace a high-density, technical aesthetic inspired by advanced forensics and aerospace instrumentation. The goal is to provide a sense of **unshakable authority and precision.** 

Unlike standard systems that rely on whitespace to create "breathing room," this system utilizes **high-information density** paired with **tonal depth**. We treat the screen as a high-fidelity instrument where every pixel serves a functional purpose. We break the "template" look through a strict adherence to sharp, 0px radius geometry (The Brutalist Edge) and sophisticated layering that mimics a glass-on-glass command center.

---

## 2. Colors: Tonal Architecture
The palette is rooted in deep, midnight blues and technical grays, punctuated by high-visibility "Alert" tones.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** To achieve a high-end, integrated feel, boundaries must be defined solely through background color shifts. For example, a `surface-container-high` panel should sit directly on a `surface` background. The change in hex value is the boundary.

### Surface Hierarchy & Nesting
Depth is achieved through the "Physical Layer" principle. Treat the UI as a series of stacked technical glass panes:
- **Base Layer:** `surface` (#060e20)
- **Primary Workspaces:** `surface-container-low` (#06122d)
- **Active Inspection Panels:** `surface-container-high` (#031d4b)
- **High-Priority Modals:** `surface-container-highest` (#00225a)

### The "Glass & Gradient" Rule
To prevent the UI from feeling "flat" or "dead," use a 5% opacity linear gradient on primary action surfaces, transitioning from `primary` (#7bd0ff) to `primary_container` (#004c69). For floating toolbars, apply a `backdrop-blur` (min 12px) to `surface_variant` at 60% opacity to create a "frosted lens" effect.

---

## 3. Typography: The Technical Script
The typography is split between a technical, wide-set display face and a high-readability body face.

*   **Headlines & Data Labels (Space Grotesk):** Chosen for its "engineered" feel. Use `headline-sm` and `display-sm` for section headers and critical forensic metrics. The slight idiosyncrasies in the letterforms suggest a custom-built tool rather than a generic interface.
*   **Data & Body (Inter):** The workhorse for high-density tables and logs. Inter’s tall x-height ensures that even at `label-sm` (0.6875rem), forensic hashes and metadata remain legible.
*   **Intentional Asymmetry:** Align primary headers to the far left, but offset data-heavy sidebars with `title-sm` labels shifted 4px to the right of the container edge to create a "mechanical" alignment look.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are forbidden. We use **Ambient Light** and **Material Stacking**.

*   **The Layering Principle:** Depth is conveyed by shifting from `surface_container_lowest` (deepest/back) to `surface_bright` (top/front). 
*   **Ambient Shadows:** If a floating element (like a context menu) requires separation, use a shadow with a 32px blur, 0px spread, and a color of `on_surface` (#dee5ff) at **4% opacity**. This mimics light refracting through deep glass.
*   **The Ghost Border Fallback:** If high-contrast separation is required for accessibility, use a "Ghost Border": `outline_variant` (#2b4680) at **15% opacity**. Never use 100% opaque lines.

---

## 5. Components: Robust & Functional

### Buttons (The "Module" Style)
*   **Primary:** Rectangular (0px radius). Background: `primary`. Text: `on_primary`. Apply a subtle 1px inner-glow (top edge only) using `primary_fixed` at 20% opacity.
*   **Secondary:** No background. `outline` border (Ghost Border style). Text: `primary`.
*   **State:** On hover, shift background to `primary_dim`. On active, shift to `inverse_primary`.

### Forensic Data Tables (High Density)
*   **Forbid Dividers:** Do not use horizontal lines between rows. Use alternating row colors: `surface` and `surface_container_low`.
*   **Typography:** Use `body-sm` for data entries. Use `label-md` with `on_surface_variant` for column headers in ALL CAPS with 0.05em letter spacing.

### Status Indicators (Alert Tones)
*   **Critical:** `error` (#ee7d77). Use for unauthorized access or data corruption.
*   **Warning/Pending:** `tertiary` (#ffb148). Use for ongoing scans or suspicious artifacts.
*   **Secure:** `primary` (#7bd0ff). Use for verified data.

### Input Fields
*   **Style:** Filled style using `surface_container`. No bottom line. A 2px vertical "accent bar" of `primary` should appear on the left side only when the field is focused.
*   **Error State:** Background shifts to `error_container` at 20% opacity with an `error` accent bar.

### Forensic Chips
*   **Metadata Tags:** Small, rectangular, using `secondary_container`. Text in `on_secondary_container`. For "Evidence" tags, use `tertiary_container` with `on_tertiary_container` to draw the investigator's eye.

---

## 6. Do's and Don'ts

### Do:
*   **Use 0px Border Radius:** Every corner must be sharp. This communicates precision and a "no-nonsense" professional environment.
*   **Embrace Density:** Information density is a feature, not a bug. Investigators need to see as much data as possible without scrolling.
*   **Use Tonal Transitions:** Separate the sidebar from the main stage using `surface_container_low` vs `surface`.

### Don't:
*   **No Rounded Corners:** Avoid the "consumer app" look. No `4px` or `8px` radii.
*   **No Generic Shadows:** Never use `#000000` shadows. Use the `on_surface` tint to maintain the deep blue atmosphere.
*   **No Dividers:** If you feel the urge to add a line, use a 16px or 24px vertical gap or a background color shift instead.
*   **No "Playful" Motion:** Animations should be "Stiff & Immediate" (e.g., 150ms Linear or Ease-In). Avoid bouncy or elastic transitions.```