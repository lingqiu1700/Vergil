**Project Overview**

- **Type:** Small Astro site (template `minimal`). Key files: `package.json`, `astro.config.mjs`, `src/pages/index.astro`, `src/pages/css/index.css`.
- **Build system:** `npm` + `astro` (see `package.json` scripts). Project uses ESM (`"type": "module"`).

**Quick Commands**

- **Dev:** `npm run dev` — starts Astro dev server (default port 4321).
- **Build:** `npm run build` — outputs production site to `dist/`.
- **Preview:** `npm run preview` — preview built site locally.
- **Astro CLI:** `npm run astro -- <cmd>` to run `astro` commands.

**Architecture & Conventions**

- **Routing:** Files in `src/pages/` become routes. Example: `src/pages/index.astro` -> `/`.
- **Assets:** Put static assets in `public/`. The site currently references an external background image from CSS; prefer `public/` for local assets.
- **Styling import:** Styles are imported directly in `.astro` frontmatter, e.g. `import '../pages/css/index.css'` at top of `src/pages/index.astro` — follow this pattern for page-scoped styles.
- **TypeScript:** `tsconfig.json` extends `astro/tsconfigs/strict`; keep that unless intentionally loosening checks.
- **Config:** `astro.config.mjs` is present but empty — most pages rely on Astro defaults. Add adapters or integrations here when needed.

**Patterns to follow (examples from this repo)**

- Page structure: keep page markup inside `src/pages/*.astro`; frontmatter imports for CSS and components.
- CSS organization: small site currently uses `src/pages/css/index.css`; add additional CSS files in the same folder and import per-page rather than global-injecting unless you intentionally want site-wide styles.
- Minimal dependency policy: `package.json` only includes `astro` — prefer adding only necessary packages and record intent in the repo README.

**What to avoid/assumptions**

- There are no test runners or CI config present — do not assume tests exist.
- No adapter configured in `astro.config.mjs` — deployment specifics are out-of-scope for the codebase until an adapter is added.

**When editing code, be explicit**

- If changing runtime behavior or routes, update `src/pages/*` and mention expected local command to verify: `npm run dev`.
- If adding new packages, update `package.json` and include exact `npm install` instructions in your PR description.

**Examples of specific tasks**

- Add a new page: create `src/pages/hello.astro` and verify via `npm run dev` at `http://localhost:4321/hello`.
- Add a global stylesheet: create `src/styles/global.css`, import it from a layout component or include in a root-level top-of-pages import.

**Files to inspect for context**

- `package.json` — scripts and declared dependency `astro@^5.16.0`.
- `astro.config.mjs` — project-level config (currently empty).
- `tsconfig.json` — TypeScript strict settings.
- `src/pages/index.astro` — landing page and example of CSS import.
- `src/pages/css/index.css` — sample styling, uses external background image.

If anything above is unclear or you want the instructions to emphasize different patterns (e.g., component conventions, CI, or deploy targets), tell me which areas to expand or examples to include.
