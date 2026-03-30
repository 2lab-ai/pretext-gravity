# Gravity Well

Text bends around your cursor like spacetime curves around mass.

**[Live Demo](https://2lab-ai.github.io/pretext-gravity/)**

## What

An interactive canvas experiment where every character is a particle in a gravity field. Your cursor is a mass — it repels or attracts text characters with physically-simulated forces.

Built with [pretext](https://github.com/chenglou/pretext) for precise multilingual text measurement and layout.

## Controls

| Input | Action |
|-------|--------|
| Mouse move | Move gravity well |
| Click / Space | Toggle repel/attract |
| Scroll / Arrow keys | Change gravity radius |
| R | Reset all characters |
| Double tap (mobile) | Toggle mode |
| Pinch (mobile) | Zoom gravity field |

## Features

- Per-character physics simulation with spring-return
- Velocity-based rotation and scale transforms
- Ghost trails on fast-moving characters
- Shockwave ripple on mode toggle
- Background starfield with twinkling
- Concentric gravity field visualization
- Smooth mouse interpolation
- Full touch + keyboard support
- Korean + English mixed text with proper width handling via pretext

## Tech

Single `index.html` — no build step, no dependencies beyond the CDN import:

```js
import { prepareWithSegments, layoutNextLine } from 'https://esm.sh/@chenglou/pretext@0.0.3'
```

pretext handles the hard part: breaking multilingual text (Korean, English, emoji, CJK) into properly measured lines that fit any width. Each character then becomes an independent physics particle.

## Credits

- [pretext](https://github.com/chenglou/pretext) by chenglou — text measurement & layout
- Built by [2lab.ai](https://github.com/2lab-ai)
