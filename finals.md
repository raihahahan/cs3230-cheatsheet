#### 0. Math and Probability
**Exponentials**
*   $a^{-1} = \frac{1}{a}$
*   $(a^m)^n = a^{mn}$
*   $a^m a^n = a^{m+n}$
*   $e^x \ge 1 + x$

**Logarithms**
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

**Stirling's approximation**
- Estimate for the factorial function
- $n! = \sqrt{2\pi n} \left(\frac{n}{e}\right)^n (1 + O(1/n))$
- $\log(n!) \in \Theta(n \log n)$

**Summation and series**
- Finite GP: $\sum_{k=0}^{n} x^k = 1 + x + x^2 + \cdots + x^n = \frac{x^{n+1} - 1}{x - 1}$
- Infinite GP: $\sum_{k=0}^{\infty} x^k = \frac{1}{1 - x}$
- AP: $\sum_{k=0}^{n} k = 1 + 2 + \cdots + n = \frac{n(n + 1)}{2}$, $\Theta(n^2)$
- Finite AP term: $T_k = a + (k-1)d$ 
- Finite AP sum: $S_n = \frac{n}{2}(2a + (n - 1)d)$
- Finite GP term: $T_k = ar^k$
- Finite GP sum: $S_n = \frac{a(1 -  r^n)}{1-r}$
- Weighted Geometric Series: $\Sigma_{i=0}^\infty ir^i = \frac{r}{(1-r)^2}, |r| < 1$
- Harmonic series: $\sum_{i=1}^{n} \frac{1}{i} = ln(n)+\gamma + o(1) \in \theta(logn)$
- Reciprocal Log: $\sum_{k=2}^{n} \frac{1}{logk} = \theta(n / logn)$ 
- Harmonic over log: $\sum_{k=2}^{n} \frac{1}{klogk} = \theta(loglogn)$
- Squared log: $\sum_{k=2}^{n} \frac{1}{k(logk)^p}$ 
	- $p > 1$: $\theta (1)$
	- $p = 1$: $\theta (loglogn)$
	- $0 < p < 1$: $\theta((logn)^{1-p})$
- Derivative of Geometric Series:
	- $\sum^{\infty}_{i=0}x^i = 1/(1-x)$
	- Differentiate both sides w.r.t $x$: $\sum^{\infty}_{i=0}i \cdot x^{i-1} = 1 / (1-x)^2$
	- Multiply both sides by $x$: $\sum^{\infty}_{i=0}i \cdot x^i = x / (1 -x)^2$
**Generalised Harmonic Series**
$\sum_{i=1}^{n} \frac{1}{i^p}$
- $p > 1$: $\theta (1)$
- $p = 1$: $\theta (logn)$
- $0 < p < 1$: $\theta(n^{1-p})$

**L'Hospital's Rule**
- technique for evaluating indeterminate limits
- if $\lim_{x\to\infty} f(x) = \infty$ and $\lim_{x\to\infty} g(x) = \infty$, then:
	- $\lim_{x\to\infty} \frac{f(x)}{g(x)} = \lim_{x\to\infty} \frac{f'(x)}{g'(x)}$
- where $f'(x)$ and $g'(x)$ are the derivatives of $f(x)$ and $g(x)$.
- $n \ln n \in o(n^2)$, meaning $n \ln n$ grows strictly slower than $n^2$

**Useful inequalities**
- $1 + x \leq e^x$

**Sample Space and Event**
* **Sample Space ($S$):** The set of all possible outcomes (elementary events) of an experiment.
*  **Event ($A$):** Any subset of the sample space.
*  **Complement of an Event ($\bar{A}$):** The set of all outcomes in $S$ that are not in $A$, defined as $\bar{A} = S - A$.

**Probability Distribution**
A probability distribution $\Pr()$ is a mapping from events to real numbers that satisfies three axioms:
1.  **Non-x:** $\Pr(A) \ge 0$ for all events $A$.
2.  **Normalization:** $\Pr(S) = 1$.
3.  **Additivity:** $\Pr(A \cup B) = \Pr(A) + \Pr(B)$ for mutually exclusive (disjoint) events $A$ and $B$.

