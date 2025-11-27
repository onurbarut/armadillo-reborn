# Repository Guidelines

## Project Structure & Module Organization
- `arm.html`: Single-page prototype using Matter.js (CDN 0.19.0) with inline CSS/JS for physics simulation, UI overlay, controls, and new build/delete modes.
- `PRD.md`: Product requirements and feature scope; keep synced when gameplay or materials change.
- `README.md`: Quickstart, controls, platform notes, and the living To-Do/Roadmap checklist.
- No build system or external assets are checked in; treat the repository as static HTML/JS unless you introduce a toolchain.

## Build, Test, and Development Commands
- Quick run (avoids CORS): `python3 -m http.server 8000` then open `http://localhost:8000/arm.html`.
- Fast open (no server): `open arm.html` (macOS) or double-click; use a server when adding external assets.
- If adding dependencies later, prefer a minimal bundler (Vite) and document install commands in `README.md`.

## Coding Style & Naming Conventions
- HTML/CSS/JS: 4-space indentation; use `const`/`let`, small descriptive names (`getNodeAt`, `setMode`), and keep logic grouped in functions.
- Keep UI palette consistent with the retro-futuristic blue/yellow theme; if expanded, extract shared colors as CSS variables.
- Players cannot create new anchors; build only between existing level anchors. Level anchors are locked (`isLocked`) and must stay undeletable.
- When introducing new files, mirror the current flat layout or add a clear `src/` and `assets/` split.
- HUD passthrough toggle is the current solution for avoiding UI occlusion; keep it intact or replace with a draggable/auto-hide HUD if redesigning.

## Testing Guidelines
- Manual verification only: load `arm.html`, build structures (create anchors on tap/click, use delete mode or right-click to remove), run simulation, and ensure win timer/overlay works.
- After layout changes, resize the browser and confirm canvas fits; refresh for large changes (ground/platform sizes remain static).
- Add lightweight smoke tests (Playwright/Cypress) once the UI stabilizes.

## Commit & Pull Request Guidelines
- Commit messages: imperative, concise (`Add delete mode`, `Improve mobile tap building`) and grouped logically.
- PRs should include: summary of behavior changes, manual test steps (including mobile/touch when applicable), and before/after screenshots or short clips for UI tweaks.
- Link to relevant PRD sections (`PRD.md`) when implementing scoped features or materials; update the README To-Do checklist when closing/opening items.
