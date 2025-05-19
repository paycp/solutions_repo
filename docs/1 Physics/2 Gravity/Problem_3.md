# Problem 3

## 1. Theoretical Foundation

The trajectory of a freely released payload near Earth depends on its initial speed, direction, and altitude — all governed by Newtonian gravity and conservation laws.

---

### Classification of Trajectories

The shape of the payload’s orbit depends on its **specific mechanical energy** \( \varepsilon \):

\[
\varepsilon = \frac{v^2}{2} - \frac{G M}{r}
\]

where:
- \( v \) is the initial velocity of the payload,
- \( r \) is the distance from Earth’s center,
- \( G \) is the gravitational constant,
- \( M \) is Earth’s mass.

---

### Types of Trajectories

| Trajectory Type     | Condition on \( \varepsilon \)       | Shape         |
|---------------------|---------------------------------------|---------------|
| Bound (orbital)     | \( \varepsilon < 0 \)                 | Elliptical    |
| Escape              | \( \varepsilon = 0 \)                 | Parabolic     |
| Unbound             | \( \varepsilon > 0 \)                 | Hyperbolic    |

- **Elliptical**: Object is captured by Earth and follows a closed orbit.  
- **Parabolic**: Object escapes Earth with exactly zero residual speed at infinity.  
- **Hyperbolic**: Object escapes with non-zero speed — e.g., interplanetary or interstellar ejection.

---

### Relation to Orbital Velocity

Let \( v_1 = \sqrt{\frac{G M}{r}} \) — the circular orbital velocity. Then:

- If \( v < v_1 \): suborbital fall back to Earth  
- If \( v = v_1 \): circular orbit  
- If \( v_1 < v < v_2 \): elliptical orbit  
- If \( v = v_2 = \sqrt{2} v_1 \): parabolic escape  
- If \( v > v_2 \): hyperbolic trajectory

---

### Orbital Equation (Polar Form)

The general conic section equation for motion under gravity:

\[
r(\theta) = \frac{p}{1 + e \cos(\theta)}
\]

where:
- \( p \) is the semi-latus rectum,
- \( e \) is the orbital eccentricity:
  - \( e = 0 \): circle
  - \( 0 < e < 1 \): ellipse
  - \( e = 1 \): parabola
  - \( e > 1 \): hyperbola

---

### Summary

The trajectory depends on initial velocity and position, and can be classified using:

- Mechanical energy \( \varepsilon \)
- Orbital velocity thresholds \( v_1 \), \( v_2 \)
- Orbital eccentricity \( e \)

> These parameters help predict whether a payload returns, stays in orbit, or escapes.


## 2. Numerical Simulation of Trajectories

To simulate the motion of a payload near Earth, we solve Newton's second law numerically:

\[
\vec{a} = -\frac{G M}{r^3} \cdot \vec{r}
\]

This is a second-order differential equation describing motion under gravity.

---

### Assumptions

- Earth is treated as a point mass.
- Only gravity acts on the payload (no atmosphere).
- Motion occurs in 2D (x, y).

---

### Python Implementation

We use `scipy.integrate.solve_ivp` to simulate the trajectory from given initial position and velocity.

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Constants
G = 6.67430e-11
M = 5.972e24       # Earth mass
R = 6.371e6        # Earth radius

# Initial position and velocity
r0 = np.array([R + 300e3, 0])  # 300 km altitude
v0 = np.array([0, 7700])       # 7.7 km/s horizontal velocity

# ODE system: y = [x, y, vx, vy]
def gravity(t, y):
    rx, ry, vx, vy = y
    r = np.sqrt(rx**2 + ry**2)
    ax = -G * M * rx / r**3
    ay = -G * M * ry / r**3
    return [vx, vy, ax, ay]

# Time span and initial state
t_span = (0, 10000)
y0 = [r0[0], r0[1], v0[0], v0[1]]
t_eval = np.linspace(*t_span, 1000)

# Solve ODE
sol = solve_ivp(gravity, t_span, y0, t_eval=t_eval)

# Extract trajectory
x, y = sol.y[0], sol.y[1]

# Plot
plt.figure(figsize=(6, 6))
plt.plot(x / 1e3, y / 1e3, label='Payload trajectory')
circle = plt.Circle((0, 0), R / 1e3, color='blue', alpha=0.3, label='Earth')
plt.gca().add_patch(circle)
plt.xlabel('x (km)')
plt.ylabel('y (km)')
plt.axis('equal')
plt.grid(True)
plt.legend()
plt.title('Trajectory of a Payload Released Near Earth')
plt.tight_layout()
plt.show()
````

---

### Initial Conditions

Try modifying:

* $v_0 < v_1$: suborbital (falls back)
* $v_0 = v_1$: circular orbit
* $v_0 > v_1$: elliptical
* $v_0 \approx v_2$: escape
* $v_0 > v_2$: hyperbolic

---

### Output

* The trajectory will curve depending on energy and eccentricity.
* The closer $v$ is to $v_2$, the further the payload travels before turning.
* $v > v_2$: the payload escapes to infinity.

> Numerical integration lets us explore any trajectory based on initial speed, angle, and altitude.

