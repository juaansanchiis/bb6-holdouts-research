# Antihydra Treatise — Volume 1: Foundations, Arithmetic Dynamics & Invariants (Parts I–V)

# Complete Treatise: The Algebraic-Adelic and Diophantine Theory of the Antihydra Conjecture in $BB(6)$

**Theoretical Framework:** Calculus of Carry Defects on Bimodular Lattices (CCDBL) and Adelic Diophantine Geometry ($\mathbb{R} \times \mathbb{Z} _ 2 \times \mathbb{Z} _ 3$).

## General Index of the Treatise

1. **Part I:** The Antihydra Turing Machine in $BB(6)$, Verifiable Reduction to the Arithmetic System $(a _ n, b _ n)$, Modular Sieve, and Triad Balance.
2. **Part II:** Spin Duality, Shifted Sequence $u _ n$, Dirichlet Character $\chi _ 4$, Exhaustive Modulo 8 Relations, Reflection $\mathcal{J}(a) = 1 - a$, and Boolean Cubic Identity.
3. **Part III:** Macro-Cycle Renormalization, Cumulative Even Count $P _ K$, Odd Core Domains, the Four Exact Valuation Laws, Universal Floor Formula, and Audited Cycle Table.
4. **Part IV:** Archimedean Domain, the Antihydra Constant $\alpha$ (with Rigorous Truncation Bound and Certified Digits), Non-Integrality $R _ n \in (0,1)$, and the Sliding Window Operator.
5. **Part V:** The Exact Integral Invariant ($44 \cdot 3^n$), the Dual Identities ($16 \cdot 3^n$ and $14 \cdot 3^n$), the Corrected Identity for $b _ N$ in Terms of $Z _ k$, and Absolute Convergence of Weighted Series.
6. **Part VI:** The Quadratic Virial Theorem and Complete Proof of the Partition Law at a Halting Time.
7. **Part VII:** Elimination of the Conditional (*If/Else*): The Pure Affine Algebraic Variety and Complete Proof of the Dyadic Rigidity Theorem.
8. **Part VIII:** Adelic Space $\mathcal{E} _ S = \mathbb{Z} _ 2 \times \mathbb{Z} _ 3 \times \mathbb{R}$, Local Topologies, Operator Continuity, and Proof of the Finite Difference Theorem $\Delta^L$.
9. **Part IX:** Strict 3-adic Contraction, 2-adic Valuation Proof for the Injectivity of Residual Sets $\mathcal{R} _ M$, and Haar Measure of the 3-adic Cantor Set.
10. **Part X:** Univocal Time Reversal via Ternary Ceilings and Complete Proof of the Exact Fractional Representation of $O _ N$ and $b _ N$.
11. **Part XI:** The System of Arithmetic Kirchhoff Equations, Telescoping Proof of $b _ N$, Koopman-Walsh Detail Subspaces, and Infinite Family of Periodic Cycles in $\mathbb{Z} _ 2$ vs. $\mathbb{Z}$.
12. **Part XII:** Backward Dynamics of the Chain $Y _ j$ ($0 \le j \le N-1$), the Corrected Quadratic Autocorrelation Invariant ($+4X^2$), and Complete Proof of the Sieve $\Psi(P _ K) \equiv 18 \pmod{36}$.
13. **Part XIII:** Exponential Generating Functions, Exact Branchwise Multiplicative Quotients, Infinite Product for $\alpha$, and Inhomogeneous Recurrence at Cube Roots of Unity.
14. **Part XIV:** Ternary Symbolic Dynamics, Carry Transducer and Populations ($U _ n, D _ n, V _ n, K _ n$), Explicit Step-by-Step Example, the Universal Tail $\frac{3^m+3}{2}$, Relation to Mahler's Problem, and Bibliographical References.
15. **Part XV:** Exact Quadratic Telescoping of Step-Times $\Delta t _ n$ and the Cumulative Turing Machine Action Law ($T _ N$).
16. **Part XVI:** 2-Adic Bernoulli Isomorphism, Fuss-Catalan Halting Measure $\varphi^{-1}$, and Integer Fibonacci Conservation Laws.
17. **Part XVII:** The Tri-Local Adelic Bridge Series $\mathcal{S}(p)$ Across $(\mathbb{R}, \mathbb{Z} _ 2, \mathbb{Z} _ 3)$ and the Cubic Virial Theorem.
18. **Part XVIII:** The 3-Adic Ballot Sieve, Unconditional Modulo-54 Strengthening of $\Psi(P)$, and Closed-Form Enumeration of Terminal Halting Classes Modulo $3^M$.
19. **Appendix A:** Complete Empirical Table of the First 20 Steps and Verification of Invariants.
20. **Appendix B:** Computational Verification Suite for Selected Identities in Python (12 Audited Test Blocks).
21. **Appendix C:** Final Mathematical Audit Report and Exhaustive Change Log.

## Part I: The Antihydra Turing Machine in $BB(6)$, Verifiable Reduction to the Arithmetic System $(a _ n, b _ n)$, Modular Sieve, and Triad Balance

### 1.0. Definition of the Antihydra Turing Machine and Verifiable Reduction to the Arithmetic System $(a _ n, b _ n)$

The $6$-state, $2$-symbol Turing machine known as **Antihydra** (discovered within *The Busy Beaver Challenge* project by `mxdys` and whose high-level rules were deduced by `Racheline` on June 28, 2024; see Ligocki [2024] and *BusyBeaverWiki* [2024]) has the standard code in `bbchallenge` format:

$$
\texttt{1RB1RA\_0LC1LE\_1LD1LC\_1LA0LB\_1LF1RE\_---0RA}
$$

Its explicit transition table over the state set $Q = \lbrace A, B, C, D, E, F\rbrace$ (with initial state $A$) and tape alphabet $\Sigma = \lbrace 0, 1\rbrace$ (with initially blank tape $0^\infty$) is:

| State | Read symbol $0$ | Read symbol $1$ |
| --- | --- | --- |
| **A** | `1RB` (writes $1$, right, goes to $B$) | `1RA` (writes $1$, right, goes to $A$) |
| **B** | `0LC` (writes $0$, left, goes to $C$) | `1LE` (writes $1$, left, goes to $E$) |
| **C** | `1LD` (writes $1$, left, goes to $D$) | `1LC` (writes $1$, left, goes to $C$) |
| **D** | `1LA` (writes $1$, left, goes to $A$) | `0LB` (writes $0$, left, goes to $B$) |
| **E** | `1LF` (writes $1$, left, goes to $F$) | `1RE` (writes $1$, right, goes to $E$) |
| **F** | `---` (**HALT**) | `0RA` (writes $0$, right, goes to $A$) |

*(Fundamental remark: The only halting transition in the entire table is `F0`).*

**Theorem 1.0 (Exact Reduction of the Antihydra Turing Machine to the Dynamical System** $(a _ n, b _ n){}$) [Proved]: For any non-negative integers $b \ge 0$ and $h \ge 0$, let us define the canonical tape configuration:

$$
\mathcal{A}(b, h) := 0^\infty \thinspace  1^b \thinspace  0 \thinspace  1^h \thinspace  \mathbf{E>} \thinspace  0^\infty
$$

(where $\mathbf{E>}$ indicates that the head is in state $E$ scanning the first symbol $0$ to the right of the block $1^h$, and analogously $\mathbf{<S}$ indicates that the head scans the first symbol to its left). Then:

1. **Initialization Phase ($11$ steps):** Starting from the blank tape $0^\infty \mathbf{A>} 0^\infty$, in exactly $11$ machine steps the initial canonical configuration is reached:

$$
0^\infty \mathbf{A>} 0^\infty \xrightarrow{11\text{ steps}} 0^\infty \thinspace  1^0 \thinspace  0 \thinspace  1^4 \thinspace  \mathbf{E>} \thinspace  0^\infty = \mathcal{A}(0, 4)
$$