**General Probability Rules**
* **Inclusion-Exclusion Principle (for two events):** $\Pr(A \cup B) = \Pr(A) + \Pr(B) - \Pr(A \cap B)$.
* **Independence:** Two events $A$ and $B$ are independent if and only if $\Pr(A \cap B) = \Pr(A) \cdot \Pr(B)$.

**Conditional Probability**
The conditional probability of event $A$ given event $B$ (where $\Pr(B) \ne 0$) is defined as:
- $\Pr(A|B) = \frac{\Pr(A \cap B)}{\Pr(B)}$

**Bayes' Theorem**
$\Pr(A|B) = \frac{\Pr(A) \Pr(B|A)}{\Pr(B)}$

The denominator $\Pr(B)$ can be expanded using the Law of Total Probability (for an event $A$ and its complement $\bar{A}$):
$$\Pr(A|B) = \frac{\Pr(A) \cdot \Pr(B|A)}{\Pr(A) \cdot \Pr(B|A) + \Pr(\bar{A}) \cdot \Pr(B|\bar{A})}$$
**Random Variable**
A function that maps the outcomes in the sample space ($S$) to real numbers.
* The function $f(x) = \Pr(X = x)$ is the **probability density function** (or probability mass function for discrete variables) of $X$.

**Expectation (Mean)**
The expectation or mean of a random variable $X$ is the weighted average of all possible values of $X$:
- $E(X) = \sum_{x} x \cdot \Pr(X = x)$

**Linearity of Expectation**
Expectation is a linear operator:
*   $E(X + Y) = E(X) + E(Y)$
*   $E(aX) = a E(X)$
*   **For independent variables:** $E(XY) = E(X) \cdot E(Y)$

**Event Operations**
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

**Permutations and Combinations**
$P^n_r=\frac{n!}{(n-r)!}=n(n-1)(n-2)\dots (n-(r-1))$ 
$n \choose {r}$ = $\frac{n!}{r!(n-r)!}$
$n\choose r$ = $n \choose (n-r)$ 

**Probability**
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

**Bernoulli Trials**
A **Bernoulli Trial** is an experiment with exactly two outcomes: success (with probability $p$) and failure (with probability $q = 1 - p$).

**Geometric Distribution**
If $X$ is the number of independent Bernoulli trials needed to obtain the first success:
*   **Probability:** $\Pr(X = k) = q^{k-1} p$
*   **Expectation:** $E(X) = \frac{1}{p}$

**Binomial Distribution**
If $X$ is the number of successes in $n$ independent Bernoulli trials:
*   **Probability:** $\Pr(X = k) = \binom{n}{k} p^k q^{n-k}$
---
#### 1. Asymptotic Analysis
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

**Properties**
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

---
#### 2. Recurrences and Master Theorem
**Remarks**:
- If $f(n) \in O(n)$, then there exists two constant $c > 0$ and $n_0 > 0$ such that $f(n) \leq cn$ if $n \geq n_0$
	- For **upper bound** calculation, we can replace $\theta(n)$ with $cn$ 
- If $f(n) \in \Omega(n)$, then there exists two constant $c > 0$ and $n_0 > 0$ such that $f(n) \geq cn$ if $n \geq n_0$
	- For **lower bound** calculation, we can replace $\theta(n)$ with $cn$ 

**(1) Telescoping Series**
- Find a way to cancel out each other
- e.g $T(n)/n = \frac{2}{n}T(\frac{n}{2}) + 1 = T(\frac{n}{2})/\frac{n}{2} + 1$ 

**(2) Substitution Method**
- Guess a solution, then verify by induction

**(3) Recursion Tree**
- Find how many levels and leaves

**(4) Master Theorem**
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

**Fibonacci**
> [!PROOF]
> 1. Loop invariant: At the start of iteration `i`: `prev2 = Fib(i - 2), prev1 = Fib(i - 1)`
> 2. Initialisation: `i = 2: prev2 = Fib(0) = 0, prev1 = Fib(1) = 1`
> 3. Maintenance: Suppose at iteration `i`, `prev2 = Fib(i - 2), prev1 = Fib(i - 1)`, then at end of the iteration, `prev2 = Fib(i - 1), prev1 = Fib(i)`
> 4. Termination: Algorithm returns `Fib(n)`

