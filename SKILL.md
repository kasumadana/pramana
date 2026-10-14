---
name: pramana
description: "Enforce craftsmanship and eliminate synthetic AI slop across UI design, copywriting, product naming, and full-stack runtime engineering. Use when building interfaces, authoring copy, designing products, or reviewing web applications."
disable-model-invocation: false
---

# Pramana (प्रमाण)

> **Pramāṇa** (Sanskrit: *the valid measure of truth, authoritative proof, reality over hallucination*).
> A deterministic quality and craftsmanship filter for autonomous coding agents.

Pramana prevents models from defaulting to the low-entropy, repetitive patterns known as **AI slop**: gratuitous pastel gradients, ghost card stacking, melodramatic buzzword copy, lazy product naming, and brittle runtime assumptions.

It operates as a **filter and quality floor**, not a style straitjacket. It rejects technique without purpose, while demanding positive craft, clear intent, and domain integrity.

---

## The Root Rule: The Purpose Gate

Every visual ornament, line of code, copy sentence, and naming decision must serve an articulated functional intent, architectural constraint, or authentic brand identity.

If an element can be removed without reducing user comprehension, data integrity, system stability, or explicit brand personality, it is **slop** and must be excised.

---

## Information Hierarchy & Progressive Disclosure

Pramana is organized into a primary core ladder supported by deep domain references:

```
pramana/
├── SKILL.md                 # Primary Core: Universal rules & triage
└── references/
    ├── ui-craft.md          # Visual hierarchy, geometry, and touch physics
    ├── copy-hygiene.md      # Prose discipline, banned tokens, and normalization
    ├── naming-doctrine.md   # Authentic, anti-cringe product naming standards
    ├── runtime-boundary.md  # Client-server boundaries, cloud ingress, type hygiene
    └── quality-gate.md      # Bounded verification and release checklist
```

Consult the disclosed references as needed:
- For interfaces, color, radius, and layouts: read [ui-craft.md](references/ui-craft.md).
- For UX writing, headlines, and content: read [copy-hygiene.md](references/copy-hygiene.md).
- For app, library, or feature naming: read [naming-doctrine.md](references/naming-doctrine.md).
- For Node.js, Cloud Run, containers, and environment vars: read [runtime-boundary.md](references/runtime-boundary.md).
- Before claiming any task is complete: run [quality-gate.md](references/quality-gate.md).

---

## 1. Hard Gates (Zero Exceptions)

Violating any rule below is an immediate fail:

1. **Truth Over Hallucination:**
   - Never fabricate metrics (`99.9% uptime`, `500k+ downloads`), client logos, testimonials, or compliance badges (`SOC 2`, `ISO 27001`).
   - If real data is absent, render an empty state or mark explicitly with `[REAL DATA]`.
2. **Functional Completeness:**
   - Interactive elements must execute real behavior. No dead buttons, no unhandled toggles, and no navbar links to missing anchors.
   - Every data view must implement three explicit states: **Loading**, **Empty**, and **Error**.
3. **Accessibility Baseline:**
   - Body text must meet WCAG AA contrast ($\ge 4.5:1$).
   - Interactive controls must support keyboard operation (`Tab`, `Shift+Tab`, `Enter`, `Escape`) with visible focus outlines.
4. **Runtime Integrity:**
   - Never mix TypeScript syntax into vanilla Node.js `.js` execution paths.
   - Never expose server-side environment variables to static browser runtimes.
   - Cloud HTTP servers must bind to `0.0.0.0` and package manifests must specify a valid `"build"` script.

---

## 2. Surface Modes

Select the surface mode before generating any UI. A single default cannot serve all products:

- **Persuade (Landing pages, campaigns, portfolios):** High visual conviction, bold typography, confident whitespace, real evidence.
- **Operate (Dashboards, tools, editors, settings):** Scannability, tabular data alignment, high information density, native keyboard affordances. Brand lives in micro-details.
- **Read (Docs, articles, changelogs):** Strict line-length bounds (65–75ch), proportional line-height (1.4–1.6), and uncluttered reading rhythm.
- **Experience (Galleries, interactive prototypes):** The interface recedes. The artifact and interaction lead the viewport.

---

## 3. The Anti-Cringe Naming Directive

Do not invent cheap, synthetic product names. When naming an app, service, CLI tool, or feature:
- **FORBIDDEN:** CamelCase mashups (`OmniAnima`, `SuperFlow`), novelty suffixes (`KinetiX`, `Workify`, `TaskAI`), and colloquial shortcuts (`KerjaIn`, `BantuIn`).
- **MANDATED:** Choose single, evocative words with genuine linguistic roots (Sanskrit, Latin, Old Norse, or classical English nouns) that reflect a core physical property or philosophy. Read [naming-doctrine.md](references/naming-doctrine.md).

---

## 4. Verification Protocol

Verify in bounded passes before reporting completion:
1. Run or build the actual code.
2. Inspect both mobile (375px) and desktop (1440px) viewports for layout collisions or overflow.
3. Test every interactive control.
4. Run the checks specified in [quality-gate.md](references/quality-gate.md).
