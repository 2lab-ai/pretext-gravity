# Gravity Well

Text bends around your cursor like spacetime curves around mass.

**[Live Demo](https://2lab-ai.github.io/pretext-gravity/)**

## What

An interactive canvas experiment where every character is a particle in a gravity field. Your cursor is a mass — it repels or attracts text characters with physically-simulated forces. Pin multiple gravity wells, toggle wave mode, and watch constellations form between flying characters.

Built with [pretext](https://github.com/chenglou/pretext) for precise multilingual text measurement and layout.

## Controls

| Input | Action |
|-------|--------|
| Mouse move | Move gravity well |
| Click / Space | Toggle repel/attract |
| Right-click | Pin a fixed gravity well (max 5) |
| Scroll / Arrow keys | Change gravity radius |
| W | Toggle wave mode (idle animation) |
| R | Reset all characters + remove pinned wells |
| 1 / 2 / 3 | Gravity presets (small / medium / large) |
| Double tap (mobile) | Toggle mode |
| Long press (mobile) | Pin gravity well |
| Pinch (mobile) | Zoom gravity field |

## Features

- Per-character physics simulation with spring-return
- Velocity-based rotation and scale transforms
- Ghost trails on fast-moving characters
- Shockwave ripple on mode toggle with impulse burst
- **Multi-gravity**: pin up to 5 independent wells with right-click
- **Wave mode**: sine/cosine displacement for idle animation
- **Constellation lines**: fast-moving nearby chars connect with glowing lines
- **Speed reactivity**: faster mouse = larger gravity influence
- Background starfield with colored twinkling
- Concentric gravity field rings
- Smooth mouse interpolation (lerp)
- Orbital particle rings (inner + outer)
- FPS + char count HUD
- Full touch + keyboard + pinch support
- Korean + English mixed text with proper width handling via pretext

## Tech

Single `index.html` — no build step, no dependencies beyond the CDN import:

```js
import { prepareWithSegments, layoutNextLine } from 'https://esm.sh/@chenglou/pretext@0.0.3'
```

pretext handles the hard part: breaking multilingual text (Korean, English, emoji, CJK) into properly measured lines that fit any width. Each character then becomes an independent physics particle.

**Physics**: quadratic gravity falloff, spring return to base position, velocity-based friction, dynamic radius boost from mouse speed.

**Perf**: trail rendering disabled above 2000 chars, constellation lines pre-filtered to active chars with 300-char cap to prevent O(n^2) blowup.

## Credits

- [pretext](https://github.com/chenglou/pretext) by chenglou — text measurement & layout
- Built by [2lab.ai](https://github.com/2lab-ai)
