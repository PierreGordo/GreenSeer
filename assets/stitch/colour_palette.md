# Design System Specification: The Emerald Intelligence

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Druid."** This concept merges high-tech, cyber-industrial aesthetics with a deep, organic vibrancy. It is designed to feel like a high-end surveillance terminal or a bio-digital interface—precise, illuminated, and authoritative.

To break the "template" look, this system rejects the standard rounded-corner "Web 2.0" aesthetic in favor of **Zero-Radius Brutalism**. By using `0px` border-radii across the board, we create a sharp, architectural silhouette. We move beyond the grid by using **intentional asymmetry**: large-scale `display-lg` typography often sits "off-axis" or overlaps surface containers, creating a sense of sophisticated, editorial motion.

## 2. Colors & Surface Architecture
The color palette is built on a "Deep Sea to Neon" transition. The primary goal is to maintain a high-contrast environment where the green accents appear to "glow" against the slate abyss.

### The "No-Line" Rule
**Prohibit 1px solid borders for sectioning.** Boundaries must be defined solely through background color shifts. Use `surface-container-low` (#091328) for section blocks sitting on a `surface` (#060e20) background. This creates a "monolithic" feel rather than a "boxed" feel.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- **Base Layer:** `surface` (#060e20)
- **Primary Containers:** `surface-container` (#0f1930)
- **Elevated Insets:** `surface-container-highest` (#192540)
Instead of a flat grid, nest an inner container using a higher tier to define its importance, creating a sense of "carved out" UI.

### The "Glass & Gradient" Rule
To prevent the UI from feeling static, use **Glassmorphism** for floating elements (like navigation bars or hovering modals). 
- **Effect:** Apply `surface-variant` (#192540) at 60% opacity with a `20px` backdrop-blur. 
- **Gradients:** Use a subtle linear gradient from `primary` (#6bff8f) to `primary-container` (#0abc56) for Hero CTAs. This adds a "pulse" of energy that flat hex codes cannot achieve.

## 3. Typography
The typography uses a high-contrast pairing: **Space Grotesk** for structural command and **Manrope** for legible intelligence.

- **The Command Layer (Space Grotesk):** Used for all `display`, `headline`, and `label` tokens. Its geometric quirks and wide stance reinforce the "high-tech" cyber aesthetic.
    - *Display-LG (3.5rem):* Use this for impact. Allow it to bleed into margins or overlap container edges.
- **The Intelligence Layer (Manrope):** Used for `body` and `title` tokens. It provides a clean, neutral balance to the aggressive nature of the headlines.
- **Hierarchy Logic:** Use `label-md` in all-caps with `0.1rem` letter-spacing for metadata and technical callouts to mimic terminal readouts.

## 4. Elevation & Depth
In this design system, depth is achieved through **Tonal Layering** rather than drop shadows.

- **The Layering Principle:** Place a `surface-container-lowest` (#000000) element on a `surface-container-low` (#091328) section to create a "recessed" effect.
- **Ambient Shadows:** Shadows are rarely used. If a "floating" effect is mandatory, use a very large blur (`40px+`) with `on_surface` (#dee5ff) at 4% opacity. This creates a faint "glow" rather than a dark shadow.
- **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline-variant` (#40485d) at 20% opacity. 100% opaque borders are strictly forbidden as they clutter the "low-poly" clean lines.
- **Glassmorphism:** Use semi-transparent surface colors to allow the "Emerald" glow of background accents to bleed through, making the interface feel integrated.

## 5. Components

### Buttons
- **Primary:** `primary` (#6bff8f) background, `on_primary` (#005f28) text. Hard `0px` corners. On hover, shift to `primary_dim` (#5bf083).
- **Secondary (Ghosted):** `outline` (#6d758c) ghost border at 20% opacity, `on_background` (#dee5ff) text. 
- **Tertiary:** No background. `primary` text. Use for low-emphasis actions.

### Inputs & Fields
- **Styling:** Use `surface_container_high` (#141f38) with a 2px bottom-only border in `primary`. 
- **States:** On focus, the bottom border "glows" (add a small 4px outer glow in `primary`). Error states use `error` (#ff7351) text and borders.

### Cards & Lists
- **No Dividers:** Forbid the use of horizontal lines. Use `spacing-6` (1.3rem) of vertical white space or a subtle shift to `surface_container_low` to separate items.
- **Interactions:** On hover, a card should shift from `surface_container` to `surface_container_highest`.

### Status Chips
- **Selection:** Use `secondary_container` (#006e2d) with `on_secondary_container` (#e4ffe2) text. 
- **Geometric Hint:** Use a small 45-degree clipped corner (via CSS clip-path) on one side to reinforce the "low-poly" aesthetic.

## 6. Do's and Don'ts

### Do:
- **Use Wide Spacing:** Utilize `spacing-16` (3.5rem) and `spacing-20` (4.5rem) to give high-tech elements room to breathe.
- **Embrace the Dark:** Keep 90% of the UI in the `surface` and `surface_container` range to ensure the green accents truly pop.
- **Typography as Art:** Treat large headlines as part of the layout's graphic design, not just information.

### Don't:
- **No Rounded Corners:** Never use `border-radius`. Everything must be sharp and precise.
- **No Generic Grey:** Use the slate-tinted neutrals provided (e.g., `outline-variant` #40485d). Never use `#333333` or pure greys.
- **No Divider Lines:** Do not use 1px lines to separate content; use background shifts and space.
- **No Default Shadows:** Avoid the standard "card shadow." Rely on color-stepping (Tonal Layering).