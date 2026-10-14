# UI & Visual Craftsmanship

Rules for visual hierarchy, layout, color, typography, and motion.

---

## 1. Color, Atmosphere & Contrast

### Committed Surfaces
- Anchor the design on a committed surface: clean off-white canvas, solid architectural neutrals, or deep committed dark tones (`#0b0e0d`, `#111215`).
- Never default to washed-out pastel text (pale baby blue, dusty mint, muted peach) for primary labels.
- Text must maintain strict WCAG AA contrast against its immediate rendered background:
  - Normal text: minimum **4.5:1**
  - Large display text ($\ge 18\text{px}$): minimum **3:1**

### Gradients as Hierarchy Markers (Purpose-Gated)
- **Allowed:** Gradients that delineate high-priority focal points (a primary CTA highlight or subtle brand header accent) where the reason is intentional.
- **Rejected:** Full-page multi-stop linear gradients (`#6366f1` to `#a855f7` to `#ec4899`) applied indiscriminately as background wallpaper.
- **Blur Blobs:** Remove decorative floating background orbs (`filter: blur(80px)`). Rely on disciplined negative space, authentic imagery, or clean architectural lines.

### Genuine Telemetry Dots
- Reserve pulsing status indicators (`animate-pulse bg-emerald-500`) exclusively for live WebSocket channels, active background workers, or real streaming endpoints.
- Never attach pulsing dots to static navigation titles or mock indicators.

---

## 2. Geometry, Elevation & Surfaces

### Radius Hierarchy
- **Content Surfaces:** Containers, data cards, dialog modals, and input fields must use tight, disciplined corner radii (**2px to 8px**).
- **Interactive Controls:** Full pill geometry (`rounded-full` / `9999px`) is reserved strictly for compact controls: standalone action buttons, filter tags, and status badges.
- Avoid uniform pill syndrome where every card, input, and modal uses `rounded-3xl` (32px+).

### Unified Elevation: The Flat or Shadow Decision
- Choose one elevation language per surface:
  - **Option A (Crisp Architectural):** 1px solid hairline borders with zero blur shadows.
  - **Option B (Soft Elevation):** Subtle, natural multi-layer drop shadows with zero thick borders.
- Reject the **Ghost-Card anti-pattern**: stacking high-opacity borders (`rgba(255,255,255,0.15)`) with heavy, muddy box shadows ($\ge 16\text{px}$ blur).

### Card Nesting Limit
- Maximum **one level** of card nesting. 
- Never place a card inside a card inside a card. Separate sub-sections using subtle background contrast, hairline dividers, or proportional vertical rhythm.

---

## 3. Typography & Text Rhythm

### Reading Measure & Flow
- Limit prose column width to **65–75 characters** (`max-w-prose` or `max-width: 65ch`).
- Set body line-height between **1.45 and 1.6** for effortless readability.
- Apply `text-wrap: balance` to headings and `text-wrap: pretty` to body copy to prevent orphan words.

### Weight Distribution
- Standardize on proven weight roles:
  - `400 (Regular)`: Body prose, table cells, descriptions.
  - `500 (Medium)` or `600 (Semibold)`: Buttons, table headers, navigation, interactive controls.
  - `700 (Bold)`: Primary section display titles.
- Avoid ultra-hairline fonts (100–200) that disappear on standard screens, and avoid 900+ heavy weights on multi-line text.

### Monospace Restraint
- Monospace fonts (`JetBrains Mono`, `Fira Code`, `Geist Mono`) belong strictly on code blocks, cryptographic hashes, tabular metrics, and technical key-value pairs.
- Never format general explanatory body text or full feature lists in monospace.
- Eliminate synthetic cyberpunk syntax like double slashes (`//`) for menu breadcrumbs. Use typographic bullets (`·`), em-spaces, or slashes with semantic meaning.

---

## 4. Branding & Visual Media Integrity

### Brand Marks & Logos
- When a client logo or brand asset is not provided, use a **clean typographic wordmark** (the brand name set in a high-quality typeface with refined kerning).
- If an icon emblem is required, display a standalone vector SVG symbol with its own natural whitespace.
- Never box an icon inside a 40x40 rounded rectangle with a 1px border to manufacture a fake app logo.

### Media Aspect Ratios & Framing
- Honor the original aspect ratio of photographs, artwork, and product screenshots.
- Use `object-contain` coupled with a harmonious container backdrop color (e.g., `#ffffff` for light modes, `#0f1214` for dark modes).
- Avoid blind `object-cover` cropping that slices off faces, headtops, camera watermarks, or crucial interface details.

---

## 5. Touch Physics & Motion

### Momentum on Touch Interfaces
- Scrollable carousels, horizontal lists, and 3D canvas viewports on touch-enabled screens must implement velocity tracking and momentum deceleration (`fling physics`).
- Abrupt hard stops the millisecond a finger lifts off the screen fail the craftsmanship standard.

### Zero-Opacity Lock Prevention
- Elements must be rendered and readable in the initial DOM tree.
- Never lock critical content behind `opacity: 0` that requires client-side JavaScript execution to become visible. If a script fails, blocks, or loads slowly, the interface must remain readable.

---

## 6. Layout Composition & Component Density

### Content-Driven Composition
- Structure section layouts around the specific narrative requirements of the product.
- Reject the generic template cycle: *Hero -> 3 Identical Cards -> Fake Terminal -> 3 Pricing Columns -> 4-Column Footer*.
- Feature highlights must reflect real hierarchy: give the flagship capability dominant visual prominence, and present secondary capabilities in compact lists, tabular summaries, or inline interactive demos.

### Tap Targets & Mobile Discipline
- Mobile touch targets must meet the minimum **44px x 44px** area.
- Zero horizontal overflow: viewports down to 375px must remain completely contained without horizontal scrollbars.
