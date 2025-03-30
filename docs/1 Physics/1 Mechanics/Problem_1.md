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
\( y(t) = 0 \)

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

we observe that the range \( R \) depends on the sine of twice the launch angle \( \theta \). This means:

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

- The same horizontal distance can be achieved with different angles, but:
  - Lower angles produce flatter, faster trajectories.
  - Higher angles result in higher arcs with longer air time.

### Visual Expectation

A plot of \( R(\theta) \) versus \( \theta \) from \( 0^\circ \) to \( 90^\circ \) will form a **symmetric curve**, peaking at \( 45^\circ \).

> This provides a solid foundation for experimental simulation or numerical analysis to visualize this behavior.

---