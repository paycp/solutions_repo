# Problem 1: Resistor Circuit Analysis

## Problem Statement

For the circuit shown in the figure, find the **equivalent resistance** of the circuit and the **current flowing through the resistor $R_5$**.

![Circuit Diagram](https://dchorazkiewicz.github.io/Mathematics_Physics_Lectures/Physics/Exercises_for_Students/img/dch_ex_fis_pr_1_1.png)

**Given values:**
* Voltage source: $V = 12 \, \text{V}$
* Resistors:
    * $R_1 = 10 \, \Omega$
    * $R_2 = 20 \, \Omega$
    * $R_3 = 30 \, \Omega$
    * $R_4 = 40 \, \Omega$
    * $R_5 = 50 \, \Omega$
    * $R_6 = 60 \, \Omega$
    * $R_7 = 70 \, \Omega$

---

## Solution

The solution is divided into two parts:
1.  Calculating the total equivalent resistance ($R_{eq}$) of the circuit.
2.  Calculating the current ($I_5$) flowing through resistor $R_5$.

### 1. Equivalent Resistance ($R_{eq}$)

To find the total equivalent resistance, we will simplify the circuit step-by-step.

**Step 1: Simplify parallel resistors $R_3$ and $R_4$**

Resistors $R_3$ and $R_4$ are in parallel. Their equivalent resistance, $R_{34}$, is:
$$ R_{34} = \frac{R_3 \cdot R_4}{R_3 + R_4} = \frac{30 \, \Omega \cdot 40 \, \Omega}{30 \, \Omega + 40 \, \Omega} = \frac{1200}{70} \, \Omega \approx 17.14 \, \Omega $$

**Step 2: Simplify parallel resistors $R_6$ and $R_7$**

Similarly, resistors $R_6$ and $R_7$ are in parallel. Their equivalent resistance, $R_{67}$, is:
$$ R_{67} = \frac{R_6 \cdot R_7}{R_6 + R_7} = \frac{60 \, \Omega \cdot 70 \, \Omega}{60 \, \Omega + 70 \, \Omega} = \frac{4200}{130} \, \Omega \approx 32.31 \, \Omega $$

**Step 3: Calculate the resistance of the two main branches**

Now, we calculate the total resistance for the two main branches that are in parallel.

* **Branch A** contains $R_2$ in series with $R_{34}$:
    $$ R_A = R_2 + R_{34} = 20 \, \Omega + 17.14 \, \Omega = 37.14 \, \Omega $$
* **Branch B** contains $R_5$ in series with $R_{67}$:
    $$ R_B = R_5 + R_{67} = 50 \, \Omega + 32.31 \, \Omega = 82.31 \, \Omega $$

**Step 4: Combine the main parallel branches**

The equivalent resistance of the two parallel branches (Branch A and Branch B), let's call it $R_{AB}$, is:
$$ R_{AB} = \frac{R_A \cdot R_B}{R_A + R_B} = \frac{37.14 \, \Omega \cdot 82.31 \, \Omega}{37.14 \, \Omega + 82.31 \, \Omega} = \frac{3057.1}{119.45} \, \Omega \approx 25.59 \, \Omega $$

**Step 5: Calculate the total equivalent resistance**

Finally, the total equivalent resistance of the circuit, $R_{eq}$, is the sum of $R_1$ and $R_{AB}$, as they are in series.
$$ R_{eq} = R_1 + R_{AB} = 10 \, \Omega + 25.59 \, \Omega = 35.59 \, \Omega $$

**The equivalent resistance of the circuit is approximately $35.6 \, \Omega$.**

---

### 2. Current Through Resistor $R_5$

To find the current through $R_5$, we first need the total current from the voltage source.

**Step 1: Calculate the total current**

Using Ohm's Law, the total current $I_{total}$ flowing from the source is:
$$ I_{total} = \frac{V}{R_{eq}} = \frac{12 \, \text{V}}{35.59 \, \Omega} \approx 0.337 \, \text{A} $$

**Step 2: Calculate the voltage across the parallel branches**

The voltage drop across the entire parallel section (containing branches A and B) is $V_{AB}$. This voltage is the product of the total current and the equivalent resistance of the parallel section, $R_{AB}$.
$$ V_{AB} = I_{total} \cdot R_{AB} = 0.337 \, \text{A} \cdot 25.59 \, \Omega \approx 8.62 \, \text{V} $$

**Step 3: Calculate the current through Branch B**

The voltage across Branch B is $V_{AB}$. The current flowing through Branch B, $I_B$, can be found using Ohm's law:
$$ I_B = \frac{V_{AB}}{R_B} = \frac{8.62 \, \text{V}}{82.31 \, \Omega} \approx 0.105 \, \text{A} $$

Since resistor $R_5$ is in series within Branch B, the current flowing through it, $I_5$, is the same as the current flowing through Branch B.

$$ I_5 = I_B \approx 0.105 \, \text{A} $$

**The current flowing through resistor $R_5$ is approximately $0.105 \, \text{A}$ or $105 \, \text{mA}$.**