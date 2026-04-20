#### Index of problems in this cheatsheet
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

#### 0. Math and Probability
##### **Exponentials**
*   $a^{-1} = \frac{1}{a}$
*   $(a^m)^n = a^{mn}$
*   $a^m a^n = a^{m+n}$
*   $e^x \ge 1 + x$
##### **Logarithms**
*   **Binary log:** $\log n = \log_2 n$
*   **Natural log:** $\ln n = \log_e n$
*   **Exponentiation:** $\log^k n = (\log n)^k$
*   **Composition:** $\log \log n = \log(\log n)$
*   $a = b^{\log_b a}$
*   $\log_c (ab) = \log_c a + \log_c b$
*   $\log_b a^c = c \log_b a$
*   **Change of Base Formula:** $\log_b a = \frac{\log_c a}{\log_c b}$
*   $\log_b (1/a) = -\log_b a$
*   $\log_b a = \frac{1}{\log_a b}$
*   $a^{\log_b c} = c^{\log_b a}$
* $a^b=e^{b\ln{a}}$
##### **Stirling's approximation**
- Estimate for the factorial function
- $n! = \sqrt{2\pi n} \left(\frac{n}{e}\right)^n (1 + O(1/n))$
- $\log(n!) \in \Theta(n \log n)$
##### **Summation and series**
- Finite GP: $\sum_{k=0}^{n} x^k = 1 + x + x^2 + \cdots + x^n = \frac{x^{n+1} - 1}{x - 1}$
- Infinite GP: $\sum_{k=0}^{\infty} x^k = \frac{1}{1 - x}$
- AP: $\sum_{k=0}^{n} k = 1 + 2 + \cdots + n = \frac{n(n + 1)}{2}$, $\Theta(n^2)$
- Finite AP term: $T_k = a + (k-1)d$ 
- Finite AP sum: $S_n = \frac{n}{2}(2a + (n - 1)d)$
- Finite GP term: $T_k = ar^k$
- Finite GP sum: $S_n = \frac{a(1 -  r^n)}{1-r}$
- Weighted Geometric Series: $\Sigma_{i=0}^\infty ir^i = \frac{r}{(1-r)^2}, |r| < 1$
- Harmonic series: $\sum_{i=1}^{n} \frac{1}{i} = ln(n)+\gamma + o(1) \in \Theta(logn)$
- Reciprocal Log: $\sum_{k=2}^{n} \frac{1}{logk} = \Theta(n / logn)$ 
- Harmonic over log: $\sum_{k=2}^{n} \frac{1}{klogk} = \Theta(loglogn)$
- Squared log: $\sum_{k=2}^{n} \frac{1}{k(logk)^p}$ 
	- $p > 1$: $\Theta (1)$
	- $p = 1$: $\Theta (loglogn)$
	- $0 < p < 1$: $\Theta((logn)^{1-p})$
- Derivative of Geometric Series:
	- $\sum^{\infty}_{i=0}x^i = 1/(1-x)$
	- Differentiate both sides w.r.t $x$: $\sum^{\infty}_{i=0}i \cdot x^{i-1} = 1 / (1-x)^2$
	- Multiply both sides by $x$: $\sum^{\infty}_{i=0}i \cdot x^i = x / (1 -x)^2$
##### **Generalised Harmonic Series**
- $\sum_{i=1}^{n} \frac{1}{i^p}$
	- $p > 1$: $\Theta (1)$
	- $p = 1$: $\Theta (logn)$
	- $0 < p < 1$: $\Theta(n^{1-p})$
##### **L'Hospital's Rule**
- technique for evaluating indeterminate limits
- if $\lim_{x\to\infty} f(x) = \infty$ and $\lim_{x\to\infty} g(x) = \infty$, then:
	- $\lim_{x\to\infty} \frac{f(x)}{g(x)} = \lim_{x\to\infty} \frac{f'(x)}{g'(x)}$
- where $f'(x)$ and $g'(x)$ are the derivatives of $f(x)$ and $g(x)$.
- $n \ln n \in o(n^2)$, meaning $n \ln n$ grows strictly slower than $n^2$
##### **Useful inequalities**
- $1 + x \leq e^x$
##### **Probability Distribution**
A probability distribution $\Pr()$ is a mapping from events to real numbers that satisfies three axioms:
1.  **Non-x:** $\Pr(A) \ge 0$ for all events $A$.
2.  **Normalization:** $\Pr(S) = 1$.
3.  **Additivity:** $\Pr(A \cup B) = \Pr(A) + \Pr(B)$ for mutually exclusive (disjoint) events $A$ and $B$.
##### **General Probability Rules**
* **Inclusion-Exclusion Principle (for two events):** $\Pr(A \cup B) = \Pr(A) + \Pr(B) - \Pr(A \cap B)$.
* **Independence:** Two events $A$ and $B$ are independent if and only if $\Pr(A \cap B) = \Pr(A) \cdot \Pr(B)$.
##### **Conditional Probability**
The conditional probability of event $A$ given event $B$ (where $\Pr(B) \ne 0$) is defined as:
- $\Pr(A|B) = \frac{\Pr(A \cap B)}{\Pr(B)}$
##### **Bayes' Theorem**
$\Pr(A|B) = \frac{\Pr(A) \Pr(B|A)}{\Pr(B)}$

The denominator $\Pr(B)$ can be expanded using the Law of Total Probability (for an event $A$ and its complement $\bar{A}$):
$$\Pr(A|B) = \frac{\Pr(A) \cdot \Pr(B|A)}{\Pr(A) \cdot \Pr(B|A) + \Pr(\bar{A}) \cdot \Pr(B|\bar{A})}$$
##### **Random Variable**
A function that maps the outcomes in the sample space ($S$) to real numbers.
* The function $f(x) = \Pr(X = x)$ is the **probability density function** (or probability mass function for discrete variables) of $X$.
##### **Expectation (Mean)**
The expectation or mean of a random variable $X$ is the weighted average of all possible values of $X$:
- $E(X) = \sum_{x} x \cdot \Pr(X = x)$
##### **Linearity of Expectation**
Expectation is a linear operator:
*   $E(X + Y) = E(X) + E(Y)$
*   $E(aX) = a E(X)$
*   **For independent variables:** $E(XY) = E(X) \cdot E(Y)$
##### **Event Operations**
1. $A \cap A' = \emptyset$
2. $A \cap \emptyset = \emptyset$
3. $A \cup A' = S$
4. $(A')' = A$
5. $A \cup (B \cap C) = (A \cup B) \cap (A \cup C)$
6. $A \cap (B \cup C) = (A \cap B) \cup (A \cap C)$
7. $A \cup B = A \cup (B \cap A')$
8. $A = (A \cap B) \cup (A \cap B')$
9. $(A_1 \cup A_2 \cup \dots \cup A_n)' = A_1' \cap A_2' \cap \dots \cap A_n'$
10. $(A \cup B)' = A' \cap B'$
11. $(A_1 \cap A_2 \cap \dots \cap A_n)' = A_1' \cup A_2' \cup \dots \cup A_n'$
12. $(A \cap B)' = A' \cup B'$
##### **Permutations and Combinations**
- $P^n_r=\frac{n!}{(n-r)!}=n(n-1)(n-2)\dots (n-(r-1))$ 
- $n \choose {r}$ = $\frac{n!}{r!(n-r)!}$
- $n\choose r$ = $n \choose (n-r)$ 
##### **Probability**
- $P(A)=P(A\cap{B})+P(A\cap \overline{B})$  
- $P(A_1 \cap A_2 \cap \dots \cap A_n) = P(A_1) + P(A_2) + \dots + P(A_n)$, if $A_i \cap A_j = \emptyset$ for any $i \neq j$
- $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ ------- Principle of Inclusion and Exclusion
- If $A \subset B$, then $P(A) \leq P(B)$ 
- $A$ and $B$ are independent $\iff$ $P(A \cap B) = P(A)P(B)$ ------- $i.e$ $A\perp B$   
- Suppose P(A) > 0, P(B) > 0. If A and B are independent, then A and B are not mutually exclusive.
- Suppose P(A) > 0, P(B) > 0. If A and B are mutually exclusive, then A and B are dependent. 
- $S$ and $\emptyset$ are independent of any other event.
- If A ⊥ B, then A ⊥ B′, A′ ⊥ B, and A′ ⊥ B′.
- $A \perp B \iff P(B | A) = \frac{P(A \cap B)}{P(A)} = \frac{P(A)P(B)}{P(A)} = P(B)$, if $P(A) \neq 0$
- Contained: $A\subset{B}$ 
- Equivalent: $A=B$
- Mutually Exclusive: $A\cap{B}=\emptyset$ 
- Law of Total Probability: $P(B) = \sum^n_{i=1}P(B\cap A_i)=\sum^n_{i=1}P(A_i)P(B|A_i)$ 
- $P(A|B)=\frac{P({A}\cap{B})}{P(B)}$ 
- $P(A|B) = \frac{P(B|A)P(A)}{P(B)}$
- $P(A_k|B)=\frac{P(A_k)P(B|A_k)}{\sum^n_{i=1}P(A_i)P(B|A_k)}$
- $P(A|B)=1-P(\overline{A}|B)$ 
- $P(A)=P(A|B)P(B)+P(A|\overline{B})P(\overline{B})$ 
##### **Bernoulli Trials**
A **Bernoulli Trial** is an experiment with exactly two outcomes: success (with probability $p$) and failure (with probability $q = 1 - p$).
##### **Geometric Distribution**
If $X$ is the number of independent Bernoulli trials needed to obtain the first success:
*   **Probability:** $\Pr(X = k) = q^{k-1} p$
*   **Expectation:** $E(X) = \frac{1}{p}$
##### **Binomial Distribution**
If $X$ is the number of successes in $n$ independent Bernoulli trials:
*   **Probability:** $\Pr(X = k) = \binom{n}{k} p^k q^{n-k}$
---
#### 1. Asymptotic Analysis
##### Limits
**Big-O (g is upper bound of f)**: $f \in O(g)$
- Definition: $\exists c > 0 \land n_0 > 0 \space \text{s.t} \space \forall n \geq n_0: 0 \leq f(n) \leq c \cdot g(n)$
- Theorem+Proof: 
	1. $lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} < \infty$
	2. $lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} = L, L \in \mathbb{R}$
	3. $\forall \epsilon > 0, \exists n_0 \space \text{s.t} \space \forall n \geq n_0, \frac{f(n)}{g(n)} - L < \epsilon$

**$\ohm$ (g is lower bound of f):** $f \in \ohm (g(n))$
- Definition: $\exists c > 0 \land n_0 > 0 \space \text{s.t} \space \forall n \geq n_0: 0 \leq c \cdot g(n) \leq f(n)$ 
- Theorem+Proof:
	1. $lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} > 0$
	2. $lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} = L, L > 0$
	3. $lim_{n\rightarrow \infty} \frac{g(n)}{f(n)} = \frac{1}{L}$
	4. $lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} < \infty$

$\theta$ **(g is tight bound of f)**: $f \in \theta (g(n))$
- Definition: $\exists c1, c2 > 0 \land n_0 > 0 \space \text{s.t} \space \forall n \geq n_0: 0 \leq c_1 \cdot g(n) \leq f(n) \leq c2 \cdot g(n)$
- Theorem+Proof:
	1. $0 < lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} < \infty$
	2. $\theta = O \cap \ohm$

**Little-o (g is strict upper bound of f)**: $f \in o(g(n))$
- Definition: $\forall c > 0, \exists n_0 > 0 \space \text{s.t} \space \forall n \geq n_0: 0 \leq f(n)  < c \cdot g(n)$
- Theorem+Proof: 
	1. $lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} = 0$
	2. $\forall \epsilon > 0,  \exists n_0 > 0 \space \text{s.t} \space \forall n \geq n_0: \frac{f(n)}{g(n)} < \epsilon$

$\omega$ **(g is strict lower bound of f)**: $f \in \omega(g(n))$
- Definition: $\forall c > 0, \exists n_0 > 0 \space \text{s.t} \space \forall n \geq n_0: 0 \leq c \cdot g(n) < f(n)$
- Theorem+Proof:
	1. $lim_{n\rightarrow \infty} \frac{f(n)}{g(n)} = \infty$
	2. $\forall M > 0, \exists n_0 \space \text{s.t} \space \forall n \geq n_0: \frac{f(n)}{g(n)} > M$

##### **Properties**
**1. Reflexivity**
- $f(n) \in O(f(n))$
	- Choose c = 1
	- $\forall n, f(n) \leq 1 \cdot f(n)$
- $f(n) \in \ohm(f(n))$
	- Choose c = 1
	- $\forall n, f(n) \geq 1 \cdot f(n)$
- $f(n) \in \theta(f(n))$
	- Chose c1 = c2 = 1

**2. Transitivity**
- $f(n) \in O(g(n)) \land g(n) \in O(h(n)) \implies f(n) \in O(h(n))$
	- $f(n) \in O(g(n)) \Rightarrow f(n) \le c_1 g(n)$
	- $g(n) \in O(h(n)) \Rightarrow g(n) \le c_2 h(n)$
	- $f(n) \leq c_1g(n) \leq c_1c_2h(n)$
	- Let c = c1c2
- $f(n) \in \ohm(g(n)) \land g(n) \in \ohm(h(n)) \implies f(n) \in \ohm(h(n))$
	- $f(n) \geq c_1g(n) \land g(n) \geq c_2h(n)$
	- $f(n) \geq c_1c_2h(n)$
- $f(n) \in \theta(g(n)) \land g(n) \in \theta(h(n)) \implies f(n) \in \theta(h(n))$
	- Prove by transitivity of $O$ and $\ohm$
- $f(n) \in o(g(n)) \land g(n) \in o(h(n)) \implies f(n) \in o(h(n))$
	- $f(n) \in o(g(n)) \implies \forall \epsilon > 0, f(n) \leq \epsilon g(n)$
	- $g(n) \in o(h(n)) \implies \forall \delta > 0, g(n) \leq \delta h(n)$
	- Choose $\epsilon = \sqrt{\eta}$, $\delta = \sqrt{\eta}$
	- $f(n) \leq \sqrt{\eta}g(n) \leq \eta h(n)$
- $f(n) \in \omega(g(n)) \land g(n) \in \omega(h(n)) \implies f(n) \in \omega(h(n))$
	- $f(n) \geq c_1g(n), g(n) \geq c_2 h(n)$
	- $f(n) \geq c_1c_2h(n)$

**3. Symmetry**
- $f(n) \in \theta(g(n)) \iff g(n) \in \theta(f(n))$
	- From definition: $c_1g(n) \leq f(n) \leq c_2g(n)$
	- $\frac{1}{c_2}f(n) \leq g(n) \leq \frac{1}{c_1}f(n)$

**4. Complementarity**
- $f(n) \in O(g(n)) \iff g(n) \in \ohm(f(n))$
	- $f(n) \leq cg(n) \iff g(n) \geq \frac{1}{c}f(n)$
- $f(n) \in o(g(n)) \iff g(n) \in \omega(f(n))$
	- $\forall \epsilon > 0, f(n) \leq \epsilon g(n) \iff \forall c > 0, g(n) \geq cf(n)$
	- (choose c = 1/$\epsilon$)

##### **Quick Facts**
**1) Poly-log vs Poly**
- $(\log n)^{100} \in o(n^{0.1})$: poly-log is always smaller than poly
- $(\log n)^{\log n} \in \omega(n^{100})$: $(\log n)^{\log n} = 2^{\log\log n \cdot \log n} = n^{\log\log n}$, larger than $n^{100}$
- $n^{0.001} \in \omega((\log n)^{1000})$: any positive poly exponent beats any poly-log
- $\log^2 n \in o(n^\epsilon)$ for any $\epsilon > 0$: poly-log always loses to any poly

**2) Exponential identities and conversions**
- $n^{1/\log n} = 2$: since $n = 2^{\log n}$, $n^{1/\log n} = 2^{\log n / \log n} = 2$. Constant, not growing.
- $2^{2\log n} = n^2$: $2^{2\log n} = (2^{\log n})^2 = n^2$
- $n^{\log k} = k^{\log n}$: both equal $2^{\log n \cdot \log k}$
- $2^{\log^2 n} = n^{\log n}$: $2^{\log^2 n} = (2^{\log n})^{\log n} = n^{\log n}$

**3) Sub-exponential and super-polynomial**
- $2^{\sqrt{n}} \in \omega(n^{100})$: $2^{\sqrt{n}} = n^{\sqrt{n}/\log n}$ and $\sqrt{n}/\log n \to \infty$
- $2^{\sqrt{n}} \in o(2^n)$: compare exponents $\sqrt{n} < n$
- $2^{\log^2 n} \in \omega(n^{100})$: equals $n^{\log n}$, exponent grows past 100
- $2^{\log^2 n} \in o(2^n)$: $\log^2 n \in o(n)$

**4) Exponential comparisons**
- $2^n \in \omega(n^c)$ for any constant $c$: exponential always dominates polynomial
- $2^n \in o(3^n)$: $(2/3)^n \to 0$, smaller base loses
- $2^{2n} \in \omega(2^n)$: $2^{2n} = (2^n)^2$, ratio $= 2^n \to \infty$. Constant factor in exponent matters.
- $2^{n+100} \in \Theta(2^n)$: additive constant in exponent is just constant factor $2^{100}$. Does not matter.
- $n \cdot 2^n \in \omega(2^n)$: polynomial factor in front is **not** absorbed. Ratio $= n \to \infty$.

**5) Factorial**
- $n! \in \omega(2^n)$: by Stirling, $n! \approx (n/e)^n$, $(n/2e)^n \to \infty$
- $n! \in o(n^n)$: $n! = 1 \cdot 2 \cdots n < n^n$
- $\log(n!) \in \Theta(n \log n)$: Stirling
- $(\log n)! \in \omega(n^{10})$: $(\log n)! \approx (\log n / e)^{\log n} = n^{\log(\log n / e)} = n^{\log\log n - \log e}$, exponent unbounded

**6) Tricky super-polynomial comparisons**
- $(\log n)^{\log\log n} \in o((\log n)^{\log n})$: same base, compare exponents $\log\log n < \log n$
- $(\log n)^{\log n} \in o(n^{\log n})$: same exponent, compare bases $\log n < n$
- $n^{\log\log n} \in o(n^{\log n})$: same base, compare exponents $\log\log n < \log n$
- $n^{\log\log n} \in \omega(n^{100})$ but $n^{\log\log n} \in o(2^n)$: sits between polynomial and exponential

**7) Common mistakes**
- $2^{n+1} \in \Theta(2^n)$: yes, just a factor of 2. But $2^{2n} \notin \Theta(2^n)$: that is squaring, not doubling.
- $\log(n^2) = 2\log n \in \Theta(\log n)$: constant factor inside log exponent does not change asymptotic class
- $\log(2^n) = n \neq \log n$: do not confuse $\log$ of exponential with $\log$ of polynomial
- $(\log n)^2 \neq \log(n^2)$: $(\log n)^2 = \log^2 n$ vs $\log(n^2) = 2\log n$. Very different growth.

---
#### 2. Recurrences and Master Theorem
**Remarks**:
- If $f(n) \in O(n)$, then there exists two constant $c > 0$ and $n_0 > 0$ such that $f(n) \leq cn$ if $n \geq n_0$
	- For **upper bound** calculation, we can replace $\theta(n)$ with $cn$ 
- If $f(n) \in \Omega(n)$, then there exists two constant $c > 0$ and $n_0 > 0$ such that $f(n) \geq cn$ if $n \geq n_0$
	- For **lower bound** calculation, we can replace $\theta(n)$ with $cn$ 
##### **(1) Telescoping Series**
- Find a way to cancel out each other
- e.g $T(n)/n = \frac{2}{n}T(\frac{n}{2}) + 1 = T(\frac{n}{2})/\frac{n}{2} + 1$ 

##### **(2) Substitution Method**
- Guess a solution, then verify by induction
##### **(3) Recursion Tree**
- Find how many levels and leaves
##### **(4) Master Theorem**
- Generic form: $T(n) = aT(n / b) + f(n)$
	- $a \geq 1$
	- $b \geq 1$
	- $f(n) \in \Omega(1)$
- Classify the work into two types and compare costs
	- Splitting/combining: $f(n)$ ==> dominant term
	- Solving base cases: Cost is linear in the **number of leaves** = $n^d$ 
- Number of leaves = $n^d$ where $d = log_ba$ is the **critical exponent**
- Recursion Tree:
	- Tree height: $log_bn$
	- Number of children of a node: $a$
	- Number of leaves: $a^{log_bn} = n^{log_ba} = n^d$
- **Case 1**: $f(n) \in O(n^{d-\epsilon})$ for some constant $\epsilon > 0$
	- Work done at leaves dominates
	- Ans: $T(n) \in \theta(n^d)$
- **Case 2**: $f(n) \in \theta(n^dlog^kn)$ for some constant $k \geq 0$ 
	- Balanced contribution at all levels
	- Ans: $T(n) \in \theta(n^dlog^{k+1}n)$ 
- **Case 3**: $f(n) \in \Omega(n^{d+\epsilon})$ for some constant $\epsilon > 0$ 
	- $af(n/b) \leq cf(n)$ for some constant $c < 1$ (regularity condition)
	- Work done at root dominates
	- Ans: $T(n) \in \theta(f(n))$
