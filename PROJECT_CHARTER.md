# Project Charter: TheAmazeingRace — Get It Running, Then Port to Browser

## Purpose
Revive a ~10-year-old college game project ("TheAmazeingRace," built on the Panda3D engine) and turn it into something shareable — first by getting the original running again, then by building a browser-playable version.

**Why this matters:** most portfolio pieces in a job search are dashboards, pipelines, or data tools. A playable game is different — approachable, shows range, and gives people something fun to actually click into.

---

## Important Correction
This project was built on **Panda3D**, a full 3D game engine (not Pygame, and not 2D as originally assumed). That changes scope meaningfully — a true 3D port to the browser means using **Three.js** and rebuilding the 3D scene/camera/models, not a simple sprite-based translation. Given that, this charter uses a phased approach instead of committing to a full 3D port up front.

**Repo:** github.com/imelendez/TheAmazeingRace
**Key files:** `FINALtheamazeingrace.py` (main game), `models/` (3D assets), `utils.py`
**Notable cleanup items:** leftover `.svn` folder (old version control), a `trash/` folder, a Windows shortcut file — safe to ignore or clean up later

---

## Phase 1: Get It Running Locally
**Goal:** see the actual game in action before deciding how to port it — 10-year-old code with unknown real scope is hard to plan around sight-unseen.

Steps:
1. Clone the repo
2. Install Panda3D (likely an old version — may need a specific Python version to match; expect some dependency archaeology given the age)
3. Attempt to run `FINALtheamazeingrace.py`
4. Fix whatever breaks (deprecated Panda3D APIs, missing assets, Python 2 vs. 3 issues — genuinely common with code this old)
5. Once running: actually play it, understand the real mechanics, take notes/screenshots/a recording for reference

**Output:** a working local copy, and a clear understanding of what the game actually does.

---

## Phase 2: Simplified 2D Browser Version
**Goal:** ship something real and playable in a browser — prioritizing "done and shareable" over "perfectly faithful to the original."

Steps:
1. Based on what Phase 1 reveals, distill the core gameplay concept (mechanics, goal, key interactions) — not every 3D detail, just what makes it fun/recognizable
2. Build a 2D browser version using HTML5 Canvas or p5.js
3. Rebuild the core loop: input handling, win/lose conditions, the central mechanic
4. Keep visuals simple — this is about a playable, shippable version, not a visual match to the original
5. Test in-browser frequently as pieces come together

**Output:** a genuinely playable, link-shareable browser game — the actual portfolio piece.

---

## Phase 3 (Stretch Goal): Full 3D Port
**Goal:** if there's appetite later, a more faithful 3D recreation using Three.js — closer to the original's actual look and feel.

This phase is explicitly optional and not required for the project to be a success — Phase 2 alone is a complete, shippable deliverable. Only pursue this if Phase 2 goes well and there's genuine interest in going further.

---

## GitHub / Workflow
- Keep working in the existing `TheAmazeingRace` repo, or create a new repo for the browser port (recommended — cleaner history, doesn't tangle with the old Panda3D code)
- Commit at each real milestone (game runs locally, core loop works, first playable browser version, polish pass) — not one giant commit at the end
- README should tell the story: what this was, what it is now, how to play it, link to the live version

## Setting This Up in Claude Code
1. Clone the repo locally
2. Save this charter as `PROJECT_CHARTER.md` in the project folder
3. Open Claude Code there and start with: *"Let's start Phase 1 — help me get this old Panda3D project running locally so I can see what it actually does."*
4. Work through phases in order — don't skip to porting before Phase 1 confirms what you're actually working with

---

## Notes
- Expect real friction in Phase 1 — 10-year-old game engine code with dependency issues is normal, not a sign anything's wrong
- This is a lower-pressure, more playful project than the job-search-focused builds — pace it however fits around everything else going on
