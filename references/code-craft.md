# Code Craft, Minimal Architecture & Comment Hygiene

Standards for clean code, DRY architecture, minimal implementation (YAGNI), zero scope creep, and comment hygiene.

---

## 1. The Minimal Code Ladder (YAGNI & DRY)

The cleanest code is code that never needed to be written. Every added line is a maintenance liability, a potential bug surface, and cognitive overhead for future engineers.

When writing or modifying code, evaluate solutions against this ladder and stop at the first rung that satisfies the requirement:

```
1. Does this need to exist at all? (Speculative need → skip it)
   ↓
2. Standard library does it? (Use built-in functions)
   ↓
3. Native platform feature covers it? (HTML5 inputs, CSS, DB constraints)
   ↓
4. Already-installed dependency solves it? (Use existing packages)
   ↓
5. Can it be expressed cleanly in 1–5 lines? (Inline minimal logic)
   ↓
6. Minimum necessary implementation (Only what is requested today)
```

### The Rules of Restraint
- **Zero Speculative Abstractions:** Do not create interfaces with only one implementation, factories for a single class, abstract base classes for one child, or configurable options for values that never change.
- **DRY Without Over-Abstraction:** Consolidate duplicate business logic and copy-pasted calculations. If two routines share identical algorithmic behavior, extract a single helper. However, avoid premature abstractions across unrelated domain boundaries.
- **Standard Library & Native Platform First:**
  - Use `<input type="date">` instead of pulling a 50KB datepicker package.
  - Use CSS Flexbox/Grid and standard transitions instead of heavy JavaScript animation libraries for simple state transitions.
  - Use native database constraints (`UNIQUE`, `CHECK`, foreign keys) instead of complex application-level validation loops.
  - Use Node.js/Python/Go standard library utilities (`crypto`, `path`, `collections`, `url`, `os`) instead of trivial micro-dependencies (`is-number`, `left-pad`).
- **Zero Unrequested Dependencies:** Never install a new package if the problem can be solved in a few lines of standard code or using packages already present in `package.json` / `requirements.txt`.
- **Deletion Over Addition:** When modifying existing code, look for opportunities to delete dead code, unused parameters, and redundant helper layers.

---

## 2. Scope Creep & Boundary Discipline

Autonomous coding agents frequently suffer from scope creep: refactoring unrelated files, reorganizing directory structures, or rewriting working code unprompted.

### The Scope Boundary Rules
1. **Touch Only What Was Asked:** Modify only the files, functions, and routes required by the user's specific request.
2. **Shortest Working Diff:** Prefer small, localized, surgical edits over wholesale file rewrites.
3. **No Unsolicited Modernization:** Do not reformat indentation, rewrite working promises into async/await, or migrate syntax in files outside the task scope unless explicitly instructed.
4. **Preserve Existing Conventions:** Match the surrounding codebase's indentation, quote styles, typing patterns, and error handling structure.

---

## 3. Code Comment Hygiene

Comments in code must serve as high-signal engineering notes. When comments are cluttered with AI-generated narration, they dilute focus and hide critical domain context.

### Banned Comment Patterns

| Pattern | Bad Example | Remediation |
|---|---|---|
| **Decorative Separators** | `// ====================`<br>`// AUTHENTICATION`<br>`// ====================` | Delete separator entirely. Use clean file structure or natural code whitespace. |
| **Restating the Obvious** | `let count = 0; // Initialize count`<br>`class User {} // User class` | Delete comment. The code is already self-describing. |
| **Workflow Narration** | `// Step 1: Validate input`<br>`// Step 2: Fetch user`<br>`// Step 3: Return response` | Delete comment. Control flow is visible in execution logic. |
| **Empty Category Labels** | `// Helper function`<br>`// Core logic`<br>`// Error handling` | Delete comment. Name the function or module with domain clarity instead. |
| **Vague Placeholders** | `// TODO: Optimize this later`<br>`// Add more validation here` | Delete unless it cites a specific technical constraint or ticket. |
| **Signature Echo** | `/** @param id The ID */`<br>`function findById(id)` | Delete redundant JSDoc tags that add zero information beyond the types. |
| **Decorative Emojis** | `// ✅ Validated`<br>`// 🚀 Fast path`<br>`// 🔒 Secure endpoint` | Strip emojis. Code comments are professional technical records. |
| **Block End Markers** | `} // end if`<br>`} // end processOrder` | Delete. Closing braces and editor indentation already mark block boundaries. |

### Preserved Comments (What Actually Belongs)
Never delete or withhold comments that explain the **why** behind non-obvious engineering decisions:
- **Business Logic & Edge Cases:** Subtle domain calculations, legal constraints, or business policies not evident from the math alone.
- **Platform Traps & Workarounds:** Workarounds for browser quirks, cloud provider rate limits, OS-specific quirks, or upstream library bugs.
- **Security & Concurrency Invariants:** Critical lock acquisition orders, cryptographic requirements, and sanitization boundaries.
- **Protocol & Hardware Constraints:** Serial baud timings, network payload bounds, or hardware calibration offsets.

Rule of thumb: **Comments explain intent and constraints (*why*), code explains the mechanism (*what*).**

---

## 4. The Ghost Filter (Zero Self-Referential Branding)

This quality system is an invisible engine. Its purpose is to ensure the user's code and documentation remain immaculate, human, and professional.

### Strict Non-Attribution Rules
1. **Never Inject Self-Branding:** Never insert the word `pramana`, `pramāṇa`, or any framework watermark into generated code, inline comments, variable names, file headers, or commit messages.
2. **Never Add Attribution Comments:**
   - ❌ `// Cleaned up via Pramana`
   - ❌ `// ✅ PRAMANA: Verified contrast`
   - ❌ `// Generated with Pramana quality gate`
   - ❌ `/* Handled under Pramana Purpose Gate */`
3. **Conversational Discipline:** Do not clutter conversational responses with self-referential jargon (e.g., *"Applying the Pramana doctrine to your code..."*). Deliver direct, authoritative engineering output without meta-commentary.

---

## 5. Clean Code Audit & Cleansing Protocol

When auditing (`audit`) or cleansing (`cleanse`) code files:

1. **Scan for Comment Slop:** Locate and remove banner separators, syntax echoes, workflow narrations, and emojis in comments.
2. **Evaluate the Minimal Ladder:** Identify unrequested abstractions, unnecessary external packages, or over-engineered single-use wrappers. Replace with standard library or direct inline logic.
3. **Verify DRY Compliance:** Check for duplicated business logic blocks or repeated error-handling boilerplate within the module. Consolidate into concise local helpers.
4. **Enforce Ghost Filter:** Ensure zero instances of framework self-attribution exist in comments, strings, or identifiers.
5. **Verify Scope Bounds:** Verify that only requested files were touched, with zero unsolicited stylistic rewrites in untouched modules.
