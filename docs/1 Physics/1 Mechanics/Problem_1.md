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

---