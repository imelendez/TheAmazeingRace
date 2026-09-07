# The Amazing Race

A third-person 3D maze shooter I built in college in 2016 on the
[Panda3D](https://www.panda3d.org/) engine.

Kill 4 enemies and collect 3 orbs, then reach the portal — a giant rotating eye —
before the 4:00 clock runs out. 13 enemies patrol the maze, donuts restore health,
and the portal refuses you until you've earned it.

![Title screen](docs/screenshots/title.png)

**[▶ Play the 2D browser port](https://claude.ai/code/artifact/6c30dc2d-4c6e-419d-87fe-32adcf744178)** —
no install, runs on the original's real maze.

---

## It still runs

Ten years on, it needed less repair than expected: a current Panda3D, and a
**four-line** Python 2 → 3 fix (bare `print` statements — nothing else). No
deprecated engine APIs, no missing assets, and the `.ogg` sound effects and `.mp3`
theme still play.

```bash
python3 -m venv .venv
.venv/bin/python -m pip install panda3d
.venv/bin/python FINALtheamazeingrace.py
```

Press **Start**. `WASD` / arrow keys move, `Enter` shoots, `Space` jumps, `Esc` quits.

Verified on Python 3.9 + Panda3D 1.10.16, macOS (Apple Silicon).
[PHASE1_NOTES.md](PHASE1_NOTES.md) has the full breakdown of what broke and how
the game's systems actually work.

## The browser port

The 2D rebuild lives in its own repo. Its maze isn't a redrawing — it was extracted
straight out of `models/solidfloormazefinal.egg` by ray-casting the mesh in Panda3D,
so the floorplan you play is this game's floorplan, down to the cell.

## Layout

```
FINALtheamazeingrace.py   main game — setup, input, collisions, win/lose logic
utils.py                  models, lighting, camera, enemy and pickup classes
models/                   3D assets, textures, audio
trash/                    earlier drafts, kept as-is from 2016
```
