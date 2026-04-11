# Design System: The Cognitive Workspace

## 1. Overview & Creative North Star
**Creative North Star: "The Editorial Scholar"**
This design system rejects the "SaaS-template" aesthetic in favor of a high-end, editorial experience. It is designed to facilitate deep work, bilingual synthesis, and professional-grade transcription. Unlike generic platforms that rely on heavy borders and loud accents, "The Editorial Scholar" uses **Atmospheric Depth** and **Intentional Asymmetry** to guide the eye. 

The layout should feel like a premium physical workspace: expansive, quiet, and organized. We achieve this by using generous negative space, sophisticated tonal layering, and a "typographic-first" hierarchy where the content is the interface.

---

## 2. Colors & Surface Philosophy
The palette is rooted in a spectrum of "Focus Blues" and "Clinical Neutrals." We use color not as decoration, but as a functional map for the user’s attention.

*   **Primary (#0040a1):** Reserved for active focus and primary progression.
*   **Secondary (#516073):** Used for metadata and bilingual secondary text to reduce visual noise.
*   **Tertiary (#940010):** A sophisticated deep red for "Live" states and recording, avoiding "Warning" orange to maintain a professional tone.

### The "No-Line" Rule
Traditional 1px borders are strictly prohibited for sectioning. They create visual friction and "box in" the user's thoughts. Instead:
*   **Tonal Transitions:** Define sections by shifting from `surface` (#f8f9fa) to `surface-container-low` (#f3f4f5).
*   **The Glass & Gradient Rule:** For floating media controls or recording overlays, use `surface_container_lowest` at 80% opacity with a `backdrop-blur` of 20px. 
*   **Signature Textures:** Main CTAs (like "Finish Transcription") should utilize a subtle linear gradient from `primary` (#0040a1) to `primary_container` (#0056d2) at a 135-degree angle to provide a "jewel" depth.

---

## 3. Typography: The Bilingual Engine
We utilize a dual-font strategy to balance authority with readability.

*   **Display & Headlines (Manrope):** A geometric neo-grotesque that feels architectural. Use `display-md` for landing moments and `headline-sm` for workspace module titles.
*   **Body & Titles (Inter):** Chosen for its exceptional x-height and legibility in bilingual contexts (e.g., English and Mandarin side-by-side). 
    *   **Transcription Areas:** Use `body-lg` with an increased line-height (1.6) to prevent eye fatigue.
    *   **Bilingual Metadata:** Use `label-md` in `secondary` color for translated sub-text.

The hierarchy must be dramatic. A `display-lg` title should sit near a `body-md` description to create an editorial, high-contrast look.

---

## 4. Elevation & Depth
We eschew the "shadow-heavy" look of Material Design for a more contemporary **Tonal Layering** approach.

*   **The Layering Principle:** 
    *   **Base:** `surface` (#f8f9fa)
    *   **Content Areas:** `surface-container-lowest` (#ffffff)
    *   **Navigation/Sidebars:** `surface-container-low` (#f3f4f5)
*   **Ambient Shadows:** For "Active" floating states (like a recording pop-up), use a shadow: `0px 20px 40px rgba(25, 28, 29, 0.06)`. The tint is derived from `on-surface` to ensure the shadow feels like a natural obstruction of light, not a gray smudge.
*   **The "Ghost Border" Fallback:** If a border is required for a file upload drag-and-drop zone, use `outline-variant` (#c3c6d6) at 20% opacity with a dashed stroke.

---

## 5. Components

### Media Player & Waveform
*   **The Waveform:** Avoid harsh bars. Use a continuous SVG path filled with `primary_fixed_dim` (#b2c5ff). The "played" portion of the waveform should transition to `primary` (#0040a1).
*   **Controls:** Nest the play/pause inside a `surface-container-highest` circle. No borders.

### Recording Controls
*   **The Record Button:** A `tertiary` (#940010) circle. When active, it should pulse with a subtle `tertiary_container` outer glow.
*   **Timer:** Display in `manrope` using `title-lg` for a high-end, "Swiss watch" precision feel.

### File Upload Areas
*   **Styling:** A large, `surface-container-low` expanse. Instead of an icon, use a `headline-sm` prompt.
*   **Interaction:** On drag-over, the background should transition smoothly to `primary_fixed` (#dae2ff).

### Transcription Text Areas
*   **Structure:** Forbid divider lines between speakers. Use `surface-container-low` blocks for Speaker A and `surface-container-lowest` for Speaker B.
*   **Interactive Text:** Hovering over a word should highlight it with `secondary_container` (#d4e4fb) with a `md` (0.375rem) corner radius.

### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_container`), `on-primary` text, `full` (9999px) roundedness for a modern "pill" look.
*   **Secondary:** No fill. `primary` text. Use `surface-variant` on hover.

---

## 6. Do’s and Don’ts

### Do:
*   **Use Asymmetry:** Place a large transcription area next to a slim, offset media control panel to create a "designer" feel.
*   **Respect the "Breath":** Give the bilingual text 32px or 48px of padding. Tight text feels "cheap."
*   **Tonal Separation:** Use `surface-dim` for the very bottom "footer" or "status bar" of the app to anchor the experience.

### Don’t:
*   **Don't Use Pure Black:** Always use `on-surface` (#191c1d) for text.
*   **Don't Use Standard Shadows:** Avoid CSS `box-shadow: 0 2px 4px rgba(0,0,0,0.5)`. It breaks the high-end aesthetic.
*   **Don't Use Dividers:** Never use a `<hr>` or a 1px solid border to separate list items. Use 16px of vertical space or a subtle background shift instead.
*   **Don't Overuse the Red:** The `tertiary` red is for "Live/Recording" states only. Do not use it for general errors; use `error` (#ba1a1a) for those.