# cs3230-cheatsheet

CS3230 AY2025/26 Sem 2 (wip) (use at own risk)

disclaimer: AI was used in generating some parts of the cheatsheet

## Index of problems in this cheatsheet

1. Proof of correctness
   1. Iterative
      1. Fibonacci
      2. Selection Sort
      3. Weighted Directed Graphs (Dijkstra)
      4. Insertion Sort
   2. Recursive (Divide and Conquer)
      1. Searching in a sorted array
      2. Exponentiation
      3. StoogeSort
      4. PeakFinding
      5. Karatsuba Multiplication
      6. H-Index
      7. Ball Weighing Problem
2. Sorting
   1. Comparison-Based
      1. Merge k-sorted Arrays
      2. Quick Sort
   2. Non-Comparison
      1. Counting Sort
      2. Radix Sort
3. Randomized Algorithms
   1. Verification of Matrix Multiplication (Freivald)
   2. Coupon Collector / Balls and Bins
   3. Hashing (expected number of items per bucket)
   4. Randomized Quick Sort
   5. Randomized Equality Testing (Communication Protocol)
   6. Random Graph Partition (Max-Cut)
   7. Random Walk on 4-Point Circle
   8. Independent Set Lower Bound
   9. Expected Input Length (Weighted Geometric Series)
4. Dynamic Programming
   1. Fibonacci
   2. Longest Common Subsequence
   3. Knapsack
   4. Coin Change
   5. Convex Polygon Triangulation
   6. Min Difference |Sx - 2Sy| (Subset sum variant)
   7. Max Sum, No Two adjacent (House Robber)
   8. Knapsack with Item Count Cap
5. Greedy
   1. Semi-Fractional Knapsack
   2. Minimum Spanning Trees
   3. Huffman Code
   4. Burning CDs
   5. Activity Selection
6. Amortized Analysis
   1. Binary Counter (k-bit increment)
   2. Queue
   3. Dynamic Table
   4. Union-Find (DSU)
7. Reductions and Intractability I
   1. Matrix Squaring $\leq_p$ Matrix Multiplication
   2. 3-SAT $\leq_p$ Independent Set
   3. Independent Set $\leq_p$ Vertex-Cover
   4. Vertex-Cover $\leq_p$ Set-Cover
   5. Partition $\leq_p$ Knapsack
   6. Partition $\nleq_p$ Ball-Partition
   7. Hamiltonian Cycle $\leq_p$ Travelling Salesman Problem
8. Reductions and Intractability II
   1. Subset-Sum is NP-Complete (3-SAT $\leq_P$ Subset-Sum)
   2. Hamiltonian Cycle is NP-Complete (Directed Hamiltonian Cycle $\leq_P$ Ham-Cycle)
   3. Clique is NP-Complete (Independent-Set $\leq_P$ Clique)
   4. Find-Family is NP-Complete (Clique $\leq_P$ Find-Family)
   5. Directed Hamiltonian Cycle is NP-Complete (3-SAT $\leq_P$ Directed-Ham-Cycle)
   6. Fantastic-Half is NP-Complete (Partition-Special $\leq_P$ Fantastic-Half)
   7. Partition-Special is NP-Complete (Partition $\leq_P$ Partition-Special)
   8. Subset-Sum is NP-Complete (3-SAT $\leq_P$ Subset-Sum)
   9. Subgraph Isomorphism is NP-Complete
   10. Half-Clique is NP-Complete
9. Approximation using Greedy
   1. Set-Cover
   2. Matching (Maximal Matching)
   3. Vertex-Cover
