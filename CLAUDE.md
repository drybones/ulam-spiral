# Ulam Spiral — Prime Number Visualiser

## Purpose

A single-page web app that visualises the distribution of prime numbers using polar spiral geometry. Created as abstract mathematical artwork to advertise a summer party event.

## Technical approach

- **Single file**: everything lives in `index.html` — no build tools, no dependencies, no frameworks.
- **Spiral geometry**: each integer `n` is placed at radius `c × √n`. Two modes toggled via `state.spiralMode`, all going through `spiralAngle(n, rot, mode)`:
  - **Sunflower** (`'golden'`) — angle `n × GOLDEN_ANGLE` (`2π/φ²`, ~137.508°). Replicates sunflower seed packing; uniform organic appearance.
  - **Sacks** (`'sacks'`) — angle `n` radians (Robert Sacks, 2003). Produces an Archimedean spiral where primes form visible radial spokes.
- **Prime detection**: Sieve of Eratosthenes (`Uint8Array`) run once per N, cached.
- **Rendering**: Canvas 2D API, two batched `beginPath()` passes (composites, then primes) to avoid per-dot draw calls. A third pass draws user-highlighted primes with a ring + glow.
- **Export**: PNG (2× resolution offscreen canvas) and SVG (reconstructed geometry with `<circle>` elements and `<filter>` glow). Both support a transparent background option.
- **Persistence**: All settings saved to `localStorage` (key `prime-spiral-v1`), restored on load.

## Key controls

| Section | Controls |
|---|---|
| Preset | Mono (default), Slate, Sand, Night |
| Spiral | Sunflower (golden angle) / Sacks (n=θ) |
| Points | N slider 500–30,000 |
| Colour | Prime colour picker, colour mode (Solid / Radial / Arc gradient) |
| Dots | Prime dot size, glow intensity |
| Composites | Show/hide toggle, opacity |
| Highlight primes | Textarea (comma/space/newline separated), highlight colour, dot size, glow, ring radius, ring thickness |
| Export | PNG, SVG, transparent background toggle |

## Colour presets

| Name | Background | Prime colour | Mode |
|---|---|---|---|
| Mono | `#f8f8f6` | `#1a1a1a` | Solid |
| Slate | `#edf2f7` | `#2b4c8c` | Radial |
| Sand | `#faf3e6` | `#b84820` | Arc |
| Night | `#0a0a0f` | `#7faaff` | Radial |

## Notes

- The app is intentionally static — no animations.
- Sidebar is collapsible (desktop) and slides in as an overlay (mobile).
- Slider styling uses a fixed `--ui-accent` colour (`#7ba7e0`) independent of the prime colour, so controls remain visible regardless of preset.
- SVG export warns when N > 10,000 (file can be ~8 MB at N=30,000).
