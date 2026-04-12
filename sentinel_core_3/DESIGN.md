```markdown
# Design System Document: Technical Precision & Forensic Clarity

## 1. Overview & Creative North Star
### The Creative North Star: "The Digital Lithograph"
Digital forensics is the art of uncovering truth within the void. This design system moves away from the "cluttered dashboard" trope, embracing a philosophy called **The Digital Lithograph**. Like a high-precision architectural blueprint, the UI is defined by extreme structural rigor, intentional density, and the complete absence of decorative "fluff."

We reject the standard "web app" aesthetic. There are no rounded corners, no heavy borders, and no "friendly" padding. Instead, we utilize **Tonal Architecture**—defining space through shifts in dark values and high-contrast typographic strikes. The result is an environment that feels authoritative, secure, and hyper-focused, where the data is the only hero.

---

## 2. Colors: The Tonal Spectrum
Our palette is a study in "Dark Mode" sophistication. We avoid true black in favor of deep, layered charcoals and cyans to reduce eye strain during 12-hour investigation shifts.

### Surface Hierarchy & Nesting
To achieve depth without using borders, we utilize the **Surface Tiering** model. Each layer of information must sit on a surface that is logically "higher" or "lower" than its parent.
*   **The Global Canvas:** `surface` (#131313) - The absolute base.
*   **The Main Workspace:** `surface_container_low` (#1C1B1B) - Primary data grids and tree views.
*   **Active Panels/Modals:** `surface_container_high` (#2A2A2A) - Floating inspectors or metadata sidebars.
*   **The "No-Line" Rule:** 1px solid borders are strictly prohibited for sectioning. Use `surface_container` tokens to create "blocks" of color. Let the change in HEX value define the edge.

### Accents & Indicators
*   **Primary (Teal - #45D8ED):** Used for "Found" data, active selection, and primary action paths.
*   **Secondary (Amber - #FFD799):** Reserved for "Warnings," suspicious metadata, or flagged file headers.
*   **Tertiary (Green - #00E475):** Indicates "Verified," "Secure," or "Checksum Match."

### The Glass & Gradient Rule
For high-level overlays (like Hex-to-String converters), use **Glassmorphism**. Apply `surface_container_highest` at 70% opacity with a `20px` backdrop blur. This maintains the "Digital Lithograph" feel while providing visual relief in dense data environments.

---

## 3. Typography: Forensic Readability
We use a dual-font strategy to separate **Interface Guidance** from **Hard Evidence**.

*   **Display & Headlines (Space Grotesk):** A technical, wide-set sans-serif. Use `display-md` for case IDs and `headline-sm` for panel titles. Its geometric nature evokes precision engineering.
*   **Body & Metadata (Inter):** High X-height for maximum readability in dense metadata panels. Use `body-sm` for standard data and `label-sm` for micro-annotations.
*   **The Evidence Layer (Monospace):** While not in the primary token list, all Hex and String data must be rendered in a high-quality Monospace font (e.g., JetBrains Mono) to ensure character alignment.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows have no place in a forensic tool. They are too "soft." Instead, we use **Ambient Stacking**.

*   **The Layering Principle:** To "lift" a metadata panel, place it (`surface_container_high`) over the main grid (`surface_container_low`). The contrast between `#2A2A2A` and `#1C1B1B` is the "shadow."
*   **The Ghost Border:** If high-density data requires a guide (e.g., in a Hex grid), use the `outline_variant` (#41484B) at **15% opacity**. It should be felt, not seen.
*   **Intentional Asymmetry:** Avoid centering content. Align all data to the top-left of its container to mimic the flow of terminal outputs and code compilers.

---

## 5. Components: Engineered for Data

### Specialized Data Grids
*   **Behavior:** No cell borders. Use alternating row colors (Shift between `surface` and `surface_container_low`).
*   **Hover State:** Row background shifts to `surface_container_highest`.
*   **Selection:** A 2px vertical "strike" of `primary` (#45D8ED) on the far-left edge of the row.

### Tree Views (File Navigators)
*   **Structure:** Use "L-shaped" ghost-border guides (10% opacity `outline`) to show nesting depth.
*   **Icons:** Monochromatic. Use `on_surface_variant` (#C1C7CB). Only use `secondary` (Amber) icons if a file is flagged for investigation.

### Forensic Tabs (Hex, String, Metadata)
*   **Style:** Flat, rectangular, zero-radius (`0px`).
*   **Active State:** Background matches the panel below, with a `primary` top-border of 2px.
*   **Inactive State:** `surface_container_lowest`.

### Input Fields
*   **Visuals:** No "box" look. Use a bottom-only border (the "Ghost Border" rule).
*   **Focus:** The bottom border transitions to 100% opaque `primary`.
*   **Typography:** Use `body-sm` for input text and `label-sm` for floating labels.

### Buttons
*   **Primary:** Solid `on_primary_container` (#009CAD) with `on_primary_fixed` text. Hard edges (0px radius).
*   **Secondary:** Ghost style. `outline` border at 30% opacity. No fill.
*   **Tertiary:** Text-only. Use `title-sm` weight for authority.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** embrace the `0px` radius. This system is about "Brutal Precision."
*   **Do** use `primary_container` for large background areas of the UI that require focus without being "loud."
*   **Do** prioritize vertical rhythm. Use 4px increments for all spacing to maintain a "coded" feel.

### Don’t:
*   **Don’t** use shadows to indicate depth. If a component doesn't stand out, adjust the `surface-container` tier.
*   **Don’t** use standard "Success Green." Use the `tertiary` (#00E475) to signify technical verification.
*   **Don’t** add padding to data grids. The goal is "Data Density"—allow the information to fill the space.
*   **Don't** use 100% white text. Use `on_surface` (#E5E2E1) to maintain the "Lithograph" aesthetic.