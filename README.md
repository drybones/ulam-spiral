# Ulam Spiral — Prime Number Visualiser

A single-page web app that visualises the distribution of prime numbers using polar spiral geometry. Two spiral modes are supported: the golden-angle sunflower (Fibonacci seed packing) and the Sacks spiral (each integer placed at angle θ = n radians).

![Ulam Spiral](https://github.com/drybones/ulam-spiral/raw/master/screenshot.png)

## Usage

Open `index.html` in any modern browser — no build step, no dependencies, no server required.

## How it works

Each integer `n` is placed at radius `c × √n`. The angle depends on the chosen spiral mode:

- **Sunflower** — angle `n × 137.508°` (the golden angle, `2π/φ²`). Replicates sunflower seed packing; gives an organic, Fibonacci-like appearance with uniform point distribution.
- **Sacks** — angle `n` radians (Robert Sacks, 2003). Produces an Archimedean spiral where primes form visible radial spokes due to their avoidance of composite multiples.

Primes are highlighted; composites can be shown or hidden.

## Controls

| Section | Controls |
|---|---|
| Preset | Mono, Slate, Sand, Night |
| Spiral | Sunflower (golden angle) / Sacks (n=θ) |
| Points | N slider 500–30,000 |
| Colour | Prime colour picker, gradient mode (Solid / Radial / Arc) |
| Dots | Prime dot size, glow intensity |
| Composites | Show/hide toggle, opacity |
| Highlight primes | Enter specific primes to ring and glow |
| Export | PNG or SVG, with optional transparent background |

## License

MIT — see [LICENSE](LICENSE).
