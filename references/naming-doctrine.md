# Product & Application Naming Doctrine

Standards for creating authentic, innovative, and enduring product and library names.

---

## 1. The Philosophy of Naming

A product's name is its first architectural commitment. 

When autonomous agents or engineers invent product names without a deliberate filter, they default to synthetic clichés: tacky suffixes, capitalized compound mashups, and lazy colloquial shortcuts. These names instantly signal cheap, throwaway AI-generated software.

Pramana mandates disciplined, memorable, and innovative naming.

---

## 2. The Forbidden Registry (Cringe AI & Startup Naming)

Never use or suggest names that exhibit any of these five synthetic patterns:

### Trap 1: The Suffix Squeeze (Tacked-on Syllables)
- **Forbidden:** Attaching trendy tech suffixes to ordinary words:
  - `-X` (e.g., `KinetiX`, `TaskX`, `LuminaX`, `DevX`)
  - `-ify` / `-ly` (e.g., `Workify`, `Promptify`, `Taskly`)
  - `-ai` / `-io` tacked onto raw features (e.g., `DocuAI`, `SearchAI`, `FormIO`)
  - `-hub` / `-gen` (e.g., `CodeHub`, `ReportGen`, `ContentGen`)

### Trap 2: The Pompous Portmanteau (Capitalized Mashups)
- **Forbidden:** Jamming two capitalized dictionary nouns together without organic phonetic resonance:
  - `OmniAnima`, `SuperFlow`, `QuickSync`, `DataStream`, `HyperScale`, `SmartEngine`
- These feel like generic placeholder projects from hackathons, not production software.

### Trap 3: The Colloquial Crutch (Indonesian Suffixes)
- **Forbidden:** Tacking colloquial suffixes onto root verbs:
  - `-in` or `-an` (e.g., `KerjaIn`, `BantuIn`, `CatatIn`, `SewaIn`, `KirimIn`)
- Colloquial suffixes produce fragile, provincial branding that does not scale to global engineering credibility.

### Trap 4: Corporate Pseudo-Tech Clichés
- **Forbidden:** Empty buzzwords recycled across generic corporate software:
  - `Nexus`, `Apex`, `Synergy`, `Velocity`, `Quantum`, `Vortex`, `Pulse`, `Aura`

### Trap 5: Novelty Misspellings & Vowel Stripping
- **Forbidden:** Substituting letters or dropping vowels for artificial uniqueness:
  - Replacing `C` with `K` (`KoolApp`), replacing `S` with `Z` (`Skillz`, `Taskz`)
  - Stripping vowels to make unpronounceable consonant clusters (`Fndr`, `Tskr`, `Wrkflw`)

---

## 3. The Pramana Naming Standard

Apply these principles when generating or selecting names for products, libraries, CLIs, or internal tools:

### Rule 1: Single-Word Authority
- Prioritize a single, elegant word. Single-word names project confidence, focus, and clarity.
- Avoid multi-word slogans masquerading as names.

### Rule 2: Grounded in Linguistic Depth
Draw inspiration from classical linguistic roots that carry centuries of genuine philosophical or physical meaning:

- **Sanskrit Heritage:**
  - Words representing epistemological truth, vision, natural balance, and craft:
  - *Pramana* (valid proof / authentic standard)
  - *Aksa* (eye / direct perception / coordinate axis)
  - *Yukti* (reasoned application / purposeful ingenuity)
  - *Taru* (tree / organic botanical lineage)
  - *Sthira* (resolute / rock-solid resilience)
  - *Kriti* (crafted masterwork)
- **Classical Latin & Romance:**
  - Words with tactile or structural gravitas:
  - *Veritas* (truth), *Cura* (care/craft), *Navis* (vessel), *Lumen* (light), *Stamen* (foundation)
- **Old Norse & Germanic:**
  - Words evoking rugged physical tools and natural phenomena:
  - *Rune*, *Grip*, *Smid*, *Forge*, *Fjord*, *Skald*
- **Classical Greek:**
  - Words rooted in fundamental philosophical principles:
  - *Telos* (inherent ultimate purpose), *Canon* (standard of judgment), *Axiom* (self-evident truth)
- **Tangible English Nouns:**
  - Concrete physical objects, materials, or natural phenomena:
  - *Stripe*, *Linear*, *Figma*, *Raycast*, *Scribe*, *Warp*, *Varnish*, *Cedar*

### Rule 3: Metaphor Over Feature Enumeration
- Name the application after its **core metaphor, physical behavior, or philosophical anchor**, never its literal feature list.
- Example: An image cropping tool should be called *Shear* or *Aksa*, not *CropEasy* or *PicCutX*.
- Example: A multi-tenant rental management system should be called *Renty* or *Lodger*, not *SewaIn* or *RentFlowAI*.

### Rule 4: Phonetic Grace & Cadence
- The name must roll off the tongue effortlessly in speech.
- Test pronunciation across languages: avoid awkward consonant collisions.
- It must sound respectable when spoken aloud by an engineering director or investor.

---

## 4. The 4-Question Naming Test

Before finalizing an app or tool name, pass it through this gate:

1. **Is it a single uncompounded word?** If it is two words glued together with CamelCase, reject it.
2. **Is it free of synthetic suffixes (`-X`, `-ify`, `-ly`, `-in`)?** If it has a tacked-on modifier, strip it.
3. **Does it carry an organic linguistic root or tangible physical metaphor?** If it is empty corporate jargon, replace it.
4. **Can you say it out loud without cringing?** If it sounds like a cheap AI generation, start over.

---

## 5. Naming Generation Protocol (For `name [concept]`)

When invoked with `name [concept]`, execute this sequence:

1. **Deconstruct the Core Mechanism:** Identify the underlying physical action, architectural primitive, or primary user transformation (e.g. schema migration -> branching, splitting, anchor).
2. **Select 3 Distinct Linguistic Roots:**
   - Candidate A: Sanskrit lineage (philosophical clarity or natural balance).
   - Candidate B: Latin / Greek / Norse lineage (tactile structure or raw tool).
   - Candidate C: Tangible English noun (everyday object or physical phenomenon).
3. **Verify via the 4-Question Gate:** Eliminate any option failing a single question.
4. **Output the Recommendation:**

```markdown
### 1. [Candidate Name] (Primary Recommendation)
- **Linguistic Root / Etymology:** [e.g., Sanskrit *Pramāṇa* (valid proof / authoritative reality)]
- **Core Metaphor:** [Why it describes the mechanism, not the feature list]
- **Cadence & Phonetics:** [Pronunciation and spoken gravitas]
- **Sample Usage:** [e.g., `aksa inspect --strict`, "Powered by Aksa"]
```
