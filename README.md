# Ulam Spiral — Prime Number Visualiser

A single-page web app that visualises the distribution of prime numbers using a golden-angle polar spiral (the sunflower/Fibonacci seed variant of the Ulam spiral).

![Ulam Spiral](https://github.com/drybones/ulam-spiral/raw/master/screenshot.png)

## Usage

Open `index.html` in any modern browser — no build step, no dependencies, no server required.

## How it works

Each integer `n` is placed at angle `n × 137.508°` (the golden angle, `2π/φ²`) and radius `c × √n`. This replicates sunflower seed packing and gives the spiral its organic, Fibonacci-like appearance. Primes are highlighted; composites can be shown or hidden.

## Controls

| Section | Controls |
|---|---|
| Preset | Mono, Slate, Sand, Sage |
| Points | N slider 500–30,000 |
| Colour | Prime colour picker, gradient mode (Solid / Radial / Arc) |
| Dots | Prime dot size, glow intensity |
| Composites | Show/hide toggle, opacity |
| Highlight primes | Enter specific primes to ring and glow |
| Export | PNG or SVG, with optional transparent background |

## License

MIT — see [LICENSE](LICENSE).
