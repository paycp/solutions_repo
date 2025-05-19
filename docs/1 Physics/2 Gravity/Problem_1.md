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

## 2. Implications for Astronomy

Kepler’s Third Law has profound implications for modern astronomy. Once the relationship

\[
T^2 = \frac{4\pi^2}{G M} r^3
\]

is established, it becomes a powerful tool for determining the **mass of a central object** or the **distance to an orbiting body**.

---

### 1. Calculating Mass from Orbital Motion

By observing a satellite’s orbital radius \( r \) and period \( T \), we can calculate the mass \( M \) of the central object using:

\[
M = \frac{4\pi^2 r^3}{G T^2}
\]

This method is commonly used to estimate:

- The **mass of the Earth** from Moon’s orbit,
- The **mass of the Sun** from planetary orbits,
- The **mass of exoplanet host stars**.

---

### 2. Determining Orbital Radius

If the mass \( M \) of the central body is known (e.g., from spectroscopy), we can rearrange Kepler’s Law to compute the orbital radius:

\[
r = \left( \frac{G M T^2}{4\pi^2} \right)^{1/3}
\]

This is used in:

- **Satellite orbit design** (e.g., geostationary satellites),
- Calculating the distance between binary stars,
- Estimating distances in planetary systems.

---

### 3. Astronomical Units and Simplified Forms

In the Solar System, if we express:
- \( T \) in Earth years,
- \( r \) in astronomical units (AU),
- \( M \) in solar masses,

then the proportionality constant becomes 1:

\[
T^2 = r^3
\]

This simplification is frequently used in **exoplanet detection**, where observational data provides \( T \), and \( r \) is inferred under this assumption.

---

### Summary

Kepler’s Third Law serves as:

- A cornerstone for **measuring planetary systems**,
- A practical method for **estimating masses and distances**,
- A theoretical link between **Newtonian gravity and orbital dynamics**.

## 3. Real-World Examples

Kepler’s Third Law can be directly applied to real celestial systems. Below are classic examples demonstrating its use.

---

### 1. The Moon’s Orbit Around Earth

- Orbital radius: \( r \approx 3.84 \times 10^8 \) meters  
- Orbital period: \( T \approx 27.3 \) days \( \approx 2.36 \times 10^6 \) seconds

Using:

\[
M = \frac{4\pi^2 r^3}{G T^2}
\]

we can estimate Earth’s mass:

\[
M \approx \frac{4\pi^2 (3.84 \times 10^8)^3}{(6.674 \times 10^{-11})(2.36 \times 10^6)^2} \approx 5.97 \times 10^{24} \text{ kg}
\]

✅ Matches accepted value for Earth’s mass.

---

### 2. Geostationary Satellite

A geostationary satellite orbits Earth once per sidereal day:

- \( T = 86,164 \) seconds  
- \( M_{\text{Earth}} = 5.97 \times 10^{24} \text{ kg} \)

Solving for \( r \):

\[
r = \left( \frac{G M T^2}{4\pi^2} \right)^{1/3}
\]

\[
r \approx \left( \frac{(6.674 \times 10^{-11})(5.97 \times 10^{24})(86164)^2}{4\pi^2} \right)^{1/3} \approx 4.22 \times 10^7 \text{ m}
\]

✅ This is approximately 35,786 km above Earth's surface — the correct altitude for geostationary orbit.

---

### 3. Planets in the Solar System

Using AU and years:

- Earth's orbit: \( r = 1 \) AU, \( T = 1 \) year  
- Mars: \( r \approx 1.52 \) AU

\[
T^2 = r^3 \quad \Rightarrow \quad T_{\text{Mars}} = \sqrt{(1.52)^3} \approx 1.88 \text{ years}
\]

✅ Matches the known orbital period of Mars.

---

### 4. Exoplanets

Kepler’s Third Law is routinely applied in detecting exoplanets:

- Transit timing gives \( T \)
- Stellar mass \( M \) known from spectral data
- \( r \) inferred via:

\[
r = \left( \frac{G M T^2}{4\pi^2} \right)^{1/3}
\]

This helps determine **habitability zones**, **orbital stability**, and even potential moons.

---

### Summary

Kepler’s Law is essential in:

- Satellite design and spaceflight,
- Measuring celestial masses,
- Understanding orbital dynamics from Earth to exoplanetary systems.


## 4. Implementation

To verify Kepler’s Third Law numerically, we simulate circular orbits of varying radii around a central mass and calculate the orbital periods for each case.

---

### Assumptions

- Circular, two-body orbits
- Central mass (e.g., the Sun): \( M = 1.989 \times 10^{30} \text{ kg} \)
- Only gravity provides the centripetal force
- Units: SI (meters, kilograms, seconds)

---

### Python Code

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11          # gravitational constant
M = 1.989e30             # mass of central body (Sun)

# Orbital radii from 0.2 to 5 AU (converted to meters)
AU = 1.496e11
radii_au = np.linspace(0.2, 5, 100)
radii_m = radii_au * AU

# Calculate periods using T = 2π * sqrt(r^3 / GM)
periods_s = 2 * np.pi * np.sqrt(radii_m**3 / (G * M))
periods_yr = periods_s / (60 * 60 * 24 * 365.25)  # convert to years

# Plot T^2 vs r^3
T_squared = periods_yr**2
r_cubed = radii_au**3

plt.figure(figsize=(8, 6))
plt.plot(r_cubed, T_squared, label='Simulated data', color='navy')
plt.xlabel('$r^3$ (AU³)')
plt.ylabel('$T^2$ (years²)')
plt.title('Verification of Kepler’s Third Law')
plt.grid(True)
plt.legend()
plt.tight_layout()
plt.show()
```

---

### Interpretation

According to Kepler’s Third Law, the relationship:

\[
T^2 = k r^3
\]

should produce a straight line when plotting \( T^2 \) versus \( r^3 \).

> The resulting graph confirms a linear relationship — verifying Kepler’s Law in the circular orbit case.

---

### Next Steps

- Try fitting a linear regression to estimate the constant \( k \).
- Extend the simulation to include **elliptical orbits** using numerical integration.
- Visualize orbits using **position updates** (x, y) for better understanding of orbital paths.

