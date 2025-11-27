# Armadillo Run Reborn

Prototype of a modern, browser-based Armadillo Run clone using Matter.js. Runs locally on macOS/Windows/Linux via a simple HTTP server; mobile devices can connect over the same LAN for quick testing.

## Quickstart (Mac/PC)
- Serve locally to avoid CORS: `python3 -m http.server 8000` then open `http://localhost:8000/arm.html`.
- Fast open (no server): double-click `arm.html` or `open arm.html` on macOS. Use a server if audio/assets are added later.
- Resize the browser; the canvas fits the viewport (refresh after big resizes to reposition level geometry).

## Quickstart (Mobile)
- Start the local server above, find your LAN IP, then open `http://<your-ip>:8000/arm.html` on iOS/Android.
- Use the on-screen buttons for material selection and simulation; tap once to pick a node, tap again to connect/create.

## Controls
- Build: tap/click an existing anchor, then tap/click a second anchor to create a link (no new anchors are created).
- Delete: right-click (mouse) or switch to `Delete Mode` on mobile, then tap a node (links attached are removed; locked anchors stay).
- Materials: 1/2/3 or UI buttons (Rope/Bar/Elastic).
- Run/Stop: Space or `RUN` button. Reset: `RESET` button.
- HUD passthrough: click `HUD: normal` to toggle into passthrough mode when you need to build under the HUD area.

## Dev Notes
- Single HTML entry point (`arm.html`) with inline CSS/JS and CDN Matter.js (0.19.0). Vendor locally when packaging.
- No build step yet; keep scripts modular in-line until we introduce a bundler.
- Target order: macOS/web first, desktop parity (Win/Linux), then mobile polish (touch UI/PWA).

## To-Do / Roadmap
- [ ] Vendor Matter.js locally and add basic asset pipeline (optional Vite/Electron shell).
- [ ] Expand materials to match PRD (cloth, sheet, rubber, rockets) with costs/behaviors.
- [ ] Add multi-level loader + persistence (budget per level, unlocks).
- [ ] Improve mobile UX (bigger buttons, PWA install, gesture tuning).
- [ ] Add automated smoke tests (Playwright/Cypress) for build-run-win loop.
- [ ] Tune material physics (stretch, load limits, snapping) to better mirror PRD properties.
