# Product Requirements Document (PRD): Armadillo Run Clone

## 1. Document Information
- **Product Name**: Armadillo Run Reborn (working title; a faithful clone/modern recreation of the 2006 indie physics puzzle game *Armadillo Run*)
- **Version**: 1.0
- **Date**: November 23, 2025
- **Author**: Grok (xAI Assistant)
- **Status**: Draft
- **Purpose**: This PRD outlines the requirements for developing a clone of *Armadillo Run*, prioritizing core gameplay fidelity while incorporating modern enhancements for accessibility, performance, and community engagement. The goal is to revive the game's creative engineering puzzles for new audiences without altering its essence.

## 2. Executive Summary
*Armadillo Run Reborn* is a 2D/3D physics-based puzzle game where players construct budget-constrained structures using ropes, bars, sheets, and other materials to guide a bouncy armadillo from a start point to a glowing portal. The original game's charm lies in its realistic physics simulation, iterative building/testing loop, and emergent creativity (e.g., Rube Goldberg-style contraptions). This clone will replicate 50 core levels, unlockable extras, and a level editor, while adding features like cross-platform support, cloud saving, and Steam Workshop integration. Target platforms: PC (Windows/Mac/Linux), with optional web and mobile ports.

Estimated development scope: 6-9 months for a small indie team (1-3 developers), using Unity or Godot for physics (Box2D or similar).

## 3. Business Objectives
- **Primary Goal**: Deliver a nostalgic yet refreshed experience that captures 90%+ fidelity to the original's mechanics, scoring 80+ on Steam user reviews.
- **Secondary Goals**:
  - Attract 50K+ downloads in Year 1 via itch.io/Steam, leveraging retro gaming communities.
  - Foster user-generated content (UGC) with 1K+ shared levels in the first quarter post-launch.
  - Educate players on basic physics/engineering principles through optional tutorials.
- **Success Metrics**:
  | Metric | Target | Measurement |
  |--------|--------|-------------|
  | Download/Installs | 50K | Platform analytics (Steam/itch.io) |
  | Average Playtime | 10+ hours | Session data |
  | UGC Uploads | 1K levels | In-game workshop |
  | Review Score | 80% Positive | Steam/Metacritic |
  | Retention (Day 7) | 40% | User engagement tools |

## 4. Target Audience
- **Primary**: Retro gamers and puzzle enthusiasts aged 25-45 who enjoyed *The Incredible Machine*, *World of Goo*, or *Poly Bridge* (nostalgia for 2000s indies).
- **Secondary**: STEM educators/parents (ages 30-50) using it for kid-friendly engineering lessons; casual mobile gamers seeking bite-sized challenges.
- **Persona Example**:
  - **Alex the Tinkerer**: 32-year-old software engineer, loves iterative problem-solving. Plays on PC evenings, shares solutions on Reddit.
  - **Jordan the Parent**: 38-year-old teacher, seeks low-violence games for 8-12yo kids to build creativity and physics intuition.
- **Market Size**: Indie puzzle genre (~$50M annually on Steam); retro revivals like *Undertale* ports show strong demand.

## 5. Core Features and Requirements
### 5.1 Gameplay Overview
- **Core Loop**: Select level → Build structure (connect anchors with materials) → Simulate physics → Iterate (undo/test) → Win by guiding armadillo to portal for 5 seconds → Progress with budget surplus for unlocks.
- **Win Condition**: Armadillo (a yellow, basketball-sized, physics-simulated sphere) must enter and remain in the blue portal for 5 continuous seconds. Failure restarts simulation without resetting build.
- **Budget System**: Each level has a fixed budget (e.g., $500-$2000). Materials cost based on length/type; tension/compression reduces flexible material costs. Exceeding budget locks completion—must optimize for efficiency.
- **Physics Fidelity**: Realistic 2D/3D simulation (gravity, tension, compression, collisions). Structures can sag, snap, bounce, or collapse dynamically.
- **Armadillo Behavior**: Inanimate until simulation starts; rolls/bounces on surfaces (center-placed materials only). Affected by gravity, impulses (e.g., rockets), and friction. No AI—pure physics object.

### 5.2 Building Materials
Replicate the original's 7 materials exactly, with identical properties for parity. Costs are length-proportional for flexibles (base for short section ~$10-50); rigids fixed per unit. Some levels restrict materials.

| Material | Placement Type | Weight | Tensile Strength | Compressive Strength | Key Properties | Cost Model | Primary Use |
|----------|----------------|--------|------------------|----------------------|----------------|------------|-------------|
| **Rope** | Outer Edge | Light | Good | Poor | Flexible, non-interfering (armadillo passes through) | Length-based (~$20/unit) | Supports, swings, crossings |
| **Cloth** | Center | Medium | Good | Poor | Flexible, rollable surface | Length-based (~$30/unit) | Platforms, slides, nets |
| **Metal Bar** | Inner Edge | Medium | Medium | Good | Rigid, supportive | Fixed (~$40/unit) | Beams, trusses near center |
| **Metal Sheet** | Center | Heavy | Medium | Good | Rigid, flat surface | Area-based (~$50/unit) | Stable floors, ramps |
| **Elastic** | Outer Edge | Light | Good | Poor | Flexible, stretchy (up to 2x length) | Length-based (~$25/unit) | Springs, catapults, dynamic pulls |
| **Rubber** | Center | Medium | Medium | Medium | Compressible, bouncy | Area-based (~$35/unit) | Cushions, bumpers, soft lands |
| **Rocket** | Center | Heavy | Poor | Poor | Propulsive (thrust forward; length = power) | Fixed (~$100/unit) + fuel | Boosters, launches |

