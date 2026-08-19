# 🏆 RBS Inter-House Championship — Live Buzzer Arena

A **single `index.html` file** that runs the school's inter-house competition live show —
no install, no framework, no game server required.

## ▶ How to use

1. Open `index.html` in any modern browser (Chrome / Edge / Safari / Firefox).
2. Choose a role and log in.
3. That's it.

| Role | Users | Password |
|---|---|---|
| 📺 **SCREEN** (audience display, TV/phone optimised) | unlimited | — |
| 🎛️ **CONTROLLER** (runs the whole show) | 1 max | `PASSWORD0011` |
| 🟥 **RED HOUSE** | 1 device | `RED` |
| 🟦 **BLUE HOUSE** | 1 device | `BLUE` |
| 🟩 **GREEN HOUSE** | 1 device | `GREEN` |
| 🟧 **ORANGE HOUSE** | 1 device | `ORANGE` |

> The game cannot start until a Controller is online.

## 🎮 Competitions

- **Spelling Bee** — 4 rounds: `EASY → HARD → DIFFICULT → RAPID FIRE`.
  Controller enters the word (auto-CAPITALS, hidden), arms the buzzers, houses buzz,
  the first tap locks everyone out and shows on Controller + Screen with reaction time.
  Controller types the house's answer into the box (live ✓MATCH indicator) →
  **✓ CORRECT = +1 point** / **✗ WRONG = buzzers re-open** (that house is locked out of the word).
- Slots for more competitions (quiz, art, sports…) are prepared for future updates.

## 🛰 Connectivity (no server!)

- **Mode 1 — one computer, many tabs:** tabs sync via BroadcastChannel + localStorage. 100% offline.
- **Mode 2 — many devices on the same Wi-Fi/LAN/hotspot:** every device opens the same file and types
  the same **ROOM CODE**; devices meet through a free PeerJS handshake (needs internet for a second),
  then all game data flows directly device-to-device over WebRTC.
- To share the file once: `python -m http.server 8000` in this folder → others open
  `http://YOUR-IP:8000` (find IP via `ipconfig` / `ifconfig`).

Full guide lives in the **INFO section at the bottom of the SCREEN panel**.

## ✅ Work & features

- 3 role panels with distinct themes (houses = house colour + black, controller = grey + black, screen = light TV theme).
- First-buzz lock-in, buzz order list, reaction times, wrong-answer lockout & re-buzz.
- Word reveal/hide toggle, letter-count boxes on screen, live answer MATCH checker.
- Live leaderboard with ranks, score bump animation, connected/offline house indicators.
- Duplicate-seat protection (2nd controller / 2nd same-house device is blocked), auto-reconnect.
- Buzzer + win/wrong sounds (WebAudio, no files), confetti, fullscreen & mute buttons.
- Mobile-first Controller/House panels (giant touch buzzer), TV-optimised Screen layout.
- Scores persist per room (survive refresh); activity log everywhere.
