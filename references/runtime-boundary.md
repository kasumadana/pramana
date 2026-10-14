# Runtime Boundaries & Systems Hygiene

Rules for environment boundaries, cloud container ingress, type discipline, and repository integrity.

---

## 1. Environment & Architecture Boundaries

### Client vs. Server Execution Boundary
- Web browsers executing client-side scripts (`index.html`, bundled scripts) have **no access to Node.js runtime globals**.
- **Forbidden:** Calling `process.env.API_KEY` directly from client-side vanilla JavaScript or HTML script tags.
- **Rule:** Server credentials and secret keys must remain on the backend. Client interfaces request data through authenticated API endpoints (`/api/...`) that sanitize responses before sending.

### Runtime Syntax Cleanliness
- **Forbidden:** Leaving TypeScript type annotations (`value: number`, `data as string`, `interface User`) inside vanilla JavaScript files (`.js`) executed directly with `node file.js`.
- This causes immediate startup crashes: `SyntaxError: Unexpected token ':'`.
- **Rule:** If the project runtime is vanilla Node.js, write valid ECMAScript without stray TypeScript annotations. If TypeScript is used, ensure the build/transpile step (`tsc`, `esbuild`, `tsx`) is properly configured before execution.

---

## 2. Cloud Ingress & Container Infrastructure

### Wildcard Host Binding (`0.0.0.0`)
- **Forbidden:** Binding production HTTP listeners strictly to `localhost` or `127.0.0.1` (e.g., `app.listen(PORT, 'localhost')`).
- Inside containerized cloud environments (Google Cloud Run, AWS ECS, Docker, Kubernetes), binding to `localhost` prevents external ingress proxy health checks from reaching the application, causing continuous 503 deployment timeouts.
- **Rule:** Always bind network listeners to the wildcard IP `0.0.0.0`:
  ```javascript
  const PORT = process.env.PORT || 8080;
  app.listen(PORT, "0.0.0.0", () => {
    console.log(`Server listening on port ${PORT}`);
  });
  ```

### Buildpack Script Requirements
- Cloud buildpacks (Google Cloud Build, Nixpacks, Vercel) mandate a `"build"` script in `package.json`.
- Never remove or omit the `"build"` target. Even for zero-build or static projects, provide a valid `"build"` script (e.g., `"build": "echo 'No build step required'"` or a bundler command) so automated CI/CD pipelines do not abort.

---

## 3. Type Hygiene & Error Resilience

### No Silent Error Swallowing
- **Forbidden:** Empty catch blocks that hide failures:
  ```javascript
  // ❌ SLOP: Application state corrupts silently
  try {
    await processPayment();
  } catch (e) {
    console.log(e);
  }
  ```
- **Rule:** Catch blocks must log structured error details and provide an observable user fallback:
  ```javascript
  // ✅ PRAMANA: Telemetry recorded, recovery state rendered
  try {
    await processPayment();
  } catch (error) {
    logger.error("Payment processing failed", { error });
    renderErrorBanner("Unable to process payment. Please verify your card details.");
  }
  ```

### Banning Lazy Type Escapes
- In TypeScript codebases, do not bypass compiler checks using `as any`, `@ts-ignore`, or untyped dictionaries `Record<string, any>`.
- Model domain data types explicitly. Use unknown types with runtime narrowing (`zod` or type guards) when ingesting external payloads.

---

## 4. Administrative Surface Separation

### Zero Administrative Leakage in Public Surfaces
- **Forbidden:** Exposing database maintenance buttons ("Sync DB"), secret API key input modals, or debugging tools directly on public-facing user screens.
- Production configurations and secret credentials belong in environment variables (`.env`). Administrative tools belong on authenticated, role-gated admin routes.

---

## 5. Repository, Documentation & Git Hygiene

### Functional README Standards
- Strip self-indulgent introductions (*"Hi 👋, I'm..."*), wall-to-wall decorative badge rows, and inflated titles (*"Rockstar Developer / 10x Architect"*).
- The README must deliver immediate engineering utility:
  1. Project name and single-sentence functional summary.
  2. Concrete system prerequisites (Node version, database requirements).
  3. One-line installation and startup commands.
  4. Explicit table of required environment variables.

### Conventional Commits
- Use crisp Conventional Commits with a subject length $\le 50$ characters:
  - `feat(auth): add session revocation endpoint`
  - `fix(carousel): add touch momentum physics to slider`
- Eliminate 4-paragraph novel commits for trivial changes, and eliminate lazy one-word commits (`fix`, `update`).

### Machine Metadata Leakage
- Never expose internal LLM instructions, prompt configuration files, or machine files (`llms.txt`) as public links in primary human navigation menus.
