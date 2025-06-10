# Problem 1

### Motivation

The acceleration of a freely falling object, $g$, is a fundamental physical constant that governs motion near the Earth's surface. A precise value of $g$ is critical in many fields, from satellite dynamics to civil engineering. The simple pendulum provides a classic and accessible experimental method to determine this value, offering a valuable lesson in measurement techniques, data analysis, and the propagation of uncertainties.

### Theoretical Foundation

The period ($T$) of a simple pendulum—the time it takes to complete one full back-and-forth swing—depends on its length ($L$) and the local gravitational acceleration ($g$). For oscillations with a small amplitude, this relationship is accurately described by the formula:

$T = 2\pi \sqrt{\frac{L}{g}}$

By rearranging this equation, we can express $g$ in terms of the measurable quantities $L$ and $T$:

$g = 4\pi^2 \frac{L}{T^2}$

Since all physical measurements have uncertainties, we must calculate how the uncertainties in our measurements of length ($\Delta L$) and period ($\Delta T$) affect the final uncertainty in our result for $g$ ($\Delta g$). The formula for this propagation of uncertainty is:

$\Delta g = g \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2\frac{\Delta T}{T}\right)^2}$

### Simulated Experimental Procedure

We will simulate the steps of a physical experiment, including defining the apparatus parameters and generating a realistic data set for analysis.

#### Setup Parameters

* **Pendulum Length (L):** The measured distance from the fixed pivot point to the center of mass of the pendulum's bob. For this simulation, we'll use a new length.
    * $L = 1.250 \text{ m}$
* **Uncertainty in Length ($\Delta L$):** Determined by the resolution of the measuring tool. Using a standard meter stick with 1 mm divisions (0.001 m), the uncertainty is taken as half the smallest division.
    * $\Delta L = \frac{0.001 \text{ m}}{2} = 0.0005 \text{ m}$

#### Data Collection

To improve accuracy and minimize the effect of reaction time error, we measured the total time for 10 complete oscillations ($T_{10}$). This process was repeated 10 times to create a statistical sample. The following data was generated to simulate these measurements, including small random variations.

**Table 1: Time Measurements for 10 Oscillations ($T_{10}$)**

| Measurement Number (i) | Time $T_{10}$ (s) |
| :--------------------: | :----------------: |
|           1            |       22.45        |
|           2            |       22.29        |
|           3            |       22.51        |
|           4            |       22.40        |
|           5            |       22.58        |
|           6            |       22.33        |
|           7            |       22.48        |
|           8            |       22.61        |
|           9            |       22.39        |
|           10           |       22.42        |

---
### Calculations and Data Analysis

#### 1. Calculating the Period ($T$) and its Uncertainty ($\Delta T$)

* **Mean Time for 10 Oscillations ($\bar{T}_{10}$):**
    $\bar{T}_{10} = \frac{1}{10} \sum_{i=1}^{10} T_{10,i} = \frac{224.46}{10} = 22.446 \text{ s}$

* **Standard Deviation of the Time Measurements ($\sigma_{T_{10}}$):**
    $\sigma_{T_{10}} = \sqrt{\frac{\sum (T_{10,i} - \bar{T}_{10})^2}{n-1}} \approx 0.108 \text{ s}$

* **Uncertainty in the Mean Time (Standard Error) ($\Delta T_{10}$):**
    $\Delta T_{10} = \frac{\sigma_{T_{10}}}{\sqrt{n}} = \frac{0.108}{\sqrt{10}} \approx 0.0341 \text{ s}$

* **Period of a Single Oscillation ($T$):**
    $T = \frac{\bar{T}_{10}}{10} = \frac{22.446}{10} = 2.2446 \text{ s}$

* **Uncertainty in the Period ($\Delta T$):**
    $\Delta T = \frac{\Delta T_{10}}{10} = \frac{0.0341}{10} = 0.00341 \text{ s}$

