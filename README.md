# NEON TETRIS

A professional neon-themed Tetris game built with **HTML5 Canvas**, **CSS3** and
modern **ES6 modules** — engineered for 60 FPS, fully responsive layouts and a
clean, layered architecture.

> **Status: Milestone 1 — Foundation & Shell.** The project scaffold is in place
> and the responsive canvas shell renders. Gameplay logic is implemented in
> later milestones (see the roadmap below).

---

## ✨ Features

Planned feature set (unlocked incrementally per milestone):

- **Classic Tetris rules** — SRS rotation with wall kicks, ghost piece, hold,
  and a 3-piece next queue.
- **Fair piece distribution** via the 7-bag randomizer.
- **Neon visual identity** — additive glow, animated line-clear effects,
  particles and responsive high-DPI canvas rendering.
- **Progression** — levels, gravity curve, combo scoring and local high scores.
- **Accessibility** — `prefers-reduced-motion` support, keyboard focus states
  and descriptive ARIA labels.
- **Multi-input** — keyboard first, touch controls on mobile.

---

## 🧱 Tech Stack

| Layer     | Technology                                   |
| --------- | -------------------------------------------- |
| Markup    | Semantic HTML5                               |
| Styling   | CSS3 custom properties (design tokens)       |
| Logic     | Vanilla JavaScript (ES6 modules, OOP)        |
| Rendering | HTML5 Canvas 2D with high-DPI support        |
| Runtime   | Modern evergreen browser (module support)    |

No build step, no framework, no dependencies — open `index.html` and play.

---

## 🚀 Getting Started

Because the project uses native ES6 modules, serve it over HTTP (module loading
fails on `file://` due to browser security).

**Option A — VS Code Live Server**

Install the *Live Server* extension, right-click `index.html`, and choose
*Open with Live Server*.

**Option B — Python one-liner**

```bash
python -m http.server 8080
# then open http://localhost:8080
```

**Option C — Node.js one-liner**

```bash
npx serve .
```

---

## 📁 Folder Structure

```
tetris game/
├── index.html                  # App shell — canvas, header, footer HUD
├── css/
│   └── style.css               # Design tokens, responsive layout, neon shell
├── js/
│   ├── main.js                 # Entry point — boots the canvas shell
│   ├── config.js               # Central config (grid, canvas, palette)
│   ├── core/                   # Gameplay logic (milestones 2+)
│   │   └── README.md           # Module registry & responsibilities
│   ├── render/                 # Rendering & visual effects (milestone 3)
│   │   └── README.md
│   └── ui/                     # HUD & overlay screens (milestones 4–5)
│       └── README.md
├── assets/
│   ├── audio/                  # Sound effects & music (milestone 5)
│   ├── fonts/                  # Self-hosted fonts (optional offline builds)
│   └── images/                 # Static images / favicons / sprites
├── docs/
│   └── architecture.md         # Full architecture & design decisions
└── README.md
```

---

## 🗺️ Milestone Roadmap

| # | Milestone                | Scope                                                            |
| - | ------------------------ | ---------------------------------------------------------------- |
| 1 | **Foundation & Shell** ✅ | Scaffold, responsive canvas shell, neon backdrop, FPS badge      |
| 2 | Core Tetris Logic        | Board, tetrominoes, SRS, collision, line clears, 7-bag           |
| 3 | Rendering & Neon FX      | Piece renderer, glow, ghost piece, line-clear effects            |
| 4 | Controls & Scoring       | Input, gravity curve, scoring, HUD, next/hold previews           |
| 5 | Game States & Polish     | Menu/pause/game-over, high scores, audio, touch controls, polish |

Each milestone ships fully functional and independently testable.

---

## 📐 Architecture Highlights

- **Fixed-timestep game loop** (`requestAnimationFrame`) for deterministic,
  frame-rate-independent simulation at 60 FPS.
- **Separated concerns** — core logic, rendering and UI never import one
  another; the `Game` orchestrator composes them.
- **Single source of truth** for tuning (`config.js`) — no magic numbers.
- **High-DPI-aware canvas** with a capped device-pixel-ratio for crisp lines
  without wasting fill-rate.

See [`docs/architecture.md`](docs/architecture.md) for the full explanation.

---

## 📄 License

Private/internal project. All rights reserved.