---
#### 3. Proof of correctness
##### **Iterative algorithm**
1. Loop invariant: Induction hypothesis
2. Initialisation: Base case
3. Maintenance: Inductive step
4. Termination: Proof by induction implies the correctness of the algo
###### **Fibonacci**
> [!PROOF]
> 1. Loop invariant: At the start of iteration `i`: `prev2 = Fib(i - 2), prev1 = Fib(i - 1)`
> 2. Initialisation: `i = 2: prev2 = Fib(0) = 0, prev1 = Fib(1) = 1`
> 3. Maintenance: Suppose at iteration `i`, `prev2 = Fib(i - 2), prev1 = Fib(i - 1)`, then at end of the iteration, `prev2 = Fib(i - 1), prev1 = Fib(i)`
> 4. Termination: Algorithm returns `Fib(n)`
###### **Selection sort**
> [!proof]
> 1. Loop invariant: $A[1..j-1]$ is sorted and ($x \leq y$ for all $x \in A[1..j-1]$ and $y \in A[j..n]$)
> 2. Initialisation: True because nothing in LHS
> 3. Maintenance: Take new element from $A[j..n]$ and swap, invariant maintained
> 4. Termination: New element inserted is bigger than that already inserted, and add this to the end. Thus it's sorted
###### **Weighted Directed Graphs**
> [!proof]
> **Definitions**
> 1. $s$: Source vertex
> 2. $R$: Set of already correct computed distances
> 3. $dist(u, v)$: Distance from $u$ to $v$
> 4. $w(u, v)$: Edge cost from $u$ to $v$
> 5. $V$: Set of all vertices
> 6. $D_v$: Set of all possible path distances from $s$ to $v$ 
> 	1. i.e $D_v = \{\forall u \in R : d(u) + w(u, v)\}$
> 7. $d(v)$: $min(D_v)$
> 
> **Algorithm**
> 1. Base case: $dist(s,s) = 0$, $R = \{s\}$
> 2. Loop: While $R \neq V$:
> 	1. Select $v \in V$ such that $v$ is not in $R$ and $v$ minimises $D_v$
> 	2. Update $d(v) = min(D_v)$
> 	3. Add $v$ to $R$
> 
> **Loop invariant**: At the start of every iteration, $\forall u \in R, dist(s, v) = min(D_v)$
> 
> **Proof of correctness of the loop invariant**
> 1. Initialisation: $dist(s, s) = d(s) = 0$
> 2. Termination: 
> 	1. At the termination point, in each iteration of the while loop, we add one extra vertex to R
> 	2. Every vertex $u \in R = d(u)$, and $R = V$ at the end of the computation (i.e every vertex has the shortest distance from $s$ computed correctly)
> 	3. So at the end of the algorithm, all the vertices will be in $R$ and $R$ represents the shortest path from $s$ to every other vertices at termination
> 3. Maintenance (i.e how each loop iteration maintains the invariant)
> 	 1. At the start of the loop iteration, the algorithm chooses a new vertex $v$ to add to $R$ such that $min(D_v)$ is minimised (step 2.1 in the algorithm) (now to prove that this maintains the invariant)
> 	 2. Consider the shortest path $P$ from $s$ to $v$. 
> 		 1. Visual: `s -> ... -> y -> v`
> 	 3. Claim: Every vertex in $P$ is in $R$ except for $v$ 
> 		 1. Visual: `(s -> ... -> y) -> v`
> 		 2. Need to prove that this claim is true, because if this claim is true, then it follows that the loop invariant is maintained (i.e $dist(s,v)$ = d(v))
> 	 4. Suppose the claim (3.3) is false:
> 		 1. Then there exists a vertex $x$ before $v$ and immediately after $y$
> 			 1. Visual: `(s -> ... -> y) -> x -> ... -> v`
> 		 2. The true shortest path from $s$ to $v$ = $dist(s, v)$ is in $D_v$. So $min(D_v) \geq dist(s,v)$
> 		 3. From the visual 3.4.1.1, we have $dist(s, v) \gt dist(s, y) + w(y, x)$
> 		 4. Since $y$ is in $R$, $dist(s,y) = min(D_y)$ 
> 		 5. $dist(s, y) + w(y, x) = min(D_y) + w(y, x) \geq min(D_x)$
> 		 6. Full inequality: $min(D_v) \geq dist(s,v) \gt dist(s,y) + w(y,x) \geq min(D_x)$ 
> 		 7. Which implies $min(D_v) \geq min(D_x)$
> 		 8. So the algorithm would've selected $x$ instead of $v$. This contradicts (3.1).
> 	 5. Thus, the claim (3.3) must be true, which implies:
> 		 1. $min(D_v) \geq dist(s, v) = d(y) + w(y, v) \geq min(D_v)$
> 		 2. $dist(d, v) = min(D_v)$
> 		 3. Visual: `(s -> ... -> y) -> v`
> 	 6. Thus, the loop invariant is satisfied ($\forall u \in R, dist(s, u) =$ $min(D_u)$)

**Efficiency of Djikstra**
- The algorithm can be implemented using a priority queue

| Data Structure | Insert    | Extract-min         | Decrease-key     | Time complexity              |
| -------------- | --------- | ------------------- | ---------------- | ---------------------------- |
| Binary Heap    | $O(logn)$ | $O(logn)$           | $O(logn)$        | $O(\|E\| + \|V\|) log\|V\|)$ |
| Fibonacci Heap | $O(1)$    | $O(logn)$ amortized | $O(1)$ amortized | $O(\|E\| + \|V\|log\|V\|)$   |
###### **Insertion Sort**
> [!NOTE]
> **Pseudocode**
> ```
> 1 for i = 1 to N − 1 do // outer for-loop i
>       // X is the next item to insert into A[0..i − 1]
> 2     Let X = A[i] 
>       // inner for-loop j
> 3     for j = i − 1 down to 0 do 
> 4       if A[j] > X then
> 			 // Make space for X	
> 5            A[j + 1] = A[j] 
> 6       else
> 7            break
> 8      A[j + 1] = X // Insert X at index j + 1
> ```
> 
> **Loop invariant for outer for-loop $i$**
> - The invariant is true at the beginning when i = 1, i.e., `A[0] = B[0]` is a single integer and by default is sorted.
> - The rest of the array is as `A[1..N − 1] = B[1..N − 1]`
> - As we have been given the assumption that the inner for-loop j is correct, after it terminates (break) and we reach Step 8, we will correctly slot X at `A[j + 1]`, maintaining that `A[0..i]` now consists of the sorted values of `B[0..i]` (one index more than before).
> - At termination, `i = N − 1`, then the invariant says that `A[0..N − 1]` consists of the sorted values of the original array `B[0..N − 1]`, which shows the correctness of InsertionSort(A).
> 
> **Loop invariant for inner for-loop $j$**
> 1. `A[0..j]A[j + 2..i]` is the sorted version of `B[0..i − 1]`.
> 2. `A[i + 1..N − 1] = B[i + 1..N − 1]`.
> 3. `X = B[i]`.
> 4. `If j + 2 ≤ i`, then `A[j + 2] > X`.
##### **Recursive Algorithms (Divide and Conquer)**
1. Base case
2. Inductive step:
	1. Assume algo is correct for any input of size $\leq n$
	2. Show the algo is correct for any input of size $n$
###### **Searching in a sorted array**
> [!NOTE]
> 1. Inductive step: Assume algo works for any input of size $< n$
> 2. If $x = A[mid]$, answer is YES
> 3. If $x > A[mid]$:
> 	1. $x \in A[lb..ub] \iff x \in A[mid + 1..ub]$ -- A is sorted
> 	2. Therefore, answer must be $\text{BinarySearch(A, mid + 1, ub, x)}$ -- Induction Hypothesis
> 4. Similar for $x < A[mid]$
> - Depth: $O(logn)$, $T(n) \in O(logn)$

**Divide and Conquer**
$$ 
T_n =  
\begin{cases}  
\Theta(1) & \text{if } n \leq 1 \\  
aT(\frac{n}{b}) + f(n) & \text{otherwise.}  
\end{cases}  ​
$$
- $a$ subproblems, each of size $\frac{n}{b}$
- $f(n)$ = cost of splitting and combining

**Improving divide-and-conquer algorithm**
1. Option 1: Reduce cost for splitting/combining
2. Option 2: Reduce number of subproblems
###### **Exponentiation**
> [!NOTE]
> **1. $a^n = a^{n-1} \cdot a$**
> - $T(n) = T(n-1) + \Theta(1) \in \Theta(n)$
> 
> **2. Fast exponentiation**
> - If $n$ is even: $a^n = a^{\lfloor n/2\rfloor} \cdot a^{\lfloor n/2 \rfloor}$
> - If $n$ is odd: $a^n = a^{\lfloor n/2 \rfloor} \cdot a^{\lfloor n/2 \rfloor} \cdot a$
> - $T(n) = T(\lfloor n/2 \rfloor) + \Theta(1) \in \Theta(\log{n})$

