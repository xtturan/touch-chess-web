# Touch Chess: Non-Visual & Accessible Chess Engine

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Web Audio API](https://img.shields.io/badge/Audio-Web%20Audio%20API-yellow.svg)](#audio-feedback-system)
[![Engine](https://img.shields.io/badge/Engine-Stockfish-red.svg)](#features)
[![UI](https://img.shields.io/badge/Stack-React%20%2B%20Vite%20%2B%20Tailwind-blue.svg)](#architecture)

**Touch Chess** is a web-based, screenless/low-vision accessible chess client designed from the ground up for visually impaired players. By eliminating dependence on visual chessboards, it translates gameplay into an intuitive single-touch audio rhythm navigation protocol backed by the Stockfish engine.

---

## 🎧 Audio & Haptic Feedback Protocol

Rather than requiring precise screen-coordinate taps, navigation relies on cadence-based timing:

| Gesture | Action | Audio Feedback |
|---|---|---|
| **Single Tap** | Increment rank/file coordinate counter (1 through 8) | High-pitch tactile audio click |
| **Hold / Long Press** | Confirm coordinate / Lock selection | Resonant melodic chime |
| **Double Tap (Counter=0)** | Cancel selection / Go back one step | Dual descending tone |
| **Invalid Action** | Illegal move or out-of-bounds attempt | Low warning tone |

Opponent and engine moves are communicated back through directional melodic pulse sequences.

---

## ⚡ Architecture

```mermaid
graph LR
    Input[Single Tap / Hold Gesture] --> Controller[Rhythm Input Controller]
    Controller --> AudioEngine[Web Audio API Synthesizer]
    Controller --> GameState[Chess Rules & State Engine]
    GameState --> Stockfish[Stockfish AI Worker]
    Stockfish --> AudioEngine
```

---

## 🚀 Quickstart

Open `index.html` directly in any modern browser, or run via a local static server:

```bash
# Using Python
python3 -m http.server 8080

# Or using Bun / Node
npx serve .
```

Navigate to `http://localhost:8080`. Headphones or stereo speakers are recommended for spatial tone perception.

---

## 📄 License
Released under the [MIT License](LICENSE).
