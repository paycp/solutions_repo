## Equivalent Resistance Using Graph Theory

### Motivation

Calculating the equivalent resistance is a fundamental task in electrical circuits. While manual methods like series-parallel reduction work for small circuits, they become impractical for complex networks. Graph theory offers a powerful and systematic alternative.

By modeling the circuit as a graph:

- **Nodes** represent junctions
- **Edges** represent resistors, with edge weights as resistance values

We can iteratively reduce the graph until only a single equivalent resistance remains between the input and output nodes.

---

### Algorithm Overview

1. **Input**: A weighted graph representing the circuit  
2. **Repeat** until no further simplification is possible:  
    - **Parallel reduction**: If multiple edges exist between two nodes, replace them with a single edge:

\[
R_{\text{eq}} = \left( \sum_i \frac{1}{R_i} \right)^{-1}
\]

    - **Series reduction**: If a node connects to exactly two others (and is not input/output), merge it:

\[
R_{\text{eq}} = R_1 + R_2
\]

3. **Output**: Final edge’s resistance between the input and output node.


---

### Pseudocode

```
function calculate_equivalent_resistance(graph):
    while graph can be simplified:
        for each pair of nodes (u, v):
            if multiple edges exist between (u, v):  # Parallel
                R_parallel = 1 / sum(1 / R for each edge between u and v)
                remove all edges between u and v
                add new edge (u, v) with R_parallel

        for each node n in graph:
            if degree(n) == 2 and n is not input/output:  # Series
                neighbors = [a, b]
                R1 = resistance between a and n
                R2 = resistance between n and b
                R_total = R1 + R2
                remove node n and its edges
                add edge (a, b) with R_total

    return resistance of the only remaining edge
```

---

### Nested Combinations

This algorithm automatically handles nested combinations. By repeatedly applying reduction rules (parallel first, then series), deeply nested circuits are simplified progressively.

---

### Next Steps

- Implement this algorithm in Python (e.g., using `networkx`)
- Visualize example graphs before and after reduction
- Test with simple, nested, and cyclic circuits

---