2. **High-Level Transition Rules (for $h \ge 4$):** Every canonical configuration $\mathcal{A}(b, h)$ with $h \ge 4$ evolves deterministically according to the parity of $h$:

   - **If $h = 2k$ is even ($k \ge 2$):** In $2b + 3k^2 + 12k + 11$ machine steps without ever visiting `F0`, it reaches:

$$
\mathcal{A}(b, 2k) \longrightarrow \mathcal{A}(b + 2, \thinspace  3k + 2) = \mathcal{A}\left(b + 2, \thinspace  \left\lfloor \frac{3h}{2} \right\rfloor + 2\right)
$$

   - **If $h = 2k + 1$ is odd ($k \ge 2$) and $b \ge 1$:** In $3k^2 + 12k + 5$ machine steps without visiting `F0`, it reaches:

$$
\mathcal{A}(b, 2k + 1) \longrightarrow \mathcal{A}(b - 1, \thinspace  3k + 3) = \mathcal{A}\left(b - 1, \thinspace  \left\lfloor \frac{3h}{2} \right\rfloor + 2\right)
$$

   - **If $h = 2k + 1$ is odd ($k \ge 2$) and $b = 0$:** In $3k^2 + 9k - 1$ machine steps, the head reaches the configuration $0^\infty \mathbf{<F} \thinspace  1101^{3k} 0^\infty$, reading the symbol $0$ in state $F$ *(`F0`) and **halting**.*
3. **Exact Conjugacy with the Shifted Sequence $a _ n = h _ n + 4$:** Let $(h _ n, b _ n) _ {n \ge 0}$ be the sequence of parameters of the canonical configurations $\mathcal{A}(b _ n, h _ n)$ visited successively starting from $(b _ 0, h _ 0) = (0, 4)$, with law $h _ {n+1} = \lfloor \frac{3h _ n}{2} \rfloor + 2$. Defining the translated change of variable:

$$
a_n := h_n + 4
$$

   one has $a _ 0 = 4 + 4 = 8$, the parity is identically preserved ($a _ n \bmod 2 = (h _ n + 4) \bmod 2 = h _ n \bmod 2 =: p _ n$), and the recurrence law transforms exactly into:

$$
a_{n+1} = h_{n+1} + 4 = \left\lfloor \frac{3(a_n - 4)}{2} \right\rfloor + 6 = \left\lfloor \frac{3a_n}{2} - 6 \right\rfloor + 6 = \left\lfloor \frac{3a_n}{2} \right\rfloor
$$

   while the counter $b _ n$ (which represents the exponent of the left block $1^{b _ n}$ on the tape) evolves according to $b _ {n+1} = b _ n + 2 - 3p _ n$, with the Turing machine halting if and only if at some step $n$ one has $b _ n = 0$ with $p _ n = 1$, which is equivalent to the counter reaching the value $b _ N = -1$ for the first time at $N = n + 1$.

**Verifiable Step-by-Step Proof:**

1. Initialization ($11$ steps): From $0^\infty \mathbf{A>} 0^\infty$:

   - Step 1 (`A0 -> 1RB`): $0^\infty 1 \mathbf{B>} 0^\infty$.
   - Step 2 (`B0 -> 0LC`): $0^\infty \mathbf{<C} 1 0^\infty$.
   - Step 3 (`C1 -> 1LC`): $0^\infty \mathbf{<C} 0 1 0^\infty$.
   - Step 4 (`C0 -> 1LD`): $0^\infty \mathbf{<D} 1 1 0^\infty$.
   - Step 5 (`D0 -> 1LA`): $0^\infty \mathbf{<A} 0 1 1 1 0^\infty$.
   - Step 6 (`A0 -> 1RB`): $0^\infty 1 \mathbf{B>} 1 1 1 0^\infty$.
   - Step 7 (`B1 -> 1LE`): $0^\infty \mathbf{<E} 1 1 1 1 0^\infty$.
   - Steps 8 to 11 (shift rule `E1 -> 1RE` applied $4$ times across $1^4$): $0^\infty 1^0 0 1^4 \mathbf{E>} 0^\infty = \mathcal{A}(0, 4)$.
2. Elementary shift rules and partial configuration $P(m, n)$: From the transition table one immediately verifies three block shift rules for every integer $s \ge 0$:

$$
\mathbf{A>} 1^s \xrightarrow{s\text{ steps}} 1^s \mathbf{A>}, \qquad 1^s \mathbf{<C} \xrightarrow{s\text{ steps}} \mathbf{<C} 1^s, \qquad \mathbf{E>} 1^s \xrightarrow{s\text{ steps}} 1^s \mathbf{E>}
$$

   Let us consider the subconfiguration $P(m, n) := 0 1^m \mathbf{E>} 0 1^n 0^\infty$ with $m \ge 4$ and $n \ge 0$:
   *In 2 steps (`E0 -> 1LF`, `F1 -> 0RA`):* $0 1^{m-1} 0 \mathbf{A>} 1^{n+1} 0^\infty$.
   In $n+1$ steps (shift `A>`): $0 1^{m-1} 0 1^{n+1} \mathbf{A>} 0^\infty$.
   *In 2 steps (`A0 -> 1RB`, `B0 -> 0LC`):* $0 1^{m-1} 0 1^{n+2} \mathbf{<C} 0^\infty$.
   In $n+2$ steps (shift `<C`): $0 1^{m-1} \mathbf{<C} 0 1^{n+2} 0^\infty$.
   *In 5 steps (`C0 -> 1LD`, `D1 -> 0LB`, `B1 -> 1LE`, `E1 -> 1RE`, `E1 -> 1RE`):* $0 1^{m-2} \mathbf{E>} 0 1^{n+3} 0^\infty = P(m - 2, n + 3)$.
   Thus, each application consumes $2$ units from $m$ and adds $3$ units to $n$ in $2n + 12$ steps: $P(m, n) \to P(m - 2, n + 3)$.
   Starting from $\mathcal{A}(b, h) = 0^\infty 1^b P(h, 0)$, we apply this reduction $\lfloor h/2 \rfloor - 1$ times:

   - **Case $h = 2k$ even:** One arrives at $0^\infty 1^b 0 1^2 \mathbf{E>} 0 1^{3k - 3} 0^\infty$. Advancing $3h + 4$ steps reaches $0^\infty 1^b \mathbf{<C} 0 0 1^{3k} 0^\infty$, which crosses the block $1^b$ in $b$ steps up to $0^\infty \mathbf{<C} 1^b 0 0 1^{3k} 0^\infty$. In $5$ steps (`C0 -> 1LD`, `D0 -> 1LA`, `A0 -> 1RB`, `B1 -> 1LE`, `E1 -> 1RE`) one obtains $0^\infty 1 \mathbf{E>} 1^{b+2} 0 0 1^{3k} 0^\infty$, and after crossing $1^{b+2}$ and the double separator $00$ (in $b + 2 + 6 + 3k$ steps) one reconstructs exactly $0^\infty 1^{b+2} 0 1^{3k + 2} \mathbf{E>} 0^\infty = \mathcal{A}(b + 2, 3k + 2)$.
   - **Case $h = 2k + 1$ odd:** One arrives at $0^\infty 1^b 0 1^3 \mathbf{E>} 0 1^{3k - 3} 0^\infty$. In $3h + 2$ additional steps the head consumes the three central ones and emerges to the left of the separator in state $F$: $0^\infty 1^b \mathbf{<F} 1 1 0 1^{3k} 0^\infty$.

     - If $b = 0$, the symbol to the left of $\mathbf{<F}$ is a $0$ of the blank tape ($0^\infty \mathbf{<F} 1 1 0 1^{3k} 0^\infty$), executing the undefined transition `F0` (**HALT**).
     - If $b \ge 1$, the symbol to the left of $\mathbf{<F}$ is the last $1$ of the block $1^b$. The transition `F1 -> 0RA` erases that $1$ (reducing the left block to $1^{b-1}$) and in $6 + 3k$ additional steps shifts the head to the right end, resulting in $0^\infty 1^{b-1} 0 1^{3k + 3} \mathbf{E>} 0^\infty = \mathcal{A}(b - 1, 3k + 3)$. $\blacksquare$

