# PLATO Nervous System — Browser Demo

A single-file browser demo showing a Plato room's nervous system running entirely client-side.

## What It Does

Real-time sensor monitoring dashboard where:
- A simulated ship engine room generates sensor readings (RPM, coolant, oil pressure, vibration)
- The deadband filter (Layer 0, pure JS) catches normal readings
- Google Chrome's built-in AI (Gemini Nano via the Prompt API) classifies ambiguous readings
- The signal chain runs visually — you can SEE each layer light up as readings flow through
- The A2UI projection shows the crab's interface in real-time

## Quick Start

```bash
# Just open index.html in Chrome
open index.html
# Or serve it
python3 -m http.server 8080
```

For the full AI experience, enable Chrome's built-in AI:
1. Open `chrome://flags/#optimization-guide-on-device-model`
2. Set to "Enabled"
3. Relaunch Chrome

Without Chrome AI, the demo uses a rule-based fallback — still fully functional.

## Features

- **Real-time simulation** — sensor readings generated every 1-2 seconds
- **Layer visualization** — each layer lights up green/yellow/red as readings flow through
- **Room state vector** — shows the room's self-model (health, thermal, stress, drift)
- **Autonomy gauge** — shows % of readings handled locally
- **Transcript** — scrolling log showing which layer resolved each reading
- **A2UI Crab View** — shows what the agent "sees" and "thinks"
- **Inject Anomaly** — trigger a real anomaly to watch the signal chain respond
- **Speed control** — 1×, 2×, 5× simulation speed
- **Mobile responsive**

## Architecture

```
Sensor Reading → L0 (Deadband) → L1 (Nano AI / Rules) → L4 (Cloud Alert)
                     76%               14%                    10%
```

Every reading flows through the chain. Most die at L0 (normal range). Ambiguous ones get classified by L1. Critical ones escalate to L4.

## Tech

- Single `index.html` — zero dependencies, zero build step
- Chrome Prompt API (`ai.languageModel`) for on-device AI
- Graceful fallback to rule-based classifier
- All CSS/JS inline, dark theme, neon accents
- Runs entirely in the browser

## License

MIT
