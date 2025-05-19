# Problem 1

## 1. Theoretical Foundation

When multiple circular waves are emitted from different point sources on a water surface, they overlap and form complex **interference patterns**. These patterns are governed by:

- The **wave equation** for each point source,
- The **principle of superposition**.

---

### Single Source Wave Equation

A wave emitted by a point source located at \( (x_0, y_0) \) on the surface is given by:

\[
\eta(x, y, t) = \frac{A}{\sqrt{r}} \cdot \cos(kr - \omega t + \phi)
\]

where:
- \( \eta(x, y, t) \) is the displacement of the water surface,
- \( A \) is the amplitude,
- \( r = \sqrt{(x - x_0)^2 + (y - y_0)^2} \) is the distance from the source to point \( (x, y) \),
- \( k = \frac{2\pi}{\lambda} \) is the wave number,
- \( \omega = 2\pi f \) is the angular frequency,
- \( \phi \) is the initial phase of the wave.

We assume all waves are **monochromatic**, **coherent**, and **have identical amplitude, frequency, and phase**.

---

### Superposition of Waves

If we place \( N \) identical sources at different positions \( (x_i, y_i) \), the resulting displacement is the sum of displacements from each:

\[
\eta_{\text{sum}}(x, y, t) = \sum_{i=1}^{N} \eta_i(x, y, t)
\]

This leads to **constructive interference** when wave crests align, and **destructive interference** when crests and troughs cancel each other.

---

### Symmetry and Patterns

If the sources are placed at the **vertices of a regular polygon**, their symmetry will be reflected in the interference pattern:

- 3 sources → triangular symmetry  
- 4 sources → square symmetry  
- 5+ sources → complex radial patterns

These symmetrical setups are useful for studying:
- Zones of maximum and minimum amplitude,
- Nodal lines (where waves cancel out),
- Phase alignment across space.

---

### Summary

| Concept                | Role                                                   |
|------------------------|--------------------------------------------------------|
| Point wave equation    | Describes wave from one source                        |
| Superposition          | Adds effects of all sources together                  |
| Interference pattern   | Emerges from wave overlap (constructive/destructive)  |
| Regular polygon layout | Introduces symmetry and periodicity to the system     |

> This theoretical base enables us to model and visualize wave interference patterns with clarity and control.
