# Design System Strategy: The Modern Conservatory

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Botanical Archivist."** 

This is not a standard restaurant website; it is a digital curation of flavor, heritage, and nature. By blending high-contrast editorial typography with a "living" color palette, we move away from the rigid, boxy templates of the food industry. The experience should feel like flipping through a premium, heavy-stock culinary journal. We achieve this through **intentional asymmetry**, where large-scale photography of Table 9’s garden and cuisine breaks the grid, and **tonal layering**, which replaces artificial borders with organic depth.

The layout prioritizes "The Pause"—generous whitespace (using the `spacing-16` and `spacing-20` tokens) that allows the vibrant food photography to breathe, creating an atmosphere of calm elegance and established authority.

---

## 2. Colors & Surface Philosophy

### The Palette
- **Primary (`#004d27`)**: The deep forest green of the conservatory. Used for high-authority elements and primary CTAs.
- **Secondary (`#835500` / `#feae2c`)**: The mustard/orange warmth of the logo, used to signify vibrant energy and "The Sun" within the garden.
- **Background (`#f7faf2`)**: A bespoke light sage/off-white that reduces eye strain and feels more organic than pure white.

### The "No-Line" Rule
Standard 1px borders are strictly prohibited for sectioning. To define boundaries, designers must use **Background Color Shifts**. 
- A section using `surface` might transition into a section using `surface-container-low` to indicate a change in content.
- Use the **Surface Hierarchy**: Place `surface-container-highest` elements (like event booking cards) over a `surface` background to create natural, "borderless" containment.

### The "Glass & Gradient" Rule
To add visual "soul," primary buttons and hero background accents should utilize a subtle linear gradient: 
- `primary` (#004d27) to `primary_container` (#006837) at a 135-degree angle.
- For floating elements (e.g., a "Reserve a Table" sticky button), use **Glassmorphism**: A semi-transparent `surface` color with a 12px-20px backdrop-blur to allow the lush garden photography to bleed through the interface.

---

## 3. Typography
The typographic pairing is designed to evoke the feeling of an established legacy institution that has embraced modern minimalism.

- **Headings (Noto Serif)**: Our "Legacy" voice. Use `display-lg` for hero statements and `headline-lg` for section titles. The serif nature conveys the "established" brand personality.
- **Body & UI (Manrope)**: Our "Functional" voice. Manrope provides a clean, geometric contrast to the serif headings. 
    - Use `body-lg` for storytelling and descriptions.
    - Use `label-md` (All Caps, 0.05em tracking) for category tags like "Multi-Cuisine" or "Event Hosting."

**Editorial Polish:** Always pair a `display-md` serif heading with a `label-md` Manrope tag positioned asymmetrically above it to create a sophisticated, magazine-style header.

---

## 4. Elevation & Depth

### The Layering Principle
Depth is a physical manifestation of the garden's layers. Use the `surface-container` tiers to "stack" content:
1.  **Level 0 (Base)**: `surface` (#f7faf2)
2.  **Level 1 (Sections)**: `surface-container-low` (#f2f5ed)
3.  **Level 2 (Interaction Components)**: `surface-container-highest` (#e0e4dc)

### Ambient Shadows
Avoid the "drop shadow" look. When an element must float (like a modal for event inquiries):
- **Shadow**: Use `on-surface` at 6% opacity.
- **Blur**: Minimum 40px blur with a 10px Y-offset to mimic soft, ambient conservatory lighting.

### The "Ghost Border" Fallback
If a visual separator is required for accessibility (e.g., input fields), use a **Ghost Border**:
- Stroke: `outline-variant` (#bec9be) at **20% opacity**. This keeps the interface feeling "soft" and botanical rather than "hard" and industrial.

---

## 5. Components

### Buttons
- **Primary**: Gradient of `primary` to `primary_container`. Text: `on-primary` (Manrope, Bold). Roundedness: `md` (0.375rem).
- **Secondary**: Ghost style. `outline-variant` (20% opacity) with `primary` text.
- **Tertiary/Action**: Manrope `label-md` with a subtle underline in `secondary` (#feae2c).

### Cards (Food & Events)
- **Styling**: No borders. Use `surface-container-low`.
- **Imagery**: Images within cards should use `lg` (0.5rem) rounding to soften the botanical aesthetic.
- **Spacing**: Internal padding must strictly follow `spacing-6` (2rem) to maintain the premium editorial feel.

### Input Fields
- **Styling**: Use a `surface-container-lowest` fill. 
- **Indicator**: On focus, the bottom border should animate to `primary` (#004d27) at 2px thickness. No full-box focus ring.

### Menu Lists
- **Rule**: Forbid divider lines. Use `spacing-4` between menu items. 
- **Interactions**: On hover, the background of a list item should shift to `surface-container-low` with a soft transition (200ms ease-in-out).

---

## 6. Do’s and Don’ts

### Do:
- **Use "The Overlap"**: Allow high-quality food photography to overlap two different surface containers to break the "web grid" feel.
- **Embrace Asymmetry**: Align a headline to the left but place the body text in a 6-column span on the right to create visual tension.
- **Prioritize the "Hero Image"**: Large-scale event hosting should be showcased with full-width `surface` bleed photography.

### Don’t:
- **Don’t use 100% Black**: Always use `on-surface` (#191d18) for text to maintain a soft, organic look.
- **Don’t use 1px Solid Lines**: Never use lines to separate sections; use the `surface-container` color shifts.
- **Don’t Over-Round**: Stay within the `md` (0.375rem) to `lg` (0.5rem) range for containers. Fully rounded "pill" shapes should be reserved strictly for small Chips/Tags.
- **Don't Crowd the Content**: If a section feels "full," double the spacing using the `spacing-12` or `spacing-16` tokens.