### 1.1. The Iterated Antihydra Operator

By virtue of Theorem 1.0, the halting problem for Antihydra is rigorously equivalent to studying the coupled discrete arithmetic dynamical system $(a _ n, b _ n)$ over the integers, governed by the operator $T: \mathbb{Z} \to \mathbb{Z}$:

$$
T(x) = x + \left\lfloor \frac{x}{2} \right\rfloor = \left\lfloor \frac{3x}{2} \right\rfloor = \frac{3x - (x \bmod 2)}{2} = \begin{cases} \frac{3x}{2} & \text{if } x \equiv 0 \pmod 2 \quad (p = 0) \cr \frac{3x - 1}{2} & \text{if } x \equiv 1 \pmod 2 \quad (p = 1) \end{cases}
$$

Given the initial condition (seed) at time $n = 0$:

$$
a_0 = 8, \qquad b_0 = 0
$$

the main sequence of states $\lbrace a _ n\rbrace _ {n=0}^\infty$ and the sequence of parity bits $\lbrace p _ n\rbrace _ {n=0}^\infty$ with $p _ n \in \lbrace 0, 1\rbrace$ are defined by the step-by-step linear recurrence relation:

$$
p_n = a_n \bmod 2 = 3a_n - 2a_{n+1}
$$

$$
2a_{n+1} = 3a_n - p_n
$$

### 1.2. The Halting Counter $b _ n$ and the Odd Step Accumulator $O _ n$

Simultaneously, the balance accumulator register or halting counter $b _ n \in \mathbb{Z}$ evolves step by step according to:

$$
b_{n+1} = b_n + 2 - 3p_n = \begin{cases} b_n + 2 & \text{if } p_n = 0 \text{ (even step)} \cr b_n - 1 & \text{if } p_n = 1 \text{ (odd step)} \end{cases}
$$

We define the **Odd Step Accumulator** $O _ n$ and the **Even Step Accumulator** $E _ n$ up to time $n-1$ as:

$$
O_n = \sum_{k=0}^{n-1} p_k, \qquad E_n = \sum_{k=0}^{n-1} (1 - p_k) = n - O_n
$$

Summing the difference equation for $b _ n$ telescopically from $k = 0$ to $n - 1$, with $b _ 0 = 0$:

$$
b_n = \sum_{k=0}^{n-1} (2 - 3p_k) = 2n - 3 \sum_{k=0}^{n-1} p_k = 2n - 3O_n = 2E_n - O_n
$$

### 1.3. Temporal Congruence Lemma for Halting

**Halting Condition:** By Theorem 1.0(3), the Antihydra Turing machine halts if and only if there exists some integer $N \ge 1$ such that the counter reaches for the first time the critical value:

$$
b_N = -1
$$

**Lemma 1.1 (Modular Restriction on $N$ and** $O _ N$) [Proved]: For every $n \ge 0$, the counter invariably satisfies the congruence $b _ n \equiv 2n \pmod 3$. Consequently, the machine can only halt at steps satisfying $N \equiv 1 \pmod 3$, that is, $N = 3P + 1$ for some integer $P \ge 0$, in which case the number of even and odd steps is rigidly fixed by:

$$
E_N = P, \qquad O_N = 2P + 1, \qquad 3O_N = 2N + 1
$$

Furthermore, for $N \ge 4$ ($P \ge 1$), the last two steps prior to the first halt are forced to be odd ($b _ {N-2} = 1, b _ {N-1} = 0, b _ N = -1 \implies p _ {N-2} = p _ {N-1} = 1$).

**Proof:**
Reducing $b _ n = 2n - 3O _ n$ modulo $3$, the term $-3O _ n$ vanishes identically, yielding $b _ n \equiv 2n \pmod 3$. If $b _ N = -1 \equiv 2 \pmod 3$, then $2N \equiv 2 \pmod 3$. Multiplying by $2$ (the inverse of $2$ modulo $3$), we obtain $N \equiv 1 \pmod 3$. Writing $N = 3P + 1$, we substitute into $2N - 3O _ N = -1$:

$$
2(3P + 1) - 3O_N = -1 \implies 6P + 3 = 3O_N \implies O_N = 2P + 1
$$

and the number of even steps is $E _ N = N - O _ N = (3P + 1) - (2P + 1) = P$. Since $N$ is the first time with $b _ N = -1$, necessarily $b _ {N-1} \ge 0$ and $b _ {N-2} \ge 0$. Given that the step increment is $+2$ or $-1$, the only way to reach $-1$ from $\ge 0$ is $b _ {N-1} = 0$ with $p _ {N-1} = 1$; and since $b _ {N-2} \equiv 2(3P-1) \equiv 1 \pmod 3$ with $b _ {N-2} \ge 0$, the only way to descend to $b _ {N-1} = 0$ is $b _ {N-2} = 1$ with $p _ {N-2} = 1$. $\blacksquare$

### 1.4. Decomposition into Aligned Triads and the Quasi-Constant Invariant $\Omega _ k$

**Theorem 1.2 (Triad Balance and Two-Sided Bound on** $\Omega _ k$) [Proved]: Dividing the trajectory up to step $3M$ into $M$ disjoint triads $B _ k = (3k, 3k+1, 3k+2)$ with $e _ k = p _ {3k} + p _ {3k+1} + p _ {3k+2} \in \lbrace 0, 1, 2, 3\rbrace$:

1. The change of the counter in each triad is $\Delta^{(3)} b _ {3k} = b _ {3k+3} - b _ {3k} = 3(2 - e _ k) \in \lbrace +6, +3, 0, -3\rbrace$. If $T _ j$ denotes the number of triads with $e _ k = j$, then $\frac{b _ {3M}}{3} = 2T _ 0 + T _ 1 - T _ 3$, and the necessary halting condition $b _ {3M} = 0$ requires $T _ 3 = 2T _ 0 + T _ 1$.
2. The triad weight $W _ k = 27a _ {3k} - 8a _ {3k+3} = 9p _ {3k} + 6p _ {3k+1} + 4p _ {3k+2}$ decomposes exactly by eliminating the central bit $p _ {3k+1}$ as:

$$
W_k = 6e_k + (3p_{3k} - 2p_{3k+2}) = 12 - 2\Delta^{(3)} b_{3k} + 3p_{3k} - 2p_{3k+2}
$$

3. Consequently, the linear combination $\Omega _ k := (27a _ {3k} - 8a _ {3k+3}) + 2(b _ {3k+3} - b _ {3k}) = 12 + 3p _ {3k} - 2p _ {3k+2}$ can only take values in the finite set $\lbrace 10, 12, 13, 15\rbrace$.

**Proof:**
Unrolling $2a _ {n+1} = 3a _ n - p _ n$ three times yields $8a _ {3k+3} = 27a _ {3k} - (9p _ {3k} + 6p _ {3k+1} + 4p _ {3k+2})$. Since $6(p _ {3k} + p _ {3k+1} + p _ {3k+2}) + 3p _ {3k} - 2p _ {3k+2} = 9p _ {3k} + 6p _ {3k+1} + 4p _ {3k+2}$ and $6e _ k = 12 - 2\Delta^{(3)}b _ {3k}$, solving for $W _ k + 2\Delta^{(3)}b _ {3k}$ results in $12 + 3p _ {3k} - 2p _ {3k+2} \in \lbrace 10, 12, 13, 15\rbrace$. $\blacksquare$

### 1.5. Closed-Form Step-by-Step Linear Trajectory Formula

Multiplying $a _ {k+1} = \frac{3}{2}a _ k - \frac{1}{2}p _ k$ by $2^{k+1} 3^{n-1-k}$ and summing telescopically from $k = 0$ to $n - 1$, we obtain the **Fundamental Trajectory Identity** [Proved]:

$$
2^n a_n = 3^n a_0 - \sum_{k=0}^{n-1} 3^{n-1-k} 2^k p_k = 8 \cdot 3^n - \sum_{k=0}^{n-1} 3^{n-1-k} 2^k p_k
$$

