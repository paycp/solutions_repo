# Problem 2

## 1. Theoretical Foundation

### Governing Equation of Motion

The motion of a forced damped pendulum is described by the second-order nonlinear differential equation:

\[
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \sin(\theta) = A \cos(\omega t)
\]

Where:  
- \( \theta \) — the angular displacement  
- \( b \) — the damping coefficient  
- \( g \) — the gravitational acceleration  
- \( L \) — the length of the pendulum  
- \( A \) — the amplitude of the external driving force  
- \( \omega \) — the driving angular frequency  
- \( t \) — time

---

### Small-Angle Approximation

For small angular displacements (\( \theta \) close to zero), we can approximate:

\[
\sin(\theta) \approx \theta
\]

Substituting this into the governing equation gives:

\[
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \theta = A \cos(\omega t)
\]

This simplifies the system to a **linear second-order nonhomogeneous differential equation** with constant coefficients.

---

### Interpretation of Terms

- The term \( b\frac{d\theta}{dt} \) represents **energy dissipation** due to damping.
- The term \( \frac{g}{L}\theta \) represents the **restoring force** due to gravity.
- The right-hand side \( A\cos(\omega t) \) represents an **external periodic driving force**.

Depending on the values of \( b \), \( A \), and \( \omega \), the system can exhibit:

- **Steady-state periodic motion**
- **Resonance phenomena**
- **Quasiperiodic or chaotic behavior**

---

### Resonance Condition

In the absence of damping and under the small-angle approximation, resonance occurs when the driving frequency \( \omega \) matches the natural frequency \( \omega_0 \) of the pendulum:

\[
\omega_0 = \sqrt{\frac{g}{L}}
\]

Under resonance:

- The amplitude of oscillations becomes significantly large.
- Energy transfer from the external driving force to the pendulum is maximized.

However, real systems with damping exhibit limited amplitudes and more complex resonance behavior.


## 2. Analysis of Dynamics

The behavior of the forced damped pendulum is strongly influenced by three key parameters:

- **Damping coefficient** (\( b \))  
    - Higher damping leads to quicker energy dissipation, causing oscillations to decay faster.
    - Lower damping allows oscillations to persist and can enable complex dynamics, including chaotic motion.

- **Driving amplitude** (\( A \))  
    - A small driving amplitude results in regular, predictable oscillations.
    - A larger driving amplitude can push the system into nonlinear and chaotic behavior.

- **Driving frequency** (\( \omega \))  
    - When the driving frequency approaches the system’s natural frequency (\( \omega_0 \)), resonance occurs, greatly amplifying oscillation amplitudes.
    - Away from resonance, the response is much smaller.

---

### Transition from Regular to Chaotic Motion

As the driving amplitude \( A \) or the driving frequency \( \omega \) increases, the system exhibits the following transitions:

- **Periodic motion**
    - Regular, repeating oscillations over time.

- **Quasiperiodic motion**
    - Oscillations combining two or more frequencies, leading to a non-repeating but structured pattern.

- **Chaotic motion**
    - Highly sensitive to initial conditions, with irregular, unpredictable behavior.  
    - Characterized by positive Lyapunov exponents and complex structures in phase space.

## 3. Practical Applications

The forced damped pendulum model, while idealized, has important applications in various real-world systems where periodic driving and damping effects are present.

### Energy Harvesting Devices

- Systems such as piezoelectric energy harvesters rely on oscillations induced by ambient vibrations.
- Understanding resonance and damping helps optimize energy extraction.

### Suspension Bridges

- Suspension bridges are susceptible to wind-induced oscillations, which can lead to resonance phenomena.
- Proper damping mechanisms are critical to prevent catastrophic failures, such as the Tacoma Narrows Bridge collapse.

### Oscillating Electrical Circuits

- Driven RLC circuits (resistor-inductor-capacitor systems) behave analogously to forced damped pendulums.
- Analysis of resonance and damping is essential for the design of stable and efficient electronic systems.

### Biomechanics and Gait Analysis

- Human gait dynamics under external perturbations (e.g., uneven surfaces or wearable devices) can be modeled similarly.
- Damping and external forcing play roles in maintaining balance and stability.

> These practical examples demonstrate the relevance of the forced damped pendulum model beyond theoretical physics, providing insight into engineering, biomechanics, and energy systems.

## 4. Implementation

To simulate the motion of a forced damped pendulum, we model the system numerically using Python.  
Given the complexity of the system, particularly for large angles and chaotic motion, we employ a numerical integration method.

### Numerical Method

We use the **fourth-order Runge-Kutta (RK4) method** to solve the system of first-order differential equations derived from the original second-order equation.

Let:

\[
\theta' = \omega
\]
\[
\omega' = -b\omega - \frac{g}{L} \sin(\theta) + A \cos(\omega_{\text{drive}} t)
\]

where:
- \( \theta \) is the angular displacement,
- \( \omega \) is the angular velocity,
- \( t \) is time.

This transforms the original second-order ODE into a system of two coupled first-order ODEs.

---

### Python Implementation

```python
import numpy as np
import matplotlib.pyplot as plt

# Parameters
g = 9.8      # gravitational acceleration (m/s^2)
L = 1.0      # length of the pendulum (m)
b = 0.2      # damping coefficient
A = 1.2      # driving amplitude
omega_drive = 2/3  # driving frequency (rad/s)

# Time settings
dt = 0.04       # time step (s)
t_max = 60      # maximum simulation time (s)
t = np.arange(0, t_max, dt)

# Initialize arrays
theta = np.zeros(len(t))
omega = np.zeros(len(t))

# Initial conditions
theta[0] = 0.2  # initial angle (radians)
omega[0] = 0.0  # initial angular velocity (radians/s)

# Runge-Kutta 4th Order Method
for i in range(len(t) - 1):
    k1_theta = omega[i]
    k1_omega = -b * omega[i] - (g/L) * np.sin(theta[i]) + A * np.cos(omega_drive * t[i])
    
    k2_theta = omega[i] + 0.5 * dt * k1_omega
    k2_omega = -b * (omega[i] + 0.5 * dt * k1_omega) - (g/L) * np.sin(theta[i] + 0.5 * dt * k1_theta) + A * np.cos(omega_drive * (t[i] + 0.5 * dt))
    
    k3_theta = omega[i] + 0.5 * dt * k2_omega
    k3_omega = -b * (omega[i] + 0.5 * dt * k2_omega) - (g/L) * np.sin(theta[i] + 0.5 * dt * k2_theta) + A * np.cos(omega_drive * (t[i] + 0.5 * dt))
    
    k4_theta = omega[i] + dt * k3_omega
    k4_omega = -b * (omega[i] + dt * k3_omega) - (g/L) * np.sin(theta[i] + dt * k3_theta) + A * np.cos(omega_drive * (t[i] + dt))
    
    theta[i+1] = theta[i] + (dt/6) * (k1_theta + 2*k2_theta + 2*k3_theta + k4_theta)
    omega[i+1] = omega[i] + (dt/6) * (k1_omega + 2*k2_omega + 2*k3_omega + k4_omega)
    
    # Keep theta within [-pi, pi] for better visualization
    if theta[i+1] > np.pi:
        theta[i+1] -= 2*np.pi
    elif theta[i+1] < -np.pi:
        theta[i+1] += 2*np.pi

# Plotting
plt.figure(figsize=(10, 6))
plt.plot(t, theta)
plt.title('Forced Damped Pendulum: Angular Displacement Over Time')
plt.xlabel('Time (s)')
plt.ylabel('Angle (radians)')
plt.grid(True)
plt.tight_layout()
plt.show()
