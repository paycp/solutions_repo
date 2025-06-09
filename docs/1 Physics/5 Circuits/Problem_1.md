# Equivalent Resistance Using Graph Theory

## Algorithm Description

To calculate the equivalent resistance of a circuit using graph theory, we treat the electrical circuit as a weighted undirected graph:

- **Nodes** represent electrical junctions.
- **Edges** represent resistors, with weights equal to resistance in ohms (Ω).

The goal is to reduce this graph step-by-step until a single edge remains, representing the total equivalent resistance between two terminals.

---

## Step-by-Step Algorithm

1. **Input**: Circuit as a weighted graph.
2. **While simplification is possible**:
   - **Find parallel resistors**: multiple edges between the same two nodes.
     - Replace them with one edge using:
       \[
       \frac{1}{R_{\text{eq}}} = \sum \frac{1}{R_i}
       \]
   - **Find series resistors**: nodes connected to exactly two neighbors, not a terminal.
     - Collapse the node and merge the two edges into one:
       \[
       R_{\text{eq}} = R_1 + R_2
       \]
3. **Repeat** the process until only one edge remains between the start and end nodes.
4. **Return** the final resistance value.

---

## Pseudocode

```plaintext
function calculate_equivalent_resistance(graph):
    while graph can be simplified:
        for each pair of nodes (u, v):
            if multiple edges exist between u and v:
                R_parallel = 1 / sum(1 / R for each edge between u and v)
                remove all edges between u and v
                add edge (u, v) with resistance R_parallel

        for each node n in graph:
            if degree(n) == 2 and n is not input/output terminal:
                neighbors = [a, b]
                R1 = resistance between a and n
                R2 = resistance between n and b
                R_total = R1 + R2
                remove node n and its edges
                add edge (a, b) with resistance R_total

    return resistance of the final edge
```