## Part II: Spin Duality, Dirichlet Character $\chi _ 4$, Modulo 8 Relations, Reflection $\mathcal{J}(a) = 1 - a$, and Boolean Cubic Identity

### 2.1. Fixed Points in $\mathbb{Z} _ 2$, the Odd Dual Coordinate $u _ n$, Character $\chi _ 4$, and Modulo 8 Classification

In the ring of 2-adic integers $\mathbb{Z} _ 2$, the two affine branches of the operator $T$ possess two fixed points:

- Even branch ($p = 0$): $T _ 0(x) = \frac{3x}{2} = x \implies x = 0$.
- Odd branch ($p = 1$): $T _ 1(x) = \frac{3x - 1}{2} = x \implies x = 1$.

To symmetrize both branches with respect to their center $1/2$, we introduce the **Shifted Dual Sequence** $u _ n$ and the **Parity Spin** $\sigma _ n$:

$$
u_n = 2a_n - 1, \qquad \sigma_n = 1 - 2p_n \in \lbrace -1, +1\rbrace
$$

Theorem 2.1 (Symmetric Spin Equation, Modulo 4 Character, and Exhaustive Modulo 8 Relations) [Proved]: For every $n \ge 0$, the integer $u _ n$ is strictly odd ($u _ n \equiv 1 \pmod 2$), starts from the seed $u _ 0 = 15$, and evolves via the symmetric law:

$$
u_{n+1} = \frac{3u_n + \sigma_n}{2} \iff 2u_{n+1} - 3u_n = \sigma_n
$$

Moreover, the spin $\sigma _ n$, its transition $\sigma _ {n+1}$, and the pair $(p _ n, p _ {n+1})$ are intrinsically determined by the residue classes of $a _ n$ modulo $4$ and modulo $8$ (equivalently, of $u _ n$ modulo $8$ and modulo $16$):

1. **Modulo 4 Character Law:** $u _ n + \sigma _ n \equiv 0 \pmod 4 \iff \sigma _ n = -\chi _ 4(u _ n) = -(-1)^{(u _ n - 1)/2}$. In terms of $a _ n = 4q + r _ 4$ ($r _ 4 \in \lbrace 0,1,2,3\rbrace$), the parity change $p _ n \oplus p _ {n+1}$ satisfies exactly:

$$
p_{n+1} \equiv p_n + \left\lfloor \frac{a_n \bmod 4}{2} \right\rfloor \pmod 2 \iff \sigma_{n+1} = (-1)^{\lfloor (a_n \bmod 4)/2 \rfloor} \sigma_n
$$

2. **Modulo 8 Spin Transition Equivalence:** $\sigma _ {n+1} = \sigma _ n \iff u _ n + \sigma _ n \equiv 0 \pmod 8 \iff a _ n \bmod 4 \in \lbrace 0, 1\rbrace$, and $\sigma _ {n+1} = -\sigma _ n \iff u _ n + \sigma _ n \equiv 4 \pmod 8 \iff a _ n \bmod 4 \in \lbrace 2, 3\rbrace$.

**Exhaustive Explicit Proof (All Residues Modulo 4 and Modulo 8):**
Substituting $a _ {n+1} = \frac{3a _ n - p _ n}{2}$ and $a _ n = \frac{u _ n + 1}{2}$ into $u _ {n+1} = 2a _ {n+1} - 1$:

$$
u_{n+1} = 3\left(\frac{u_n + 1}{2}\right) - p_n - 1 = \frac{3u_n + (1 - 2p_n)}{2} = \frac{3u_n + \sigma_n}{2}
$$

Subtracting $u _ n$ from both sides yields the key identity:

$$
u_{n+1} - u_n = \frac{u_n + \sigma_n}{2}
$$

Since $u _ n = 2a _ n - 1$ and $u _ {n+1} = 2a _ {n+1} - 1$ are both odd for all $n \ge 0$, their difference $u _ {n+1} - u _ n = 2(a _ {n+1} - a _ n)$ is always even. Therefore, $\frac{u _ n + \sigma _ n}{2}$ is an even integer, which is equivalent to $u _ n + \sigma _ n \equiv 0 \pmod 4$. Since $\sigma _ n \in \lbrace -1, +1\rbrace$, if $u _ n \equiv 1 \pmod 4$ then $\sigma _ n = -1 = -\chi _ 4(u _ n)$, and if $u _ n \equiv 3 \pmod 4$ then $\sigma _ n = +1 = -\chi _ 4(u _ n)$.

For the transition to the next step, we reduce the identity $u _ {n+1} - u _ n = \frac{u _ n + \sigma _ n}{2}$ modulo $4$:

- By part (1) applied to $n+1$, we have $\sigma _ {n+1} = -\chi _ 4(u _ {n+1})$, hence $\sigma _ {n+1} = \sigma _ n \iff u _ {n+1} \equiv u _ n \pmod 4 \iff 4 \mid (u _ {n+1} - u _ n) \iff 4 \mid \frac{u _ n + \sigma _ n}{2} \iff u _ n + \sigma _ n \equiv 0 \pmod 8$.
- Analogously, $\sigma _ {n+1} = -\sigma _ n \iff u _ {n+1} - u _ n \equiv 2 \pmod 4 \iff \frac{u _ n + \sigma _ n}{2} \equiv 2 \pmod 4 \iff u _ n + \sigma _ n \equiv 4 \pmod 8$.

Let us explicitly check the 8 possible residues of $a _ n = 8k + r _ 8$ ($r _ 8 \in \lbrace 0, 1, \dots, 7\rbrace$) without omitting any case:

| Class $a _ n \bmod 8$ | $u _ n = 2a _ n - 1 \bmod 16$ | $(p _ n, \sigma _ n)$ | $u _ n + \sigma _ n \bmod 8$ | Exact expression $a _ {n+1}$ | Class $a _ {n+1} \bmod 4$ | $(p _ {n+1}, \sigma _ {n+1})$ | Triplet $(p _ n, p _ {n+1}, p _ {n+2})$ |
| --- | --- | --- | --- | --- | --- | --- | --- |
| $0$ ($8k$) | $16k - 1 \equiv 15$ | $(0, +1)$ | $0 \pmod 8$ | $12k$ | $0 \pmod 4$ | $(0, +1)$ | $(0, 0, 0)$ |
| $1$ ($8k+1$) | $16k + 1 \equiv 1$ | $(1, -1)$ | $0 \pmod 8$ | $12k + 1$ | $1 \pmod 4$ | $(1, -1)$ | $(1, 1, 1)$ |
| $2$ ($8k+2$) | $16k + 3 \equiv 3$ | $(0, +1)$ | $4 \pmod 8$ | $12k + 3$ | $3 \pmod 4$ | $(1, -1)$ | $(0, 1, 0)$ |
| $3$ ($8k+3$) | $16k + 5 \equiv 5$ | $(1, -1)$ | $4 \pmod 8$ | $12k + 4$ | $0 \pmod 4$ | $(0, +1)$ | $(1, 0, 0)$ |
| $4$ ($8k+4$) | $16k + 7 \equiv 7$ | $(0, +1)$ | $0 \pmod 8$ | $12k + 6$ | $2 \pmod 4$ | $(0, +1)$ | $(0, 0, 1)$ |
| $5$ ($8k+5$) | $16k + 9 \equiv 9$ | $(1, -1)$ | $0 \pmod 8$ | $12k + 7$ | $3 \pmod 4$ | $(1, -1)$ | $(1, 1, 0)$ |
| $6$ ($8k+6$) | $16k + 11 \equiv 11$ | $(0, +1)$ | $4 \pmod 8$ | $12k + 9$ | $1 \pmod 4$ | $(1, -1)$ | $(0, 1, 1)$ |
| $7$ ($8k+7$) | $16k + 13 \equiv 13$ | $(1, -1)$ | $4 \pmod 8$ | $12k + 10$ | $2 \pmod 4$ | $(0, +1)$ | $(1, 0, 1)$ |

The table exhausts all 8 residue classes modulo $8$ without exception. $\blacksquare$

