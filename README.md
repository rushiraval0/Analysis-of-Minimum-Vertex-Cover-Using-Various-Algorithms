# Optimal Placement of Security Cameras Using Vertex Cover

## Introduction
This project explores the minimum vertex cover problem in graph theory. A vertex cover is a set of vertices such that each edge in the graph has at least one endpoint in this set. Finding the smallest vertex cover is an NP-hard problem. We implemented and analyzed three algorithms to approach this problem:

1. **CNF SAT**: Uses Minisat SAT solver for Boolean satisfiability.
2. **ApproxVC1**: Greedy approach selecting the most connected vertex.
3. **ApproxVC2**: Brute-force approach covering edges without duplicates.

## Solutions

### CNF-SAT
Transforms the graph into a Boolean formula in CNF and uses a SAT solver to find a vertex cover. Key steps:
- Encode graph into CNF format.
- Use SAT solver to find assignments that satisfy the CNF formula.

### ApproxVC1
A greedy algorithm that iteratively selects the vertex with the highest degree, removes it, and adds it to the vertex cover.

### ApproxVC2
A brute-force algorithm that randomly selects edges and adds their vertices to the vertex cover without duplication until all edges are covered.

## Multithreading
To improve performance, the algorithms were executed concurrently using multithreading with the `pthread.h` library in C++.

## Analysis

### Running Time
- **CNF-SAT**: Efficient for small graphs (up to 15 vertices) but exponentially slow for larger graphs.
- **ApproxVC1**: Running time varies but generally increases with the graph size.
- **ApproxVC2**: Linear increase in running time with respect to graph size.

### Approximation Ratio
- **CNF-SAT**: Always finds the optimal solution but impractical for larger graphs.
- **ApproxVC1**: Closest to optimal with a linear approximation ratio.
- **ApproxVC2**: Higher and more variable approximation ratio.

## Conclusion
- **CNF-SAT**: Best for optimal solutions on smaller graphs.
- **ApproxVC1**: Suitable for larger graphs due to polynomial running time and close-to-optimal solutions.
- **ApproxVC2**: Fast but less accurate, useful for quick approximations on larger graphs.
