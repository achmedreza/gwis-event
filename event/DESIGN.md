# Design System Strategy: Kinetic Velocity

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"Kinetic Velocity."** 

Unlike traditional information systems that feel static and encyclopedic, this system captures the fluid motion and high-impact energy of inline skating. We are moving away from the "standard dashboard" look toward a **High-End Editorial** experience. This is achieved through "The Tilt"—a structural commitment to diagonal lines, overlapping photography, and intentional asymmetry. We treat the screen not as a container, but as a path; elements should feel as though they are caught in a state of motion, utilizing breathing room to emphasize speed and precision.

## 2. Colors & Surface Architecture
The palette is rooted in a deep, technical charcoal to allow the "Electric Blue" and "Vibrant Orange" to vibrate with maximum intensity.

### The "No-Line" Rule
To maintain a premium, seamless feel, **1px solid borders are strictly prohibited** for sectioning or containment. We define boundaries through tonal shifts. For example:
*   A card using `surface-container-lowest` (#0e0e0e) should sit on a `surface` (#131313) background.
*   A sidebar or navigation rail should be defined by a shift to `surface-container-low` (#1c1b1b), not a stroke.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
*   **Base:** `surface` (#131313)
*   **Submerged Content:** `surface-container-lowest` (#0e0e0e) for backgrounds that need to recede.
*   **Active Layers:** `surface-container-high` (#2a2a2a) and `highest` (#353534) for interactive elements and modals.
Depth is created by nesting these values. An inner container should always be at least one tier higher or lower than its parent to create a "soft edge."

### The "Glass & Gradient" Rule
To move beyond a flat UI, use **Glassmorphism** for floating overlays. Apply `surface` colors at 60-80% opacity with a 12px to 20px backdrop-blur. 
*   **Signature Gradients:** For CTAs and hero highlights, utilize a linear gradient (135°) transitioning from `primary_container` (#0062ff) to `primary` (#b4c5ff). This mimics the metallic sheen of high-end skate frames.

## 3. Typography: The Editorial Edge
We utilize a high-contrast pairing to balance technical precision with human readability.

*   **Display & Headlines (Space Grotesk):** This is our "Technical Soul." Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero sections. Headlines should often be "cropped" by container edges or overlapped by action photography to create depth.
*   **Body & Labels (Manrope):** This provides the "Functional Balance." Manrope’s geometric but friendly curves ensure that technical skating data remains readable. 
*   **Visual Hierarchy:** Use `on_tertiary_fixed` (#390c00) for small labels on orange backgrounds to maintain a "Safety Gear" aesthetic—high visibility and high contrast.

## 4. Elevation & Depth
We eschew traditional drop shadows in favor of **Tonal Layering**.

*   **Ambient Shadows:** When an element must float (e.g., a floating action button), use a shadow color tinted with `surface_tint` (#b4c5ff) at 8% opacity. The blur should be expansive (32px+) to mimic natural light dispersion.
*   **The "Ghost Border" Fallback:** If a boundary is required for accessibility in complex data views, use the `outline_variant` (#424656) at **10% opacity**. It should be felt, not seen.
*   **Diagonal Force:** Layouts should utilize `clip-path` or CSS transforms to create 15-degree diagonal breaks between major sections. This breaks the "box" feel and directs the eye downward through the content.

## 5. Components

### Buttons
*   **Primary:** High-gloss gradient (`primary_container` to `primary`). No border. `md` (0.375rem) roundedness.
*   **Secondary:** Ghost style. No background, use `outline` (#8c90a2) for the "Ghost Border" at 20% opacity. Text in `primary_fixed`.
*   **Tertiary:** Bold `tertiary` (#ffb59c) text with a 15-degree slanted hover state.

### Cards & Action Frames
*   **Rule:** Forbid divider lines. 
*   **Style:** Use `surface-container-low` with high-quality action photography that breaks the container's top boundary. Incorporate a "Kinetic Notch"—a clipped corner using the `none` roundedness setting on one specific corner to suggest a skate blade's edge.

### Inputs & Form Fields
*   **Style:** Minimalist. No bounding box. Use a `surface-container-highest` bottom-heavy border (2px). Upon focus, transition the border to `secondary` (Vibrant Orange).
*   **Feedback:** Error states use `error` (#ffb4ab) but must be accompanied by a subtle `error_container` glow behind the input field.

### Specialized Component: The Velocity Chip
*   For skating stats (speed, hardness, wheel size), use `tertiary_container` (#c84000) chips with `on_tertiary_fixed` text. These should be styled with `full` roundedness (9999px) to contrast against the sharp diagonal lines of the layout.

## 6. Do's and Don'ts

### Do:
*   **Do** overlap text and images. A "Display-LG" headline should partially sit behind a skater in an action shot.
*   **Do** use `primary_fixed_dim` for sub-headers to create a sophisticated, low-contrast hierarchy.
*   **Do** use the `xl` (0.75rem) roundedness for large containers to soften the "industrial" feel of the charcoal.

### Don't:
*   **Don't** use pure black (#000000). Always use the `surface` or `surface_container_lowest` tokens to maintain depth.
*   **Don't** use vertical dividers. Use 48px or 64px of vertical white space from the spacing scale to separate content blocks.
*   **Don't** use standard 90-degree grids for everything. At least one major element per viewport should be "Off-Axis" (slanted or offset).

## 7. Signature Textures
To elevate the "Modern Sporty" feel, apply a subtle grain overlay (3% opacity) to the `background` (#131313). This adds a "pavement" texture that grounds the electric colors and makes the digital interface feel tactile and premium.