### 2.2. Total Magnetization and the Boolean Cubic Identity of Triads

We define the **Cumulative Magnetization** up to step $n$:

$$
M_n^{(\sigma)} = \sum_{k=0}^{n-1} \sigma_k = \sum_{k=0}^{n-1} (1 - 2p_k) = E_n - O_n = n - 2O_n
$$

Substituting $O _ n = \frac{n - M _ n^{(\sigma)}}{2}$ into $b _ n = 2n - 3O _ n$, we obtain $b _ n = \frac{n + 3M _ n^{(\sigma)}}{2}$, so that the halting condition $b _ N = -1$ is equivalent to $3M _ N^{(\sigma)} = -(N + 2)$.

Theorem 2.2 (Boolean Cubic Identity of Spin Triads) [Proved]: In any block of three consecutive steps $(n, n+1, n+2)$, let $W _ n^{(\sigma)} = 8u _ {n+3} - 27u _ n = 9\sigma _ n + 6\sigma _ {n+1} + 4\sigma _ {n+2} \in \lbrace \pm 1, \pm 7, \pm 11, \pm 19\rbrace$. Then:

1. $(8u _ {n+3} - 27u _ n)^2 = 133 + 108\sigma _ n\sigma _ {n+1} + 72\sigma _ n\sigma _ {n+2} + 48\sigma _ {n+1}\sigma _ {n+2}$.
2. The sign $\operatorname{sgn}(8u _ {n+3} - 27u _ n)$ always coincides with the majority sign $\operatorname{sgn}(\sigma _ n + \sigma _ {n+1} + \sigma _ {n+2}) \in \lbrace -1, +1\rbrace$*, and the **Exact Boolean Cubic Identity** holds:*

$$
\sigma_n + \sigma_{n+1} + \sigma_{n+2} = 2\operatorname{sgn}(8u_{n+3} - 27u_n) + \sigma_n \sigma_{n+1} \sigma_{n+2}
$$

**Proof:**
Since $6 + 4 = 10 > 9$, if at least two spins in the triad equal $+1$, then $9\sigma _ n + 6\sigma _ {n+1} + 4\sigma _ {n+2} \ge -9 + 6 + 4 = +1 > 0$; and if at least two equal $-1$, the sum is $\le +9 - 6 - 4 = -1 < 0$. Evaluating $\sigma _ n + \sigma _ {n+1} + \sigma _ {n+2} - \sigma _ n\sigma _ {n+1}\sigma _ {n+2}$ on the 8 triads of $\lbrace -1, +1\rbrace ^3$, it equals $+2$ when there are two or three $+1$'s and equals $-2$ when there are two or three $-1$'s, coinciding identically with $2\operatorname{sgn}(8u _ {n+3} - 27u _ n)$. $\blacksquare$

### 2.3. Self-Duality Theorem via Affine Reflection $\mathcal{J}(a) = 1 - a$

**Theorem 2.3 (Conjugacy by Inversion** $\mathcal{J}$) [Proved]: Let $\mathcal{J}: \mathbb{Z} _ 2 \to \mathbb{Z} _ 2$ be the affine involution defined by $\mathcal{J}(a) = 1 - a$. Then:

1. $\mathcal{J}$ *inverts the parity of every state:* $(1 - a) \bmod 2 = 1 - (a \bmod 2)$.
2. $\mathcal{J}$ commutes exactly with the Antihydra operator $T$:

$$
T(1 - a) = 1 - T(a) \qquad \forall a \in \mathbb{Z}_2
$$

3. For every $k \ge 1$, $T^k(1 - a) = 1 - T^k(a)$. If a state $a \in \mathbb{Z} _ 2$ generates the infinite sequence of parity bits $(p _ 0, p _ 1, p _ 2, \dots)$, the reflected state $1 - a$ generates the exact complementary sequence $(1 - p _ 0, 1 - p _ 1, 1 - p _ 2, \dots)$.

**Proof:**
Let $p = a \bmod 2 \in \lbrace 0, 1\rbrace$. The integer $\tilde{a} = 1 - a$ has parity $\tilde{p} = 1 - p$. Applying $T$:

$$
T(1 - a) = \frac{3(1 - a) - (1 - p)}{2} = \frac{2 - 3a + p}{2} = 1 - \frac{3a - p}{2} = 1 - T(a) \quad \blacksquare
$$

## Part III: Macro-Cycle Renormalization, Cumulative Even Count $P _ K$, the Four Valuation Laws, and the Universal Floor Formula

### 3.1. Well-Defined Decomposition of the Orbit into Even ($r _ i$) and Odd ($m _ i$) Runs and Notation $P _ K$

(Notational remark: To avoid any symbolic collision with the Archimedean residual defect $R _ n = a _ n - \alpha(3/2)^n$ of Part IV, throughout the treatise we denote by $P _ K$ the cumulative number of even steps at the close of macro-cycle $K$).

**Proposition 3.0 (Finiteness of Runs and Well-Definedness of Macro-Cycles in** $\mathbb{Z} _ {\ge 2}$) [Proved]: For any even integer seed $a _ 0 \ge 2$ (in particular $a _ 0 = 8$), every phase of consecutive even steps and every phase of consecutive odd steps has finite length:

1. If $a _ n \ge 2$ is even, let $r = v _ 2(a _ n) \ge 1$ be its exact 2-adic valuation ($a _ n = 2^r c$ with $c \ge 1$ odd). Then for $0 \le j < r$, $a _ {n+j} = 3^j 2^{r-j} c$ is even, and at $j = r$ the odd integer $a _ {n+r} = 3^r c$ is reached.
2. If $a _ t \ge 3$ is odd, then $a _ t - 1 \ge 2$ is a non-zero positive even integer. Let $m = v _ 2(a _ t - 1) \ge 1$ be its exact 2-adic valuation ($a _ t - 1 = 2^m d$ with $d \ge 1$ odd). Since $a _ {k+1} - 1 = \frac{3}{2}(a _ k - 1)$ when $a _ k$ is odd, for $0 \le j < m$ one has $a _ {t+j} = 3^j 2^{m-j} d + 1 \equiv 1 \pmod 2$, and at $j = m$ the even integer $a _ {t+m} = 3^m d + 1 \equiv 0 \pmod 2$ is reached.

Consequently, the Antihydra trajectory starting from $a _ 0 = 8$ partitions uniquely and infinitely into macro-cycles $i = 1, 2, \dots$. Each cycle $i \ge 1$ consists of:

1. A maximal **even pumping** phase of finite duration $r _ i \in \mathbb{Z} _ {\ge 1}$ consecutive steps with $p _ n = 0$ (where the counter rises by $+2r _ i$).
2. Followed by a maximal **odd drop** phase of finite duration $m _ i \in \mathbb{Z} _ {\ge 1}$ consecutive steps with $p _ n = 1$ (where the counter falls by $-m _ i$).

We define the cumulative times up to the end of cycle $K$:

$$
P_K := \sum_{i=1}^{K} r_i, \qquad M_K := \sum_{i=1}^{K} m_i, \qquad N_K := P_K + M_K, \qquad t_i := P_i + M_{i-1} \quad (M_0 := 0, N_0 := 0)
$$

### 3.2. Internal Dynamics of a Cycle and Domain of the Odd Cores $(c _ i, d _ i)$

- **During even phase $i$ (of duration $r _ i \ge 1$):**
  The state at the start of the cycle at step $N _ {i-1}$ factors uniquely in $\mathbb{Z} _ {\ge 2}$ by extracting its maximal power of $2$:

$$
a_{N_{i-1}} = 2^{r_i} c_i, \qquad \text{with } c_i \in \mathbb{Z}_{\ge 1}, \quad c_i \equiv 1 \pmod 2 \text{ (entry odd core)}
$$

  After $r _ i$ multiplications by $3/2$, the state at the peak of the cycle (step $t _ i$) is the odd integer:

$$
a_{t_i} = 3^{r_i} c_i
$$

- **During odd phase $i$ (of duration $m _ i \ge 1$):**
  Factoring the positive even integer $a _ {t _ i} - 1 = 3^{r _ i} c _ i - 1 \ge 26$:

$$
a_{t_i} - 1 = 3^{r_i} c_i - 1 = 2^{m_i} d_i, \qquad \text{with } d_i \in \mathbb{Z}_{\ge 1}, \quad d_i \equiv 1 \pmod 2 \text{ (valley odd core)}
$$

  After these $m _ i$ odd steps, at time $N _ i = t _ i + m _ i$, the state reaches the even number that initiates cycle $i+1$:

$$
a_{N_i} = 3^{m_i} d_i + 1 = 2^{r_{i+1}} c_{i+1}
$$

### 3.3. Theorem of the Four Exact Valuation Laws (2-adic and 3-adic Symmetry)

Theorem 3.1 (The Four Macro-Cycle Valuation Laws) [Proved]: For every cycle $i \ge 1$, the cores $c _ i, d _ i \in \mathbb{Z} _ {\ge 1}$ are odd and coprime to $3$ ($3 \nmid c _ i$ and $3 \nmid d _ i$, since for $i=1$, $c _ 1 = 1 \not\equiv 0 \pmod 3$, $2^{m _ i} d _ i = 3^{r _ i}c _ i - 1 \equiv -1 \pmod 3 \implies 3 \nmid d _ i$, and $2^{r _ {i+1}}c _ {i+1} = 3^{m _ i}d _ i + 1 \equiv 1 \pmod 3 \implies 3 \nmid c _ {i+1}$). Consequently, the durations $r _ i$ and $m _ i$ simultaneously satisfy the four exact identities:

1. **2-adic Even Pumping Law:** $r _ i = v _ 2(3^{m _ {i-1}} d _ {i-1} + 1)$ (for $i \ge 2$, with $r _ 1 = v _ 2(8) = 3$).
2. **3-adic Even Pumping Law:** $r _ i = v _ 3(2^{m _ i} d _ i + 1)$ (for all $i \ge 1$).
3. **2-adic Odd Drop Law:** $m _ i = v _ 2(3^{r _ i} c _ i - 1)$ (for all $i \ge 1$).
4. **3-adic Odd Drop Law:** $m _ i = v _ 3(2^{r _ {i+1}} c _ {i+1} - 1)$ (for all $i \ge 1$).

**Proof:**
From $3^{r _ i} c _ i = 2^{m _ i} d _ i + 1$ with $2 \nmid d _ i$ and $3 \nmid c _ i$, taking $p$-adic valuations yields $v _ 2(3^{r _ i} c _ i - 1) = v _ 2(2^{m _ i} d _ i) = m _ i + v _ 2(d _ i) = m _ i$, and $v _ 3(2^{m _ i} d _ i + 1) = v _ 3(3^{r _ i} c _ i) = r _ i + v _ 3(c _ i) = r _ i$. Analogously, from $2^{r _ {i+1}} c _ {i+1} = 3^{m _ i} d _ i + 1$ with $2 \nmid c _ {i+1}$ and $3 \nmid d _ i$, taking $v _ 2$ and $v _ 3$ yields laws (1) and (4). $\blacksquare$

### 3.4. The Double Bridge Identity and the Universal Floor Formula for Odd Cores

Theorem 3.2 (Universal Floor Formula between Consecutive Cores) [Proved]: Consecutive odd cores $d _ i$ and $d _ {i+1}$ are directly coupled without passing through $c _ {i+1}$ via the exact Diophantine equation:

$$
3^{m_i + r_{i+1}} d_i + 3^{r_{i+1}} - 2^{r_{i+1}} = 2^{r_{i+1} + m_{i+1}} d_{i+1}
$$

Solving for $d _ i$ in terms of $d _ {i+1}$, for every cycle $i \ge 1$ the exact floor identity (free of integer boundary cases) holds:

$$
d_i = \left\lfloor \frac{2^{r_{i+1} + m_{i+1}}}{3^{m_i + r_{i+1}}} d_{i+1} \right\rfloor
$$

whose fractional part belongs strictly to the open interval $(0, 1/3)$ and equals:

$$
\left\lbrace \frac{2^{r_{i+1} + m_{i+1}}}{3^{m_i + r_{i+1}}} d_{i+1} \right\rbrace = \frac{3^{r_{i+1}} - 2^{r_{i+1}}}{3^{m_i + r_{i+1}}} = \frac{1 - (2/3)^{r_{i+1}}}{3^{m_i}} \in \left(0, \frac{1}{3}\right)
$$

Furthermore, in every cycle $i \ge 1$ one has $(2^{m _ i} d _ i + 1) \bmod 9 \in \lbrace 0, 6\rbrace$.

**Proof:**
Equating the two expressions for $c _ {i+1} = \frac{3^{m _ i} d _ i + 1}{2^{r _ {i+1}}} = \frac{2^{m _ {i+1}} d _ {i+1} + 1}{3^{r _ {i+1}}}$ and dividing by $3^{m _ i}$:

$$
\frac{2^{r_{i+1} + m_{i+1}}}{3^{m_i + r_{i+1}}} d_{i+1} = d_i + \frac{1 - (2/3)^{r_{i+1}}}{3^{m_i}}
$$

Given that $r _ {i+1} \ge 1$ and $m _ i \ge 1$, we have $(2/3)^{r _ {i+1}} \in (0, 2/3]$ and $3^{m _ i} \ge 3$, so that the fractional remainder strictly satisfies:

$$
0 < \frac{1 - 2/3}{3^{m_i}} \le \frac{1 - (2/3)^{r_{i+1}}}{3^{m_i}} < \frac{1}{3^{m_i}} \le \frac{1}{3} < 1
$$

In particular, the rational quotient $\frac{2^{r _ {i+1} + m _ {i+1}}}{3^{m _ i + r _ {i+1}}} d _ {i+1}$ is never an integer, and since $d _ i \in \mathbb{Z}$, its floor is exactly $d _ i$. Finally, since $2^{m _ i} d _ i + 1 = 3^{r _ i} c _ i$, if $r _ i \ge 2$ it is $\equiv 0 \pmod 9$, and if $r _ i = 1$ (which can only occur for $i \ge 2$) then $2 c _ i = 3^{m _ {i-1}} d _ {i-1} + 1 \equiv 1 \pmod 3 \implies c _ i \equiv 2 \pmod 3 \implies 3c _ i \equiv 6 \pmod 9$. $\blacksquare$

### 3.5. Audited Table of the First 10 Macro-Cycles of Antihydra

Computing with exact integer precision from $a _ 0 = 8 = 2^3 \cdot 1$ ($r _ 1 = 3, c _ 1 = 1$), we obtain the exact parameters of the first 10 macro-cycles (where $B _ i = b _ {N _ i} = \sum _ {j=1}^i (2r _ j - m _ j){}$) [Computationally Verified in Finite Range $1 \le i \le 10$]:

| Cycle ($i$) | Even pumping ($r _ i$) | Odd drop ($m _ i$) | Cumulative even ($P _ i$) | Even core ($c _ i$) | Odd core ($d _ i$) | Jump $\Delta B _ i = 2r _ i - m _ i$ | Counter ($B _ i$) | Step ($N _ i$) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **1** | 3 | 1 | 3 | 1 | 13 | $+5$ | 5 | 4 |
| **2** | 3 | 1 | 6 | 5 | 67 | $+5$ | 10 | 8 |
| **3** | 1 | 1 | 7 | 101 | 151 | $+1$ | 11 | 10 |
| **4** | 1 | 3 | 8 | 227 | 85 | $-1$ | 10 | 14 |
| **5** | 3 | 2 | 11 | 287 | 1937 | $+4$ | 14 | 19 |
| **6** | 1 | 1 | 12 | 8717 | 13075 | $+1$ | 15 | 21 |
| **7** | 1 | 1 | 13 | 19613 | 29419 | $+1$ | 16 | 23 |
| **8** | 1 | 1 | 14 | 44129 | 66193 | $+1$ | 17 | 25 |
| **9** | 2 | 2 | 16 | 49645 | 111701 | $+2$ | 19 | 29 |
| **10** | 1 | 2 | 17 | 502655 | 376991 | $0$ | 19 | 32 |