**Selection sort**
> [!proof]
> 1. Loop invariant: $A[1..j-1]$ is sorted and ($x \leq y$ for all $x \in A[1..j-1]$ and $y \in A[j..n]$)
> 2. Initialisation: True because nothing in LHS
> 3. Maintenance: Take new element from $A[j..n]$ and swap, invariant maintained
> 4. Termination: New element inserted is bigger than that already inserted, and add this to the end. Thus it's sorted

**Weighted Directed Graphs**
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
##### **Recursive Algorithms**
1. Base case
2. Inductive step:
	1. Assume algo is correct for any input of size $\leq n$
	2. Show the algo is correct for any input of size $n$

**Searching in a sorted array**
1. Inductive step: Assume algo works for any input of size $< n$
2. If $x = A[mid]$, answer is YES
3. If $x > A[mid]$:
	1. $x \in A[lb..ub] \iff x \in A[mid + 1..ub]$ -- A is sorted
	2. Therefore, answer must be $\text{BinarySearch(A, mid + 1, ub, x)}$ -- Induction Hypothesis
4. Similar for $x < A[mid]$
- Depth: $O(logn)$, $T(n) \in O(logn)$

**Divide and Conquer**
$$ 
T_n =  
\begin{cases}  
\theta(1) & \text{if } n \leq 1 \\  
aT(\frac{n}{b}) + f(n) & \text{otherwise.}  
\end{cases}  ​
$$
- $a$ subproblems, each of size $\frac{n}{b}$
- $f(n)$ = cost of splitting and combining

**Improving divide-and-conquer algorithm**
1. Option 1: Reduce cost for splitting/combining
2. Option 2: Reduce number of subproblems

**Exponentiation**
**1. $a^n = a^{n-1} \cdot a$**
- $T(n) = T(n-1) + \theta(1) \in \theta(n)$

**2. Fast exponentiation**
- If $n$ is even: $a^n = a^{\lfloor n/2\rfloor} \cdot a^{\lfloor n/2 \rfloor}$
- If $n$ is odd: $a^n = a^{\lfloor n/2 \rfloor} \cdot a^{\lfloor n/2 \rfloor} \cdot a$
- $T(n) = T(\lfloor n/2 \rfloor) + \theta(1) \in \theta(logn)$

**Fibonacci with matrices**
$$
\begin{pmatrix}
F_{n+1} & F_n \\
F_n & F_{n-1}
\end{pmatrix}
=
\begin{pmatrix}
F_n + F_{n-1} & F_n \\
F_{n-1} + F_{n-2} & F_{n-1}
\end{pmatrix}
=
\begin{pmatrix}
F_n & F_{n-1} \\
F_{n-1} & F_{n-2}
\end{pmatrix}
\begin{pmatrix}
1 & 1 \\
1 & 0
\end{pmatrix}
$$
$$
\begin{pmatrix}
F_{n+1} & F_n \\
F_n & F_{n-1}
\end{pmatrix}
=
\begin{pmatrix}
1 & 1 \\
1 & 0
\end{pmatrix}^n
$$

**Matrix Multiplication**
**1. Divide and conquer**
Partition matrices (A), (B), and (C) into block matrices:
$$  
C =
\begin{pmatrix}  
r & s \\  
t & u  
\end{pmatrix},  
\quad  
A =  
\begin{pmatrix}  
a & b \\  
c & d  
\end{pmatrix},  
\quad  
B =  
\begin{pmatrix}  
e & f \\  
g & h  
\end{pmatrix}  
$$
Then:
$$
\begin{pmatrix}  
r & s \\  
t & u  
\end{pmatrix}
=
\begin{pmatrix}  
a & b \\ 
c & d  
\end{pmatrix}
\cdot
\begin{pmatrix}  
e & f \\  
g & h  
\end{pmatrix}  
$$
- $r = ae + bg, s = af + bh, t = ce + dg, u = cf + dh$  
- All blocks $(r,s,t,u,a,b,c,d,e,f,g,h)$ are $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices.
- 8 multiplications of $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices
- 4 additions of $\left(\frac{n}{2} \times \frac{n}{2}\right)$ matrices
- $T(n) = 8T\left(\frac{n}{2}\right) + \Theta(n^2)$
- $T(n) \in \Theta(n^{\log_2 8})$ = $\theta(n^3)$

**2. Strassen's Algorithm**
> [!NOTE]
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

