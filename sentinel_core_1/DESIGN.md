# Design System Strategy: The Forensic Lens

## 1. Overview & Creative North Star
**Creative North Star: "The Silent Observer"**
This design system rejects the "dashboard-as-a-toy" aesthetic. It is built for the high-stakes, high-density world of digital forensics where clarity is the only metric that matters. To achieve an authoritative, high-end editorial feel, we move away from traditional borders and "boxy" layouts, opting instead for **Tonal Architecture**. 

The "Silent Observer" aesthetic uses intentional asymmetry—where data-heavy sidebars contrast with expansive, airy preview panels—to guide the investigator's eye. We are not just building an interface; we are building a precision instrument. By utilizing deep navy layering and sophisticated typographic scales, we ensure the tool feels like a premium workspace, not a generic software suite.

## 2. Colors & Surface Philosophy
The palette is rooted in the depth of a midnight sky, using varying shades of navy and slate to create a sense of focused immersion.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. They clutter the visual field and distract from the data. Instead, define boundaries through **background color shifts**. Use `surface-container-low` for the base canvas and `surface-container-high` for active modules.

### Surface Hierarchy & Nesting
Treat the interface as a physical stack of forensic evidence.
*   **Base Layer:** `surface` (#0b1326) – The deep void of the investigation.
*   **Primary Workspaces:** `surface-container-low` (#131b2e) – Large areas for data tables.
*   **Active Modules:** `surface-container-highest` (#2d3449) – To highlight a selected file or active process.
*   **Nesting:** A `surface-container-lowest` card (#060e20) placed inside a `surface-container-high` section creates a "recessed" effect, ideal for input fields or technical logs.

### The "Glass & Gradient" Rule
For floating inspectors or modal overlays, use **Glassmorphism**. Apply `surface_variant` with a 60% opacity and a `24px` backdrop blur. This keeps the investigator tethered to the background context while they work in the foreground. Use a subtle linear gradient (from `primary` to `primary_container`) only for high-action states like "Generate Report" to provide a signature, polished "soul" to the otherwise austere environment.

## 3. Typography: The Editorial Scale
We use two distinct typefaces to balance technical authority with modern sophistication.

*   **Display & Headlines (Space Grotesk):** This typeface provides a mathematical, slightly "tech-brutalist" edge. Use `display-lg` for case numbers and `headline-sm` for section headers. It signals that this tool is a modern, high-tier instrument.
*   **Body & Technical Data (Inter):** The workhorse. Inter is used for all forensic data, logs, and file paths. It is highly legible even at `label-sm` (0.6875rem) for high-density metadata tables.
*   **Hierarchy as Navigation:** Bold `title-sm` labels in `on_surface` contrast against `body-sm` metadata in `on_surface_variant` to ensure the eye hits the "Key" before the "Value."

## 4. Elevation & Depth
Depth is a functional tool, not a stylistic flourish.

*   **Tonal Layering:** Avoid shadows for static elements. Use the difference between `surface-container-lowest` and `surface-container-high` to create a "stepping" effect.
*   **Ambient Shadows:** For floating elements (like a file preview card), use an extra-diffused shadow: `box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4)`. The shadow must feel like a soft glow of the underlying navy, never a harsh black drop shadow.
*   **The "Ghost Border" Fallback:** If a container must be separated (e.g., in a high-density list), use `outline_variant` (#454652) at **15% opacity**. This creates a "suggestion" of a line that only becomes visible upon focus.

## 5. Components & Data Visualization

### Data Tables & Lists
*   **The Forbidding of Dividers:** Do not use horizontal lines between rows. Instead, use a 4px `surface-container-high` hover state and 12px of vertical `body-sm` spacing to separate entries.
*   **Status Badges:** Use `tertiary` (#fabd00) for "Warning/Processing" and `error` (#ffb4ab) for "Critical Finding." These must be small, high-contrast pills with `label-sm` text.

### File Preview Cards
*   Use `surface-container-low` as the card base.
*   No borders. Use a `sm` (0.125rem) corner radius for a sharp, professional look.
*   Header areas should use `surface-container-highest` to differentiate the filename from the file content preview.

### Activity Timelines
*   The timeline stem should be a 1px `outline_variant` at 20% opacity.
*   Events are marked by `primary` dots. "Critical" events use a `error` dot with a soft 4px glow (blur) of the same color to draw immediate attention without breaking the layout.

### Input Fields
*   Use `surface-container-lowest` for the field background.
*   The only "line" allowed is a 2px `primary` underline that appears only on focus, signaling the "active investigation" state.

## 6. Do's and Don'ts

### Do
*   **Embrace Density:** Forensic investigators need data. Use `body-sm` and `label-sm` aggressively to maximize information per square inch.
*   **Use Intentional Asymmetry:** Align technical metadata to the right and descriptive labels to the left to create an editorial, "NASA-control-room" feel.
*   **Prioritize Clarity:** Ensure `on_tertiary_container` text on `tertiary_container` backgrounds meets AA accessibility standards for alert states.

### Don't
*   **Don't use Rounded Corners for everything:** Stick to `sm` (2px) or `none` for data containers. Large `xl` radii look too "consumer-friendly" and diminish the tool's authority.
*   **Don't use pure black:** Always use the `background` (#0b1326) to maintain the "Navy Slate" depth.
*   **Don't use 100% Opaque Dividers:** If you feel the need to draw a line, use a background color shift instead. If you must use a line, it must be a "Ghost Border" at 15% opacity.