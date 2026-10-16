# Fractal Maker

An infinite tap-to-grow fractal garden. One glowing dot on the left of the
screen — every tap, click, or press-and-hold grows it into sprawling,
one-of-a-kind spirals. When the fractal fills the screen, the camera backs
up to make more room, so it can keep growing forever.

## The math

Every fractal is born with its own secret growth laws, rolled fresh on load:

- **Curl bias** — a constant per-step turn that bends growth into logarithmic-spiral arcs
- **Sine-wave wobble** — a sinusoidal turn component with random amplitude/frequency/phase
- **Chaos jitter** — random turn noise so no two branches ever agree
- **Golden-angle branching** — new branches kick off near 137.508°, the same angle sunflowers use to pack seeds

Growth is an incremental turtle system: each living tip advances, curls, and
sometimes splits. Tips retire as the frontier expands, so it never stalls.

## The infinite canvas

Segments paint onto an offscreen world buffer with additive blending (glow).
When the fractal outgrows the buffer, the buffer's contents shrink by half —
doubling the room to grow into. The camera continuously eases to fit the
fractal's bounding box, which is the "backs up to make more room" effect.

## Controls

- **Tap / click / hold anywhere** — grow (hold for continuous growth)
- **✦ New** — roll a brand-new fractal with new math (or press `N`)
- **◑ Colors** — cycle palettes; new growth picks up the new palette, old growth keeps its history (or press `C`)
- **⤓ Save** — export the current view as PNG
- **Spacebar** — grow once

No dependencies, no build step — just open `index.html`.
