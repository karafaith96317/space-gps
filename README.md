# Space GPS

Interactive browser tool to see **where you are on Earth**, where **Earth sits in the solar system**, and first-cut **orbital / Hohmann Δv** numbers for flight planning.

Educational **mean-element ephemeris** and **two-body** math — good for orientation and mission sketches, **not** flight software or navigation.

**Repo:** [github.com/karafaith96317/space-gps](https://github.com/karafaith96317/space-gps)

## How to open

No build step, no npm. Just open the file:

```bash
# clone, then open in any modern browser
open index.html
# or: python -m http.server 8080  →  http://localhost:8080
```

Double-click `index.html`, or drag it into a browser tab. Works offline once loaded.

## Modes

| Mode | What it does |
|------|----------------|
| **Where am I** | Lat/lon/alt fix, presets (NY, Equator, N Pole, Antipode NY), America/New_York + UTC clocks, Julian day, LST, day/night from sun altitude, min launch inclination \(i \ge |\mathrm{lat}|\), SVG solar map (Mercury–Saturn, Earth highlighted), distances table |
| **Orbit** | Circular Earth orbit: \(v_\mathrm{circ}\), \(v_\mathrm{esc}\), period, radius, specific energy; quick LEO 400 / GEO 35786 |
| **Transfer Δv** | Hohmann Earth circular→circular; presets LEO→GEO, LEO 400→800, LEO→lunar distance; Δv₁, Δv₂, total, TOF |
| **Deep space** | Target Moon / Venus / Mars / Jupiter: range, one-way light time, phase now vs ideal Hohmann, heliocentric Hohmann Δv + TOF (planets), round-trip delay, map |

Ephemeris and clocks refresh every **1 second**.

## Accuracy disclaimer

**Approximate — not for navigation or flight software.**

- Planetary positions: J2000-style mean elements + Kepler (approx.)
- Earth μ = 398600.4418 km³/s², R⊕ = 6371 km
- Sun μ and AU as conventional constants; Moon via truncated analytical series
- Hohmann assumes coplanar circular orbits; ignores plane change, drag, third bodies
- Deep-space range is ecliptic-plane geometry (except Moon: geocentric distance)

## Constants

| Symbol | Value |
|--------|-------|
| μ_earth | 398600.4418 km³/s² |
| R_earth | 6371 km |
| μ_sun | 1.32712440018×10¹¹ km³/s² |
| AU | 149597870.7 km |

## License

MIT — Copyright © 2026 Kara Faith. See [LICENSE](LICENSE).
