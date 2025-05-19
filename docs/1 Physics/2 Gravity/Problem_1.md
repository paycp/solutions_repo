# Problem 1

## 1. Theoretical Foundation

### Newtonian Derivation of Kepler’s Third Law for Circular Orbits

To derive the relationship between the square of the orbital period \( T \) and the cube of the orbital radius \( r \), we begin with Newton’s law of universal gravitation and the centripetal force required for circular motion.

#### Step 1: Gravitational Force

According to Newton's law:

\[
F_{\text{gravity}} = \frac{G M m}{r^2}
\]

where:
- \( G \) is the gravitational constant,
- \( M \) is the mass of the central body (e.g., the Sun),
- \( m \) is the mass of the orbiting body,
- \( r \) is the orbital radius.

#### Step 2: Centripetal Force

For uniform circular motion:

\[
F_{\text{centripetal}} = \frac{m v^2}{r}
\]

Setting the gravitational force equal to the centripetal force:

\[
\frac{G M m}{r^2} = \frac{m v^2}{r}
\]

Canceling \( m \) and solving for \( v \):

\[
v^2 = \frac{G M}{r}
\]

#### Step 3: Orbital Period

The orbital period \( T \) is related to the orbital speed and circumference:

\[
T = \frac{2\pi r}{v}
\quad \Rightarrow \quad v = \frac{2\pi r}{T}
\]

Substitute into the equation for \( v^2 \):

\[
\left( \frac{2\pi r}{T} \right)^2 = \frac{G M}{r}
\]

\[
\frac{4\pi^2 r^2}{T^2} = \frac{G M}{r}
\]

Multiply both sides by \( r \):

\[
\frac{4\pi^2 r^3}{T^2} = G M
\]

Now solve for \( T^2 \):

\[
T^2 = \frac{4\pi^2}{G M} \cdot r^3
\]

---

### Final Result

This is **Kepler’s Third Law** for circular orbits:

\[
T^2 \propto r^3
\]

The constant of proportionality depends on the gravitational constant and the mass of the central body:

\[
T^2 = k r^3
\quad \text{where} \quad k = \frac{4\pi^2}{G M}
\]

This result explains why planets farther from the Sun take longer to orbit and provides a way to infer masses of celestial bodies from orbital data.
