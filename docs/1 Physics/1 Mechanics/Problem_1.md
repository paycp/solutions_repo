# Problem 1

## 1. Theoretical Foundation

### Governing Equations of Motion

To analyze projectile motion, we start with Newton’s laws and decompose the motion into two perpendicular components: horizontal (x-axis) and vertical (y-axis). Assuming no air resistance and a flat surface, the equations of motion are:

- **Horizontal motion:**

\[
x(t) = v_0 \cdot \cos(\theta) \cdot t
\]

- **Vertical motion:**

\[
y(t) = v_0 \cdot \sin(\theta) \cdot t - \frac{1}{2}gt^2
\]

Where:  
- \( v_0 \) is the initial speed,  
- \( \theta \) is the launch angle,  
- \( g \) is the acceleration due to gravity,  
- \( t \) is time.  

### Time of Flight

The projectile returns to the ground when its vertical position becomes zero:  

\[
y(t) = 0
\]

Solving for \( t \):

\[
t = \frac{2v_0 \cdot \sin(\theta)}{g}
\]

This represents the **total time of flight**.

### Range of the Projectile

Substitute the time of flight into the horizontal equation:

\[
R = v_0 \cdot \cos(\theta) \cdot \frac{2v_0 \cdot \sin(\theta)}{g}
\]

Using the trigonometric identity \( 2 \cdot \sin(\theta) \cdot \cos(\theta) = \sin(2\theta) \), we simplify:

\[
R = \frac{v_0^2 \cdot \sin(2\theta)}{g}
\]

### Family of Solutions

This final equation shows that the range \( R \) depends on:  
- the square of the initial speed \( v_0 \),  
- the sine of twice the launch angle \( \theta \),  
- and the gravitational acceleration \( g \).  

For fixed \( v_0 \) and \( g \), the range varies **only with the launch angle**, forming a family of solutions that can be explored analytically and computationally.

## 2. Analysis of the Range

### Behavior of the Range Function

From the equation:

\[
R(\theta) = \frac{v_0^2 \cdot \sin(2\theta)}{g}
\]

we observe that the range \( R \) depends on the sine of twice the launch angle \( \theta \). 

This means:  
- The function \( \sin(2\theta) \) reaches its **maximum value of 1** when \( 2\theta = 90^\circ \), i.e. \( \theta = 45^\circ \).  
- Therefore, the **maximum range** is achieved when the projectile is launched at an angle of **45°**.  

### Symmetry in the Range

The function \( \sin(2\theta) \) is **symmetric** around \( \theta = 45^\circ \). This implies that:

\[
R(\theta) = R(90^\circ - \theta)
\]

**Example:**  
- A launch at \( 30^\circ \) gives the same range as a launch at \( 60^\circ \).  
- Likewise, \( 20^\circ \) and \( 70^\circ \) give the same range.

This symmetry creates **pairs of angles** with identical range values, despite different trajectories.

### Implications
The same horizontal distance can be achieved with different angles, but:  
  - Lower angles produce flatter, faster trajectories.  
  - Higher angles result in higher arcs with longer air time.

### Visual Expectation

A plot of \( R(\theta) \) versus \( \theta \) from \( 0^\circ \) to \( 90^\circ \) will form a **symmetric curve**, peaking at \( 45^\circ \).

> This provides a solid foundation for experimental simulation or numerical analysis to visualize this behavior.

## 3. Code Implementation

To analyze the relationship between the launch angle and the projectile range, we simulate the motion using Python with `numpy` and `matplotlib`.

### Python Code

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
v0 = 10  # initial velocity in m/s
g = 9.8  # acceleration due to gravity in m/s^2

# Angle range from 0 to 90 degrees
angles_deg = np.linspace(0, 90, 1000)
angles_rad = np.deg2rad(angles_deg)

# Range formula
range_values = (v0**2 * np.sin(2 * angles_rad)) / g

# Plotting
plt.figure(figsize=(10, 6))
plt.plot(angles_deg, range_values, label='Range vs Angle', color='teal')
plt.axvline(45, color='gray', linestyle='--', label='Maximum Range at 45°')

plt.title('Projectile Range as a Function of Launch Angle')
plt.xlabel('Launch Angle (degrees)')
plt.ylabel('Range (meters)')
plt.grid(True)
plt.legend()
plt.tight_layout()
plt.show()
```

## 4. Graph and Interpretation

### Visualization Overview

The plot generated by the simulation shows how the projectile range varies with respect to the launch angle \( \theta \) from 0° to 90°.

Key observations:  
- The range increases as the angle increases from 0° to 45°.  
- The **maximum range** is achieved at **45°**.  
- Beyond 45°, the range **decreases symmetrically**, approaching zero at 90°.  
- The plot is symmetric around 45°, confirming that:

\[
R(\theta) = R(90^\circ - \theta)
\]

This illustrates that different launch angles can result in the same horizontal distance but with different flight characteristics (trajectory height and flight time).

### Real-World Insight

Such graphical analysis provides a deeper understanding of projectile motion:  
- In sports, optimizing throw or kick angles improves performance.  
- In engineering, ideal launch angles reduce energy costs or material usage.  
- In aerospace, it helps model ideal launch trajectories (neglecting drag).

This visualization confirms the theoretical predictions and provides a strong foundation for exploring more complex or real-world scenarios in future sections.

## 5. Limitations and Further Improvements

### Idealized Assumptions

This model makes several simplifying assumptions:  
- **No air resistance**: In reality, drag significantly affects the range, especially at higher velocities.  
- **Launch from ground level**: The model does not account for launches from elevated platforms or terrains.  
- **Constant gravity**: Gravitational acceleration is treated as constant, though it can vary slightly with altitude or location.  
- **No wind or atmospheric effects**: Wind direction and speed can greatly alter projectile behavior.

### Possible Extensions

To increase realism, future versions of the model can include:  
- Air resistance (quadratic drag or using differential equations),  
- Launch from an arbitrary height,  
- Custom terrain elevation or slope,  
- Variable gravitational environments (e.g., other planets),  
- 3D projectile motion.

These refinements make the model more applicable to engineering, aerospace, and defense systems where precision is critical.

---