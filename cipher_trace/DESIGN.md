# Design System Document: Tactical Precision & The Forensic Lens

## 1. Overview & Creative North Star
### The Creative North Star: "The Digital Sentinel"
In the world of digital forensics, clarity is the difference between a breakthrough and a missed lead. This design system moves away from the "cluttered dashboard" trope of technical tools and instead embraces a high-end, editorial approach to data density. We treat information as a premium asset.

The system is built on the concept of **"The Digital Sentinel"**—an environment that feels authoritative, impenetrable, and surgically precise. We achieve this by rejecting the "standard" boxy UI in favor of asymmetric data layouts, layered depth through tonal shifts, and a sophisticated interplay between the tech-forward *Space Grotesk* and the utilitarian *Inter*. This is not a generic portal; it is a professional workstation designed for cognitive flow.

---

## 2. Colors: Tonal Depth & The No-Line Rule
The palette is rooted in deep, midnight blues and charcoals to reduce eye strain during long investigations.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. Layout boundaries must be defined solely through background color shifts. 
*   *Implementation:* Use `surface_container_low` for the main canvas, and `surface_container` for primary work areas. The transition in tone is the boundary.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Hierarchy is achieved by nesting darker tones within lighter ones (or vice versa) to create a "recessed" or "elevated" effect.
*   **Base:** `background` (#060e20)
*   **Sectioning:** `surface_container_low` (#06122d)
*   **Focused Workspaces:** `surface_container` (#05183c)
*   **Floating Panels:** `surface_container_highest` (#00225a)

### The Glass & Gradient Rule
To prevent the UI from feeling "flat" or "dead," use semi-transparent surfaces with backdrop-blur (12px–20px) for floating overlays. Main CTAs should utilize a subtle vertical gradient from `primary` (#7bd0ff) to `primary_container` (#004c69) to provide a "machined metal" sheen.

---

## 3. Typography: The Editorial Data Scale
We prioritize high-contrast typography to ensure that even in dense data views, the hierarchy is unmistakable.

*   **Display & Headlines (Space Grotesk):** Used for high-level metrics and view titles. *Space Grotesk* provides a technical, slightly avant-garde feel that distinguishes this as a modern tool.
*   **Body & Labels (Inter):** Used for all data points, logs, and evidence descriptions. *Inter* is chosen for its exceptional legibility at small sizes.

**Key Rule:** Large `display-lg` headers should be paired with `label-sm` metadata in close proximity to create an "Editorial" look—high contrast in scale creates a premium feel.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows and borders are replaced by a physics-based layering system.

### The Layering Principle
Depth is achieved by "stacking" surface tiers. To create a card effect, place a `surface_container_highest` element onto a `surface_container` background. The contrast in the blues provides a "soft lift."

### Ambient Shadows
If an element must float (e.g., a context menu), use a "Tinted Shadow":
*   **Color:** `surface_container_lowest` (#000000)
*   **Blur:** 24px–40px
*   **Opacity:** 15%
*   **Note:** Shadows must never be neutral grey; they must feel like an occlusion of the deep blue background.

### The "Ghost Border" Fallback
If a visual separator is required for accessibility, use a "Ghost Border": `outline_variant` (#2b4680) at 15% opacity. It should be felt, not seen.

---

## 5. Components: Robust & Precise

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_dim`), roundedness `sm` (0.125rem). The sharp corner suggests precision.
*   **Secondary:** No fill. `outline` (#5b74b1) at 30% opacity. Text in `on_surface`.
*   **Tertiary:** Text only in `primary_dim`, transitioning to `primary` on hover.

### Input Fields & Data Entry
*   **Style:** `surface_container_lowest` backgrounds. 
*   **Focus State:** No thick border. Use a subtle glow using `surface_tint` at 10% opacity and a 1px `primary` ghost border.
*   **For Forensic Integrity:** Use `label-sm` for all helper text to ensure the investigator has context without cluttering the scan path.

### Evidence Cards & Log Lists
*   **No Dividers:** Lists must not use horizontal lines. Use a 4px vertical gap between items and alternate background colors between `surface_container_low` and `surface_container` if necessary.
*   **Status Indicators:** Use `tertiary` (#ff6f7e) for high-priority alerts and `primary` (#7bd0ff) for informational pings. These should be small, high-intensity "pips."

### Forensic-Specific Components
*   **The "Hash-Tag" Chip:** Use `secondary_container` for file hashes. These should be mono-spaced if possible, using `label-md` for maximum character distinction.
*   **Timeline Scrubber:** A custom component using `surface_bright` to indicate the current "window of investigation" against a `surface_variant` track.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use intentional asymmetry. Align high-level stats to the right while labels stay left to create a sophisticated, non-template look.
*   **Do** embrace "Negative Space as a Separator." Allow your data to breathe; the dark palette makes empty space feel like part of the "void" of the system.
*   **Do** use `primary_fixed_dim` for non-interactive technical metadata to keep it legible but secondary.

### Don’t:
*   **Don't** use `9999px` (full) roundedness except for notification badges. We want the tool to feel "engineered," not "bubbly." Stick to `sm` (0.125rem) and `md` (0.375rem).
*   **Don't** use pure white (#ffffff) for text. Use `on_surface` (#dee5ff) to maintain the "night-vision" comfort of the system.
*   **Don't** ever use a standard "Drop Shadow" preset. If it doesn't look like ambient light hitting a surface, it doesn't belong in this system.