**Fibonacci with matrices (Strassen's Algorithm)**
> [!NOTE]
> $$
> \begin{pmatrix}
> F_{n+1} & F_n \\
> F_n & F_{n-1}
> \end{pmatrix}
> =
> \begin{pmatrix}
> F_n + F_{n-1} & F_n \\
> F_{n-1} + F_{n-2} & F_{n-1}
> \end{pmatrix}
> =
> \begin{pmatrix}
> F_n & F_{n-1} \\
> F_{n-1} & F_{n-2}
> \end{pmatrix}
> \begin{pmatrix}
> 1 & 1 \\
> 1 & 0
> \end{pmatrix}
> $$
> $$
> \begin{pmatrix}
> F_{n+1} & F_n \\
> F_n & F_{n-1}
> \end{pmatrix}
> =
> \begin{pmatrix}
> 1 & 1 \\
> 1 & 0
> \end{pmatrix}^n
> $$
> 
> **Matrix Multiplication**
> **Divide and conquer**
> Partition matrices (A), (B), and (C) into block matrices:
> $$  
> C =
> \begin{pmatrix}  
> r & s \\  
> t & u  
> \end{pmatrix},  
> \quad  
> A =  
> \begin{pmatrix}  
> a & b \\  
> c & d  
> \end{pmatrix},  
> \quad  
> B =  
> \begin{pmatrix}  
> e & f \\  
> g & h  
> \end{pmatrix}  
> $$
> Then:
> $$
> \begin{pmatrix}  
> r & s \\  
> t & u  
> \end{pmatrix}
> =
> \begin{pmatrix}  
> a & b \\ 
> c & d  
> \end{pmatrix}
> \cdot
> \begin{pmatrix}  
> e & f \\  
> g & h  
> \end{pmatrix}  
> $$
> - $r = ae + bg, s = af + bh, t = ce + dg, u = cf + dh$  
> - All blocks $(r,s,t,u,a,b,c,d,e,f,g,h)$ are $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices.
> - 8 multiplications of $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices
> - 4 additions of $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices
> - $T(n) = 8T\left(\frac{n}{2}\right) + \Theta(n^2)$
> - $T(n) \in \Theta(n^{\log_2 8})$ = $\theta(n^3)$
> 
> $$  
> C =  
> \begin{pmatrix}  
> r & s \\  
> t & u  
> \end{pmatrix},  
> \quad  
> A =  
> \begin{pmatrix}  
> a & b \\ 
> c & d  
> \end{pmatrix},  
> \quad  
> B =  
> \begin{pmatrix}  
> e & f \\ 
> g & h  
> \end{pmatrix}  
> $$
> 
> **Strassen’s 7 Products**
> - Instead of 8 multiplications, compute:
> $$
> \begin{aligned}  
> P_1 &= a(f - h) \\  
> P_2 &= (a + b)h \\  
> P_3 &= (c + d)e \\  
> P_4 &= d(g - e) \\  
> P_5 &= (a + d)(e + h) \\  
> P_6 &= (b - d)(g + h) \\  
> P_7 &= (a - c)(e + f)  
> \end{aligned}  
> $$
> 
> **Expansion**
> $$
> \begin{aligned}  
> r &= P_5 + P_4 - P_2 + P_6 \\  
> s &= P_1 + P_2 \\  
> t &= P_3 + P_4 \\  
> u &= P_5 + P_1 - P_3 - P_7  
> \end{aligned}  
> $$
> **Time complexity**
> - 7 multiplications of $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices
> - 18 additions/subtractions of $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices
> - $T(n) = 7T\left(\frac{n}{2}\right) + \Theta(n^2)$
> - $T(n) \in \Theta(n^{\log_2 7})  \in \Theta(n^{2.807...})$
###### StoogeSort
> [!NOTE]
> **Pseudocode**
> ```
> 1 Let n be the length of array A
> 2 if n = 2 and A[0] > A[1] then
> 3     Swap A[0] and A[1]
> 4 if n > 2 then
> 5     Apply StoogeSort to sort the first ⌈2n/3⌉ elements recursively
> 6     Apply StoogeSort to sort the last ⌈2n/3⌉ elements recursively
> 7     Apply StoogeSort to sort the first ⌈2n/3⌉ elements recursively
> ```
> - We prove the correctness of the algorithm by an induction on the array size n.
> - Base case: If `n = 1`, the algorithm is trivially correct, as the array is already sorted.
> - If n = 2, the algorithm is correct due to Step 2.
> - Inductive step: Now consider the case of n > 2. By induction hypothesis, assume that the algorithm is correct on any array of size smaller than n. Let `r = n − ⌈2n/3⌉ = ⌊n/3⌋`. 
> - We make the following observation:
> 	- After Step 5, the r largest numbers of A must be in the final ⌈2n/3⌉ entries of A.
> 	- This observation implies that the r largest numbers of A are correctly sorted after Step 6.
> 	- Therefore, at the beginning of Step 7, the initial n−r = ⌈2n/3⌉ numbers of the array are precisely the ⌈2n/3⌉ smallest numbers of A. After Step 7, these ⌈2n/3⌉ numbers are also correctly sorted. 
> - In the subsequent discussion, we prove the above observation.
> 	- Let x be any number in the set of r largest numbers of A. 
> 	- We show that x must be in the final ⌈2n/3⌉ entries of A after Step 5.
> 	- Suppose x is not one of the initial ⌈2n/3⌉ numbers of A at the beginning of Step 5. 
> 	- The algorithm of Step 5 does not change the position of x, so x is still in the final n − ⌈2n/3⌉ ≤⌈2n/3⌉ entries of A after Step 5.
> 	- Suppose x is one of the initial ⌈2n/3⌉ numbers of A at the beginning of Step 5. 
> 	- Among these ⌈2n/3⌉ numbers, at least ⌈2n/3⌉ − r ≥ r of them are smaller than x. 
> 	- Therefore, after Step 5, x is not in the initial r entries of A. In other words, x is in the final n − r = ⌈2n/3⌉entries of A after Step 5
> 
> **Time complexity**
> - The runtime T (n) of the algorithm on an array of size n is given by the recurrence relation T (n) = O(1) if n ≤ 2.
> - 3T (⌈2n/3⌉) + O(1) if n > 2. 
> - Since a = 3, b = 3/2, and d = $\log_{3/2}{3}$ ≈ 2.7095 . . . and f (n) ∈ O($n^{d−ϵ}$) for some 0.5 = ϵ > 0, by Case 1 of the Master Theorem, we get T (n) ∈ O($n^d$) = O($n^{2.7095...}$).
> 
> **Why ⌈2n/3⌉?**
> - The algorithm sorts in 3 recursive calls. Each call must handle **more than half** the array, otherwise elements can "hide" in the uncovered region and never get compared.
> - Specifically, the first $\lceil 2n/3 \rceil$ and last $\lceil 2n/3 \rceil$ overlap by $\lceil 2n/3 \rceil + \lceil 2n/3 \rceil - n = \lceil n/3 \rceil$ elements. This overlap is what forces misplaced elements to eventually be compared and moved.
> - The uncovered tail after Step 5 has $r = \lfloor n/3 \rfloor$ positions. The key invariant is: **the $r$ largest elements must end up in the last $\lceil 2n/3 \rceil$ positions after Step 5**. This works because:
>     - If a top-$r$ element was already in the tail (not in the first $\lceil 2n/3 \rceil$), Step 5 does not touch it, and the tail has $\leq \lceil 2n/3 \rceil$ positions, so it is already where it needs to be.
>     - If a top-$r$ element was in the first $\lceil 2n/3 \rceil$, then among those $\lceil 2n/3 \rceil$ elements, at least $\lceil 2n/3 \rceil - r \geq r$ are smaller than it. So after sorting, it sits at position $> r$ (i.e., not in the first $r$ slots), meaning it is in the last $n - r = \lceil 2n/3 \rceil$ positions.
> - If you used anything $< 2n/3$ (say $n/2$), the overlap would be too small. The uncovered region $r$ would be too large, and you could not guarantee the top-$r$ elements land in the overlap zone. The correctness argument breaks.
> - If you used anything $> 2n/3$ (say $3n/4$), correctness still holds but the recurrence $T(n) = 3T(3n/4) + O(1)$ gives a worse exponent ($\log_{4/3} 3 \approx 3.82$ vs $\log_{3/2} 3 \approx 2.71$).
> - So $2n/3$ is the **smallest fraction that makes the correctness proof work**, giving the best possible time complexity for this 3-call structure.
###### Peak Finding
> [!NOTE]
> Given a 2D array with m rows and n columns, where each cell contains a number, a peak is a cell
> whose value is no smaller than all of its (up to) four neighbours: top, right, bottom, and left
> 
> **There is a peak in every 2D array**
> Since any 2D array must contain at least one maximal element, and a maximal element is no smaller than any other cell (including its four neighbors), all maximal elements are peaks.
> 
> **Pseudocode**
> ```
> 1 if A has n = 1 column then
> 2     return a maximal element in the column
> 3 if A has n ≥ 2 columns then
> 4     Let Cm be the middle column of A
> 5     Find a maximal element in Cm
> 6     if the above maximal element in Cm is a peak then
> 7         return that element
> 8     else
> 9         X ← FindPeakSp(Left Half of A without Cm)
> 10        Y ← FindPeakSp(Right Half of A without Cm)
> 11        if X or Y is a peak then
> 12            return the peak (X or Y )
> 13        else
> 14            return None
> ```
> 
> **Time Complexity**
> - Time complexity of finding a maximal element in any column is Θ(m), as there are m rows.
> - So, we can consider how many columns are processed, then multiply the result by Θ(m).
> - Let T (n) be the number of columns to be processed, then T (n) = 2 · T (n/2) + 1.
> - Since a = 2, b = 2, d = log2 = 1, and f (n) ∈ O($n^{d−ϵ}$) for some 0.5 = ϵ > 0, by Case 1 of the Master Theorem, we get T (n) ∈ Θ($n^d$) = Θ($n^{\log{2}}$) = Θ(n).
> - Thus, FindPeakSp(A) runs in T (n) × Θ(m) = Θ(n) × Θ(m) ∈ Θ(nm).
> 
> **Why always return a peak**
> - If we reach Step 8, the chosen maximal element W in the middle column (the k-th column) is not a peak. 
> - This implies one of the following scenarios for W :
> 	- Only the right neighbour of W is larger.
> 	- Only the left neighbour of W is larger. (Symmetric to above)
> 	- Both the left and right neighbours of W are larger. (Covered by the two cases above)
> - Hence, we focus on the case where the right neighbour of W in column k + 1 (denoted as X) is larger.
> - ![[Screenshot 2026-04-20 at 4.31.54 PM.png]]
> - Figure 1: Illustration of the scenario where the right neighbor X in column k + 1 is larger than W .
> - The figure highlights the relevant elements W (max in Cm), X, Y , and Z (special-peak of A′).
> - We argue below that this guarantees the existence of a special-peak in the columns k + 1, k + 2, . . .(i.e., columns > k). Refer to Figure 1 for an illustration of this scenario.
> - A special-peak in the right subarray `A′ = A[1..m][k + 1..n]` must also be a special-peak of A if it is located in any column other than column k + 1. 
> - Thus, the only case requiring further consideration is when a special-peak of A′ is located in column k + 1, as it directly borders column k.
> - Let Z be a special-peak of A′ located in column k + 1 of A. Observe the following:
> 	- Z is a maximal element in column k + 1 of A, so Z ≥ X, where X is the right neighbor of W 
> 	- Z is not smaller than any of its neighbors in A′, i.e., it is not smaller than its top, bottom, or right neighbours. 
> - To confirm that Z is also a special-peak of A, we need to show that Z is not smaller than its left neighbour Y in column k.
> - Since the right neighbur of W is larger (X > W ) and Z ≥ X, it follows that: Z ≥ X > W ≥ Y.
> - This implies that Z is not smaller than its left neighbour Y . 
> - Therefore, Z is a special-peak of A.
> 
> **How to optimise the else condition**
> ```
> 1 if A has n = 1 column then
> 2     return a maximal element in the column
> 3 if A has n ≥ 2 columns then
> 4     Let Cm be the middle column of A
> 5     Find a maximal element in Cm
> 6     if the above maximal element in Cm is a peak then
> 7         return that element
> 8     elif right ngb of above maximal element in Cm is larger then
> 10        return FindPeakSp-Imp(Right Half of A without Cm)
> 11    else
> 12        return FindPeakSp-Imp(Left Half of A without Cm)
> ```
> - Now we analyse its asymptotic behaviour.
> - Let T (n) represent the number of columns processed. In this case, the recurrence is: T (n) = T (n/2)+1.
> - Since a = 1, b = 2, d = 0, and f (n) ∈ Θ($n^d$), Case 2 of the Master Theorem yields: T (n) ∈ Θ(log n). 
> - Thus, the overall algorithm runs in T (n) × Θ(m) = Θ(log n) × Θ(m) ∈ Θ(m log n), which is asymptotically faster.
###### Karatsuba Multiplication
> [!NOTE]
> - Multiplies two $n$-digit numbers faster than the naive $O(n^2)$ grade-school algorithm.
> - Key idea: reduce 4 sub-multiplications to **3** using an algebraic trick, at the cost of extra additions.
> - Time: $T(n) = 3T(n/2) + O(n) \Rightarrow O(n^{\log_2 3}) \approx O(n^{1.585})$ by Master Theorem (Case 1).
> 
> **Setup**
> - Split two $n$-digit numbers $x$ and $y$ at the midpoint $m = \lfloor n/2 \rfloor$: $$x = x_1 \cdot B^m + x_0, \quad y = y_1 \cdot B^m + y_0$$
> - where $B$ is the base (e.g., 10 or $2^{32}$), $x_1, y_1$ are the high halves, $x_0, y_0$ are the low halves.
> 
> **Naive approach (4 multiplications)** $$x \cdot y = x_1 y_1 \cdot B^{2m} + (x_1 y_0 + x_0 y_1) \cdot B^m + x_0 y_0$$
> 
> - Requires 4 recursive multiplications: $x_1 y_1$, $x_1 y_0$, $x_0 y_1$, $x_0 y_0$. Gives $T(n) = 4T(n/2) + O(n) = O(n^2)$.
> 
> **Karatsuba's trick (3 multiplications)**
> - Compute only 3 products:
>     - $p_0 = x_0 \cdot y_0$
>     - $p_2 = x_1 \cdot y_1$
>     - $p_1 = (x_0 + x_1)(y_0 + y_1)$
> - Recover the cross term: $x_1 y_0 + x_0 y_1 = p_1 - p_0 - p_2$
>     - This works because $(x_0 + x_1)(y_0 + y_1) = x_0 y_0 + x_0 y_1 + x_1 y_0 + x_1 y_1$, so subtracting $p_0$ and $p_2$ isolates the cross term.
> - Final result: $$x \cdot y = p_2 \cdot B^{2m} + (p_1 - p_0 - p_2) \cdot B^m + p_0$$
> ```
> KARATSUBA(x, y, n):
>     if n = 1: return x * y    // base case
> 
>     m = ⌊n/2⌋
>     // split
>     x1, x0 = x / B^m, x mod B^m
>     y1, y0 = y / B^m, y mod B^m
> 
>     // 3 recursive multiplications
>     p0 = KARATSUBA(x0, y0, m)
>     p2 = KARATSUBA(x1, y1, n - m)
>     p1 = KARATSUBA(x0 + x1, y0 + y1, n - m + 1)
> 
>     return p2 * B^(2m) + (p1 - p0 - p2) * B^m + p0
> ```
> 
> > **Example**: $x = 1234$, $y = 5678$, base $B = 10$, $m = 2$.
> > 
> > - Split: $x_1 = 12, x_0 = 34$, $y_1 = 56, y_0 = 78$.
> > - $p_0 = 34 \times 78 = 2652$
> > - $p_2 = 12 \times 56 = 672$
> > - $p_1 = (34 + 12)(78 + 56) = 46 \times 134 = 6164$
> > - Cross term: $6164 - 2652 - 672 = 2840$
> > - Result: $672 \times 10^4 + 2840 \times 10^2 + 2652 = 6720000 + 284000 + 2652 = 7006652$.
> > - Verify: $1234 \times 5678 = 7006652$. Correct.
> 
> **Why it matters**
> - Saved 1 multiplication per recursive level. Sounds small, but changes the recurrence branching factor from 4 to 3, reducing exponent from $\log_2 4 = 2$ to $\log_2 3 \approx 1.585$.
> - Same principle generalizes: Toom-Cook splits into more pieces to get closer to $O(n^{1+\epsilon})$, and FFT-based multiplication achieves $O(n \log n \log \log n)$.
###### H-Index
> [!NOTE]
> - Given array $A[1..n]$ sorted in **non-increasing** order. Find the largest index $i$ such that $A[i] \geq i$.
> - Intuition: a researcher has H-index $h$ if $h$ of their papers have $\geq h$ citations each.
> - Convention: extend array so $A[0] > 0$ and $A[n+1] < n+1$. Guarantees a unique answer.
> 
> **Key monotonic property (enables binary search)**
> - If $A[j] \geq j$, then $A[j-1] \geq j-1$ (everything to the left is also valid).
> - If $A[j] < j$, then $A[j+1] < j+1$ (everything to the right is also invalid).
> - So the array looks like: $T, T, T, \ldots, T, F, F, \ldots, F$. We want the last $T$.
> 
> **Method 1: Linear Search -- $O(n)$**
> - Iterate $i = 1$ to $n$, find the last $i$ where $A[i] \geq i$.
> - Simple but slow for large $n$.
> 
> **Method 2': Double Binary Search -- $O(\log c_1 \cdot \log n)$**
> - Binary search on the **answer value** between $lo = 0$ and $hi = c_1$ (max citation count).
> - At each guess $mid$: binary search the sorted array to find how many papers have $\geq mid$ citations (i.e., find index $i$ where $c_i \geq mid$).
> - If $i \geq mid$: enough papers, guess higher, set $lo = mid$.
> - If $i < mid$: not enough papers, guess lower, set $hi = mid$.
> - Outer loop: $O(\log c_1)$ iterations. Inner binary search: $O(\log n)$ each. Total: $O(\log c_1 \cdot \log n)$.
> - Downside: depends on $c_1$ (citation values), not just $n$.
> 
> **Method 2: Binary Search on index -- $O(\log n)$**
> - Binary search on the **index** between $lo = 0$ and $hi = n$ instead (answer never exceeds $n$).
> - At each guess $mid$: directly check if $A[mid] \geq mid$.
>     - If yes: answer is $\geq mid$, search right half ($lo = mid$).
>     - If no: answer is $< mid$, search left half ($hi = mid$).
> - $O(\log n)$ total. Simpler and faster than Method 2'.
> ```
> H-INDEX-BINARY(A, n):
>     lo = 0, hi = n
>     while lo < hi:
>         mid = ⌈(lo + hi + 1) / 2⌉   // upper-mid to avoid infinite loop
>         if A[mid] >= mid:
>             lo = mid
>         else:
>             hi = mid - 1
>     return lo
> ```
> 
> **Method 3: Doubling + Binary Search -- $O(\log i)$ where $i$ is the answer**
> - If n is very large but the H-Index is actually small
> - First, find the least $k$ such that $A[2^k] < 2^k$, by trying $k = 0, 1, 2, \ldots$. Takes $O(\log i)$ steps.
> - If $k = 0$: answer is 0, done.
> - Otherwise: $A[2^{k-1}] \geq 2^{k-1}$ but $A[2^k] < 2^k$. Answer lies in $[2^{k-1}, 2^k]$.
> - Binary search within this range: $O(\log(2^k - 2^{k-1})) = O(k) = O(\log i)$.
> - Total: $O(\log i)$. **Output-sensitive**: faster when the answer is small relative to $n$.
###### **Ball Weighing Problem (D&C + Lower Bound)**
> [!NOTE]
> - $n$ balls, all same weight except one heavier ball. Find it using a balance scale. Minimize worst-case weighings.
> - Balance scale has **3 outcomes** per weighing: left heavy, right heavy, balanced ($<, =, >$).
> 
> **Strategy: divide into 3 groups**
> - Split balls into 3 groups of $\lfloor n/3 \rfloor$ (as equal as possible).
> - Weigh group 1 vs group 2.
>     - If one side heavier: heavy ball is in that group.
>     - If balanced: heavy ball is in group 3 (the unweighed group).
> - Recurse on the identified group of size $n/3$.
> - Each weighing eliminates $2/3$ of the balls.
> 
> **Number of weighings**: $T(n) = T(n/3) + 1 = \lceil \log_3 n \rceil$
> 
> **Lower bound proof**
> - Each weighing has 3 possible outcomes, so $k$ weighings can distinguish at most $3^k$ scenarios.
> - There are $n$ possible answers (any of the $n$ balls could be heavy).
> - Need $3^k \geq n \Rightarrow k \geq \lceil \log_3 n \rceil$.
> - The divide-into-3 strategy **matches** this lower bound, so it is optimal.
> 
> **Why not split into 2 groups?**
> - Splitting in half wastes information. Each weighing gives 3 outcomes but splitting into 2 only uses 2 (heavier side or lighter side). The balanced outcome is wasted.
> - Would need $\lceil \log_2 n \rceil$ weighings instead of $\lceil \log_3 n \rceil$.

---
#### 4. Sorting
##### Comparison-based
**Lower bound for comparison-based sorting**
- **Theorem: The worst-case complexity of any comparison-based sorting algo is $\ohm(nlogn)$**
- Decision tree: binary tree with at least $n!$ leaves, each permutation a possible answer
- Height of tree at least $log(n!) \in nlogn - nloge + O(logn) \subseteq \Theta(nlogn)$ (Stirling's approx.)
###### **Merge $k$ sorted arrays**
- As the $k$ arrays are sorted, number of possible ways to combine them is ${(kn)!}/{(n!)^k}$
- $\log({(kn)!}/{(n!)^k}) \in \ohm(kn\log k)$
###### **Quick Sort**
> [!NOTE]
> **Partition**
> 1. Choose pivot.
> 2. Partition cost:  $\Theta(n)$
> 
> **Worst Case**
> - If pivot always smallest or largest: $T(n) = T(n-1) + cn$
> - $\boxed{T(n) = \Theta(n^2)}$
> 
> **Average Case**
> Assume:
> - All permutations equally likely
> - Elements distinct
> - Pivot uniformly random
> 
> Expected recurrence: $A(n) = \frac{1}{n} \sum_{j=1}^{n} [A(j-1) + A(n-j)] + cn$
> - Simplifies to: $A(n) = cn + \frac{2}{n} \sum_{j=0}^{n-1} A(j)$
> - Using harmonic series: $\sum_{i=1}^{n} \frac{1}{i} \approx \ln n$
> - $\boxed{A(n) = O(n \log n)}$
> 
##### **Desirable Properties of Sorting**
1. Stable (order preserved)
	- $A[i] = A[j], ; i<j$
	- Insertion sort: stable
	- Merge sort: stable (proper implementation)
	- Quicksort: usually not stable
2. In-place
	- Uses small extra memory.
	- Insertion sort: $O(1)$
	- Merge sort: $O(n)$ 
	- Quicksort: $O(\log n)$ stack
##### **Non-comparison sorts**
Assume:  $A[i] \in {1,2,\dots,k}$
Algorithm:
- Count occurrences
- Reconstruct sorted array
- $O(n + k)$, no comparisons required.
###### Counting Sort
> [!NOTE]
> - **Not comparison-based**. Exploits the fact that input values come from a known finite range.
> - Input: array $A[0..n-1]$ where each element $\in {0, 1, \ldots, k}$.
> - Time: $O(n + k)$. Space: $O(n + k)$.
> - **Stable**: equal elements appear in the output in the same order as the input. This is critical when used as a subroutine in radix sort.
> - Beats the $\Omega(n \log n)$ comparison-based lower bound because it does not compare elements.
> 
> **Algorithm**
> 1. Create count array $C[0..k]$, initialized to 0.
> 2. For each $A[i]$: increment $C[A[i]]$.
> 3. Compute prefix sums: for $j = 1$ to $k$, set $C[j] = C[j] + C[j-1]$. Now $C[j]$ = number of elements $\leq j$.
> 4. Build output array $B[0..n-1]$: iterate $A$ from right to left (for stability). For each $A[i]$: place $A[i]$ at $B[C[A[i]] - 1]$, then decrement $C[A[i]]$.
> 
> ```
> COUNTING-SORT(A, k):
>     n = len(A)
>     C = array of size (k+1), all zeros
>     B = array of size n
> 
>     // Step 1: count occurrences
>     for i = 0 to n-1:
>         C[A[i]] += 1
> 
>     // Step 2: prefix sums (C[j] = # elements <= j)
>     for j = 1 to k:
>         C[j] = C[j] + C[j-1]
> 
>     // Step 3: place elements (right to left for stability)
>     for i = n-1 downto 0:
>         B[C[A[i]] - 1] = A[i]
>         C[A[i]] -= 1
> 
>     return B
> ```
> 
> > **Example**: $A = [2, 0, 2, 1, 1, 0]$, $k = 2$.
> > 
> > - Count: $C = [2, 2, 2]$ (two 0s, two 1s, two 2s).
> > - Prefix sum: $C = [2, 4, 6]$.
> > - Place (right to left): $A[5]=0 \to B[1], C[0]=1$. $A[4]=1 \to B[3], C[1]=3$. $A[3]=1 \to B[2], C[1]=2$. $A[2]=2 \to B[5], C[2]=5$. $A[1]=0 \to B[0], C[0]=0$. $A[0]=2 \to B[4], C[2]=4$.
> > - Result: $B = [0, 0, 1, 1, 2, 2]$.
> 
> **Why right-to-left in Step 3?**
> - Guarantees stability. Elements with the same value are placed from the last occurrence first, filling positions from right to left within their group. This preserves original relative order.
> 
> **When to use**
> - $k \in O(n)$: runs in $O(n)$, very efficient.
> - $k \in \omega(n \log n)$: worse than comparison-based sorts. Not worth it.
> - Primarily used as a subroutine in **radix sort**, where $k$ is small (e.g., base 10 or base $n$) and stability is required for correctness.
###### Radix Sort
> [!NOTE]
> - Sorts $n$ integers by processing one digit at a time, from **least significant to most significant**.
> - Uses a **stable** sub-sort (typically counting sort) at each digit position. Stability is critical: it preserves the relative order from previous digit passes.
> - Not comparison-based. Bypasses the $\Omega(n \log n)$ lower bound.
> 
> **Algorithm**
> ```
> RADIX-SORT(A, d):
>     for i = 1 to d:          // from least significant to most significant digit
>         Stable-sort A on digit i    // typically counting sort
> ```
> - $d$ = number of digits, $k$ = range of each digit (base).
> - Each pass of counting sort: $O(n + k)$.
> - Total: $O(d \cdot (n + k))$.
> 
> **Choosing the base**
> - Given $n$ numbers, each in range $[0, U)$. Represent in base $b$: number of digits $d = \lceil \log_b U \rceil$.
> - Total time: $O(\lceil \log_b U \rceil \cdot (n + b))$.
> - Set $b = n$ to minimize: $d = \lceil \log_n U \rceil$, each pass is $O(n + n) = O(n)$.
> - Total: $O(n \cdot \lceil \log_n U \rceil)$.
> - If $U \in O(n^c)$ for some constant $c$: $\log_n U = O(c) = O(1)$, total $O(n)$. Linear time.
> 
> **Why least significant digit first?**
> - Most significant first would require recursing into sub-buckets (like MSD radix sort), which is more complex.
> - LSD approach: after processing digits $1, \ldots, i$, all numbers are correctly sorted by their last $i$ digits. Stability ensures that when digit $i+1$ is the same, the ordering from the previous pass (digits $1, \ldots, i$) is preserved.
> 
> > **Example**: sort $[329, 457, 657, 839, 436, 720, 355]$ in base 10 ($k = 10$, $d = 3$).
> > 
> > - Pass 1 (ones): $[720, 355, 436, 457, 657, 329, 839]$
> > - Pass 2 (tens): $[720, 329, 436, 839, 355, 457, 657]$
> > - Pass 3 (hundreds): $[329, 355, 436, 457, 657, 720, 839]$
> > - Sorted.
> 
> **When to use**
> - $n$ integers in $[0, n^c - 1]$: radix sort with base $n$ gives $O(cn) = O(n)$. Beats comparison sort.
> - $n$ integers in $[0, 2^n - 1]$: $d = \lceil n / \log n \rceil$, total $O(n^2 / \log n)$. Worse than $O(n \log n)$. Not worth it.
> - Strings of length $L$ over alphabet $\Sigma$: $O(L \cdot (n + |\Sigma|))$.
> 
> **Comparison with counting sort**
> - Counting sort: $O(n + k)$, works directly when range $k$ is small.
> - Radix sort: breaks a large range into $d$ small-range passes. Effectively extends counting sort to large ranges without blowing up space.
> - Radix sort calls counting sort as a subroutine, once per digit.

---
#### 5. Randomized Algorithms
##### **Verification of Matrix Multiplication (Freivald)**
> [!NOTE]
> - Given $A,B,C \in \mathbb{R}^{n \times n}$.  
> - Check if:  $AB = C$
> - Naive: compute $AB$ - $O(n^3) \quad \text{(or } O(n^{2.807}) \text{ with Strassen)}$  
> 
> **Idea**
> - Given $n\times n$ matrices A, B and C, check if $A \times B=C$
> - Matrix multiplication AxB is too expensive
> - Solution: take a vector $v = \{v_1, v_2, ... , v_n\}$, where each $v_i$ is either 0 or 1 chosen uniformly at random
> - Use $ABv = Cv$ to check by first computing $Bv$ then $A(Bv)$ to avoid expensive matrix multiplication => Reduce to $O(n^2)$ from $O(n^3)$
> - If $AB = C$, then $ABv=Cv$ is always correct
> - If $AB \neq C$, then the algorithm correctly shows that $AB != C$ with a probability of $\geq$ $\frac{1}{2}$
> 
> **Proof of probability $\geq \frac{1}{2}$:**
> 1. If $AB = C$, then any vector v will result in $ABv = Cv$
> 2. If $AB \neq C$:
>     - $AB \neq C$ => $AB - C = D$, where $D$ is a non zero matrix
>     - Let $Dv = u$, where $u$ is a vector = $\{u_1, u_2, .., u_n\}$
>     - Algorithm is incorrect $\iff$ $ABv = Cv$ $\iff u_i = 0 \space \forall i \in [0 .. n]$
>     - $\implies$ algorithm is correct $\iff u_i = 0 \space \exists i \in [0 .. n]$
>     - Each $u_i = d_i1 \cdot v_1 + d_i2\cdot v_2 + ... d_ij\cdot v_j + ... + d_in\cdot v_n = ... + d_ij\cdot v_j$
>     - Fix $v_j$, then there is at most one choice of $v_j$ that makes $u_i = 0$
> 	    - If $v_j = 0$, then $u_i = 0 \implies AB \neq C \implies$ algorithm is correct
> 	    - If $v_j = 1$, then $u_i = 0 \implies AB = C \implies$ algorithm is incorrect
> 3. So algorithm is always correct if $AB = C$, but correct with probability = $\frac{1}{2}$ if $AB \neq C$
> 
> **Monte Carlo**
> - Since probability of getting correct is only $\frac{1}{2}$, the error probability can be reduced to at most $f$ by repeating the algo for $t = \lceil(\log(\frac{1}{f}))\rceil$ times
> 	- If all $t$ outputs $AB = C$, then $AB = C$
> 	- Else, $AB \neq C$
> - Because if $AB \neq C$, and repeat for $t = \lceil(\log(\frac{1}{f}))\rceil$ times, then error probability $\frac{1}{2^t} \leq f$
> 
> **Why bound 1/2 is actually the best possible**
> - Consider the smallest 1 × 1 matrices A = (1), B = (0), and C = (1). We have AB != C.
> - In Freivalds’ algorithm, v = (v1), where v1 is chosen from {0, 1} uniformly at random.
> - With probability 1/2, v1 = 0, in which case1 A(Bv) = Cv (the answer is incorrect).
> - With probability 1/2, v1 = 1, in which case A(Bv)̸ = Cv (the answer is correct).
> - By appending zeros, the construction can be extended to n × n matrices for every positive integer n.
##### **Coupon Collector / Balls and Bins**
> [!NOTE]
> **Idea**
> - Throw $m$ balls into $n$ bins independently.
> - Probability a fixed bin is empty: $\left(1-\frac{1}{n}\right)^m \le e^{-m/n}$  
> - Union bound: $Pr[\exists \text{ empty bin}] \le n e^{-m/n}$
> - If $m \ge 2n \ln n$, then $Pr[\text{all bins nonempty}] \ge 1 - \frac{1}{n}$
> 
> **Expected Value**
>   - $E[X] = \sum_x x \cdot Pr(X=x)$
##### **Markov Inequality**
- If $X \ge 0, Pr(X \ge aE[X]) \le \frac{1}{a}$
- Application:
	- $E[T] = t$  
	- $Pr(T \ge 100t) \le \frac{1}{100}$
##### **Linearity of Expectation**
- $E[X+Y] = E[X] + E[Y]$
- More generally: $E\left[\sum_i X_i\right] = \sum_i E[X_i]$
- No independence required.

**Indicator Variables**
- For event $\mathcal{E}$:  
$$
1_{\mathcal{E}} =  
\begin{cases}  
1 & \text{if } \mathcal{E} \text{ occurs} \\  
0 & \text{otherwise}  
\end{cases}  
$$
- $E[1_{\mathcal{E}}] = Pr(\mathcal{E})$. Good for counting

##### **Hashing**
> [!NOTE]
> - Hash table of size $n$.  
> - Hash function: $h: U \to {1,\dots,n}$
> - Chain hashing: collisions stored in linked list.
> - Expected number of balls in one bin:  $E[X] = \frac{m}{n}$
> - Expected size of list for element’s bin: $1 + \frac{m-1}{n}$
> - Goal: reduce collisions
##### Randomized Quick Sort
> [!NOTE]
> - Pivot chosen uniformly at random.
> - Partition cost: $\Theta(n)$
> - Runtime proportional to number of comparisons.
> 
> **Expected Comparisons**
> $$
> X_{i,j} =  
> \begin{cases}  
> 1 & \text{if } a_i, a_j \text{ compared} \\  
> 0 & \text{otherwise}  
> \end{cases}  
> $$
> 
> - Then: $E[\text{\#comparisons}] = \sum_{1 \le i < j \le n} E[X_{i,j}]$
> - Observation: $Pr[X_{i,j}=1] = \frac{2}{j-i+1}$
> - $E[\text{\#comparisons}]= \sum_{i<j} \frac{2}{j-i+1}$
> - $O(n \log n)$
> 
> **Theorem:**
> - $E[T(n)] = O(n \log n)$
> - Using Markov: $T(n) = O(n \log n) \space \text{with probability } \ge 0.99$
##### **Randomized Equality Testing (Communication Protocol)**
> [!NOTE]
> - Alice holds $n$-bit string $S_A$, Bob holds $n$-bit string $S_B$. Goal: decide if $S_A = S_B$.
> - Deterministic lower bound: $\Omega(n)$ bits must be communicated (proven below).
> - Randomized protocol communicates only $O(\log n)$ bits with error $\leq 1/n$.
> 
> **Protocol**
> 1. Let $S$ = set of the $n^2$ smallest prime numbers.
> 2. Alice samples $p$ from $S$ uniformly at random.
> 3. Alice sends $p$ and $S_A \bmod p$ to Bob ($O(\log p) \subseteq O(\log n)$ bits, since by Prime Number Theorem $p \in O(n^2 \log n)$).
> 4. Bob computes $S_B \bmod p$.
> 5. If $S_A \bmod p = S_B \bmod p$: Bob decides $S_A = S_B$. Otherwise: $S_A \neq S_B$.
> 
> **Correctness: error $\leq 1/n$**
> - Case $S_A = S_B$: $S_A \bmod p = S_B \bmod p$ for all $p$. Always correct. Probability 1.
> - Case $S_A \neq S_B$: error occurs iff $p$ divides $d = |S_A - S_B|$.
>     - $1 \leq d < 2^n$ (both are $n$-bit strings).
>     - Let $k$ = number of distinct prime factors of $d$. Every prime $\geq 2$, so product of $k$ distinct primes $\geq 2^k$. Since $2^k \leq d < 2^n$, we get $k \leq n - 1$.
>     - $\Pr[\text{error}] = \Pr[p \mid d] \leq \frac{n - 1}{|S|} = \frac{n-1}{n^2} \leq \frac{1}{n}$.
> - Correct with probability $\geq 1 - 1/n$.
> - Trade-off: smaller $|S|$ means faster sampling but lower correctness probability. If $|S| = n$ instead of $n^2$, correctness drops to $\approx 1/n$ (almost useless).
> 
> **Deterministic lower bound: $\Omega(n)$ bits required**
> - Proof (one-way communication): there are $2^n$ possible strings $S_A$.
> - If Alice sends only $n - 1$ bits, there are $2^{n-1}$ possible messages.
> - By pigeonhole: $\exists$ two distinct strings $X \neq Y$ such that Alice sends the same message for both.
> - Bob cannot distinguish $S_A = X$ from $S_A = Y$. He must fail on at least one of $(S_A = X, S_B = X)$ or $(S_A = Y, S_B = X)$.
> - Therefore at least $n$ bits are required. Any deterministic protocol needs $\Omega(n)$ bits.
> - The randomized protocol achieves $O(\log n)$ bits: **exponential separation** between randomized and deterministic.
##### **Random Graph Partition (Max-Cut)**
> [!NOTE]
> - Given graph $G = (V, E)$ (no self-loops). Partition $V = V_1 \cup V_2$. 
> - A **cut** is the set of edges crossing $V_1$ and $V_2$. Goal: show the expected cut size.
> 
> **Basic random partition: expected cut $= |E|/2$**
> - Each vertex independently joins $V_1$ with probability $1/2$, else $V_2$.
> - For each edge $e = \{u, v\}$, let $X_e$ = indicator that $e$ crosses the cut.
> - $e$ crosses $\iff$ $u$ and $v$ are in different parts. Four equally likely cases:
>     - $u \in V_1, v \in V_1$: no cross ($1/4$)
>     - $u \in V_1, v \in V_2$: cross ($1/4$)
>     - $u \in V_2, v \in V_1$: cross ($1/4$)
>     - $u \in V_2, v \in V_2$: no cross ($1/4$)
> - $E[X_e] = 1/2$.
> - By linearity of expectation: $E[X] = \sum_{e \in E} E[X_e] = |E|/2$.
> - **Corollary**: any graph admits a cut of size at least $|E|/2$ (since expected value $= |E|/2$, at least one partition achieves it).
> 
> **Improvement 1: force one edge -- expected cut $= (|E|+1)/2$**
> - Pick one edge $e = \{u, v\}$. Force $u^* \in V_1$ and $v^* \in V_2$. All other vertices assigned randomly.
> - $E[X_e] = \begin{cases} 1 & \text{if } e = e^* \ 1/2 & \text{if } e \neq e^* \end{cases}$
> - $E[X] = 1 + \frac{|E| - 1}{2} = \frac{|E| + 1}{2}$
> 
> **Improvement 2: balanced partition ($|V|$ even) -- expected cut $= \frac{|E|}{2} \cdot \frac{|V|}{|V|-1}$**
> - Choose $V_1$ uniformly at random from all $\binom{|V|}{|V|/2}$ subsets of size $|V|/2$. Set $V_2 = V \setminus V_1$.
> - For edge $e = {u, v}$:
>     - $\Pr(u \in V_1) = \frac{|V|/2}{|V|} = \frac{1}{2}$
>     - $\Pr(v \in V_2 \mid u \in V_1) = 1 - \frac{|V|/2 - 1}{|V| - 1} = \frac{|V|/2}{|V| - 1}$
>     - By symmetry (both orderings): $E[X_e] = 2 \cdot \frac{1}{2} \cdot \frac{|V|/2}{|V|-1} = \frac{|V|/2}{|V|-1}$
> - $E[X] = |E| \cdot \frac{|V|/2}{|V|-1} = \frac{|E|}{2} \cdot \frac{|V|}{|V|-1}$
> - This is strictly better than $|E|/2$ since $\frac{|V|}{|V|-1} > 1$. Tight for complete graphs.
> - Intuition: forcing equal-sized parts prevents "lopsided" partitions (e.g., $|V_1| = 1, |V_2| = |V|-1$) that waste edges.
##### **Random Walk on 4-Point Circle (State-based Probability)**

> [!NOTE]
> - 4 points $0, 1, 2, 3$ clockwise on a circle. Start at 0 (visited). Each step: jump to adjacent point (clockwise or counterclockwise) with probability $1/2$ each. Continue until all 4 visited.
> - Question: probability that point 2 is the **last** point visited?
> - Define states based on current position and visited set:
>     - $x$ = $\Pr[\text{2 is last} \mid \text{at 0, visited } {0,1}]$
>     - $y$ = $\Pr[\text{2 is last} \mid \text{at 1, visited } {0,1}]$
> - From state $x$ (at 0): jump to 3 with prob $1/2$ (then 2 is last) or jump to 1 with prob $1/2$ (enter state $y$): $x = \frac{1}{2} + \frac{y}{2}$
> - From state $y$ (at 1): jump to 2 with prob $1/2$ (2 is NOT last, since 3 unvisited) or jump to 0 with prob $1/2$ (enter state $x$): $y = \frac{x}{2}$
> - Solve: substitute $y = x/2$ into first equation: $x = \frac{1}{2} + \frac{x}{4} \Rightarrow x = \frac{2}{3}$, $y = \frac{1}{3}$.
> - Initial state (at 0, visited ${0}$): jump to 1 with prob $1/2$ (state $y = 1/3$) or jump to 3 with prob $1/2$ (by symmetry, also $1/3$).
> - Answer: $\frac{1}{2} \cdot \frac{1}{3} + \frac{1}{2} \cdot \frac{1}{3} = \frac{1}{3}$.
> 
##### **Independent Set Lower Bound (Random Ordering)**

> [!NOTE]
> - Undirected simple graph $G = (V, E)$. $d(v)$ = degree of $v$.
> - Take a uniformly random ordering $v_1, v_2, \ldots, v_n$ of vertices. Define $I = {v_i : \text{all neighbours of } v_i \text{ appear after } v_i}$ (i.e., $v_i$ comes first among itself and its neighbours).
> - **$I$ is an independent set**: if $u \in I$ and $(u, v) \in E$, then $v$ appears after $u$, so $v \notin I$. No two adjacent vertices can both be in $I$.
> - **Expected size**: let $X_v = 1$ if $v \in I$. $v \in I$ iff $v$ appears before all $d(v)$ neighbours. Among $v$ and its $d(v)$ neighbours ($d(v) + 1$ vertices total), $v$ is first with probability $\frac{1}{d(v)+1}$. $$E[|I|] = \sum_{v \in V} E[X_v] = \sum_{v \in V} \frac{1}{d(v) + 1}$$
> - **Existence**: since the expected size equals $\sum_{v \in V} \frac{1}{d(v)+1}$, at least one ordering achieves this size. So there exists an independent set of size $\geq \sum_{v \in V} \frac{1}{d(v)+1}$.
##### **Expected Input Length (Weighted Geometric Series)**
> [!NOTE]
> - $\Pr[\text{input length} = i] = \frac{1}{2^{i+1}}$ for each $i \geq 0$.
> - $E[i] = \sum_{i \geq 0} i \cdot \frac{1}{2^{i+1}} = \frac{1}{2} \sum_{i \geq 1} \frac{i}{2^i}$
> - Rewrite: $\sum_{i \geq 1} \frac{i}{2^i} = \sum_{i \geq 1} \sum_{j=0}^{i-1} \frac{1}{2^i}$. Swap summation order (sum over columns $j$ first): $$= \sum_{j \geq 0} \sum_{i \geq j+1} \frac{1}{2^i} = \sum_{j \geq 0} \frac{1}{2^j} \cdot \underbrace{\sum_{i \geq 1} \frac{1}{2^i}}_{=1} = \sum_{j \geq 0} \frac{1}{2^j} = 2$$
> - $E[i] = \frac{1}{2} \cdot 2 = 1$.
> - Useful identity: $\sum_{i \geq 1} \frac{i}{r^i} = \frac{r}{(r-1)^2}$ for $r > 1$. Here $r = 2$: $\frac{2}{1} = 2$. Matches.

##### Two Types of Randomized Algorithms
**Las Vegas**
- Always correct.
- Runtime bounded in expectation.
- Example: randomized quicksort.

**Monte Carlo**
- Runtime bounded.
- May output wrong answer with small probability.
- Example: Freivald’s.

Conversion:
- Las Vegas → Monte Carlo possible.
- Reverse not generally possible.

**Additional notes**
- For randomised algos, what we argue for is for the worst input. The expectation is only for the algorithm. We analyse for worst input, not the average input

---
#### 6. Dynamic Programming
##### **Template**
**Optimal Substructure for DP**
1. Let P be the original problem. Define OPT(P) as the value of an optimal solution.
2. Let O be an optimal solution to P with cost/value OPT(P).
3. Suppose O makes choice c at the current decision point, which decomposes P into subproblems P1, P2, ..., Pk.
4. Let O1, O2, ..., Ok be the sub-solutions within O corresponding to P1, P2, ..., Pk.
5. Then OPT(P) = cost(c) + cost(O1) + cost(O2) + ... + cost(Ok).
6. Claim: each Oi is optimal for Pi.
7. Proof by contradiction. Suppose some Oi is not optimal for Pi. Then there exists a feasible solution Oi' to Pi with cost(Oi') < cost(Oi).
8. Construct S by replacing Oi with Oi' in O. S is still a feasible solution to P.
9. cost(S) = cost(c) + ... + cost(Oi') + ... < cost(c) + ... + cost(Oi) + ... = OPT(P).
10. This contradicts the optimality of O.
11. Therefore each Oi must be optimal for Pi.

**Recurrence**
- Given optimal substructure, the recurrence follows directly:
- OPT(P) = best over all valid choices c of { cost(c) + OPT(P1) + OPT(P2) + ... + OPT(Pk) }
- DP then computes this bottom-up (tabulation) or top-down (memoization), reusing solutions to overlapping subproblems.

##### **Key Properties**
- **Optimal substructure:** an optimal solution contains optimal solutions to subproblems
- **Overlapping subproblems:** recursive solution recomputes the same subproblems many times
- Two approaches:
    - **Top-down (memoization):** recursive, store results before returning, no need to care about ordering
    - **Bottom-up (tabulation):** iterative, fill table in order, must determine ordering beforehand
##### **Fibonacci**
> [!NOTE]
> - $F(0) = 0, F(1) = 1, F(n) = F(n-1) + F(n-2)$ for $n > 1$
> - Recursive: $\ge 2^{(n-2)/2}$ operations (exponential), recomputes same subproblems
> - Iterative/memoized: $O(n)$ (linear), each subproblem computed once
##### **Longest Common Subsequence**
> [!NOTE] **Longest Common Subsequence**
> - **Input:** two sequences $A[1..n]$ and $B[1..m]$
> 
> - **Output:** longest sequence $C$ that is a subsequence of both $A$ and $B$
> - $C$ is a **subsequence** of $A$ if there exist $1 \le i_1 < \dots < i_k \le n$ such that $C[j] = A[i_j]$ for all $1 \le j \le k$
> - Brute force: $2^n$ subsequences of $A$, check each against $B$ in $O(m)$, total $O(m \cdot 2^n)$
> 
> **Recurrence.** Let $L(i, j)$ = length of LCS of $A[1..i]$ and $B[1..j]$.
> $$L(i,j) = \begin{cases} 0 & \text{if } i = 0 \text{ or } j = 0 \\ L(i-1, j-1) + 1 & \text{if } a_i = b_j \\ \max(L(i-1, j),\ L(i, j-1)) & \text{if } a_i \ne b_j \end{cases}$$
> 
> - If $a_i = b_j$: LCS must end with $a_i$ (cut-and-paste argument: if it didn't, we could extend it by appending $a_i$, contradiction)
> - If $a_i \ne b_j$: either $a_i$ or $b_j$ is not the last symbol of LCS, so take the better of dropping either
> - 
> **LCS Algorithm (Bottom-up)**
> 
> ```
> L(n, m):
>   For i = 0 to n: T[i,0] = 0
>   For j = 0 to m: T[0,j] = 0
>   For i = 1 to n:
>     For j = 1 to m:
>       If a_i == b_j:
>         T[i,j] = T[i-1,j-1] + 1
>       Else:
>         T[i,j] = max(T[i-1,j], T[i,j-1])
>   Return T[n,m]
> ```
> 
> - Time: $O(nm)$. Space: $O(nm)$, reducible to $O(\min(n,m))$ by keeping only two rows.
> - $(n+1)(m+1)$ distinct subproblems, each computed once in $O(1)$.
##### **Knapsack**
> [!NOTE]
> 
> - **Input:** $n$ items with weights $w_i$ and values $v_i$, capacity $W$
> - **Output:** $S \subseteq {1, \dots, n}$ maximizing $\sum_{i \in S} v_i$ subject to $\sum_{i \in S} w_i \le W$
> - Brute force: $2^n$ subsets
> 
> **Recurrence.** Let $m[i,j]$ = max value using items ${1, \dots, i}$ with capacity $j$.
> 
> $$m[i,j] = \begin{cases} 0 & \text{if } i = 0 \text{ or } j = 0 \\ \max(m[i-1, j-w_i] + v_i,\ m[i-1, j]) & \text{if } w_i \le j \\ m[i-1, j] & \text{otherwise} \end{cases}$$
> 
> - Case 1 (take item $i$): remaining capacity $j - w_i$, add $v_i$, solve for items ${1, \dots, i-1}$
> - Case 2 (skip item $i$): same capacity $j$, solve for items ${1, \dots, i-1}$
> - Optimal substructure by cut-and-paste: if the sub-solution were not optimal, we could substitute a better one
> 
> **Knapsack Algorithm (Bottom-up)**
> 
> ```
> KNAPSACK(v, w, W):
>   For j = 0 to W: m[0,j] = 0
>   For i = 1 to n: m[i,0] = 0
>   For i = 1 to n:
>     For j = 0 to W:
>       If j >= w[i]:
>         m[i,j] = max(m[i-1, j-w[i]] + v[i], m[i-1, j])
>       Else:
>         m[i,j] = m[i-1, j]
>   Return m[n, W]
> ```
> 
> - Time: $O(nW)$. This is **pseudo-polynomial**: polynomial in the numeric value $W$, but exponential in the input length $\log W$.
> - Knapsack is NP-hard, so no known truly polynomial-time algorithm exists.
##### **Coin Change**
> [!NOTE]
> 
> - **Input:** amount $n$ cents, denominations $d_1, d_2, \dots, d_k$
> - **Output:** fewest coins to make exactly $n$ cents
> - Greedy (largest first) does NOT work in general
> 
> **Recurrence.** Let $M[j]$ = min coins to make $j$ cents.
> 
> $$M[j] = \begin{cases} 0 & j = 0 \\ \infty & j < 0 \ 1 + \min_{i \in [k]} M[j - d_i] & j > 0 \end{cases}$$
> 
> - Optimal substructure: if $M[j] = t$ using coins $d_{i_1} + \dots + d_{i_t}$, then $M[j'] = t - 1$ where $j' = j - d_{i_t}$ (by cut-and-paste)
> **Coin Change Algorithm (Bottom-up)**
> 
> ```
> NUM-COINS-DP(n, d):
>   For j = 0 to n: M[j] = inf
>   M[0] = 0
>   For j = 1 to n:
>     For i = 1 to k:
>       If (j - d_i >= 0) and (M[j - d_i] + 1 < M[j]):
>         M[j] = M[j - d_i] + 1
>   Return M[n]
> ```
> 
> - Time: $O(nk)$

 ##### **Convex Polygon Triangulation**
> [!NOTE]
>
> ![[Screenshot 2026-04-20 at 5.27.22 PM.png]]
> - Given convex polygon with $n$ ($n \geq 2$) vertices labeled $1, 2, \ldots, n$. Triangulate into $n - 2$ triangles.
> - Triangle $(x, y, z)$ has weight $W(x, y, z)$ (black-box $O(1)$ function).
> - Objective: minimize total weight of all $n - 2$ triangles.
> 
> **Subproblem definition**
> - $TRI(x, y)$ = minimum weight triangulation of the sub-polygon using vertices $(x, x+1, \ldots, y)$.
> - Answer: $TRI(1, n)$.
> 
> **Recurrence** 
> - If $y-x=1$: $TRI(x,y) = 0$
> - Else: $TRI(x,y) = \displaystyle\min_{k \in [x+1, y-1]} \left[ TRI(x, k) + W(x, k, y) + TRI(k, y) \right]$
> 
> - Base case: $y - x = 1$ means just two adjacent vertices (a line segment), no triangle possible, cost 0.
> - Recursive case: fix edge $(x, y)$ as one side of a triangle. Try every $k$ between $x$ and $y$ as the third vertex. This creates triangle $(x, k, y)$ and splits the remaining polygon into two sub-polygons $(x, \ldots, k)$ and $(k, \ldots, y)$.
> 
> **Naive recursion: $O(3^n)$**
> - Recurrence for runtime: $T(n) = \sum_{k=2}^{n-1} [T(k) + T(n-k+1) + c]$.
> - Expanding $T(n)$ and $T(n-1)$ and subtracting: $$T(n) - T(n-1) = 2T(n-1) + c \implies T(n) = 3T(n-1) + c \implies T(n) \in O(3^n)$$
> - Exponential because of **many overlapping subproblems**: there are only $O(n^2)$ distinct $(x, y)$ pairs but the naive recursion recomputes them exponentially many times.
> 
> **Top-Down DP (memoization): $O(n^3)$**
> - Create 2D memo table of size $n \times n$, initialized to $-1$.
> - In $TRI(x, y)$: if $memo[x][y] \neq -1$, return it. Otherwise compute, store in $memo[x][y]$, and return.
> - $O(n^2)$ distinct subproblems, each computed once in $O(n)$ (iterating over $k$).
> - Total: $O(n^2 \times n) = O(n^3)$.
> 
> **Bottom-Up DP (tabulation): $O(n^3)$**
> - Same $n \times n$ table, but must fill in correct order.
> - $TRI(x, y)$ depends on $TRI(x, k)$ and $TRI(k, y)$ for all $k$ between $x$ and $y$, i.e., all entries in the same row to the left and same column below. These are all sub-polygons with fewer vertices.
> - Correct fill order: **anti-diagonally** by increasing gap $\Delta = y - x$. Base case sits at $\Delta = 1$, then fill $\Delta = 2, 3, \ldots, n-1$.
> 
> ```
> // Base case: Δ = 1 (adjacent vertices, no triangle)
> for each x in [1..n-1]:
>     TRI[x][x+1] = 0
> 
> // Recursive case: fill anti-diagonally
> for each Δ in [2..n-1]:
>     for each x in [1..n-1-Δ]:
>         y = x + Δ
>         TRI[x][y] = ∞
>         for each k in [x+1..y-1]:
>             TRI[x][y] = min(TRI[x][y], TRI[x][k] + W(x,k,y) + TRI[k][y])
> 
> return TRI[1][n]
> ```
> - Three nested loops $\Rightarrow O(n^3)$ time. $O(n^2)$ space.
> - Same asymptotic complexity as top-down. Bottom-up avoids recursion overhead but requires figuring out the fill order.
> 
> **Why anti-diagonal fill order?**
> - When computing $TRI[x][y]$ with gap $\Delta$, all needed subproblems $TRI[x][k]$ and $TRI[k][y]$ have gap $< \Delta$ (since $k$ is strictly between $x$ and $y$). So processing by increasing $\Delta$ guarantees all dependencies are already computed.
> - This is unlike typical 2D DP where row-by-row left-to-right works. Here the dependency structure follows the DAG's topological order along anti-diagonals.
> 
> **Connection to Matrix Chain Multiplication**
> - Same recurrence structure. Matrix chain: $M(i, j) = \min_{k} [M(i,k) + M(k+1,j) + p_{i-1}p_k p_j]$. Both are interval DP problems with $O(n^2)$ subproblems, $O(n)$ choices per subproblem, $O(n^3)$ total.
##### **Min Difference $|S_X - 2 S_Y|$ (Subset Sum variant)**
> [!NOTE]
> - **Problem:** Partition indices into $X, Y$ to minimize $|\sum_{i \in X} A[i] - 2 \sum_{i \in Y} A[i]|$
> - **Key insight:** Let $S = \sum A[i]$, $t = \sum_{i \in Y} A[i]$. Then $$|S_X - 2S_Y| = |(S-t) - 2t| = |S - 3t| = 3 \cdot |S/3 - t|$$
> - **Reduction:** Find subset sum $t$ closest to $S/3$ → standard subset-sum DP
> - **State:** $m[p, k] = 1$ iff some subset of $A[1..k]$ sums to $p$
> - **Recurrence:**
> 
> $$m[p, k] = \begin{cases} 1 & k=0, p=0 \ 0 & k=0, p \neq 0 \ \max{m[p, k-1],\ m[p - A[k], k-1]} & k > 0,\ p \geq A[k] \ m[p, k-1] & \text{otherwise} \end{cases}$$
> 
> - **Answer:** Scan $m[p, n]$ for $p$ closest to $S/3$ with $m[p,n]=1$, return $|S - 3p|$
> - **Order:** Fill by increasing $k$ (each layer depends only on $k-1$)
> - **Complexity:** $O(n^2 M)$ time, since $S \leq nM$
> 
> > **Trick to remember:** Whenever you see "minimize weird linear combination of two subset sums," try to algebraically reduce to "find subset sum closest to some target." It's almost always subset-sum DP underneath.

 ##### **Max Sum, No Two Adjacent (House Robber)**
> [!NOTE]
> - **Problem:** Pick subset of $A[1..n]$ with no two adjacent indices, maximize sum (empty set allowed, sum $= 0$)
> - **State:** $m[i] =$ max sum using elements from $A[1..i]$ with no two adjacent
> - **Choice at index $i$:** include $A[i]$ (then skip $i-1$) or exclude $A[i]$
> - **Recurrence:**
> 
> $$m[i] = \begin{cases} 0 & i = 0 \ \max{0, A[1]} & i = 1 \ \max{m[i-2] + A[i],\ m[i-1]} & \text{otherwise} \end{cases}$$
> 
> - **Answer:** $m[n]$
> - **Complexity:** $O(n)$ time, $O(1)$ space (only need last two values)
> 
> > **Why $\max{0, A[1]}$ for base case?** Elements can be negative, so empty subset (value 0) might beat including $A[1]$.
##### **Knapsack with Item Count Cap (≤ R items)**
> [!NOTE]
> - **Problem:** Standard 0/1 knapsack but additionally pick **at most $R$ items**
> - **State:** $m[i, j, k] =$ max value using first $i$ items, weight $\leq j$, count $\leq k$
> - **Recurrence:**
> 
> $$m[i, j, k] = \begin{cases} 0 & i=0 \lor j=0 \lor k=0 \ \max{m[i-1, j-w_i, k-1] + v_i,\ m[i-1, j, k]} & w_i \leq j \ m[i-1, j, k] & \text{otherwise} \end{cases}$$
> 
> - **Answer:** $m[n, W, R]$
> - **Order:** Fill by increasing $i$ (each layer depends only on $i-1$)
> - **Complexity:** $O(nWR)$ time
> 
> > **Pattern:** When you see "do problem $P$ but with an extra constraint $\leq C$," add a dimension to the DP state tracking that constraint and decrement it on every "take" transition.
> 

---
#### 7. Greedy
##### **Template**
**Greedy Choice Property**
1. Let O be any optimal solution to problem P. Let g be the greedy choice.
2. Case 1: O begins with g. Then an optimal solution beginning with g exists. Done.
3. Case 2: O begins with some other choice x (x != g). Construct O' = (O \ x) $\cup$ g, i.e. swap x for g.
4. Argue that cost(O') <= cost(O). (This is the exchange argument - problem-specific.)
5. Since O was optimal and cost(O') <= cost(O), O' is also optimal.
6. Therefore there exists an optimal solution that begins with the greedy choice g.

**Optimal Substructure Property**
1. Let O be an optimal solution to P that begins with g (guaranteed to exist by the greedy choice property).
2. Let P' = P after committing to g (the remaining subproblem).
3. Let O' = O \ g (the remainder of O after removing g).
4. O' is a feasible solution to P', and cost(O) = cost(g) + cost(O').
5. Claim: O' is optimal for P'.
6. Proof by contradiction. Suppose O' is not optimal for P'. Then there exists some feasible solution O'' to P' with cost(O'') < cost(O').
7. Construct S = g union O''. S is a feasible solution to P.
8. cost(S) = cost(g) + cost(O'') < cost(g) + cost(O') = cost(O).
9. This contradicts the optimality of O.
10. Therefore O' must be optimal for P'.

**Conclusion**: By induction, the greedy algorithm produces an optimal solution. At each step, committing to the greedy choice is safe (greedy choice property), and the residual problem is a smaller instance with the same structure (optimal substructure). Repeating until the base case yields a complete optimal solution.
##### **Overview**
- Recast the problem so that only **one subproblem** needs to be solved at each step. Beats divide-and-conquer and dynamic programming, when it works.
- At every step, choose one subproblem. Must prove that the choice is correct and optimal.
- Correctness requires: **greedy-choice property** AND **optimal substructure property**
##### **DP vs Greedy**
- DP: optimal substructure + overlapping subproblems. Avoids repeated computation but still goes over every possible solution.
- Greedy: optimal substructure + each step chooses only one subproblem. Does **not** consider every possible solution. Need to prove optimality.
##### **Semi-Fractional Knapsack**
> [!NOTE]
> **Definition**
> - Input: $(w_1, v_1), (w_2, v_2), \ldots, (w_n, v_n)$ and $W$
> - Output: integer weights $x_1, \ldots, x_n$ that maximize $\sum_i v_i \cdot \frac{x_i}{w_i}$ subject to: $\sum_i x_i \leq W$ and $0 \leq x_j \leq w_j$ for all $j \in {1, 2, \ldots, n}$
> - (Semi)-Fractional: allowed to take fractional parts of items. Standard Knapsack: take or don't take.
> 
> **Optimal Substructure (cut-and-paste proof)**
> - If we remove $w$ kgs of item $j$ from the optimal knapsack, the remaining load must be the optimal knapsack weighing at most $W - w$ kgs from the $n-1$ original items and $w_j - w$ kgs of item $j$.
> - Proof: let $X$ be the value of the optimal knapsack. Suppose remaining load after removing $w$ kgs of item $j$ was not optimal for weight $W - w$.
>     - Then there exists a knapsack of value $> X - v_j \cdot \frac{w}{w_j}$ with weight $\leq W - w$ among the $n-1$ other items and $w_j - w$ kgs of item $j$.
>     - Combining with $w$ kgs of item $j$ gives value $> X$ with weight $\leq W$. Contradiction.
> 
> **DP formulation** (too slow)
> - Let $m[i, j]$ = maximum value using subset of items ${1, 2, \ldots, i}$ with total weight $\leq j$.
> $$
> m[i, j] = \max \begin{cases} m[i-1, j] \\ m[i-1, j-1] + v_i \cdot \frac{1}{w_i} \\ m[i-1, j-2] + v_i \cdot \frac{2}{w_i} \\ \ldots \\ m[i-1, \max{j - w_i, 0}] + v_i \cdot \frac{\min{w_i, j}}{w_i} \end{cases} 
> $$
> - Output: $m[n, W]$. Time complexity: $O(nW^2)$. Too many branches.
> 
> **Greedy-choice property**
> - For item $i$, each kg of item $i$ is worth $\frac{v_i}{w_i}$. Intuition: prioritise items with larger $\frac{v_i}{w_i}$.
> - **Claim**: let $j^*$ be the item with maximum value/kg $v_j/w_j$. Then there exists an optimal knapsack containing $\min(w_{j^*}, W)$ kgs of item $j^*$.
> - Proof (exchange argument): given any solution not containing $\min(w_{j^*}, W)$ kgs of $j^*$, decrease 1 kg of any other item $j$ and increase 1 kg of $j^*$. Value decreases by $v_j/w_j$, increases by $v_{j^*}/w_{j^*}$. Since $v_{j^*}/w_{j^*}$ is maximum, total value increases. Contradiction.
> - If $w_{j^*} \geq W$: spend all $W$ kgs on $j^*$. Else: take $j^*$ whole and recurse on $W - w_{j^*}$.
> 
> **Greedy strategy**
> 1. Cast the problem where we make a choice and are left with one subproblem.
> 2. Prove there is always an optimal solution that makes the greedy choice (greedy-choice property).
> 3. Use optimal substructure to show combining greedy choice + optimal subproblem solution = optimal overall solution.
> 
> **Iterative greedy algorithm**
> 
> ```
> ITER-FRAC-KNAPSACK(v, w, W):
>     ValPerKg ← [1, 2, ..., n]
>     Sort ValPerKg using ≼ where i ≼ j if v[i]/w[i] ≤ v[j]/w[j]
>     for i = n to 1:
>         if W = 0: break
>         j ← ValPerKg[i]
>         k ← min(w[j], W)
>         print "k kgs of item j"
>         W ← W - k
>     return
> ```
> 
> - Correct because of greedy-choice property + optimal substructure. Time: $O(n \log n)$.
> 
> 
##### **Minimum Spanning Trees**
> [!NOTE]
> **Definition**
> - Input: connected, undirected graph $G = (V, E)$ with weight function $w: E \to \mathbb{R}^+$.
> - All edge weights assumed distinct for simplicity.
> - Output: a spanning tree $T$ (connects all vertices) of minimum weight.
> 
> **MST Optimal Substructure**
> - Theorem: remove any edge $(u, v) \in T$. Then $T$ is partitioned into two subtrees $T_1$ and $T_2$.
> - $T_1$ is an MST of $G_1 = (V_1, E_1)$, the subgraph of $G$ induced by vertices of $T_1$: $V_1 = \text{vertices of } T_1$, $E_1 = \{(x,y) \in E : x, y \in V_1\}$. Similarly for $T_2$.
> - **Proof (cut-and-paste):** 
> 	- $w(T) = w(u,v) + w(T_1) + w(T_2)$. 
> 	- If $T_1'$ were a lower-weight spanning tree than $T_1$ for $G_1$, then $T' = {(u,v)} \cup T_1' \cup T_2$ would be lower-weight than $T$ for $G$. Contradiction.
> - MST also has overlapping subproblems (DP could work), but MST has a greedy property enabling an even more efficient algorithm.
> 
> **MST Greedy-choice property**
> - Theorem: let $T$ be the MST of $G = (V, E)$, and let $A \subseteq V$. Suppose $(u, v) \in E$ is the least-weight edge connecting $A$ to $V - A$. Then $(u, v) \in T$.
> - **Proof (exchange argument):** 
> 	- Suppose $(u, v) \notin$ MST.
> 	- Let $e$ be the edge on the path connecting $(u,v)$ in the MST that connects $A$ and $V-A$. Replace $e$ with $(u,v)$. 
> 	- Since $w(u,v) < w(e)$ (all weights distinct), the weight of the spanning tree decreases. Contradiction.
> 	- So $(u,v)$ must be in the MST.
> 
> **Prim's Algorithm**
> - Start with arbitrary vertex $v$, set $A = {v}$, $T = \emptyset$.
> - At each step: let $e$ be the least-weight edge connecting $A$ and $V - A$. Add $e$ to $T$. Update $A$ as the vertices connected by $T$.
> - Until $A = V$. Output $T$.
> - Implementation: using a priority queue (min-heap).
> 
> **Kruskal's Algorithm**
> - At each step, add a least-weight edge that does **not** cause a cycle.
> - Greedy-choice property: any edge that is not a maximum weight edge in a cycle must be in the MST.
> - Implementation: using union-find to detect cycles.
##### **Huffman Code**
> [!NOTE]
> **Binary Coding Setup**
> - Alphabet set $A: {a_1, a_2, \ldots, a_n}$. A text file is a sequence of alphabets.
> - Fixed-length coding: encode each alphabet to a unique binary string of the same length $\lceil \log_2 n \rceil$. Easy to decode (just split every $\lceil \log_2 n \rceil$ bits). Suboptimal when frequencies vary hugely.
> - Key insight: more frequent alphabets $\leftarrow$ shorter bit string. Less frequent alphabets $\leftarrow$ longer bit string.
> - $\text{ABL}(\gamma) = \sum_{x \in A} f(x) \cdot |\gamma(x)|$, where $f(x)$ is frequency and $|\gamma(x)|$ is code length.
> 
> **Prefix Coding**
> - A coding $\gamma(A)$ is prefix coding if there do not exist $x, y \in A$ such that $\gamma(x)$ is a prefix of $\gamma(y)$.
> - Algorithmic problem: given set $A$ of $n$ alphabets and their frequencies, compute prefix coding $\gamma$ such that $\gamma$ is prefix coding and $\text{ABL}(\gamma)$ is minimum.
> 
> **Prefix Code and Labelled Binary Tree**
> - Theorem: for each prefix code of $A$ with $n$ alphabets, there exists a binary tree $T$ on $n$ leaves such that:
>     - There is a bijective mapping between alphabets and leaves.
>     - Label of path from root to a leaf = prefix code of corresponding alphabet.
> - Therefore: $\text{ABL}(\gamma) = \sum_{x \in A} f(x) \cdot |\gamma(x)| = \sum_{x \in A} f(x) \cdot |\text{depth}_T(x)|$
> - Optimal tree must be a **full binary tree**: every internal node has degree exactly 2. (If not, we can shorten the code of some alphabet without changing others.)
> 
> **Observations on Optimal Tree (Greedy-choice property)**
> - Let $a_1, a_2, \ldots, a_n$ be alphabets in non-decreasing order of frequency.
> - Higher frequency $\to$ shorter depth in tree. Lower frequency $\to$ deeper in tree.
> - $a_1$ (lowest frequency) must be at the deepest level. Proof: suppose $a_1$ is at a shallower level. Then there exists some other leaf $a_i$ deeper than $a_1$. Swapping $a_1$ with $a_i$ increases $a_1$'s depth and decreases $a_i$'s — total ABL cannot increase (since $f(a_1) \leq f(a_i)$). So $a_1$ belongs at deepest level.
> - Sibling of $a_1$ must also be a leaf. The sibling of $a_1$ can be $a_2$ (same swap argument and contradiction).
> - **Lemma**: there exists an optimal prefix coding in which $a_1$ and $a_2$ appear as siblings in the corresponding labeled binary tree.
> - **Important**: it is inaccurate to claim "in **every** optimal prefix coding, $a_1$ and $a_2$ appear as siblings." The lemma only claims existence of one such optimal tree. Algorithmically, we just focus on that tree.
> 
> **Subproblem Structure (Optimal Substructure)**
> - Combine $a_1$ and $a_2$ into a new alphabet $a_{1,2}$ with $f(a_{1,2}) = f(a_1) + f(a_2)$.
> - Consider alphabet set ${a_3, \ldots, a_n, a_{1,2}}$.
> - Any coding for ${a_3, \ldots, a_n, a_{1,2}}$ can be converted to a coding for ${a_1, \ldots, a_n}$ with ABL increased by $f(a_1) + f(a_2)$ (since $a_1, a_2$ are one level deeper than $a_{1,2}$).
> - Optimal coding for ${a_3, \ldots, a_n, a_{1,2}}$ can be converted to optimal coding for ${a_1, \ldots, a_n}$.
> - Greedy-choice property + Optimal Substructure $\Rightarrow$ Huffman's algorithm is correct.
> 
> **Huffman Algorithm**
> ```
> HUFFMAN-CODE({a1, ..., an}):
>     if n = 1: output a single node
>     Find two alphabets a1, a2 with least frequency
>     Replace a1, a2 with a_{1,2} with frequency f(a_{1,2}) = f(a1) + f(a2)
>     Run HUFFMAN-CODE({a3, ..., an, a_{1,2}})
>     Replace node a_{1,2} with two children a1 and a2
> ```
> - Implementation: use a min-heap (priority queue) for efficient extraction of two minimum-frequency nodes. Time: $O(n \log n)$.
##### **Burning CDs**
> [!NOTE]
> - $n$ music files, each $< 100$ MB. Each CD holds 100 MB and **at most 2 files**. Files cannot be split. Minimize number of CDs.
> 
> **Optimal substructure**
> - For any pair $f_1, f_2$ that share a CD in an optimal solution: $MinCD(A) = 1 + MinCD(A \setminus {f_1, f_2})$.
> - Proof (cut-and-paste): remove the pair from the first CD. Remaining must be optimal, else replacing it with a better allocation contradicts optimality of the original.
> - Note: you cannot just pair **any** two files, nor always pair smallest + largest (largest + smallest may exceed 100 MB).
> 
> > **Counterexample (pairing smallest + largest blindly)**: $A = {10, 20, 30, 95, 99}$. Smallest $= 10$, largest $= 99$, sum $= 109 > 100$. Does not fit. Optimal is ${10, 20}, {30}, {95}, {99}$ = 4 CDs.
> 
> **Greedy-choice property (two parts)**
> 
> _Part 1: smallest file can always be in a pair (if any pair exists in OPT)._
> - If smallest file $f$ is already paired in OPT, done.
> - If not, $f$ is alone. Some other pair ${a, b}$ exists in OPT. Swap $f$ with $a$. Since $\text{size}(f) \leq \text{size}(a)$ and $a + b \leq 100$, we get $f + b \leq 100$. Also $a \leq 100$ so $a$ alone on a CD is fine. Total CDs unchanged. Exchange argument works.
> 
> _Part 2: smallest file $f_1$ can be paired with the largest file $f_2$ that fits with it._
> - From Part 1, some OPT has $f_1$ in a pair. If $f_1$ is paired with some $f_3 \neq f_2$, swap $f_3$ with $f_2$:
>     - If $f_2$ was unpaired: ${f_1, f_2}$ fits (since $f_2$ is the largest that fits with $f_1$), $f_3$ goes alone. No extra CDs.
>     - If $f_2$ was paired with $f_4$: before swap ${f_1, f_3}$ and ${f_2, f_4}$. After swap ${f_1, f_2}$ and ${f_3, f_4}$. Since $f_2 > f_3$ and $f_2 + f_4 \leq 100$, we get $f_3 + f_4 \leq 100$. Still 2 CDs.
> - Note: pairing smallest with **largest overall** (not largest that fits) is **wrong**.
> 
> **Algorithm**
> 1. Sort file sizes. (Can use counting sort in $O(n)$ if sizes are small integers in $[0..100]$.)
> 2. Two pointers: `lo = 0` (smallest), `hi = n-1` (largest).
> 3. While `lo <= hi`:
>     - If $A[lo] + A[hi] \leq 100$: pair them on one CD, advance `lo`, retreat `hi`.
>     - Else: $A[hi]$ alone on one CD, retreat `hi` only.
> 4. Return total CDs used.
> 
> - Time: $O(n \log n)$ for sort, $O(n)$ for two-pointer pass.
> 
> 
##### **Activity Selection**
> [!NOTE]
> - $n$ activities $S = {a_1, \ldots, a_n}$, each with interval $[s_i, f_i)$ (start inclusive, finish exclusive).
> - Two activities compatible iff $s_i \geq f_j$ or $s_j \geq f_i$ (no overlap).
> - Goal: find the **largest** subset of mutually compatible activities.
> 
> **Which greedy strategies work?**
> - **Starts last**: Correct. Proven below.
> - **Ends last**: Wrong.
>     - Counterexample: $a_1 = [1, 10), a_2 = [1, 5), a_3 = [6, 9)$. $a_1$ ends last, picked, blocks everything. Optimal: ${a_2, a_3}$.
> - **Shortest activity**: Wrong.
>     - Counterexample: $a_1 = [1, 4), a_2 = [3, 5), a_3 = [4, 10)$. $a_2$ is shortest, picked, blocks everything. Optimal: ${a_1, a_3}$.
> - (Equivalent correct strategy from CLRS: **ends first**, which is the mirror of starts last.)
> 
> **Optimal substructure**
> - If optimal schedule $S$ contains activity $a_j$, define:
>     - $Before_j = {a_i : f_i \leq s_j}$ (finish before $a_j$ starts)
>     - $After_j = {a_i : s_i \geq f_j}$ (start after $a_j$ finishes)
> - $S$ must also contain optimal schedules for $Before_j$ and $After_j$. Proof by contradiction (cut-and-paste): if either sub-schedule were suboptimal, replacing it gives a better overall schedule, contradicting optimality of $S$.
> 
> **Greedy-choice property (starts last)**
> - Let $a^*$ be the activity with the latest start time overall. Let $a$ be the activity with the latest start time in some optimal solution $S$.
> - Exchange argument: replace $a$ with $a$ in $S$. Since $s_{a} \geq s_a$, activity $a$ starts no earlier than $a$, so it cannot conflict with anything that $a$ did not conflict with. Schedule remains compatible, same size. So the modified schedule with $a$ is also optimal.
> 
> **Algorithm**
> 1. Sort activities by start time in non-decreasing order: $O(n \log n)$.
> 2. Initialize empty schedule $S$.
> 3. Iterate in **reverse** order (latest start first):
>     - Select $a^*$ = latest-starting activity compatible with current $S$.
>     - Add $a^*$ to $S$.
> 4. Return $S$.
> 
> - After sorting, the greedy pass is $O(n)$. Total: $O(n \log n)$.
> 
> > **Example**: $a_1 = [3, 10), a_2 = [15, 20), a_3 = [5, 15)$.
> > 
> > - Sorted by start time: $a_1 = [3, 10), a_3 = [5, 15), a_2 = [15, 20)$.
> > - Reverse iteration: pick $a_2$ (starts at 15). Then $a_3$ conflicts ($f_3 = 15$, $s_{a_2} = 15$, compatible? $15 \geq 15$ yes). Actually $a_1$: $f_1 = 10 \leq 15$, compatible. Pick $a_1$.
> > - Result: ${a_1, a_2}$, size 2. Optimal.
> 

---
#### 8. Amortized Analysis
##### **Definition**
- Sequence of $n$ operations $o_1, o_2, \ldots, o_n$. $t(i)$ = true cost of $i$th op. 
- $T(n) = \sum_{i=1}^{n} t(i) \leq n \cdot f(n)$ where $f(n)$ = worst-case cost of any single op. Naive bound can be grossly wrong.
- Strategy to show average cost per op is small even if individual ops are expensive. **No probability involved**. Guarantees average performance per op in the worst case.
- Amortized cost $= T(n)/n$
- Amortized $\neq$ Average case: amortized is still worst-case analysis, just averaged over a sequence. Average case assumes a distribution over inputs and randomly samples an input.
##### **Three Methods of Amortized Analysis**
- Aggregate, Accounting (Banker's), Potential
- Aggregate is simplest but least precise. Accounting and Potential assign a specific amortized cost per operation.

**1. Aggregate**
- Just do brute force calculation

**2. Accounting (Banker's) Method**
- Charge $i$th op a fictitious amortized cost $c(i)$ (fixed). True cost $t(i)$ varies.
- Must satisfy: $\sum_{i=1}^{n} t(i) \leq \sum_{i=1}^{n} c(i)$ for all $n$
- Total amortized cost is upper bound on total true cost.
- Excess charge = **credit** stored for future expensive ops. Credit must never go negative. Different operations can have different amortized costs.

**3. Potential Method**
- $\phi$: potential function of the data structure. $\phi(i)$: potential after $i$th op. $c_i$: amortized cost. $t_i$: true cost. 
- Key relation: $c_i = t_i + \phi(i) - \phi(i-1)$
- Summing: $c_1 + c_2 + \cdots + c_n = t_1 + t_2 + \cdots + t_n + \phi(n) - \phi(0)$
- Set $\phi(0) = 0$. As long as $\phi(n) \geq 0$ for all $n$: $\sum c_i \geq \sum t_i$, so amortized cost is upper bound on true cost. 
- If $\Delta\phi > 0$: charge more amortized than true. If $\Delta\phi < 0$: charge less amortized than true (drawing from stored potential).
##### **Binary Counter (k-bit INCREMENT)**
> [!NOTE]
> 
> **Aggregate:**
> ```
> INCREMENT(A)
> 1. i ← 0
> 2. while i < length[A] and A[i] = 1 do
> 3.     A[i] ← 0       ▷ flip 1→0
> 4.     i ← i + 1
> 5. if i < length[A]
> 6.     then A[i] ← 1  ▷ flip 0→1
> ```
> - Attempt 1 (loose): Let $t(i)$ = no. of bit flips during $i$th increment
> 	- $T(n) = \sum_{i=1}^{n} t(i)$
> 	- Worst case $t(i) = \log n \Rightarrow T(n) \in O(n \log n)$
> 	- Not tight. Half of increments flip only 1 bit.
> - Attempt 2 (tighter): Let $f(i)$ = no. of times $i$th bit flips. 
> 	- $T(n) = \sum_{i=0}^{k-1} f(i)$
>     - $f(0)=n,\ f(1)=n/2,\ f(2)=n/4,\ f(i)=n/2^i$
>     - $T(n) = n\sum_{i=0}^{k-1} 2^{-i} < 2n \Rightarrow T(n) \in O(n)$
> 
> **Accounting:**
> - Charge $\$2$ for each $0 \to 1$ flip. \$1 pays for the actual set, \$1 stored in bank on that bit.
> - $1 \to 0$ reset is paid by the stored $1 (free).
> - Invariant: every 1-bit in counter has \$1 in bank. After $i$ increments, bank balance = number of 1s in binary rep of $i$ $\geq 0$.
> - Amortized cost per increment $= $2 \in O(1)$. 
> 	- Amortized cost for $n$ increments $= 2n \in O(n)$. 
> 	- Actual cost for $n$ increments $= O(n)$.
##### Queue Example
> [!NOTE]
> **Definition**
> - INSERT: $\Theta(1)$. 
> - EMPTY (delete all one-by-one): $\Theta(n)$ worst case.
> - Key insight: #DELETEs $\leq$ #INSERTs. If $k$ INSERTs in sequence, total EMPTY cost $\leq k$.
> - Total cost $\leq k + k = 2k \leq 2n \Rightarrow$ amortized cost $O(1)$.
> 
> **Accounting:**
> - INSERT: amortized cost = 2 (true cost = 1). 
> - EMPTY: amortized cost = 0 (true cost = queue size).
> - Each INSERT pays extra $1 as credit for its future DELETE.
> - Total cost $\leq 2 \times \text{NUM\_INSERT} \leq 2n$
> 
> **Potential:**
> - $\phi(i)$ = number of elements in queue after $i$th op. $\phi(0)=0$, $\phi(n) \geq 0$ always.
> - INSERT: $c_i = t_i + \phi(i) - \phi(i-1) = 1 + 1 = 2$
> - EMPTY ($k$ elements): $c_i = t_i + \phi(i) - \phi(i-1) = k + 0 - k = 0$
##### **Dynamic Table**
> [!NOTE]
> **Definition**
> - Goal: table as small as possible but no overflow. Problem: size unknown in advance.
> - Solution: when full, allocate new table of **double** the size via `malloc`/`new`, copy all elements, free old.
> 
> **Aggregate** 
> $$t(i) = \begin{cases} i & \text{if } i-1 \text{ is exact power of 2} \\ 1 & \text{otherwise} \end{cases}$$
> - Cost of $n$ insertions $= \sum_{i=1}^{n} t(i) \leq n + \sum_{j=0}^{\lfloor\log(n-1)\rfloor} 2^j \leq n + 2(n-1) \leq 3n$
> - Average cost per insertion $= O(n)/n = O(1)$
> 
> **Accounting**
> - Charge $3 per insertion.
> - $1 for inserting into current table
> - $\$1$ stored for moving this item when table expands
> - $\$1$ stored for moving one of the existing $m/2$ items when table expands (table has size $m$, holds $m/2$ elements after expansion)
> - New elements have credit to pay for old elements. Total cost $\leq 3n \in O(n)$.
> 
> **Potential** 
> - $\phi(i) = 2i - l$ where $l = \text{size of current table}$.
> - Case 1 (table not full): $t_i = 1$, $\phi(i-1) = 2(i-1) - l$, $\phi(i) = 2i - l$, $\Delta\phi_i = 2$, $c_i = 1 + 2 = 3$
> - Case 2 (table full, size was $i-1$): $t_i = i$, $\phi(i-1) = 2(i-1)-(i-1)=i-1$, $\phi(i) = 2i - 2(i-1) = 2$, $\Delta\phi_i = 2-(i-1) = 3-i$, $c_i = i + (3-i) = 3$
> - Amortized cost for $n$ insertions $= 3n \in O(n)$. Actual cost $= O(n)$.
##### **Union-Find / Disjoint Set**
> [!NOTE]
> **Definition**
> - $n$ objects. Initially $n$ singleton sets. Two operations:
>     - `Union(p,q)`: combines sets containing $p$ and $q$
>     - `Find(p,q)`: checks if $p$ and $q$ in same set
> 
> **Quick-Find**
> - array `id[1..n]`. Same set $\Rightarrow$ same id.
> - `Union(p,q)`: for all $r$ with `id[r]=id[p]`, set `id[r]=id[q]`
> - `Find(p,q)`: check `id[p]==id[q]`
> - Find: $O(1)$, Union: $O(n)$
> 
> **Lazy / Quick-Union**
> - `id[i]` = parent of $i$. Root when `id[i]=i`.
> - `root(i)`: follow `id[id[...id[i]...]]` until stable
> - `Union(p,q)`: `id[root(p)] = root(q)`
> - `Find(p,q)`: `root(p)==root(q)`
> - Cost depends on depth; depth can be very large (e.g., calling `Union(1,2), Union(1,3), Union(1,4),...` creates a chain)
> - Both Union and Find call `root` 2 times. Only need to analyse cost of `root`.
> 
> **Path Compression**
> - after calling `root(i)`, set `id` of every node on the path directly to the root.
> - Tree gets flattened; future ops much cheaper. Amortized cost $= O(\log n)$.
> - Classify edges: for node $i$ with parent $j$:
>     - edge $(i,j)$ is **blue** if $\text{size}(i) \leq \text{size}(j)/2$
>     - edge $(i,j)$ is **red** if $\text{size}(i) > \text{size}(j)/2$
>     - On path from any node to root: at most $\log n$ blue edges (size at least doubles each blue step).
>     - Depth $= O(\log n) + \text{num red edges}$
>     - Observation: if $j$ is not a root, after path compression $\text{size}(j)$ decreases by $\text{size}(i)$. If $(i,j)$ is a red edge, $\text{size}(j)$ decreases by at least half.
> 
> ***Path Compression Potential***
> - $\phi_i = \log(\text{size}(i))$, $\phi = \sum_i \phi_i$
> - If $(i,j)$ is red and $j$ is not root, after path compression $\text{size}(j)$ decreases by $\text{size}(i) \Rightarrow \phi_j$ decreases by at least 1.
> - If path has $\alpha$ red edges, $\phi$ decreases by at least $\alpha - 1$.
> 
> ***Union-Find Amortized Cost***
> - for $T$ total ops, let $\phi^+(t)$ = potential increase from Union at op $t$, $\phi^-(t)$ = potential decrease from path compression at op $t$.
> - $\text{Cost}(t) = O(\log n + \phi^-(t))$
> - $\phi^+(t) = O(\log n)$ (Union changes one root pointer; $\phi$ increases by at most $\log n$)
> - $\phi(0)=0,\ \phi(t) \geq 0 \Rightarrow \sum_{t=1}^{T}\phi^+(t) \geq \sum_{t=1}^{T}\phi^-(t)$
> - $\sum_{t=1}^{T}\text{Cost}(t) = O(T\log n) + O!\left(\sum\phi^-(t)\right) = O(T\log n) + O!\left(\sum\phi^+(t)\right) = O(T\log n)$
##### Example Question
> [!NOTE]
> **Problem**
> - Suppose we perform a sequence of $n$ operations
> - The $i$-th operation costs $i^2$ if $i$ is a power of 2, and costs 1 otherwise.
> - What is the asymptotic amortized cost per operation?
> 
> **Answer**
> - $\Theta(n^2)$: The sum is at least $n^2$

##### **Amortized Analysis Summary**
- Amortized costs provide a clean abstraction of data-structure performance.
- All 3 methods are valid; aggregate is simplest, accounting and potential are more precise.
- Potential function choice can be tricky — sometimes need to try different options.
- Actual cost $\leq$ Amortized cost (guaranteed by non-negative bank balance / non-negative potential).
---
#### 9. Reductions and Intractability
##### **Reductions**
- Given two problems $A$ and $B$, $A$ **reduces to** $B$ ($A \le_P B$) means: we can solve $A$ using a solver for $B$
- Pipeline: instance $\alpha$ of $A$ $\to$ convert to instance $\beta$ of $B$ $\to$ solve $B(\beta)$ $\to$ output $A(\alpha)$
- Two conditions:
    1. $\alpha$ is a YES-instance of $A$ $\iff$ $\beta$ is a YES-instance of $B$
    2. The transformation $\alpha \to \beta$ runs in polynomial time
##### **$p(n)$-time Reduction**
- If $\alpha \to \beta$ takes $p(n)$ time, and $B$ runs in $T(n)$ time, then $A$ runs in $T(O(p(n))) + O(p(n))$ time
- Size of $\beta$ is at most $p(n)$ (cannot write more than $p(n)$ output in $p(n)$ time)
- **Polynomial-time reduction:** $A \le_P B$ if $p(n) = O(n^c)$ for some constant $c$
##### **Implications of $A \le_P B$**
- If $B$ is solvable in poly-time, then so is $A$
- Contrapositive: if $A$ is not solvable in poly-time, then neither is $B$
- $A \le_P B$ means $A$ is no harder than $B$ (equivalently, $B$ is at least as hard as $A$)
- Does NOT mean $B \le_P A$. The mapping is one-way: for every $\alpha$ there exists a $\beta$, but not necessarily the reverse
- Transitivity: $A \le_P B, B \le_P C \implies A \le_P C$
##### **Matrix Squaring  $\le_P$  Matrix Multiplication**
> [!NOTE]
> **Matrix Squaring $\le_P$ Matrix Multiplication**
> - Input: matrix $C$, want $C^2$
> - Set $A = C, B = C$, feed into Mat-Multi blackbox
> - $AB = C^2$. Done.
> 
> **Matrix Multiplication $\le_P$ Matrix Squaring**
> 
> - Input: matrices $A, B$, want $AB$
> - Construct: $M = \begin{bmatrix} 0 & A \\ B & 0 \end{bmatrix}$
> - Then $M^2 = \begin{bmatrix} AB & 0 \\ 0 & BA \end{bmatrix}$
> - Extract top-left block to get $AB$
> - Input size $n = N^2$ (two $N \times N$ matrices). Constructing $M$ and extracting result both take $O(N^2) = O(n)$, so this is an $O(n)$-time reduction.
> 
> **T-Sum $\le_P$ 0-Sum**
> 
> - T-Sum: given array $B$ and number $T$, find $i, j$ such that $B[i] + B[j] = T$
> - 0-Sum: given array $A$, find $i, j$ such that $A[i] + A[j] = 0$
> - Reduction: define $A[i] = B[i] - T/2$
> - If $A[i] + A[j] = 0$, then $B[i] + B[j] = T$
##### **Pseudo-polynomial Algorithms**
- An algorithm that runs in time polynomial in the **numeric value** of the input but exponential in the **length of the encoding**
- Example: Knapsack DP runs in $O(nW)$
    - Input size is $O(n \log W + \log W)$ since each number takes $\Theta(\log W)$ bits
    - $W$ can be exponential in input length (e.g. $W = 2^{\log W}$), so $O(nW)$ is not polynomial in input size
- Fractional Knapsack runs in $O(n \log n)$, which is polynomial in input size
- If input is a number n, then input size is $\log{n}$
- If input is n numbers, then input size is n
##### **Decision Problems**
- A decision problem maps an instance to ${\text{YES}, \text{NO}}$
- Any optimisation problem can be converted to a decision problem: "is there a solution with value $\le k$?" (minimisation) or "$\ge k$?" (maximisation)
- Decision $\le_P$ Optimisation: given the optimal value, just check if it meets the threshold
- If the decision version is hard, the optimisation version is also hard
##### **Reductions Between Decision Problems**
- For decision problems, the YES/NO answer is simply "copied" through the reduction
- We show $\alpha$ and $\beta$ are equivalent (same YES/NO answer), but this does not mean $A$ and $B$ are equivalent as problems
##### **3-SAT**
![[Screenshot 2026-03-29 at 12.02.00 PM.png]]
- **Literal:** a boolean variable $x_i$ or its negation $\overline{x_i}$
- **Clause:** a disjunction (OR) of literals, e.g. $C_j = x_1 \lor \overline{x_2} \lor x_3$
- **CNF:** a conjunction (AND) of clauses: $\Phi = C_1 \land C_2 \land \dots \land C_k$
- **3-SAT:** SAT where each clause has exactly 3 literals
- $\Phi$ is a YES-instance $\iff$ there exists at least one satisfying assignment
##### **Independent-Set**
- A set of vertices in a graph with no edges between any pair of them.
##### **Vertex cover**
- A set of vertices such that every edge in the graph has at least one endpoint in the set.
- **Independent set => Vertex cover:** Take the complement of the independent set; all remaining vertices form a vertex cover.
##### **Set cover** 
- Given a universe of elements and a collection of subsets, a selection of subsets whose union covers the entire universe.
- **Vertex cover => Set cover:** Treat each vertex as a set of incident edges; selecting vertices that cover all edges becomes selecting sets that cover the universe of edges.
##### **3-SAT $\le_P$ Independent-Set**
> [!NOTE] **3-SAT $\le_P$ Independent-Set**
> 
> **Reduction:**
> - For each clause in $\phi$, create 3 vertices in $G$ (one per literal)
> - Connect 3 literals within the same clause in a triangle (intra-clause edges)
> - Connect each literal to all occurrences of its negation across clauses (inter-clause edges)
> - Set $k$ = number of clauses
> 
> **Step 1:** Polynomial time. Graph has $3k$ vertices and $O(k^2)$ edges.
> 
> **Step 2 ($\Rightarrow$):** Suppose $\phi$ is satisfiable.
> - Pick one true literal per clause. This gives $k$ vertices.
> - No two are in the same clause (we pick one per triangle), so no intra-clause edge.
> - No two are negations of each other (both are true under the same assignment), so no inter-clause edge.
> - Therefore these $k$ vertices form an independent set.
> 
> **Step 3 ($\Leftarrow$):** Suppose $(G, k)$ has an independent set $S$ of size $k$.
> - Intra-clause edges force at most one vertex per clause. Since $|S| = k$ and there are $k$ clauses, exactly one vertex per clause.
> - Inter-clause edges ensure no two selected literals are negations. So setting all selected literals to true is consistent.
> - One true literal per clause means every clause is satisfied, so $\phi$ is satisfiable.

![[Screenshot 2026-03-29 at 4.53.29 PM.png]]
##### Independent-Set $\le_P$ Vertex-Cover
> [!NOTE] **Independent-Set $\le_P$ Vertex-Cover**
> 
> **Reduction:** Given $(G, k)$ for Independent-Set, output $(G, n - k)$ for Vertex-Cover, where $n = |V|$.
> 
> **Step 1:** Polynomial time. Same graph, just change the parameter.
> 
> **Step 2 ($\Rightarrow$):** Suppose $S$ is an independent set of size $\ge k$.
> 
> - Claim: $V \setminus S$ is a vertex cover of size $\le n - k$.
> - For any edge $(u, v) \in E$: both $u, v$ cannot be in $S$ (independent set). So at least one of $u, v$ is in $V \setminus S$.
> - Every edge has an endpoint in $V \setminus S$, so $V \setminus S$ is a vertex cover.
> 
> **Step 3 ($\Leftarrow$):** Suppose $S$ is a vertex cover of size $\le n - k$.
> 
> - Claim: $V \setminus S$ is an independent set of size $\ge k$.
> - If $(u, v) \in E$ with both $u, v \in V \setminus S$, then $S$ does not cover $(u, v)$. Contradiction.
> - So no two vertices in $V \setminus S$ are adjacent, i.e. $V \setminus S$ is an independent set.

##### Vertex-Cover $\le_P$ Set-Cover
> [!NOTE] **Vertex-Cover $\le_P$ Set-Cover**
> 
> **Reduction:** Given $(G, k)$ for Vertex-Cover, construct Set-Cover instance $(n, k', \mathcal{S})$:
> - In vertex-cover, we are choosing vertices to collect edges
> - In set-cover, we are choosing sets to collect elements
> - Vertex => Sets || Edges => Elements
> - $n = |E(G)|$, $k' = k$
> - Label edges $e_1, \dots, e_n$. Universe $U = {1, \dots, n}$.
> - For each vertex $v \in V(G)$: $S_v = {i : e_i \text{ is incident on } v}$
> - $\mathcal{S} = {S_v : v \in V(G)}$
> 
> **Intuition:** "vertex $v$ covers edge $e_i$" $\iff$ "subset $S_v$ contains element $i$"
> 
> **Step 1:** Polynomial time. Just relabelling edges as elements and vertices as sets.
> 
> **Step 2 ($\Rightarrow$):** Suppose vertex cover $U \subseteq V$ with $|U| \le k$.
> 
> - Every edge $e_i$ is incident to some $u \in U$, so $i \in S_u$.
> - $\bigcup_{u \in U} S_u = {1, \dots, n}$. Set cover of size $\le k = k'$.
> 
> **Step 3 ($\Leftarrow$):** Suppose set cover ${S_{v_1}, \dots, S_{v_t}}$ with $t \le k$.
> 
> - Each $S_{v_j}$ corresponds to vertex $v_j$, and their union covers all elements (edges).
> - So ${v_1, \dots, v_t}$ is a vertex cover of size $\le k$.
**Reductions Cheatsheet**

##### **Reduction: Partition $\leq_P$ Knapsack**
> [!NOTE]
> **Partition**: given positive integers ${w_1, \ldots, w_n}$ with total sum $S$, can they be split into two subsets of equal sum $S/2$?
> 
> **Knapsack (decision)**: given items with weights and values, capacity $W$, threshold $V$, is there a subset with weight $\leq W$ and value $\geq V$?
> 
> **Transformation**: from Partition instance ${w_1, \ldots, w_n}$, construct Knapsack instance with items ${(w_i, w_i)}$ (weight = value = $w_i$), capacity $W = S/2$, threshold $V = S/2$. Runs in $O(n)$.
> 
> $(\Rightarrow)$: if Partition is YES, subset $S_1$ sums to $S/2$. Use $S_1$ for Knapsack: weight $= S/2 \leq W$, value $= S/2 \geq V$. Knapsack YES.
> 
> $(\Leftarrow)$: if Knapsack is YES, subset $Z$ has weight $\leq S/2$ and value $\geq S/2$. Since weight = value for each item, the only possibility is weight = value = exactly $S/2$. So $Z$ and its complement partition the original set into equal sums. Partition YES.
##### **Reduction: Partition $\not\leq_P$ Ball-Partition (WRONG reduction)**
> [!NOTE]
> **Ball-Partition**: given $k$ balls, can they be divided into two boxes with equal count?
> 
> **Attempted transformation**: given Partition instance $S$, let $k = \sum S$.
> 
> **Why it fails**: $(\Leftarrow)$ direction breaks. $S = {1, 7}$, sum $= 8$. Ball-Partition with $k=8$: YES (split ${4,4}$). But Partition: NO (${1}$ vs ${7}$ are not equal). A YES for Ball-Partition does not imply YES for Partition.
> 
> The $(\Rightarrow)$ direction does work: if Partition is YES with two subsets summing to $S/2$ each, then $k = S$ is even and Ball-Partition is YES. But a reduction needs **both** directions.
##### **Reduction: Hamiltonian-Cycle $\leq_P$ TSP**
> [!NOTE]
> **HC**: given graph $G = (V, E)$, does $G$ have a cycle visiting every vertex exactly once?
> 
> **TSP (decision)**: given complete weighted graph, is there a tour of cost $\leq C$?
> 
> **Transformation**: from HC instance $G = (V, E)$, construct complete graph $G'$ on same vertices $V$:
> 
> - If $(u, v) \in E$: $w(u, v) = 1$
> - If $(u, v) \notin E$: $w(u, v) = 2$
> - Set threshold $C = n = |V|$.
> - Runs in $O(n^2)$ (at most $n(n-1)/2$ edges).
> 
> **Claim**: $G$ has a Hamiltonian cycle iff $G'$ has a TSP tour of cost $\leq n$.
> 
> $(\Rightarrow)$: if $G$ has HC $C$, then $C$ exists in $G'$ (since $G$ is a subgraph of complete $G'$). $C$ has $n$ edges, each with weight 1 in $G'$ (since they were in $E$). Total cost $= n$. TSP YES.
> 
> $(\Leftarrow)$: if $G'$ has tour $C$ of cost $\leq n$, then $C$ has $n$ edges. Each edge has weight $\geq 1$, so $n$ edges with total $\leq n$ means every edge has weight exactly 1. Weight 1 edges correspond to edges in $E$. So $C$ is a Hamiltonian cycle in $G$. HC YES.

##### **NP-Completeness**
- $P$: class of decision problems solvable in polynomial time
- $NP$: class of decision problems where a proposed solution can be **verified** in polynomial time
    - 3-SAT: given an assignment, check all clauses in $O(n)$
    - Independent Set: given a subset, check no two adjacent and $|S| \ge k$
- $NP$-complete: a problem $X$ is NP-complete if:
    1. $X \in NP$
    2. Every problem in $NP$ reduces to $X$ in poly-time ($\forall A \in NP, A \le_P X$)
- All NP-complete problems reduce to each other: $A \le_P B \le_P C \le_P \dots \le_P A$
- If any one NP-complete problem has a poly-time algorithm, then $P = NP$ and all of them do
- No poly-time algorithm is known for any NP-complete problem; this is the strongest evidence that $P \ne NP$\
##### **Additional notes**
1. Fractional knapsack can be poly-time reduced to knapsack: True. Fractional knapsack has poly-time algorithm. Any poly-time algorithm can be reduced to any problem.
2. Knapsack can be poly-time reduced to Fractional-Knapsack: We don't know if it's true or false. If P=NP then it's true, else false.
3. Knapsack can be poly-time reduced to 3-SAT: True. Knapsack is an NP problem. Any NP problem can be reduced to 3-SAT.

---
#### 10. Reductions and Intractability II
**Complexity Classes Overview**
- Complexity theory: classify problems into classes where each class has the same level of hardness. Even without knowing if a problem is hard, we can compare hardness of two problems.
- **P**: problems solvable in deterministic poly-time.
- **NP**: problems that poly-time reduce to 3-SAT (i.e., polynomial-time verifiable certificates of membership for YES-instances exist, of polynomial size). Short for "non-deterministic polynomial."
- **NP-Complete**: problems computationally equivalent to 3-SAT. In NP and NP-Hard.
- If 3-SAT has a poly-time algorithm $\Rightarrow$ every problem in NP is poly-time solvable $\Rightarrow$ P = NP.
- Problems believed hard form the basis of cryptosystems (credit cards, HTTPS, digital signatures).

**The class NP**
- NP (non-deterministic polynomial): class of problems for which polynomial-time verifiable **certificates** exist for YES-instances. Certificates are of polynomial size.
- Certificates only required for YES-instances. No certificate required for NO-instances.
- Intuition: proving a statement is TRUE is hard. But if someone gives you a proof, verifying it is easy.
- Equivalently: problems solvable in poly-time by a non-deterministic Turing machine.
- NP captures natural search problems — "we know we have the needle when we see it."

##### **Subset-Sum is NP-Complete**
> [!NOTE]
> _Step 1: Subset-Sum is in NP_
> - Problem: given set of integers $S$ and target $t$, is there $S' \subseteq S$ with $\sum_{s \in S'} s = t$?
> - Certificate: the subset $S'$ itself.
> - Verifier: sum elements of $S'$, check if equal to $t$. Poly-time.
> 
> _Step 2: Subset-Sum is NP-Hard (reduce from 3-SAT)_
> - Given 3-SAT instance $\Phi$ with $n$ variables $x_1, \ldots, x_n$ and $m$ clauses $C_1, \ldots, C_m$, construct a Subset-Sum instance.
> - For each variable $x_i$, create two numbers $v_i$ (for $x_i = T$) and $v_i'$ (for $x_i = F$).
> - For each clause $C_j$, create two "slack" numbers $s_j$ and $s_j'$.
> - Numbers are encoded in base 10 with $n + m$ digits (one column per variable, one column per clause). This avoids carry issues.
> - Variable digit columns ($i$-th column): $v_i$ and $v_i'$ both have a 1 in column $i$, all other variable numbers have 0 in column $i$.
> - Clause digit columns ($j$-th column): if literal $x_i$ appears in $C_j$, then $v_i$ has a 1 in clause column $j$. If $\bar{x_i}$ appears in $C_j$, then $v_i'$ has a 1 in clause column $j$. Slack $s_j$ has 1 in column $j$, $s_j'$ has 2 in column $j$ (or $s_j = 1, s_j' = 1$, depending on formulation).
> - Target $t$: has 1 in every variable column (exactly one of $v_i, v_i'$ chosen per variable) and 4 in every clause column (3 from literals + slacks fill up to 4).
> - Reduction is poly-time: $O(nm)$ to construct.
> - $(\Rightarrow)$: satisfying assignment picks $v_i$ or $v_i'$ per variable. Each clause has 1-3 true literals contributing 1-3 in its column. Slacks fill the remaining to reach 4.
> - $(\Leftarrow)$: target forces exactly one of $v_i, v_i'$ per variable (variable columns sum to 1). Clause columns sum to 4, and slacks contribute at most 3, so at least 1 must come from a literal, meaning each clause is satisfied.

##### **Ham-Cycle (undirected) is NP-Complete**
> [!NOTE]
> _Step 1: Ham-Cycle is in NP_
> 
> - Problem: given undirected graph $G$, is there a simple cycle visiting every vertex exactly once?
> - Certificate: the cycle itself (sequence of vertices).
> - Verifier: check (1) all $n$ vertices appear exactly once, (2) consecutive vertices (and last-to-first) are connected by edges in $G$. Poly-time.
> 
> _Step 2: Ham-Cycle is NP-Hard (reduce from Directed-Ham-Cycle)_
> 
> - Given directed graph $G = (V, E)$ with $n$ vertices, construct undirected graph $G'$ such that $G$ has a directed Hamiltonian cycle iff $G'$ has an undirected Hamiltonian cycle.
> - **Construction**: replace each vertex $v \in V$ with 3 vertices $v_{in}, v_{mid}, v_{out}$:
>     - Add undirected edges $(v_{in}, v_{mid})$ and $(v_{mid}, v_{out})$. This forms a short path $v_{in} - v_{mid} - v_{out}$.
>     - For each directed edge $(u, v) \in E$: add undirected edge $(u_{out}, v_{in})$.
> - $|V'| = 3n$, $|E'| = 2n + |E|$. Poly-time construction.
> - Key property: $v_{mid}$ has degree exactly 2 (connected only to $v_{in}$ and $v_{out}$), so any Hamiltonian cycle must traverse $v_{in} - v_{mid} - v_{out}$ in order. This enforces a direction.
> - $(\Rightarrow)$: if $G$ has directed HC $u_1 \to u_2 \to \cdots \to u_n \to u_1$, then $G'$ has undirected HC: $u_{1,in} - u_{1,mid} - u_{1,out} - u_{2,in} - u_{2,mid} - u_{2,out} - \cdots - u_{n,out} - u_{1,in}$.
> - $(\Leftarrow)$: if $G'$ has undirected HC, the degree-2 constraint on each $v_{mid}$ forces the cycle through each gadget as $v_{in} - v_{mid} - v_{out}$. Reading off the order of gadgets visited gives a directed HC in $G$. The direction is determined because the cycle must enter via $v_{in}$ and exit via $v_{out}$ (entering via $v_{out}$ would require leaving via $v_{in}$, which also gives a valid directed cycle in the reverse reading).

**P $\subseteq$ NP**
- Any problem in P is in NP. The certificate can be anything. Verifier $V(x, \cdot)$ ignores the certificate, solves for instance $x$ by itself in poly-time, and checks if $x$ is a YES-instance.

**NP-Hard and NP-Complete**
- Problem $A$ is **NP-Hard** if for every problem $B$ in NP: $B \leq_P A$ (every NP problem poly-time reduces to $A$).
- If we have an algorithm for $A$, we have an algorithm for any NP problem. So $A$ is harder than every NP problem.
- Problem $A$ is **NP-Complete** if it is in NP and also NP-Hard (one of the hardest NP problems).

**Cook-Levin Theorem**
- Theorem: any problem in NP poly-time reduces to 3-SAT. Hence 3-SAT is NP-Hard and NP-Complete.
- Hence so are Ham-Cycle, Subset-Sum, Set-Cover, Vertex-Cover, Independent-Set, ...
- 3-SAT recap:
    - **Literal**: a Boolean variable or its negation $x_i, \bar{x_i}$
    - **Clause**: disjunction (OR) of literals: $C_j = x_1 \vee \bar{x_2} \vee x_3$
    - **CNF (Conjunctive Normal Form)**: conjunction (AND) of clauses: $\Phi = C_1 \wedge C_2 \wedge C_3 \wedge C_4$
    - **SAT**: given CNF formula $\Phi$, does it have a satisfying truth assignment?
    - **3-SAT**: SAT where each clause contains exactly 3 literals.

**General template to prove NP-Completeness**
1. Prove the problem is in NP: give a certificate (YES-instance) and show it can be verified in poly-time. **Do not forget this step.**
2. Prove NP-Hardness: reduce from a known NP-Complete problem.
    - Show reduction runs in poly-time.
    - $(\Rightarrow)$: YES-instance of known problem $\Rightarrow$ YES-instance of new problem.
    - $(\Leftarrow)$: YES-instance of new problem $\Rightarrow$ YES-instance of known problem.
##### **Clique is NP-Complete**
> [!NOTE]
> - Problem: given graph $G = (V, E)$ and integer $k$, is there a subset of $k$ (or more) vertices such that there is an edge between each pair of vertices?
> - Step 1 (in NP): certificate is the $k$ vertices such that the induced subgraph is a clique. Verify in $O(k^2)$ time.
> - Step 2 (NP-Hard): reduce from Independent-Set. Independent-Set is NP-Hard (any NP problem reduces to it). Show Independent-Set $\leq_P$ Clique. By transitivity of poly-time reductions, Clique is NP-Hard.
>     - Independent-Set: given $G = (V, E)$ and integer $k$, is there a subset of $k$ (or more) vertices such that no two are adjacent?
>    
> **Reduction: Independent-Set $\leq_P$ Clique**
> 
> - Reduction: to check whether $G$ has an independent set of size $k$, check whether $\bar{G}$ has a clique of size $k$.
> - $\bar{G}$ is the complementary graph of $G$: for any pair of vertices $(u, v)$, there is an edge between them in $\bar{G}$ iff there is no edge between them in $G$.
> - Proof:
>     1. Reduction runs in poly-time: converting $G$ to $\bar{G}$ takes $O(n^2)$ time.
>     2. $(\Rightarrow)$: if $G$ has an independent set of size $k$, no edge between any pair of these vertices. Therefore there is an edge between each pair in $\bar{G}$ $\Rightarrow$ clique of size $k$ in $\bar{G}$.
>     3. $(\Leftarrow)$: if $\bar{G}$ has a clique of size $k$, there is an edge between each pair of these vertices in $\bar{G}$. Therefore no edge between any pair in $G$ $\Rightarrow$ independent set of size $k$ in $G$.
##### **Find-Family is NP-Complete**
> [!NOTE]
> - **Bipartite graph** $G = (L \cup R, E)$: two disjoint vertex sets $L$ and $R$, every edge has one endpoint in $L$ and one in $R$.
> - **Siblings**: a pair $u, v \in L$ are siblings if $\exists r \in R$ such that both $(u, r)$ and $(r, v)$ are edges (i.e., $u$ and $v$ share a common neighbour in $R$).
> - **Family**: a subset $F \subseteq L$ such that for all distinct $u, v \in F$, $u$ and $v$ are siblings. Intuitively, every pair in $F$ must share at least one common right-neighbour.
>
> - **Find-Family**: given bipartite graph $G = (L \cup R, E)$ and integer $k$, is there a family of size $\geq k$?
> **Example**: $L = {0, 2, 4}$, $R = {1, 3}$. Edges: $(0,1), (2,1), (2,3), (4,3)$. Here 0 and 2 are siblings (share $r=1$), 2 and 4 are siblings (share $r=3$), but ${0, 2, 4}$ is not a family since 0 and 4 are not siblings (share no common $r$).
> 
> - Step 1 (in NP): certificate is the subset $F \subseteq L$ with $|F| \geq k$. Verifier checks for every pair $u, v \in F$ whether $\exists r \in R$ adjacent to both. Polynomial time. Hence Find-Family is in NP. This verification runs in $O(|F|^2 \cdot |R|) \in O(|L|^2 \cdot |R|)$, poly-time w.r.t. input size 
> - Step 2 (NP-Hard): reduce from Clique.
> 
> **Reduction: Clique $\leq_P$ Find-Family**
> 
> **Construction**: given instance $(G = (V, E), k)$ of Clique, construct bipartite graph $G' = (L \cup R, E')$:
> 
> - $L = V$ (left vertices are original graph vertices)
> - $R = {r_e : e \in E}$ (one right vertex per edge of $G$)
> - For each edge $e = {u, v} \in E$, add bipartite edges $(u, r_e)$ and $(v, r_e)$
> 
> **Key observation**: two vertices $u, v \in L$ are siblings in $G'$ iff ${u, v} \in E$ in $G$. The right vertex $r_{{u,v}}$ is adjacent to both iff ${u,v}$ was an original edge. So a family in $G'$ is exactly a clique in $G$.
> 
> **Proof:**
> 
> 1. Reduction runs in poly-time: $|L| = |V|$, $|R| = |E|$, construction is $O(|V| + |E|)$.
> 2. $(\Rightarrow)$: suppose $C \subseteq V$ is a clique of size $\geq k$. For every distinct $u, v \in C$, edge ${u,v} \in E$, so $r_{{u,v}} \in R$ is adjacent to both $u$ and $v$ $\Rightarrow$ $u$ and $v$ are siblings. This holds for all pairs in $C$, so $C$ is a family of size $\geq k$ in $G'$.
> 3. $(\Leftarrow)$: suppose $F \subseteq L$ is a family of size $\geq k$. For every distinct $u, v \in F$, $\exists r_e \in R$ adjacent to both. By construction, this is only possible if $e = {u, v} \in E$. So every pair in $F$ is adjacent in $G$ $\Rightarrow$ $F$ is a clique of size $\geq k$ in $G$.
> 
> Hence Clique $\leq_P$ Find-Family. Since Clique is NP-Complete, Find-Family is NP-Hard. Combined with Step 1, Find-Family is NP-Complete.
##### **Directed Ham-Cycle is NP-Complete**
> [!NOTE]
> - Problem: given a directed graph $G$, decide whether there is a simple cycle visiting each vertex once.
> - Step 1 (in NP): certificate is the cycle itself. Verifier checks in poly-time whether it is a cycle and visits each vertex once.
> - Step 2 (NP-Hard): reduce from 3-SAT. Given instance $\Phi$ of 3-SAT, construct directed graph $G$ such that $G$ has a Hamiltonian cycle iff $\Phi$ is satisfiable. Any truth assignment in $\Phi$ corresponds to some graph $G$ that has a Hamiltonian cycle.
> 
> **Reduction: 3-SAT $\leq_P$ Directed-Ham-Cycle**
> **Construction:**
> - For each literal $x_i$ in the CNF, construct a **zig-zag path** of length $3m+1$ (where $m$ = number of clauses).
> - Connect paths via a global source $s$ and sink $t$: $s \to x_1 \to x_2 \to \cdots \to x_n \to t \to s$.
> - Traversing path $x_i$ left-to-right $\Rightarrow x_i = \text{True}$. Right-to-left $\Rightarrow x_i = \text{False}$.
> - For each clause $C_j$, create a clause vertex $C_j$. Connect it to the paths of its literals (not to the $1$st, $4$th, $7$th,... vertex of each path — different clauses connect to different vertices).
> - Clause vertex $C_j$ for clause $x_1 \vee \bar{x_2} \vee x_3$: reachable via detour $u \to C_j \to v$ only when traversing $x_1$ left-to-right, $x_2$ right-to-left, or $x_3$ left-to-right.
> 
> **Gadget structure** (local backbone $x \to w \to u \to v \to y$):
> 
> - $w$ is not connected to any clause (every 3rd vertex is clause-free).
> - $w$ only connects to $x$ and $u$: forced ordering $x \to w \to u$ (Hamiltonian constraint means no revisits, so direction is fixed).
> - Clause detour is forced: entering $C$ via $u \to C$ forces exiting via $C \to v$. Once you enter $C$, path is forced: $u \to C \to v$.
> - The cycle must go back to the path it came from after visiting a clause vertex.
> 
> **Proof:**
> 
> 1. Reduction runs in poly-time: $G$ has polynomial number of vertices and edges and can be constructed in poly-time.
> 2. $(\Rightarrow)$: if $\Phi$ is satisfiable, construct Hamiltonian cycle following each literal path in the direction given by the satisfying assignment. For each clause, at least one literal is true $\Rightarrow$ at least one reachable detour to that clause vertex. Travel back to $t$ then back to $s$.
> 3. $(\Leftarrow)$: if $G$ has a Hamiltonian cycle, local gadget constraints force it to follow the standard backbone. By the claim (after visiting clause vertex, must return to path it came from), skipping all clause detours leaves a Hamiltonian cycle of the backbone alone $\Rightarrow$ must follow standard route. Read off the direction through each variable path $\Rightarrow$ truth assignment. Every clause vertex $C_j$ was visited $\Rightarrow$ at least one literal per clause is true $\Rightarrow$ $\Phi$ satisfied.
> 
> **Example**: $\Phi = (\bar{x_1} \vee x_2 \vee x_3) \wedge (x_1 \vee \bar{x_2} \vee \bar{x_4}) \wedge (\bar{x_2} \vee \bar{x_3} \vee x_4)$, satisfying assignment $x_1 = \text{False}, x_2 = \text{False}, x_3 = \text{True}, x_4 = \text{True}$. Start from $s$. Since $x_1 = \text{False}$, traverse $x_1$ right-to-left. Since $x_2 = \text{False}$, traverse $x_2$ right-to-left. And so on. At appropriate $u$ nodes, take detours to clause vertices and return. Travel to $t$ then back to $s$.

![[Screenshot 2026-04-11 at 10.48.03 PM.png]]
![[Screenshot 2026-04-11 at 10.48.59 PM.png]]
##### **Fantastic-Half is NP-Complete**
> [!NOTE]
> - Problem: given non-negative integers $a_1, \ldots, a_n$ (sum $A$) and $b_1, \ldots, b_n$ (sum $B$), decide if $\exists S \subseteq {1, \ldots, n}$ of size $n/2$ such that $\sum_{i \in S} a_i \geq A/2$ and $\sum_{i \in S} b_i \geq B/2$.
> - Step 1 (in NP): certificate is the set $S$ itself. Verifier checks in poly-time whether $|S| = n/2$, $\sum_{i \in S} a_i \geq A/2$, and $\sum_{i \in S} b_i \geq B/2$.
> - Step 2 (NP-Hard): reduce from Partition-Special.
>     
>     - **Partition-Special**: given non-negative integers $x_1, \ldots, x_n$, decide whether they can be partitioned into two parts with **equal size and equal sum**.
>     - Partition-Special is NP-Hard (exercise: reduce from Partition).
> 
> **Reduction: Partition-Special $\leq_P$ Fantastic-Half**
> 
> **Core challenge**: Fantastic-Half uses $\geq$ while Partition-Special needs $=$. Need two constraints squeezing from both sides to force equality.
> 
> **Attempt 1** ($a_i = b_i = x_i$): fails. $(\Rightarrow)$ works. $(\Leftarrow)$ breaks: Fantastic-Half only guarantees $\sum_{i \in S} x_i \geq \sum_{i \notin S} x_i$, not equality.
> 
> - Counterexample: $x = (1, 2, 3, 5)$, $S = {3, 4}$ gives $\sum_{i \in S} x_i = 8 \geq 3$. Fantastic-Half says YES, Partition-Special says NO (no subset of size 2 sums to $11/2$).
> 
> **Attempt 2** ($a_i = x_i$, $b_i = x_{n+1-i}$): fails. Reversing index order does not change what subsets achieve. Same counterexample: $S = {1, 4}$ gives $a_1 + a_4 = 6 \geq 11/2$ and $b_1 + b_4 = 7 \geq 11/2$. Fantastic-Half YES, Partition-Special NO.
> 
> **Attempt 3** ($a_i = x_i$, $b_i = -x_i$): right idea, wrong execution. The two constraints now oppose each other: $\sum_{i \in S} x_i \geq \sum_{i \notin S} x_i$ and $\sum_{i \in S} x_i \leq \sum_{i \notin S} x_i$ $\Rightarrow$ forces equality. But Fantastic-Half requires $b_i \geq 0$ and $-x_i \leq 0$. Instance is **invalid**.
> 
> **Attempt 4** ($a_i = x_i$, $b_i = X - x_i$ where $X = \sum_{i=1}^n x_i$): **correct**. Preserves the opposing-constraint squeeze while keeping $b_i \geq 0$ (since $x_i \leq X$). Reduction runs in poly-time.
> 
> - $A = \sum a_i = X$, $B = \sum b_i = \sum(X - x_i) = nX - X = (n-1)X$, so $B/2 = (n-1)X/2$.
> - $(\Rightarrow)$: if $I$ is YES for Partition-Special, $|S| = n/2$ and $\sum_{i \in S} x_i = X/2$. Then $\sum_{i \in S} a_i = X/2 = A/2$ and $\sum_{i \in S} b_i = \frac{n}{2}X - X/2 = (nX - X)/2 = B/2$. Both satisfied. $I'$ is YES for Fantastic-Half.
> - $(\Leftarrow)$: if $I'$ is YES for Fantastic-Half, $\sum_{i \in S} a_i \geq A/2 \Rightarrow \sum_{i \in S} x_i \geq X/2$. From $b_i$ constraint: $\sum_{i \in S}(X - x_i) \geq B/2 \Rightarrow \frac{n}{2}X - \sum_{i \in S} x_i \geq \frac{(n-1)X}{2} \Rightarrow \sum_{i \in S} x_i \leq X/2$. Combined: $\sum_{i \in S} x_i = X/2$. This is exactly equal partition. $I$ is YES for Partition-Special.

##### **Partition-Special is NP-Complete**
> [!NOTE]
> - Problem: given non-negative integers $x_1, \ldots, x_n$, decide if they can be partitioned into two parts of equal size and equal sum.
>     
> - Step 1 (in NP): certificate is the set $S$ itself. Verifier checks $|S| = n/2$ and $\sum_{i \in S} x_i = \sum_{i \notin S} x_i$ in poly-time.
> **Reduction: Partition $\leq_P$ Partition-Special**
> 
> **Partition**: given non-negative integers $x_1, \ldots, x_n$, decide if they can be partitioned into two parts of **equal sum** (no size constraint).
> 
> **Construction**: given instance $I = (x_1, \ldots, x_n)$ of Partition, construct instance $I'$ of Partition-Special. Let $X = \sum_{i=1}^n x_i$. Two cases to handle: $n$ may be odd, and the sizes of the two parts may differ.
> 
> Set $I' = (x_1, \ldots, x_n, \underbrace{0, 0, \ldots, 0}_{n \bmod 2 \text{ zeros}})$ if $n$ is odd (pad with a zero to make even count), then add a "balancing" element. More precisely:
> 
> - If $n$ is even: add two elements $x_{n+1} = X/2 + 1$ and $x_{n+2} = X/2 + 1$ (or more carefully, use the construction below).
> - Simpler correct construction: let $I' = (x_1, \ldots, x_n, p, q)$ where $p$ and $q$ are chosen so that any equal-sum equal-size partition of $I'$ must put $p$ and $q$ in opposite halves, forcing equal-sum partition of $x_1, \ldots, x_n$.
> 
> **Clean version**: set $I' = (2x_1, \ldots, 2x_n, X+1, X+1)$ where $X = \sum x_i$. Now $|I'| = n+2$ (even). Total sum $= 2X + 2X + 2 = 4X + 2$. Each half must sum to $2X + 1$.
> 
> - The two copies of $X+1$ cannot both be in the same half (their sum alone is $2X + 2 > 2X + 1$). So they must be split: one in $S$, one outside.
> - Say $X+1 \in S$. Then $\sum_{i \in S, i \leq n} 2x_i = 2X + 1 - (X+1) = X$. So $\sum_{i \in S, i \leq n} x_i = X/2$.
> - $|S| = (n+2)/2 \Rightarrow$ exactly $n/2$ of the original $x_i$ are in $S$.
> - $(\Rightarrow)$: if Partition is YES, $\exists$ subset of ${x_1, \ldots, x_n}$ summing to $X/2$. Put those doubled values plus one copy of $X+1$ into $S$. Both size and sum conditions of Partition-Special are met.
> - $(\Leftarrow)$: if Partition-Special is YES for $I'$, by above the two $X+1$ elements are split, and $\sum_{i \in S, i \leq n} x_i = X/2$. So the original $x_i$ are partitioned with equal sum. Partition is YES.
> - Reduction runs in poly-time ($O(n)$ construction).
##### **Subset-Sum is NP-complete (using 3-SAT)**
> [!NOTE]
> **Step 1: Find a reduction**
> We reduce from 3-SAT. Given a 3-CNF formula with variables $x_1, \dots, x_n$ and clauses $C_1, \dots, C_m$, construct a SUBSET-SUM instance as follows:
> - For each variable $x_i$, create two numbers $t_i$ and $f_i$, each with $n + m$ digits.
> - In variable position $i$: both $t_i$ and $f_i$ have digit 1; all other variable positions are 0.
> - In clause position $j$: $t_i$ has digit 1 iff $x_i \in C_j$; $f_i$ has digit 1 iff $\neg x_i \in C_j$.
> - For each clause $C_j$, add slack numbers $s_j$ and $u_j$ with digits 1 and 2 respectively, only in clause position $j$.
> - Set target $W$ with digit 1 in each variable position and digit 4 in each clause position:
> 
> $$W = \underbrace{11\cdots1}_{n}\underbrace{44\cdots4}_{m}$$
> 
> **Step 2: Show the reduction runs in polynomial time**
> We construct $2n$ variable numbers and $2m$ slack numbers, each with $n + m$ digits. The total size of the instance is $O((n + m)^2)$, which is polynomial in the size of the formula.
> 
> **Step 3: 3-SAT YES-instance $\implies$ SUBSET-SUM YES-instance**
> Suppose the formula is satisfiable. Fix a satisfying assignment. For each variable $x_i$, choose $t_i$ if $x_i = \text{true}$, and $f_i$ if $x_i = \text{false}$.
> - **Variable columns:** since exactly one of $t_i, f_i$ is chosen per variable, and both have digit 1 in variable position $i$, each variable column sums to exactly 1. $\checkmark$
> - **Clause columns:** since the assignment satisfies every clause $C_j$, at least one chosen variable-number contributes a 1 to clause column $j$. The contribution is therefore 1, 2, or 3. We can always choose slack numbers $s_j$ and $u_j$ (with values 1 and 2 in column $j$) to top up the total to exactly 4. $\checkmark$
> 
> So the subset sums to $W$, and the SUBSET-SUM instance is a YES-instance.
> 
> **Step 4: SUBSET-SUM YES-instance $\implies$ 3-SAT YES-instance**
> Suppose there exists a subset summing to $W$.
> - **Variable columns:** the target digit is 1 in each variable position $i$, and only $t_i$ and $f_i$ contribute to that column. So exactly one of $t_i, f_i$ must be chosen. This defines a valid truth assignment: set $x_i = \text{true}$ if $t_i$ is chosen, $x_i = \text{false}$ if $f_i$ is chosen.
> - **Clause columns:** the target digit is 4 in each clause position $j$. The slack numbers contribute at most $1 + 2 = 3$ to column $j$, so the chosen variable-numbers must contribute at least 1. This means at least one chosen variable-number has a 1 in clause column $j$, which means the corresponding literal satisfies $C_j$. So every clause is satisfied. $\checkmark$
> 
> Therefore the truth assignment satisfies the formula, and the 3-SAT instance is a YES-instance.
> **Conclusion:** Since $\text{3-SAT} \leq_p \text{SUBSET-SUM}$ and 3-SAT is NP-hard, SUBSET-SUM is NP-hard. $\blacksquare$
> 
> **Example**
> Take $(x_1 \vee \neg x_2 \vee x_3) \wedge (\neg x_1 \vee x_2 \vee x_3)$.
> There are 3 variable columns and 2 clause columns, so every number has 5 digits: $[x_1\ x_2\ x_3\ C_1\ C_2]$.
> 
> |Number|Digits|Reason|
> |---|---|---|
> |$t_1$|$10010$|$x_1$ appears in $C_1$|
> |$f_1$|$10001$|$\neg x_1$ appears in $C_2$|
> |$t_2$|$01001$|$x_2$ appears in $C_2$|
> |$f_2$|$01010$|$\neg x_2$ appears in $C_1$|
> |$t_3$|$00111$|$x_3$ appears in both clauses|
> |$f_3$|$00100$|$\neg x_3$ appears nowhere|
> |$s_1$|$00010$|slack for $C_1$|
> |$u_1$|$00020$|slack for $C_1$|
> |$s_2$|$00001$|slack for $C_2$|
> |$u_2$|$00002$|slack for $C_2$|
> |$W$|$11144$|target|
> 
> Try assignment $x_1 = x_2 = x_3 = \text{true}$, choosing $t_1, t_2, t_3$:
> $t_1 + t_2 + t_3 = 10010 + 01001 + 00111 = 11122$
> Add slack $u_1 + u_2 = 00020 + 00002 = 00022$:
> 
> $11122 + 00022 = 11144 = W \checkmark$
> 

**Key takeaways**
- To prove NP-Completeness: (1) show in NP via certificate + poly-time verifier, (2) reduce from known NP-Complete problem with poly-time reduction preserving YES/NO.
- Transitivity of reductions: if $A \leq_P B$ and $B \leq_P C$, then $A \leq_P C$.
- Core design challenge in reductions: match the structure of the target problem. When target uses $\geq$ but source needs $=$, create two opposing constraints that squeeze to equality.
- NP-Hard does not require being in NP. NP-Complete = NP $\cap$ NP-Hard.
---
#### 11. Approximation Algorithms by Greedy

**Overview**
- For NP-Complete problems, no known poly-time exact algorithm exists. Instead, use a greedy approximation: not optimal, but provably close.
- Key insight: greedy uses only **local information** at each step instead of exploring all subproblems.

**Approximation Algorithm Definition**
- Given optimisation problem and $\alpha \geq 1$, algorithm $\mathcal{A}$ is an $\alpha$-approximation algorithm if for any instance $I$:
    - Minimization: $OPT \leq \mathcal{A}(I) \leq \alpha \cdot OPT$
    - Maximization: $\frac{OPT}{\alpha} \leq \mathcal{A}(I) \leq OPT$
- $\alpha$ is the **approximation ratio**. Smaller $\alpha$ means closer to optimal.
##### **Set-Cover**
> [!NOTE]
> - Problem: given collection $\mathcal{S}$ of subsets of ${1, \ldots, n}$, choose the fewest subsets whose union equals ${1, \ldots, n}$.
> - Set-Cover is NP-Complete. No known poly-time exact algorithm.
> - **Greedy choice**: at each step, pick the set that covers the largest number of currently uncovered elements.
> 
> **Example**: 12 elements in a $3 \times 4$ grid. $S_1, S_2$ cover columns, $S_3, S_4, S_5$ cover rows.
> 
> - Greedy: picks ${S_1, S_2, S_3, S_4, S_5}$ (5 sets, picks columns first then rows).
> - Optimal: ${S_3, S_4, S_5}$ (3 sets, just rows cover everything).
> - Greedy is suboptimal here but still within $O(\log n)$ factor.
> 
> **Analysis of Greedy Set-Cover**
> - Suppose there are $\ell$ uncovered elements. $OPT$ sets can cover all elements, so at least one set covers $\geq \lceil \ell / OPT \rceil$ uncovered elements.
> - After this round, at most $\left(1 - \frac{1}{OPT}\right)\ell$ elements remain.
> - After $k$ rounds, at most $\left(1 - \frac{1}{OPT}\right)^k n$ elements remain.
> - After $O(OPT)$ rounds: $\left(1 - \frac{1}{OPT}\right)^{OPT} n \approx \frac{n}{e}$ elements remain (using $(1 - \frac{1}{n})^n \approx \frac{1}{e}$).
> - After $O(\log n \cdot OPT)$ rounds: at most $\left\lfloor \frac{n}{e^x} \right\rfloor$ elements remain where $e^x \geq n$, so 0 elements remain.
> - **Greedy is an $O(\log n)$-approximation algorithm for Set-Cover.** Number of sets chosen $\leq O(\log n) \cdot OPT$.

##### **Matching**
> [!NOTE]
> - Given graph $G$, a **matching** $M$ is a subgraph where every vertex has degree at most 1 (no two edges share a vertex). If $(u, v) \in M$, we say $u$ is matched to $v$.
> - **Maximum matching**: largest possible matching.
> - **Maximal matching**: a matching where no more edges can be added without making some vertex have degree 2 (i.e., you cannot add any edge without violating the matching property). The greedy algorithm outputs a maximal matching.
> - **Maximal $\neq$ Maximum**: maximal just means you can't extend it further; maximum is the globally largest.
> 
> **Greedy-Matching Algorithm**
> 
> ```
> M = ∅
> Repeat:
>     Pick any edge (u, v) such that both u and v are unmatched in M
>     M = M ∪ {(u, v)}
> Until every edge has at least one endpoint matched in M
> ```
> - Does not try to pick the "best" edge, just any valid unmatched edge. Arbitrary choice suffices.
> 
> **Claim: Maximal matching $\geq \frac{1}{2}$ maximum matching (greedy is a 2-approximation)**
> - Intuition: maximal matching $M$ is forced to be "locally complete" — every edge in $G$ has at least one endpoint in $M$. This means $M$ must touch enough of the graph that it cannot be smaller than half the optimal.
> - Proof: let $M^*$ be a maximum matching.
>     - For any edge $(u, v) \in M^*$, since $M$ is maximal, at least one of $u$ or $v$ must already be matched in $M$ (otherwise we could have added $(u,v)$ to $M$, contradicting maximality).
>     - So $M$ contains at least one vertex from every edge of $M^*$.
>     - $M$ has $|M|$ edges, each "covered" by at least one vertex of $M$.
>     - $M$ has $2|M|$ matched vertices total (each edge contributes 2).
>     - Therefore $2|M| \geq |M|$, i.e., $|M| \geq \frac{|M|}{2}$.
> - Since $|M^*| = OPT$: $\frac{OPT}{2} \leq |M| \leq OPT$. Greedy is a **2-approximation** for maximum matching.
> 

##### **Vertex-Cover**
> [!NOTE]
> - Problem: given graph $G = (V, E)$ and integer $k$, is there a subset of $k$ (or fewer) vertices such that every edge is incident to at least one vertex in the subset?
> - Vertex-Cover is NP-Complete.
> 
> **Vertex-Cover $\leq_P$ Set-Cover**
> - Reduction: given $G = (V, E)$, construct Set-Cover instance $(n, \mathcal{S})$:
>     - $n = |E(G)|$, order edges arbitrarily $e_1, \ldots, e_n$.
>     - For each vertex $v \in V(G)$, define $S_v = {i : e_i \text{ is incident to } v}$.
>     - $\mathcal{S}$ is the collection of all such subsets $S_v$.
> - Intuition: vertex $\Rightarrow$ set, edge $\Rightarrow$ element. A vertex "covers" all its incident edges, so choosing a set of vertices covers a set of elements (edges).
> - **Claim**: $G$ has a vertex cover of size $k$ iff $(n, \mathcal{S})$ has a set cover of size $k$.
> - **Consequence**: if we have an $\alpha$-approximation for Set-Cover, we also have an $\alpha$-approximation for Vertex-Cover. So greedy gives $O(\log n)$-approximation for Vertex-Cover.
> 
> **Vertex-Cover by Maximal Matching (better: 2-approximation)**
> - **Claim**: given graph $G$, if $M$ is a maximal matching of $G$, then:
>     1. The set of vertices matched in $M$ forms a valid vertex cover of $G$.
>     2. $|M| \leq VC(G) \leq 2|M|$, where $VC(G)$ is the size of the minimum vertex cover.
> - This gives a **2-approximation algorithm**: compute maximal matching $M$, output all matched vertices.
> - **Proof of part 1** (matched vertices form a vertex cover):
>     - Suppose for contradiction some edge $(u, v)$ is not covered, i.e., neither $u$ nor $v$ is matched in $M$.
>     - But then $(u, v)$ could be added to $M$ without violating the matching property.
>     - This contradicts $M$ being a maximal matching. So every edge must be covered.
> - **Proof of part 2** ($|M| \leq VC(G) \leq 2|M|$):
>     - **Upper bound** $VC(G) \leq 2|M|$: $M$ has $|M|$ edges, contributing $2|M|$ matched vertices. These vertices form a valid vertex cover (by part 1). So minimum vertex cover $\leq 2|M|$.
>     - **Lower bound** $VC(G) \geq |M|$: each edge in $M$ must be covered by at least one vertex. The edges in $M$ share no vertices (matching property), so each edge in $M$ needs a distinct vertex to cover it. Therefore any vertex cover must have at least $|M|$ vertices.
>     - Combined: $|M| \leq VC(G) \leq 2|M|$, so the algorithm outputs a cover of size $2|M| \leq 2 \cdot VC(G) = 2 \cdot OPT$.
> 
>**Example**: path graph $1 - 2 - 3 - 4 - 5$.
>  
>  - Maximal matching (greedy): pick $(1,2)$, then $(3,4)$. $M = {(1,2),(3,4)}$, matched vertices $= {1,2,3,4}$.
>  - Minimum vertex cover: ${2,4}$ covers all edges. $VC(G) = 2$, $|M| = 2$, $2|M| = 4$. Ratio is 2.
##### **Subgraph Isomorphism is NP-complete**
> [!NOTE]
> - **Problem:** Given graphs $G$ and $H$, does $H$ have a subgraph $H'$ such that $G$ is isomorphic to $H'$?
> - **Isomorphism recap:** $G_1 \cong G_2$ iff $\exists$ bijection $f: V_1 \to V_2$ with $(u,v) \in E_1 \iff (f(u), f(v)) \in E_2$
> 
> **(1) In NP:**
> - **Certificate:** the subgraph $H' \subseteq H$ + the bijection $f: V(G) \to V(H')$
> - **Verification (poly time):**
>     - Check $H' \cong G$ using $f$ (iterate edges of $G$, check $(f(u), f(v)) \in E(H')$, and vice versa)
>     - Check $H'$ is a subgraph of $H$ by scanning adjacency lists/matrices
> 
> **(2) NP-hard: reduce from Independent Set**
> - **Independent Set instance:** $(\hat{G}, k)$ — does $\hat{G}$ have an IS of size $k$?
> - **Reduction:** Set $H = \hat{G}$, and let $G$ = graph on $k$ vertices with **no edges**
> 
> **Correctness ($\iff$):**
> - ($\Leftarrow$) YES Subgraph Iso $\Rightarrow$ YES IS: the isomorphic subgraph $H'$ is an edgeless graph on $k$ vertices inside $\hat{G}$, i.e. an independent set of size $k$
> - ($\Rightarrow$) YES IS $\Rightarrow$ YES Subgraph Iso: any IS of size $k$ in $\hat{G}$ induces an edgeless subgraph $H' \subseteq \hat{G}$ that is isomorphic to $G$
> - Equivalently (contrapositive): NO Subgraph Iso $\Rightarrow$ NO IS
> 
> **Running time:** Building the empty graph on $k \leq |V(\hat{G})|$ vertices is polynomial (else IS is trivial).
> 
> > **Why this works:** $G$ being edgeless forces $H'$ to be edgeless too (isomorphism preserves edges). An edgeless induced subset of size $k$ in $H = \hat{G}$ is exactly an independent set of size $k$.
##### **Half Clique is NP-complete**
> [!NOTE]
> - **Problem:** Given undirected $G = (V, E)$ with $|V|$ even, is there a clique of size **exactly** $|V|/2$?
> 
> **(1) In NP:**
> - **Certificate:** subset $S \subseteq V$ with $|S| = |V|/2$
> - **Verification (poly time):** check every pair in $S$ is connected by an edge
> 
> **(2) NP-hard: reduce from Clique**
> - **Clique instance:** $(\hat{G}, k)$ with $|V(\hat{G})| = n$
> - **Reduction — build $G$:**
>     - Start with $\hat{G}$
>     - **Add $n - k$ new vertices**, all adjacent to each other AND to every vertex of $\hat{G}$
>     - **Add $k$ isolated vertices** (no edges)
>     - Total: $n + (n-k) + k = 2n$ vertices, so $|V(G)|/2 = n$
> 
> **Correctness ($\iff$):**
> - ($\Rightarrow$) YES Clique $\Rightarrow$ YES Half Clique: take the $k$-clique in $\hat{G}$ $\cup$ the $n-k$ added connector vertices. They're all pairwise adjacent (connectors are adjacent to everything; the $k$ vertices form a clique), giving a clique of size $n = |V(G)|/2$
> - ($\Leftarrow$) YES Half Clique $\Rightarrow$ YES Clique: the $n$-clique in $G$ uses at most $n-k$ connector vertices (and zero isolated vertices, since they have no edges), so it must use $\geq k$ vertices from $\hat{G}$, and those $k$ vertices form a clique in $\hat{G}$
> 
> **Running time:** Adding $n - k$ connector vertices and $k$ isolated vertices is polynomial.
> > **Padding trick to remember:** To force the answer size to be exactly $|V|/2$, pad with two types of vertices, connectors that "boost" any small clique up to size $n$, and isolated vertices to inflate $|V|$ so that $|V|/2$ lands on the right number.

**Facts (T/F)**
- **(a) Any problem in P reduces to 3-SAT: TRUE**
    - $P \subseteq NP$, and every problem in NP poly-reduces to 3-SAT (3-SAT is NP-complete).
- **(b) If MST decision (does $G$ have a spanning tree of weight $\leq k$?) is NP-complete, then $P = NP$: TRUE**
    - MST has a known polynomial algorithm, so this problem is in P. If it's also NP-hard, every NP problem reduces to it and is solvable in poly time $\Rightarrow$ $P = NP$.
- **(c) 3-SAT might be solvable in poly time: TRUE**
    - Would hold if $P = NP$ (currently unknown).
- **(d) Independent Set might not be solvable in poly time: TRUE**
    - Would hold if $P \neq NP$ (currently unknown).
- **(e) Some NP-complete problems might be in P while others are not: FALSE**
    - All NP-complete problems are poly-reducible to each other. If one is in P, all of them are.

**Further Remarks**
- Other approximation techniques beyond greedy: Linear Programming, Gradient Descent, Randomisation (outputs $\alpha$-approximation with probability $\geq p$).
- **Hardness of approximation**:
    - For any $\varepsilon \geq 0$, there is no poly-time $(\sqrt{2} - \varepsilon)$-approximation algorithm for Vertex-Cover unless P=NP.
    - For any constant $\alpha \geq 1$, there is no poly-time $\alpha$-approximation algorithm for Independent-Set unless P=NP.
    - Although Vertex-Cover and Independent-Set are structurally almost the same problem (complement), the hardness of approximation is very different.