# Repository Guidelines

## Project Structure & Module Organization
- `src/`: Landing site source (Vue/HTML/CSS/TS when present).
- `public/`: Static assets copied as-is to the build.
- `dist/`: Production build output (do not commit).
- `.github/`: Workflows, issue/PR templates, and CODEOWNERS.
- `README.md`: Product overview and links.

If the project has not been scaffolded yet, use this layout when adding code.

## Build, Test, and Development Commands
The CI auto-detects Node projects and runs scripts only if available.
- `npm ci`: Install dependencies (used in CI).
- `npm run dev`: Start local dev server with hot reload.
- `npm run build`: Produce optimized static assets into `dist/`.
- `npm test`: Run unit tests; CI runs `--ci` if supported.
- `npm run lint`: Lint and format code when configured.

## Coding Style & Naming Conventions
- Indentation: 2 spaces; LF endings; final newline; trim trailing whitespace (see `.editorconfig`).
- Filenames: kebab-case (`landing-header.vue`, `site-config.ts`).
- Components/Classes: PascalCase (`HeroSection.vue`). Variables/functions: lowerCamelCase.
- Keep modules small and cohesive; colocate tests next to code when practical.

## Testing Guidelines
- Framework: Vitest or Jest (choose one and stick to it).
- Locations: `src/**/__tests__/*` or `tests/` with `*.spec.[tj]s` naming.
- Aim for meaningful coverage of logic and rendering; avoid brittle snapshot-only tests.
- Example: `npm test` or `vitest run --coverage`.

## Commit & Pull Request Guidelines
- Conventional Commits required; PR titles are validated (see `.github/workflows/pr-title-check.yml`).
  - Examples: `feat(landing): add hero CTA`, `fix(build): correct base path`.
- Branches: `feat/…`, `fix/…`, `chore/…`, `docs/…`.
- PRs: complete the template, link issues (`Closes #123`), add screenshots for UI changes, and note breaking changes.
- CODEOWNERS: default reviewers are defined in `.github/CODEOWNERS`.

## CI Notes & Security
- CI runs on Node 20, installs with `npm ci`, and executes `lint/test` only if scripts exist.
- Do not commit secrets; use GitHub Actions secrets for tokens/keys.
