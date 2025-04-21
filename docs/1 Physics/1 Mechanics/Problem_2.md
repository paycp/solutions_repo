# Problem 2

## 1. Theoretical Foundation

### Governing Equation of Motion

The motion of a forced damped pendulum is described by the second-order nonlinear differential equation:

\[
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \sin(\theta) = A \cos(\omega t)
\]

Where:  
- \( \theta \) — the angular displacement,  
- \( b \) — the damping coefficient,  
- \( g \) — the gravitational acceleration,  
- \( L \) — the length of the pendulum,  
- \( A \) — the amplitude of the external driving force,  
- \( \omega \) — the driving angular frequency,  
- \( t \) — time.


### Small-Angle Approximation

For small angular displacements (\( \theta \) close to 0), we can use the approximation:

\[
\sin(\theta) \approx \theta
\]

Substituting this into the governing equation simplifies it to:

\[
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \theta = A \cos(\omega t)
\]

This is now a **linear second-order nonhomogeneous differential equation** with constant coefficients.

### Interpretation
- The term \( b\frac{d\theta}{dt} \) represents **energy dissipation** (damping).  
- The term \( \frac{g}{L} \theta \) is the **restoring force** due to gravity.  
- The right-hand side \( A \cos(\omega t) \) models an **external periodic driving force**.

Depending on the parameters \( b \), \( A \), and \( \omega \), the system can exhibit a variety of behaviors, including:  
- **Steady-state oscillations** (harmonic motion),  
- **Resonance phenomena**,  
- **Chaotic dynamics** at larger driving amplitudes and specific frequencies.

### Resonance Conditions

In the absence of damping and at small angles, resonance occurs when the driving frequency \( \omega \) matches the natural frequency of the pendulum:

\[
\omega_0 = \sqrt{\frac{g}{L}}
\]

Under resonance conditions:  
- The amplitude of oscillations grows significantly.  
- Energy input from the external force is maximally efficient.

However, damping and nonlinearity in the full equation modify the resonance behavior, preventing unbounded amplitude growth and introducing complex dynamics.

## 2. Analysis of Dynamics

The behavior of the forced damped pendulum is strongly influenced by three key parameters.

- **Damping coefficient** (\( b \))
  
  * Higher damping leads to quicker energy dissipation, causing oscillations to decay faster.
  * Lower damping allows oscillations to persist and can enable complex dynamics, including chaotic motion.

- **Driving amplitude** (\( A \))
  
  * A small driving amplitude results in regular, predictable oscillations.
  * A larger driving amplitude can push the system into nonlinear and chaotic behavior.

- **Driving frequency** (\( \omega \))
  
  * When the driving frequency approaches the system’s natural frequency (\( \omega_0 \)), resonance occurs, greatly amplifying oscillation amplitudes.
  * Away from resonance, the response is much smaller.

### Transition from Regular to Chaotic Motion

As the driving amplitude \( A \) or the driving frequency \( \omega \) increases, the system exhibits the following transitions:

- **Periodic motion**  
  + Regular, repeating oscillations over time.

- **Quasiperiodic motion**  
  + Oscillations combining two or more frequencies, leading to a non-repeating but structured pattern.

- **Chaotic motion**  
  + Highly sensitive to initial conditions, with irregular, unpredictable behavior.  
  + Characterized by positive Lyapunov exponents and complex structures in phase space.
