# Design System Strategy: The Rogue Experiment

## 1. Overview & Creative North Star
**Creative North Star: "The Interstellar Rogue"**

This design system is a departure from the sterile, predictable world of corporate "SaaS-blue" aesthetics. It is an intentional fusion of high-precision technology and organic chaos—inspired by the duality of Experiment 626. We are building a "Digital Cockpit" that feels like a piece of salvaged galactic tech: high-performance, slightly dangerous, and undeniably premium.

To break the "template" look, we move away from centered, symmetrical layouts. Instead, we embrace **Intentional Asymmetry**. Large typography (`display-lg`) should bleed off edges or overlap containers, while grid patterns act as a structural anchor for floating glass elements. The result is a UI that feels alive, layered, and deep—mimicking the vastness of a deep-space environment.

---

## 2. Colors & Surface Architecture
The palette is rooted in the deep void of space, punctuated by the high-voltage energy of neon gas.

*   **Primary Background (`surface`):** The foundation is `#000e26`. Never use pure black; this deep blue provides the necessary tonal depth to make our glass effects pop.
*   **The "No-Line" Rule:** We do not use 1px solid borders to separate sections. Boundaries are defined by shifting between `surface-container-low` and `surface-container-high`. If you need to separate a section, change the background color—do not draw a line.
*   **Surface Hierarchy & Nesting:** Treat the UI as a series of stacked translucent sheets. 
    *   **Level 0:** `surface` (The Void)
    *   **Level 1:** `surface-container-low` (The Base Grid)
    *   **Level 2:** `surface-container-highest` (Floating Glass Cards)
*   **The "Glass & Gradient" Rule:** All primary cards must use **Glassmorphism**. Apply `surface-variant` with a 40-60% opacity and a `backdrop-blur` of 12px to 20px. 
*   **Signature Textures:** Incorporate a subtle, repeating 24px grid pattern across the `surface-container-low` tier using the `outline-variant` color at 10% opacity. This reinforces the "high-tech" engineering aesthetic.

---

## 3. Typography
Typography is our primary tool for editorial impact. We contrast the rigid geometry of the body text with the aggressive, futuristic display fonts.

*   **Display & Headlines (Space Grotesk):** This is our "Tech" voice. Use `display-lg` for hero sections with tight letter spacing (-0.05em). It should feel massive, commanding, and slightly "glitchy" in its precision.
*   **Body & Titles (Manrope):** This is our "Functional" voice. Manrope provides a geometric clarity that ensures readability against complex glass backgrounds. 
*   **Scale Contrast:** To achieve a high-end editorial feel, pair `display-lg` directly with `body-md`. The extreme jump in scale creates a visual hierarchy that feels curated rather than automated.

---

## 4. Elevation & Depth
In this system, depth is not simulated by light sources, but by **Tonal Layering** and **Luminance**.

*   **The Layering Principle:** Use the Material `surface-container` tokens to "lift" objects. A `surface-container-highest` card sitting on a `surface` background creates a natural, soft lift.
*   **Ambient Shadows:** We avoid dark grey shadows. When a floating state is required, use a shadow color derived from `surface-tint` (#5ed4fd) at 5% opacity with a 40px blur. It should look like the element is emitting a faint cyan glow onto the surface below, not casting a shadow.
*   **The "Ghost Border" Fallback:** Where a container needs to pop against a similar background, use a **Ghost Border**. This is a 1px inner stroke using `outline-variant` at 15% opacity. It mimics the edge of a glass pane catching light.
*   **Neon Accents:** Use `primary` (#5ed4fd) for "active" tech elements and `secondary` (#fe9da9) for "organic/playful" elements. These should be used sparingly—like a warning light on a dashboard.

---

## 5. Components

### Buttons
*   **Primary:** Solid `primary` (#5ed4fd) background with `on-primary` text. Apply a subtle outer glow using `primary` at 20% opacity.
*   **Secondary:** Glass-style. Background: `surface-variant` (30% opacity) + `backdrop-blur`. Border: Ghost Border using `primary`.
*   **Shape:** Use the `sm` (0.125rem) or `none` (0px) roundedness scale for a "Brutalist-Tech" feel. Avoid large rounds for buttons.

### Cards & Lists
*   **Cards:** Strictly forbid divider lines. Use `surface-container-high` as the card background against a `surface` background. Use 32px or 48px of padding to let content breathe.
*   **Lists:** Separate items using a background shift on hover (`surface-container-highest`) rather than lines. 

### Inputs & Interaction
*   **Text Fields:** Use a "Bottom-Line Only" approach or a fully enclosed glass container. 
*   **Focus State:** When an input is active, the Ghost Border should transition to 100% opacity `primary` with a faint cyan glow.
*   **Chips:** Use `secondary_container` for a playful "Stitch" pink accent. These should be rounded at the `full` scale to contrast with the sharp edges of the rest of the UI.

### Technical HUD Elements
*   **Data Visualization:** Use `tertiary` (#8da4ff) for secondary data streams. All charts and graphs should be rendered in thin 1px lines (no fills) to maintain the "blueprint" look.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical margins. If the left margin is 80px, try making the right margin 120px to create movement.
*   **Do** overlap elements. Let a glass card sit halfway over a large background headline.
*   **Do** use `secondary` (#fe9da9) for micro-interactions, like heart icons or success states, to add a "mischievous" personality to the tech.

### Don't:
*   **Don't** use 100% opaque borders. It breaks the glass illusion and feels "cheap."
*   **Don't** use standard drop shadows. If it doesn't look like light is passing through it, it doesn't belong in this system.
*   **Don't** crowd the interface. The "Galactic" feel requires negative space to represent the vastness of the theme.