# DEPENDENCIES — plato-browser

## Signal Chain Layer

**L0–L1 (Browser-Native Parallel) — Zero-Install Demo**

HTML demo that runs entirely in the browser using Chrome's built-in AI (Gemini Nano). Mirrors the plato-nervous signal chain concepts without requiring Rust or native builds.

## Ecosystem Dependencies

| Repo | Relationship | Description |
|------|-------------|-------------|
| [plato-nervous](https://github.com/SuperInstance/plato-nervous) | **Mirrors** | Browser-native reimplementation of plato-nervous signal chain concepts |
| [concrete-token-demo](https://github.com/SuperInstance/concrete-token-demo) | **Sister demo** | For users who want the CLI/Rust version with real ollama calls |
| [plato-vision-jepa](https://github.com/SuperInstance/plato-vision-jepa) | **Related** | Vision concepts adapted for browser WebRTC/getUserMedia |
| [plato-audio-jepa](https://github.com/SuperInstance/plato-audio-jepa) | **Related** | Audio concepts adapted for Web Audio API |

## Data Flow

```
IN:
  - Browser sensors (WebRTC camera, microphone via getUserMedia)
  - Chrome built-in AI (Gemini Nano) for local inference

OUT:
  - Browser-native signal chain visualization
  - Client-side token demonstration
  - Zero-install first taste of PLATO Nervous System
```