## Part IV: Archimedean Domain, the Antihydra Constant $\alpha$, Non-Integrality $R _ n \in (0,1)$, and the SWRO

### 4.1. Construction, Rigorous Truncation Bound, and Certified Exact Value of $\alpha$

Dividing the Fundamental Trajectory Identity $2^n a _ n = 8 \cdot 3^n - \sum _ {k=0}^{n-1} 3^{n-1-k} 2^k p _ k$ by $3^n$, we define the monotonically non-increasing rational sequence:

$$
\alpha_n := \left(\frac{2}{3}\right)^n a_n = 8 - \sum_{k=0}^{n-1} \frac{2^k}{3^{k+1}} p_k
$$

**Theorem 4.1 (Absolute Convergence, Truncation Bound of $\alpha$, and Strict Confinement** $R _ n \in (0,1){}$) [Proved]: 

1. The series $\sum _ {k=0}^{\infty} \frac{2^k}{3^{k+1}} p _ k$ is dominated term-by-term by the convergent geometric series $\frac{1}{3}\sum _ {k=0}^\infty (2/3)^k = 1$, so it converges absolutely to a real number $\alpha = \lim _ {n\to\infty} \alpha _ n \in [7, 8]$ *(the **Antihydra Constant**).*
2. For any integer truncation horizon $M \ge 1$, the excess error $\alpha _ M - \alpha$ satisfies the rigorous bound:

$$
0 < \alpha_M - \alpha = \sum_{k=M}^{\infty} \frac{2^k}{3^{k+1}} p_k < \frac{1}{3} \sum_{k=M}^{\infty} \left(\frac{2}{3}\right)^k = \left(\frac{2}{3}\right)^M
$$

   In particular, for $M = 300$, the exact value of the geometric bound is:

$$
\left(\frac{2}{3}\right)^{300} \approx 1.4880663064957113 \times 10^{-53} < 1.49 \times 10^{-53}
$$

   Evaluating $\alpha _ {300} = (2/3)^{300} a _ {300}$ with exact rational arithmetic yields:

$$
\alpha_{300} = 7.8641772620566189724051685296822813853074242517735940028\dots
$$

   Since $\alpha _ {300} - 1.49 \times 10^{-53} < \alpha < \alpha _ {300}$ and the decimal digits from position $1$ to position $52$ after the decimal point of $\alpha _ {300}$ (`...735940...`) undergo no borrows when subtracting $1.49 \times 10^{-53}$ (which affects only from decimal position $53$ *onward), the first **50 decimal digits after the decimal point** are rigorously certified and immutable as:*

$$
\alpha = 8 - \sum_{k=0}^{\infty} \frac{2^k}{3^{k+1}} p_k = 7.86417726205661897240516852968228138530742425177359\dots
$$

3. For every integer $n \ge 0$, the Archimedean residual defect:

$$
R_n := a_n - \alpha\left(\frac{3}{2}\right)^n = \sum_{j=0}^{\infty} \frac{2^j}{3^{j+1}} p_{n+j}
$$

   satisfies the strict inequality $0 < R _ n < 1$. In particular, $\alpha(3/2)^n \notin \mathbb{Z}$ for all $n \ge 0$, so the integer boundary values are never attained, and the exact identities hold simultaneously for all $n \ge 0$:

$$
a_n = \left\lceil \alpha \left(\frac{3}{2}\right)^n \right\rceil, \qquad a_n - 1 = \left\lfloor \alpha \left(\frac{3}{2}\right)^n \right\rfloor
$$

**Proof of (3) (Rigorous Exclusion of the Endpoints $R _ n = 0$ and $R _ n = 1$):**
Since $p _ {n+j} \in \lbrace 0, 1\rbrace$ and $\sum _ {j=0}^\infty \frac{2^j}{3^{j+1}} = 1$, we have $0 \le R _ n \le 1$.

- If $R _ n = 0$, then since each summand is non-negative we would have $p _ {n+j} = 0$ for all $j \ge 0$. However, by Proposition 3.0(1), since $a _ n \ge a _ 0 = 8 > 0$, the valuation $r = v _ 2(a _ n) < \infty$ is finite and $p _ {n+r} = 1$, a contradiction. Hence $R _ n > 0$.
- If $R _ n = 1$, then $1 - R _ n = \sum _ {j=0}^\infty \frac{2^j}{3^{j+1}}(1 - p _ {n+j}) = 0 \implies p _ {n+j} = 1$ for all $j \ge 0$. However, by Proposition 3.0(2), since $a _ n \ge 8 > 1$, the valuation $m = v _ 2(a _ n - 1) < \infty$ is finite and after at most $m$ steps an even state with $p _ {n+m} = 0$ is reached, a contradiction. Hence $R _ n < 1$.
  Since $a _ n \in \mathbb{Z}$ and $a _ n - 1 < a _ n - R _ n = \alpha(3/2)^n < a _ n$, the ceiling and floor formulas are proved for all $n \ge 0$. $\blacksquare$

### 4.2. Ergodic Equation of $R _ n$ and the Sliding Window Operator

**Corollary 4.2 (Recurrence of $R _ n$ and Decomposition of** $b _ N$) [Proved]: For all $n \ge 0$:

1. The exponential part $\alpha(3/2)^n$ vanishes identically in the difference operator $2a _ {n+1} - 3a _ n = -p _ n$, leaving:

$$
2R_{n+1} - 3R_n = -p_n \iff R_n = \frac{p_n}{3} + \frac{2}{3}R_{n+1}
$$

   which partitions the interval $(0, 1)$ into two regimes: if $p _ n = 0 \implies R _ n \in (0, 2/3)$, and if $p _ n = 1 \implies R _ n \in (1/3, 1)$.
2. Substituting $p _ k = 3R _ k - 2R _ {k+1}$ into $b _ N = \sum _ {k=0}^{N-1}(2 - 3p _ k)$, the counter satisfies the exact identity:

$$
b_N = \sum_{k=0}^{N-1} (2 - 3R_k) + 6(R_N - R_0) > \sum_{k=0}^{N-1} (2 - 3R_k) - 1
$$

   (where the last inequality uses $R _ 0 = 8 - \alpha \approx 0.1358227379\dots < 1/6$ and $R _ N > 0$, whence $6(R _ N - R _ 0) > -6R _ 0 > -1$).

## Part V: The Exact Integral Invariant ($44 \cdot 3^n$), the Dual Identities ($O _ n, E _ n$), the Corrected Identity for $b _ N$ in Terms of $Z _ k$, and Convergence of Weighted Series

### 5.1. Diophantine Integral Invariant Theorem and the Exact Identities for $O _ n$, $E _ n$, and $b _ N$

Let us define the **Auxiliary Charge Sequence** $Q _ n$ and the **Master Control Variable** $Z _ n$:

$$
Q_n = 6a_n - b_n - 4, \qquad Z_n = \frac{Q_n + b_n}{2} = 3a_n - 2 \qquad (Q_0 = 44, \thickspace  Z_0 = 22)
$$

**Theorem 5.1 (Integral Conservation Laws for $b _ n$, $O _ n$, $E _ n$ and Area-Parity Relation in** $Z _ k$) [Proved]: For every step $n \ge 1$ and every $N \ge 1$, the complete history of the accumulators $b _ k$, $O _ k$, and $E _ k$ satisfies the exact Diophantine identities in $\mathbb{Z}$:

1. **Counter Integral Invariant ($44 \cdot 3^n$):**

$$
44 \cdot 3^n + \sum_{k=1}^{n-1} 3^{n-1-k} 2^k b_k = 2^n (6a_n - b_n - 4) = 2^n Q_n
$$

2. **Positive Odd Integral Invariant ($16 \cdot 3^n$):**

$$
16 \cdot 3^n = 2^n (2a_n + O_n) + \sum_{k=1}^{n-1} 3^{n-1-k} 2^k O_k
$$