---
#### 4. Sorting
**Lower bound for comparison-based sorting**
- **Theorem: The worst-case complexity of any comparison-based sorting algo is $\ohm(nlogn)$**
- Decision tree: binary tree with at least $n!$ leaves, each permutation a possible answer
- Height of tree at least $log(n!) \in nlogn - nloge + O(logn) \subseteq \Theta(nlogn)$ (Stirling's approx.)

**Merge $k$ sorted arrays: $\ohm(kn\log k)$**
- As the $k$ arrays are sorted, number of possible ways to combine them is ${(kn)!}/{(n!)^k}$
- $\log({(kn)!}/{(n!)^k}) \in \ohm(kn\log k)$

**Non-comparison sorts**
Assume:  $A[i] \in {1,2,\dots,k}$
Algorithm:
- Count occurrences
- Reconstruct sorted array
- $O(n + k)$, no comparisons required.

**Quick Sort**
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

**Desirable Properties of Sorting**
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
---
#### 5. Randomized Algorithms
##### **Verification of Matrix Multiplication**
- Given $A,B,C \in \mathbb{R}^{n \times n}$.  
- Check if:  $AB = C$
- Naive: compute $AB$ - $O(n^3) \quad \text{(or } O(n^{2.807}) \text{ with Strassen)}$  

**Freivald’s Algorithm**
> [!NOTE]
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

**Hashing**
- Hash table of size $n$.  
- Hash function: $h: U \to {1,\dots,n}$
- Chain hashing: collisions stored in linked list.
- Expected number of balls in one bin:  $E[X] = \frac{m}{n}$
- Expected size of list for element’s bin: $1 + \frac{m-1}{n}$
- Goal: reduce collisions
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

---
#### 6. Dynamic Programming
**Template**
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
- $F(0) = 0, F(1) = 1, F(n) = F(n-1) + F(n-2)$ for $n > 1$
- Recursive: $\ge 2^{(n-2)/2}$ operations (exponential), recomputes same subproblems
- Iterative/memoized: $O(n)$ (linear), each subproblem computed once
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

---
#### 7. Greedy
**Template**
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
##### **Decision Problems**
- A decision problem maps an instance to ${\text{YES}, \text{NO}}$
- Any optimisation problem can be converted to a decision problem: "is there a solution with value $\le k$?" (minimisation) or "$\ge k$?" (maximisation)
- Decision $\le_P$ Optimisation: given the optimal value, just check if it meets the threshold
- If the decision version is hard, the optimisation version is also hard
##### **Reductions Between Decision Problems**
- For decision problems, the YES/NO answer is simply "copied" through the reduction
- We show $\alpha$ and $\beta$ are equivalent (same YES/NO answer), but this does not mean $A$ and $B$ are equivalent as problems
##### **3-SAT**
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
- No poly-time algorithm is known for any NP-complete problem; this is the strongest evidence that $P \ne NP$

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

**Example: Subset-Sum in NP**
> [!NOTE]
> 
> 
> - Problem: given list of integers $S$ and target $t$, decide if $\exists S' \subseteq S$ summing to $t$.
> - Certificate: the subset $S'$ itself.
> - Verifier: check whether sum of elements of $S'$ equals $t$ in poly-time.
> - Hence Subset-Sum is in NP.

**Example: Ham-Cycle in NP**
> [!NOTE]
> 
> - Problem: given graph $G$, decide whether there is a simple cycle visiting each vertex once.
> - Certificate: the cycle itself.
> - Verifier: check in poly-time whether it is a cycle and visits each vertex once.
> - Hence Ham-Cycle is in NP.

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

**Clique is NP-Complete**
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

**Directed Ham-Cycle is NP-Complete**
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

**Fantastic-Half is NP-Complete**
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

**Partition-Special is NP-Complete**
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

**Key takeaways**
- To prove NP-Completeness: (1) show in NP via certificate + poly-time verifier, (2) reduce from known NP-Complete problem with poly-time reduction preserving YES/NO.
- Transitivity of reductions: if $A \leq_P B$ and $B \leq_P C$, then $A \leq_P C$.
- Core design challenge in reductions: match the structure of the target problem. When target uses $\geq$ but source needs $=$, create two opposing constraints that squeeze to equality.
- NP-Hard does not require being in NP. NP-Complete = NP $\cap$ NP-Hard.