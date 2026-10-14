# The Pramana Quality Gate & Delivery Verification

A checkable, exhaustive quality gate to be executed before declaring any interface, feature, or code task finished.

---

## 1. The Bounded Verification Protocol

Do not engage in endless subjective re-polishing. Execute verification in a disciplined, bounded sequence:

1. **Build & Execute:** Run the local dev server or build command. Inspect the console for zero errors.
2. **Batched Viewport Inspection:** Inspect both primary viewports simultaneously:
   - Mobile: 375px width (iPhone standard).
   - Desktop: 1440px width.
3. **Interactive Control Walkthrough:** Click every link, button, dropdown, and form control to verify that its real handler or destination executes.
4. **Single Remediation Pass:** Fix all detected defects in one batched edit session.
5. **Confirm & Deliver:** Re-verify the remediations once and deliver.

---

## 2. Checkable Delivery Gate Checklist

Before reporting completion to the user, verify that each statement below is true:

### A. Visual & Spatial Craft (UI)
- [ ] **Contrast Compliance:** Every line of rendered text achieves $\ge 4.5:1$ contrast against its direct background (WCAG AA).
- [ ] **Zero Pastel Trap:** Functional labels, body copy, and button text use solid, legible values rather than low-contrast pastel tones.
- [ ] **Disciplined Radii:** Card containers and panels use tight radii (2px–8px). Full pill radii (`rounded-full`) are applied exclusively to compact buttons, tags, or badges.
- [ ] **Unified Elevation:** Surfaces use either flat 1px hairline borders OR soft shadows. No ghost-card border + heavy blur stacking.
- [ ] **Prose Measure:** Long-form text columns are constrained to 65–75ch with line-height $\ge 1.45$.
- [ ] **Media Aspect Preservation:** Photographs and screenshots use `object-contain` with harmonized background containers, with zero heads or interface text arbitrarily cropped.
- [ ] **Touch Physics:** Touch-scrollable elements implement natural momentum (`fling physics`) with exponential deceleration.
- [ ] **Mobile Clearance:** Zero horizontal overflow across 375px–1440px viewports. Tap targets measure $\ge 44\text{px} \times 44\text{px}$.

### B. Prose & Content Hygiene (Copy)
- [ ] **Vocabulary Sweep:** Zero occurrences of synthetic AI filler words (*delve, elevate, empower, streamline, revolutionize, tapestry, seamless, robust, cutting-edge*).
- [ ] **Punctuation Cleanliness:** Zero em-dashes (`—`). Sentences structured with periods, commas, or parentheses.
- [ ] **Rhetorical Sweep:** Zero binary contrast gimmicks (*"Not just X, but Y"*) and zero universal openers (*"Whether you are an X or a Y"*).
- [ ] **Authentic Evidence:** Zero fabricated statistics (`99.9% uptime`), fake testimonials, or hallucinated client logos. Missing items rendered as explicit empty states or `[REAL DATA]`.

### C. Product Naming Compliance
- [ ] **Single-Word Identity:** App or tool name is a single, uncompounded word.
- [ ] **Zero Suffix Clichés:** Name contains no tacked-on suffixes (`-X`, `-ly`, `-ify`, `-io`, `-ai`, `-hub`).
- [ ] **Zero Colloquial Crutches:** Name contains no informal Indonesian suffixes (`-in`, `-an`).
- [ ] **Organic Linguistic Root:** Name carries genuine depth (Sanskrit, Latin, Old Norse, Greek, or tangible English noun) representing the core mechanism or metaphor.

### D. Systems & Runtime Cleanliness (Code)
- [ ] **Boundary Separation:** Client-side JavaScript files contain zero calls to server-side `process.env`.
- [ ] **Syntax Purity:** Vanilla Node.js `.js` files are free of TypeScript annotations.
- [ ] **Cloud Container Ingress:** Network listeners explicitly bind to `0.0.0.0` with dynamic port fallback (`process.env.PORT || 8080`).
- [ ] **Build Target Present:** `package.json` contains a valid `"build"` script.
- [ ] **Error Hygiene:** Zero empty catch blocks. Failures record structured telemetry and render fallback UI.
- [ ] **Functional Interactive Elements:** Every button and navigation link executes real behavior. No dead `#` anchors or non-functional mock buttons.