- **Enhancements**: Add material previews (hover tooltips with stats); optional "ghost mode" to visualize armadillo path pre-simulation.

### 5.3 Tools and Editing Mechanics
- **Modes**: Structure (build links), Tension (adjust red/green forces), Timer (self-destruct delays for rockets/cloth).
- **Link Creation**: Click-drag between anchors/nodes (auto-snap); max length for rigids (splits into segments); min length for flexibles.
- **Advanced**: Multi-select (rubber-band), copy/paste (with flip/rotate), undo/redo stack (50 actions), forces visualization (color-coded).
- **Simulation Controls**: Play/pause, slow-mo (0.1x-2x speed), step-frame advance, tracking camera.

### 5.4 Levels and Progression
- **Core Content**: 50 main levels (progressive difficulty: simple bridges to complex multi-portal mazes). Unlock extras (10-15) by saving $10,000 total budget across mains.
- **Level Variety**: Include pre-built obstacles, wind/gravity variations, timed elements. Backgrounds cycle thematically (e.g., space, factories).
- **Scoring**: Efficiency score = budget remaining × completion time bonus. Leaderboards per level (global/personal bests).
- **New Content**: 10 tutorial levels; 5 daily challenges (randomized budgets/materials).

### 5.5 Level Editor
- **Full Parity**: Anchor placement, portal/armadillo setup, budget/material restrictions, background swaps.
- **UGC Integration**: Export/import .lvl files; Steam Workshop/itch.io upload (with thumbnails, descriptions). In-game browser for top-rated/user-curated sets.
- **Validation**: Auto-check for solvability (e.g., budget feasibility); community voting/ratings.

### 5.6 Modern Enhancements (Non-Core)
- **Accessibility**: Color-blind modes, one-handed controls, adjustable physics sliders (e.g., gravity scale).
- **Social**: Share screenshots/videos of solutions; cross-play leaderboards.
- **Monetization**: Free demo (first 10 levels); $9.99 full (one-time); optional $4.99 DLC for 20 new levels.
- **Achievements**: 20 Steam badges (e.g., "Budget Baron: Save $5000 total"; "Rocket Scientist: Use 10 rockets in one level").

## 6. User Interface and Experience
- **UI Style**: Clean, retro-futuristic (original's blue/yellow palette; pixel art accents). Minimalist HUD: Budget counter, material selector (hotkeys 1-7), mode icons.
- **Views**: Free (pan/zoom/rotate), Side (2D ortho), Tracking (follow armadillo), First-Person (armadillo POV).
- **Controls**:
  | Action | Keyboard/Mouse | Gamepad |
  |--------|----------------|---------|
  | Build Link | LMB Drag | Left Stick + A |
  | Delete | RMB | B |
  | Simulate | Space | Start |
  | Undo | Ctrl+Z | Left Bumper |
  | Zoom | Ctrl + RMB Drag | Right Trigger |
- **Onboarding**: 5-min interactive tutorial; tooltips for materials.
- **Audio/Visual**: FMOD-like sound (creaks, snaps, armadillo squeaks); dynamic music swells on success. 60FPS target; scalable graphics (low-end support).

## 7. Technical Requirements
- **Engine**: Unity 2023+ (built-in physics) or Godot 4 (open-source, lightweight).
- **Platforms**:
  | Platform | Priority | Notes |
  |----------|----------|-------|
  | Windows PC | High | Native .exe; Steam integration |
  | macOS/Linux | Medium | Via Steam/Proton/Wine |
  | Web (Browser) | Low | HTML5 export; touch controls |
  | iOS/Android | Future | Touch-optimized; haptic feedback |
- **Performance**: <100MB install; 30FPS min on integrated GPUs (e.g., Intel UHD).
- **Dependencies**: No external APIs beyond Steamworks; offline-first (cloud saves optional).
- **Security/Privacy**: UGC scanning for exploits; no user data collection without consent.
- **Localization**: English core; prepare for 5 languages (e.g., Spanish, German).

## 8. Risks and Assumptions
- **Risks**: Physics inaccuracies leading to "unsolvable" clones (mitigate: reference original binaries if available); low UGC adoption (mitigate: seeded content packs).
- **Assumptions**: Access to original assets/docs for reference (public manual); no IP issues (clone as fair-use homage; consult legal for "Reborn" title).
- **Dependencies**: Beta testing with 50+ original fans via Discord/Reddit.

## 9. Roadmap
- **Phase 1 (Months 1-2)**: Prototype core physics/materials (5 levels).
- **Phase 2 (Months 3-5)**: Full levels, editor, UI polish.
- **Phase 3 (Months 6-7)**: UGC, platforms, beta testing.
- **Phase 4 (Month 8+)**: Launch, post-launch DLC.

## 10. Appendices
- **References**: Original manual (armadillorun.com/documents/manual.html); community solutions (armadillorun.com/solutions).
- **Change Log**: [Initial draft].

This PRD serves as a living document—feedback from stakeholders will refine priorities. For prototypes or wireframes, provide additional specs!