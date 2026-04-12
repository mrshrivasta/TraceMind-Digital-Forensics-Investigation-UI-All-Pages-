# Design System Specification: Digital Forensics & Investigation

## 1. Overview & Creative North Star: "The Digital Sentinel"
In the high-stakes world of digital forensics, clarity is authority. This design system departs from generic "admin dashboard" aesthetics to embrace a philosophy we call **The Digital Sentinel**. 

The Sentinel avoids the visual noise of traditional grids. Instead, it utilizes **Atmospheric Precision**—a combination of deep tonal layering, intentional asymmetry, and ultra-sharp typography. We are not just building a tool; we are building a lens through which investigators find the truth. The interface should feel like a high-end command center: silent, powerful, and utterly reliable. By breaking the "template" look with overlapping data panels and varying container depths, we move from a flat application to a sophisticated investigative environment.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a spectrum of deep navies and slate grays, designed to reduce eye strain during long-form data analysis while emphasizing critical action points with a sharp, electric blue.

### The "No-Line" Rule
Standard 1px solid borders are strictly prohibited for sectioning. They create visual "jail bars" that clutter technical data. Boundaries must be defined through **Background Color Shifts**. 
*   *Example:* A `surface-container-low` section should sit directly on a `surface` background. The eye perceives the edge through the shift in luminance, not a physical line.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of obsidian glass.
*   **Base:** `surface` (#071327) – The foundational "ground."
*   **Panels:** `surface-container` (#142034) – Secondary workspace areas.
*   **Active Focus:** `surface-container-high` (#1f2a3f) – Modals or active investigation streams.
*   **Interaction:** Use `surface-bright` (#2e394f) to highlight hover states or selected rows.

### The "Glass & Gradient" Rule
To elevate the "Technical" aesthetic, main CTAs and critical status indicators should utilize **Subtle Gradients**. 
*   **Primary Action:** Transition from `primary` (#adc7ff) to `on-primary-container` (#1b7fff) at a 135-degree angle. 
*   **Glassmorphism:** For floating toolbars or inspection overlays, use `surface-container-highest` at 80% opacity with a `20px` backdrop-blur. This allows data to bleed through subtly, maintaining context.

---

## 3. Typography: Editorial Authority
We utilize a dual-font strategy to balance high-end editorial feel with technical rigor.

*   **Display & Headlines (Space Grotesk):** This is our "Editorial" voice. Use `display-lg` to `headline-sm` for high-level case titles and summary metrics. Its geometric nature feels engineered and authoritative.
*   **Data & Body (Inter):** For the evidence itself—IP addresses, hash values, and file paths—Inter provides unrivaled legibility. 
*   **The Technical String:** When displaying raw terminal output or hex code, use Inter with `letter-spacing: -0.02em` to mimic the density of professional forensics monitors.

---

## 4. Elevation & Depth
In this system, depth is a functional tool, not a stylistic flourish.

### The Layering Principle
Achieve hierarchy by "stacking" container tiers. Place a `surface-container-lowest` (#030e22) card inside a `surface-container-low` (#101b30) section to create a "sunken" well for data entry, suggesting a secure, contained environment.

### Ambient Shadows
When a floating element is required (e.g., a context menu), use a shadow tinted with `primary` at 4% opacity.
*   **Shadow Specs:** `0px 16px 32px rgba(173, 199, 255, 0.04)`. This mimics the subtle glow of a high-resolution monitor in a dark room.

### The "Ghost Border" Fallback
If accessibility requirements demand a border (e.g., in high-contrast mode), use a **Ghost Border**.
*   **Spec:** `outline-variant` (#44474c) at 15% opacity. Never use 100% opaque borders; they shatter the "Sentinel" atmosphere.

---

## 5. Components

### Data Tables (The Forensic Grid)
*   **Layout:** Forbid divider lines. Use `surface-container-low` for the header and alternating `surface` and `surface-container-lowest` for rows.
*   **Alignment:** Numeric data and technical strings must be tabular-num (monospaced feel) using Inter.

### Secure Input Fields
*   **Style:** Minimalist. No bounding box. Use a 2px bottom-weighted border in `outline-variant`. On focus, transition the border to `tertiary` (#00daf3) with a subtle glow (0-4px blur).
*   **States:** Error states use `error` (#ffb4ab) with an icon prefix—never just color alone.

### Buttons & Chips
*   **Primary Button:** `primary` fill with `on-primary` text. Apply a `DEFAULT` (0.25rem) radius for a "precision-cut" look.
*   **Chips:** Use `secondary-container` for filter chips. For evidence "Tags," use `tertiary` text on a `tertiary-container` background to make them "pop" against the navy surfaces.

### Investigation Sidebar
*   **Structure:** A fixed width, `surface-container-lowest` panel. Use "Active Markers"—a 2px vertical line of `primary`—to indicate the current module, rather than highlighting the entire background.

### Evidence Status Badges
*   **Visual:** Small, high-contrast pills.
    *   *Verified:* `on-tertiary-container` text on `tertiary-container`.
    *   *Flagged:* `on-error-container` text on `error-container`.

---

## 6. Do's and Don'ts

### Do:
*   **Use Asymmetry:** Place critical metadata in an offset right-hand panel to break the "standard dashboard" feel.
*   **Embrace Negative Space:** Allow data to breathe. A dense tool doesn't have to feel cluttered.
*   **Color as Signal:** Reserve `tertiary` (#00daf3) exclusively for "live" data or active triggers.

### Don't:
*   **Don't use Rounded Corners > 0.5rem:** High-end technical tools feel precise. Large "bubbly" radii (xl, full) undermine authority. Stick to `sm` (0.125rem) and `md` (0.375rem).
*   **Don't use Pure Black:** Always use `surface` (#071327). Pure black (#000000) creates "black smear" on many monitors and feels unrefined.
*   **Don't use Standard Shadows:** Avoid generic grey shadows. If it doesn't have a hint of the `primary` or `surface` tint, it doesn't belong in this system.