#### 2. Determining the Value of $g$

We now calculate our experimental value for $g$ using the primary formula:

$g = 4\pi^2 \frac{L}{T^2} = 4\pi^2 \frac{1.250}{(2.2446)^2} \approx 4\pi^2 \frac{1.250}{5.0382} \approx 9.792 \text{ m/s}^2$

#### 3. Propagating the Uncertainty in $g$ ($\Delta g$)

Finally, we calculate the uncertainty in our value for $g$:

$\Delta g = g \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2\frac{\Delta T}{T}\right)^2}$$\Delta g = 9.792 \sqrt{\left(\frac{0.0005}{1.250}\right)^2 + \left(2 \cdot \frac{0.00341}{2.2446}\right)^2}$$\Delta g = 9.792 \sqrt{(0.0004)^2 + (0.00304)^2}$
$\Delta g = 9.792 \sqrt{1.6 \times 10^{-7} + 9.24 \times 10^{-6}} \approx 9.792 \cdot \sqrt{9.40 \times 10^{-6}} \approx 9.792 \cdot 0.00307 \approx 0.030 \text{ m/s}^2$

Rounding the uncertainty to one significant figure and the result accordingly:
$\Delta g \approx 0.03 \text{ m/s}^2$
$g \approx 9.79 \text{ m/s}^2$

**Final Experimental Result:**
$g = (9.79 \pm 0.03) \text{ m/s}^2$

---
### Analysis

#### 1. Comparison with the Standard Value

The accepted standard value for gravitational acceleration is $g_{std} = 9.81$ m/s². Our experimental result gives a confidence interval of $[9.79 - 0.03, 9.79 + 0.03] = [9.76, 9.82]$ m/s².

The standard value of $9.81$ m/s² falls just within this experimental range. This indicates a successful experiment with a result that is consistent with the accepted value, within the calculated margin of error.

#### 2. Discussion of Uncertainty Sources

* **Dominant Source of Uncertainty:** Let's compare the relative contributions to the final uncertainty.
    * Contribution from length: $(\Delta L / L) \approx 0.04\%$
    * Contribution from period: $2 \cdot (\Delta T / T) \approx 0.30\%$
    This comparison clearly demonstrates that the random error in the measurement of the period is the dominant source of uncertainty, contributing much more significantly to the final uncertainty $\Delta g$ than the precision of the length measurement.

* **Experimental Limitations and Potential Systematic Errors:**
    Even though our result is consistent, it's important to consider factors that could introduce systematic errors, which are not captured by the statistical uncertainty $\Delta g$.
    1.  **The Small-Angle Approximation:** The period formula is an approximation. If the initial angle of release was consistently larger than $15^\circ$, the actual period would be slightly longer than the formula predicts, causing our calculated $g$ to be an underestimate of the true value.
    2.  **Air Resistance:** Air drag acts as a damping force on the pendulum, which can slightly increase the period of oscillation. This would also lead to a calculated value of $g$ that is lower than the actual value.
    3.  **Physical Pendulum vs. Simple Pendulum:** The model assumes a point-like mass (bob) on a massless string. In reality, the string has mass and the bob has a non-zero radius. Treating this system as an ideal simple pendulum introduces a small systematic error.

### Deliverables

1.  **Tabulated Data:** The simulated measurement data is presented in Table 1.
2.  **Calculated Values:**
    * $L = 1.250 \text{ m}$
    * $\Delta L = 0.0005 \text{ m}$
    * $\bar{T}_{10} = 22.446 \text{ s}$
    * $\Delta T = 0.00341 \text{ s}$
    * **$g_{exp} = 9.79 \text{ m/s}^2$**
    * **$\Delta g = 0.03 \text{ m/s}^2$**

3.  **Discussion of Uncertainty and Results:** This is provided in the Analysis section above. The results are consistent with the accepted value of $g$, and the primary source of random error was identified as the timing measurement.