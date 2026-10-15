# Copywriting & Content Hygiene

Rules for authentic prose, elimination of synthetic rhetoric, and domain data normalization.

---

## 1. The Banned AI Vocabulary

Language models suffer from a statistical bias toward bloated, hyperbolic adjectives and Latinate filler verbs. Strip these terms from all user-facing prose, landing page copy, documentation, and interface micro-text:

### Banned Action Verbs
- *delve* (The definitive AI marker)
- *elevate*
- *empower*
- *streamline*
- *revolutionize*
- *unleash*
- *curate*
- *orchestrate*
- *foster*
- *harness*

### Banned Conceptual Metaphors
- *tapestry* (e.g., "a rich tapestry of features")
- *testament* (e.g., "a testament to innovation")
- *landscape* (e.g., "in today's digital landscape")
- *journey* (e.g., "start your coding journey")
- *symphony*
- *beacon*
- *paradigm*
- *synergy*

### Banned Marketing Adjectives
- *seamless*
- *robust*
- *cutting-edge*
- *next-level*
- *game-changing*
- *tailored*
- *pivotal*
- *vibrant*
- *meticulously*
- *effortless*

**The Rule:** Replace hollow buzzwords with concrete verbs that describe the exact physical or algorithmic action:
- *Slop:* *"Empowering developers to orchestrate seamless database workflows."*
- *Pramana:* *"Migrate and branch PostgreSQL schemas without downtime."*

---

## 2. Syntactic Formulas & Rhetorical Traps

### Em-Dash (`—`) Eradication
- **Forbidden:** Using the em-dash (`—`) to inject artificial theatrical pauses into sentences.
- **Replacement:** Use periods to create crisp, confident short sentences. Use commas, colons, or parentheses where appropriate.

### Binary Contrasts ("Not X, but Y")
- **Forbidden:** Dramatic formulas that establish a fake contradiction:
  - *"It's not just a note-taking app, it's your external brain."*
  - *"Not another analytics tool, but a growth companion."*
- **Replacement:** State the actual capability directly without the theatrical buildup:
  - *"Capture thoughts with instant local search."*

### The Universal Net ("Whether you're an X or a Y")
- **Forbidden:** Sentences that attempt to address every possible human being:
  - *"Whether you're a seasoned CTO, an aspiring founder, or a curious hobbyist..."*
- **Replacement:** Speak directly to the primary persona who needs the product today.

### Significance Inflation
- **Forbidden:** Treating everyday CRUD features as civilizational milestones:
  - *"Unlocking a new era of personal organization."*
  - *"Revolutionizing the way humans interact with tabular spreadsheets."*
- **Replacement:** Describe the functional reality with measured confidence:
  - *"Filter rows and export clean CSVs in two clicks."*

---

## 3. Voice, Agency & Directness

### Active Voice With Real Human Actors
- Ensure sentences feature a human subject performing a real action.
- Avoid passive voice where responsibility disappears (*"Errors were encountered"* -> *"The server rejected the payload"*).
- Avoid inanimate agency where inanimate code performs human cognitive tasks (*"The dashboard realizes you are tired"* -> *"The system automatically pauses notifications after midnight"*).

### Chatbot Leakage & Conversational Debris
- Eliminate conversational pleasantries from user interfaces:
  - *"Here is your summary:"*
  - *"Let's dive into..."*
  - *"Hope this helps!"*
- Interfaces are tools, not chatbots. Present the data, labels, and actions without conversational padding.

---

## 4. Domain Data Normalization

Never blindly mirror raw, unformatted technical dumps if the target industry maintains an established human convention:

### Example: Photography & Optics
- Smartphone camera APIs often report the raw physical sensor focal length (e.g., `7mm` or `5.4mm`).
- In photography portfolio contexts, presenting `7mm` is technically blind. Photographers understand perspective through 35mm full-frame equivalents (e.g., `24mm` or `28mm`).
- **Rule:** Convert and normalize technical metrics to the standard notation understood by domain experts.

### Example: Financial & Quantities
- Raw database dumps (`12500000`) must be formatted according to locale conventions (`Rp 12.500.000` or `$12,500`).
- Round unmanageable floating-point metrics (`98.2349182%` -> `98.2%`) unless cryptographic or scientific precision is strictly required.

---

## 5. Copy Cleansing Protocol (For `cleanse [target]`)

When invoked with `cleanse [target]` on copy or content:

1. **Scan Banned Vocabulary:** Identify and replace all synthetic filler verbs, metaphors, and hollow adjectives.
2. **Neutralize Syntactic Traps:** Eliminate em-dashes (`—`), binary contrasts (*"Not X, but Y"*), and universal nets (*"Whether you are..."*).
3. **Restore Agency:** Convert passive constructions to active human or system actions. Strip conversational chatbot fluff.
4. **Normalize Domain Values:** Format currency, numbers, and technical specifications into authentic domain notations.
5. **Output Cleanse Diff:**

```markdown
### Copy Cleanse: [Target Section / File]

| Element | Slop (Incumbent) | Pramana (Cleansed) | Rationale |
|---|---|---|---|
| Headline | *"Empowering teams to orchestrate seamless database journeys."* | *"Branch and migrate PostgreSQL schemas without downtime."* | Replaced hollow verbs with concrete algorithmic action. |
| Subhead | *"Whether you're a CTO or a curious hobbyist—we elevate your workflow."* | *"Zero-lock migrations for production web services."* | Removed universal opener, em-dash, and buzzwords. |
```
