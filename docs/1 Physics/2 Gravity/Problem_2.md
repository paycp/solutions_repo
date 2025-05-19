# Problem 2

## 1. Theoretical Foundation

Cosmic velocities define the minimum speeds required to achieve specific goals in gravitational systems — from stable orbit to escaping the Solar System.

---

### First Cosmic Velocity (\( v_1 \)) – Orbital Velocity

This is the minimum horizontal velocity required to maintain a **stable circular orbit** near the surface of a celestial body.

\[
v_1 = \sqrt{\frac{G M}{r}}
\]

- \( G \) — gravitational constant  
- \( M \) — mass of the celestial body  
- \( r \) — orbital radius (typically the radius of the planet for low Earth orbit)

✅ A satellite launched at this speed will remain in free fall around the planet.

---

### Second Cosmic Velocity (\( v_2 \)) – Escape Velocity

This is the minimum speed required to **break free from the gravitational pull** of a celestial body without further propulsion.

\[
v_2 = \sqrt{\frac{2 G M}{r}} = \sqrt{2} \cdot v_1
\]

- This velocity allows an object to reach **infinity with zero final velocity**.
- Used for missions leaving Earth toward the Moon, Mars, etc.

✅ The spacecraft overcomes gravitational binding energy.

---

### Third Cosmic Velocity (\( v_3 \)) – Interstellar Escape Velocity

This is the minimum speed required to **leave the entire Solar System** from Earth’s orbit, overcoming the Sun’s gravitational field.

Assuming a starting point at Earth's orbit (neglecting Earth's own gravity):

\[
v_3 = \sqrt{\frac{2 G M_{\odot}}{r_{\text{Earth}}}}
\]

- \( M_{\odot} \) — mass of the Sun  
- \( r_{\text{Earth}} \) — Earth's orbital radius around the Sun

To launch from Earth’s surface and escape the Solar System, both Earth’s gravity and orbital motion must be taken into account:

\[
v_3^{\text{total}} = \sqrt{v_{2,\text{Earth}}^2 + v_3^2 - 2 v_{1,\text{Earth}} v_3 \cos(\theta)}
\]

✅ Often achieved through gravity assists and deep-space propulsion.

---

### Summary

| Velocity | Meaning | Formula |
|----------|---------|---------|
| \( v_1 \) | Circular orbital velocity | \( \sqrt{GM/r} \) |
| \( v_2 \) | Escape from planet | \( \sqrt{2GM/r} \) |
| \( v_3 \) | Escape from star system | \( \sqrt{2GM_{\odot}/r} \) |

These velocities form the foundation of **orbital mechanics** and are critical for mission planning, satellite deployment, and interplanetary navigation.

## 2. Mathematical Derivations and Dependencies

The first, second, and third cosmic velocities are derived from **Newton's law of universal gravitation** and principles of **conservation of energy**.

---

### First Cosmic Velocity (\( v_1 \))

This is the orbital speed for a circular orbit just above the surface:

From Newton’s law of gravitation:

\[
F_{\text{gravity}} = \frac{G M m}{r^2}
\]

From Newton's second law (centripetal force):

\[
F = \frac{m v^2}{r}
\]

Equating the forces:

\[
\frac{G M m}{r^2} = \frac{m v_1^2}{r}
\Rightarrow
v_1 = \sqrt{\frac{G M}{r}}
\]

---

### Second Cosmic Velocity (\( v_2 \))

This is derived from **energy conservation**:

\[
\text{Initial total energy} = \text{Final total energy}
\]

\[
\frac{1}{2} m v_2^2 - \frac{G M m}{r} = 0
\Rightarrow
v_2 = \sqrt{\frac{2 G M}{r}} = \sqrt{2} \cdot v_1
\]

Here:
- The kinetic energy must exactly cancel the gravitational potential energy.
- Final energy at infinity is zero.

---

### Third Cosmic Velocity (\( v_3 \))

To escape the Sun’s gravity from Earth’s orbit:

\[
E = \frac{1}{2} m v_3^2 - \frac{G M_{\odot} m}{r_{\text{Earth}}} = 0
\Rightarrow
v_3 = \sqrt{\frac{2 G M_{\odot}}{r_{\text{Earth}}}}
\]

But if launched from Earth, must also overcome Earth’s escape velocity \( v_{2,\text{Earth}} \).  
The **actual total velocity** depends on launch direction and existing orbital motion:

\[
v_3^{\text{total}} = \sqrt{v_2^2 + v_3^2 - 2 v_1 v_3 \cos(\theta)}
\]

where:
- \( \theta \) is the angle between launch direction and Earth’s orbital velocity vector.

---

### Parameter Dependencies

| Parameter | Influence |
|----------|-----------|
| \( M \) — central mass | All three velocities increase with mass |
| \( r \) — orbital radius | All velocities decrease with larger radius |
| \( G \) — gravitational constant | Appears in all expressions |
| \( \theta \) — launch angle (only for \( v_3^{\text{total}} \)) | Affects net velocity due to vector addition |

---

> These derivations form the basis for calculating required launch speeds, designing trajectories, and estimating fuel needs in orbital mechanics.