3. **Even Integral Invariant ($14 \cdot 3^n$):**

$$
14 \cdot 3^n + \sum_{k=1}^{n-1} 3^{n-1-k} 2^k E_k = 2^n (2a_n - E_n - 2)
$$

4. **Area-Parity Relation Theorem (with initial term $Z _ 0 = 22$ included):**

$$
O_N = 24 - 2a_N + \sum_{k=1}^{N-1} a_k = 16 - 2a_N + \sum_{k=0}^{N-1} a_k
$$

$$
b_N = 2N + 6(a_N - 8) - 3 \sum_{k=0}^{N-1} a_k = 2Z_N - 44 - \sum_{k=0}^{N-1} Z_k = 2Z_N - 66 - \sum_{k=1}^{N-1} Z_k
$$

**Complete Proof (including the derivation in terms of $Z _ k$ and check at $N = 1$):**
Eliminating $p _ k$ between $3a _ k - 2a _ {k+1} = p _ k$ and $b _ {k+1} - b _ k = 2 - 3p _ k$, we obtain $2Q _ {k+1} - 3Q _ k = b _ k$ with $Q _ 0 = 44$. Multiplying by $3^{n-1-k} 2^k$ and summing from $k = 0$ to $n - 1$ (with $b _ 0 = 0$) yields (1). Substituting $b _ k = 2k - 3O _ k$ and $b _ k = 3E _ k - k$ together with the geometric identity $\sum _ {k=1}^{n-1} 3^{n-1-k} 2^k k = 2 \cdot 3^n - 2^n(n + 2)$ yields (2) and (3).

To prove (4) directly from the definitions of $Z _ k = 3a _ k - 2$ and $b _ N$:
Summing $p _ k = 3a _ k - 2a _ {k+1}$ from $k = 0$ to $N - 1$:

$$
O_N = \sum_{k=0}^{N-1} (3a_k - 2a_{k+1}) = 3a_0 - 2a_N + \sum_{k=1}^{N-1} a_k = 24 - 2a_N + \sum_{k=1}^{N-1} a_k = 16 - 2a_N + \sum_{k=0}^{N-1} a_k
$$

Substituting $O _ N$ into $b _ N = 2N - 3O _ N$:

$$
b_N = 2N - 3\left(16 - 2a_N + \sum_{k=0}^{N-1} a_k\right) = 2N + 6a_N - 48 - 3\sum_{k=0}^{N-1} a_k
$$

Since $3a _ k = Z _ k + 2$ for all $k \ge 0$ (and in particular $6a _ N = 2Z _ N + 4$), we substitute $3\sum _ {k=0}^{N-1} a _ k = \sum _ {k=0}^{N-1} (Z _ k + 2) = \sum _ {k=0}^{N-1} Z _ k + 2N$:

$$
b_N = 2N + (2Z_N + 4) - 48 - \left(\sum_{k=0}^{N-1} Z_k + 2N\right) = 2Z_N - 44 - \sum_{k=0}^{N-1} Z_k
$$

Separating the $k = 0$ term ($Z _ 0 = 3(8) - 2 = 22$), this is written equivalently as:

$$
b_N = 2Z_N - 44 - Z_0 - \sum_{k=1}^{N-1} Z_k = 2Z_N - 66 - \sum_{k=1}^{N-1} Z_k
$$

Explicit verification at $N = 1$: For $N = 1$, we have $Z _ 0 = 22$, $a _ 1 = 12 \implies Z _ 1 = 3(12) - 2 = 34$, and $b _ 1 = 2$. The formula with the sum starting at $k = 0$ gives $2Z _ 1 - 44 - Z _ 0 = 68 - 44 - 22 = 2 = b _ 1$, and the form with the sum starting at $k = 1$ (empty sum $= 0$) gives $2Z _ 1 - 66 - 0 = 68 - 66 = 2 = b _ 1$. $\blacksquare$

### 5.2. The Autonomous System of $Z _ n$ and Absolute Convergence of the Future-Tail Weighted Series

Since $Z _ n = 3a _ n - 2 \equiv a _ n \equiv p _ n \pmod 2$, $Z _ n$ forms an autonomous dynamical system:

$$
Z_{n+1} = \frac{3Z_n + 2 - 3p_n}{2} = \begin{cases} \frac{3}{2}Z_n + 1 & \text{if } Z_n \text{ is even } (p_n = 0) \cr \frac{3}{2}Z_n - \frac{1}{2} & \text{if } Z_n \text{ is odd } (p_n = 1) \end{cases}
$$

**Theorem 5.2 (Absolute Convergence of the Weighted Series of** $b _ k, O _ k, E _ k$ and Future-Tail Identity) [Proved]: For all $n \ge 0$, the weighted infinite series $\sum _ {k=1}^\infty \left(\frac{2}{3}\right)^k b _ k$, $\sum _ {k=1}^\infty \left(\frac{2}{3}\right)^k O _ k$, $\sum _ {k=1}^\infty \left(\frac{2}{3}\right)^k E _ k$, and $\sum _ {j=1}^\infty \left(\frac{2}{3}\right)^j b _ {n+j}$ ***converge absolutely** in* $\mathbb{R}$*, and satisfy the exact identities:*

$$
\alpha = 8 - \frac{1}{3}\sum_{k=0}^{\infty} \left(\frac{2}{3}\right)^k p_k = \frac{22}{3} + \frac{1}{18}\sum_{k=1}^{\infty} \left(\frac{2}{3}\right)^k b_k
$$

$$
2b_n + 12 - 18R_n = \sum_{j=1}^{\infty} \left(\frac{2}{3}\right)^j b_{n+j}
$$

**Proof of Absolute Convergence and Passage to the Limit:**

1. **Explicit dominating bound and comparison/ratio test:** By definition, for all $k \ge 1$, since $p _ m \in \lbrace 0, 1\rbrace$, the accumulators satisfy the deterministic linear bounds:

$$
0 \le O_k \le k, \qquad 0 \le E_k \le k, \qquad |b_k| = |2E_k - O_k| \le 2k
$$

   Consequently, the general term in absolute value of the series is explicitly majorized by:

$$
\left| \left(\frac{2}{3}\right)^k b_k \right| \le 2k \left(\frac{2}{3}\right)^k, \qquad \left| \left(\frac{2}{3}\right)^j b_{n+j} \right| \le 2(n + j) \left(\frac{2}{3}\right)^j
$$

   Applying **D'Alembert's ratio test** to the majorizing series of positive terms $\sum _ {k=1}^\infty 2k(2/3)^k$:

$$
\lim_{k \to \infty} \frac{2(k+1)(2/3)^{k+1}}{2k(2/3)^k} = \frac{2}{3} \lim_{k \to \infty} \left(1 + \frac{1}{k}\right) = \frac{2}{3} < 1
$$

   By the Weierstrass comparison test, all series considered are **absolutely convergent** (with majorizing sum $\sum _ {k=1}^\infty 2k(2/3)^k = 2 \cdot \frac{2/3}{(1 - 2/3)^2} = 12 < \infty$).
2. **Proof of the identities:** Dividing the Integral Invariant (Theorem 5.1(1)) by $6 \cdot 3^n$:

$$
\frac{22}{3} + \frac{1}{18} \sum_{k=1}^{n-1} \left(\frac{2}{3}\right)^k b_k = \left(\frac{2}{3}\right)^n a_n - \frac{b_n + 4}{6}\left(\frac{2}{3}\right)^n
$$

   Since $|b _ n + 4| \le 2n + 4$, we have $\lim _ {n\to\infty} \frac{b _ n + 4}{6}(2/3)^n = 0$ and $\lim _ {n\to\infty} (2/3)^n a _ n = \alpha$, obtaining the first identity. Subtracting its partial sum up to $n$ from the infinite series and multiplying by $18 \cdot (3/2)^n$, since $18\left(\alpha(3/2)^n - a _ n\right) = -18R _ n$, we obtain $2b _ n + 12 - 18R _ n = \sum _ {j=1}^\infty (2/3)^j b _ {n+j}$. $\blacksquare$

