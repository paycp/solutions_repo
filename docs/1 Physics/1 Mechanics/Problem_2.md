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

To explore the behavior of the forced damped pendulum, we develop a computational model using Python.

We use a numerical method, specifically the fourth-order Runge-Kutta method (`scipy.integrate.solve_ivp`), to solve the system of ordinary differential equations (ODEs).

---

### Mathematical Model

The second-order differential equation describing the forced damped pendulum is:

\[
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \sin(\theta) = A \cos(\omega t)
\]

This can be rewritten as a system of two first-order equations:

\[
\frac{d\theta}{dt} = \omega
\quad \quad
\frac{d\omega}{dt} = -b\omega - \frac{g}{L} \sin(\theta) + A \cos(\omega_{\text{drive}} t)
\]

where:  
- \( \theta \) is the angular displacement,  
- \( \omega \) is the angular velocity,  
- \( b \) is the damping coefficient,  
- \( g \) is the gravitational acceleration,  
- \( L \) is the length of the pendulum,  
- \( A \) is the amplitude of the external driving force,  
- \( \omega_{\text{drive}} \) is the driving angular frequency.

---

### Python Code

    import numpy as np
    import matplotlib.pyplot as plt
    from scipy.integrate import solve_ivp

    # Parameters
    g = 9.8          # gravitational acceleration (m/s^2)
    L = 1.0          # length of pendulum (m)
    b = 0.2          # damping coefficient
    A = 1.2          # amplitude of driving force
    omega_drive = 2/3  # driving frequency (rad/s)

    # Time span
    t_span = (0, 60)
    t_eval = np.linspace(t_span[0], t_span[1], 1000)

    # System of equations
    def pendulum(t, y):
        theta, omega = y
        dtheta_dt = omega
        domega_dt = -b * omega - (g/L) * np.sin(theta) + A * np.cos(omega_drive * t)
        return [dtheta_dt, domega_dt]

    # Initial conditions
    y0 = [0.2, 0.0]  # Small initial angle, zero initial velocity

    # Solve ODE
    solution = solve_ivp(pendulum, t_span, y0, t_eval=t_eval, method='RK45')

    # Extract results
    theta = solution.y[0]
    omega = solution.y[1]
    time = solution.t

    # Normalize theta to [-pi, pi]
    theta = (theta + np.pi) % (2 * np.pi) - np.pi

    # Plotting
    plt.figure(figsize=(12, 6))

    # Angle vs Time
    plt.subplot(2, 1, 1)
    plt.plot(time, theta, label='Theta (angle)')
    plt.xlabel('Time (s)')
    plt.ylabel('Angle (radians)')
    plt.title('Angle vs Time')
    plt.grid(True)
    plt.legend()

    # Phase Portrait
    plt.subplot(2, 1, 2)
    plt.plot(theta, omega, '.', markersize=1, label='Phase Portrait')
    plt.xlabel('Angle (radians)')
    plt.ylabel('Angular velocity (rad/s)')
    plt.title('Phase Portrait')
    plt.grid(True)
    plt.legend()

    plt.tight_layout()
    plt.show()

---

### Visualization Overview  
![Plot1.2.1](../../_pics/plot1.2.1.png)

- **Angle vs Time**  
  Shows how the pendulum's angle evolves under the combined effects of damping and external forcing.

- **Phase Portrait**  
  Plots angular velocity versus angle to visualize the dynamical behavior of the system.  
  In chaotic regimes, the phase portrait appears scattered and complex.


## 6. Advanced Visualizations

This section presents additional tools for analyzing the complex behavior of the forced damped pendulum. These include:

- **Poincaré sections**: useful for visualizing transitions to chaos by sampling the phase space at regular intervals.
- **Bifurcation diagrams**: show how the system’s behavior evolves as a parameter (typically the driving amplitude \( A \)) changes.

---

### Poincaré Section

The Poincaré section is constructed by sampling the state \((\theta, \omega)\) once per driving cycle:

\[
T = \frac{2\pi}{\omega_{\text{drive}}}
\]

Only values at \( t_n = nT \) are recorded, providing a simplified view of the system's long-term behavior.  
![Plot1.2.2](../../_pics/plot1.2.2.png)

    # Define driving period
    T_drive = 2 * np.pi / omega_drive
    sample_times = np.arange(0, t_span[1], T_drive)

    # Solve the ODE with dense output
    solution_dense = solve_ivp(pendulum, t_span, y0, dense_output=True)

    # Sample at multiples of T
    poincare = solution_dense.sol(sample_times)
    theta_p = (poincare[0] + np.pi) % (2 * np.pi) - np.pi
    omega_p = poincare[1]

    # Plot Poincaré section
    plt.figure(figsize=(6, 6))
    plt.plot(theta_p, omega_p, 'o', markersize=2)
    plt.xlabel('Angle (radians)')
    plt.ylabel('Angular velocity (rad/s)')
    plt.title('Poincaré Section')
    plt.grid(True)
    plt.show()

Periodic motion produces discrete points. Quasiperiodic motion forms closed curves. Chaotic motion leads to scattered, dense regions.

---

### Bifurcation Diagram

In this plot, the driving amplitude \( A \) is gradually varied. For each value, the system's angle is sampled once per cycle (after transients) to observe how behavior changes:  
![Plot1.2.3](../../_pics/plot1.2.3.png)


```python
A_values = np.linspace(1.0, 1.6, 200)
theta_samples = []

for A_current in A_values:
    def pendulum_A(t, y):
        theta, omega = y
        dtheta_dt = omega
        domega_dt = -b * omega - (g/L) * np.sin(theta) + A_current * np.cos(omega_drive * t)
        return [dtheta_dt, domega_dt]
    
    sol = solve_ivp(pendulum_A, (0, 300), y0, dense_output=True)
    
    # Sample last 50 cycles after transient
    T = 2 * np.pi / omega_drive
    times = np.arange(250, 300, T)
    sampled = sol.sol(times)
    thetas = (sampled[0] + np.pi) % (2 * np.pi) - np.pi
    
    theta_samples.append(thetas)

# Plot bifurcation diagram
plt.figure(figsize=(10, 6))
for i, A_val in enumerate(A_values):
    plt.plot([A_val]*len(theta_samples[i]), theta_samples[i], ',k')

plt.xlabel('Driving Amplitude (A)')
plt.ylabel('Angle (radians)')
plt.title('Bifurcation Diagram')
plt.grid(True)
plt.show()
```

> The diagram shows stable periodic orbits, period doubling bifurcations, and transitions to chaos as \( A \) increases.

---

### Summary

These advanced visualizations help identify and classify dynamic regimes:

- **Phase portraits**: visualize continuous trajectories.
- **Poincaré sections**: reduce dimensionality, reveal structure.
- **Bifurcation diagrams**: track system response to parameter changes.

Together, they provide powerful insight into nonlinear dynamics and chaotic systems.

