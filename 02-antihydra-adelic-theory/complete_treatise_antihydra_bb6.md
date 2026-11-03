# Complete Treatise: The Algebraic-Adelic and Diophantine Theory of the Antihydra Conjecture in $BB(6)$

**Theoretical Framework:** Calculus of Carry Defects on Bimodular Lattices (CCDBL) and Adelic Diophantine Geometry ($\mathbb{R} \times \mathbb{Z}_2 \times \mathbb{Z}_3$).

## General Index of the Treatise

1. **Part I:** The Antihydra Turing Machine in $BB(6)$, Verifiable Reduction to the Arithmetic System $(a_n, b_n)$, Modular Sieve, and Triad Balance.
2. **Part II:** Spin Duality, Shifted Sequence $u_n$, Dirichlet Character $\chi_4$, Exhaustive Modulo 8 Relations, Reflection $\mathcal{J}(a) = 1 - a$, and Boolean Cubic Identity.
3. **Part III:** Macro-Cycle Renormalization, Cumulative Even Count $P_K$, Odd Core Domains, the Four Exact Valuation Laws, Universal Floor Formula, and Audited Cycle Table.
4. **Part IV:** Archimedean Domain, the Antihydra Constant $\alpha$ (with Rigorous Truncation Bound and Certified Digits), Non-Integrality $R_n \in (0,1)$, and the Sliding Window Operator.
5. **Part V:** The Exact Integral Invariant ($44 \cdot 3^n$), the Dual Identities ($16 \cdot 3^n$ and $14 \cdot 3^n$), the Corrected Identity for $b_N$ in Terms of $Z_k$, and Absolute Convergence of Weighted Series.
6. **Part VI:** The Quadratic Virial Theorem and Complete Proof of the Partition Law at a Halting Time.
7. **Part VII:** Elimination of the Conditional (*If/Else*): The Pure Affine Algebraic Variety and Complete Proof of the Dyadic Rigidity Theorem.
8. **Part VIII:** Adelic Space $\mathcal{E}_S = \mathbb{Z}_2 \times \mathbb{Z}_3 \times \mathbb{R}$, Local Topologies, Operator Continuity, and Proof of the Finite Difference Theorem $\Delta^L$.
9. **Part IX:** Strict 3-adic Contraction, 2-adic Valuation Proof for the Injectivity of Residual Sets $\mathcal{R}_M$, and Haar Measure of the 3-adic Cantor Set.
10. **Part X:** Univocal Time Reversal via Ternary Ceilings and Complete Proof of the Exact Fractional Representation of $O_N$ and $b_N$.
11. **Part XI:** The System of Arithmetic Kirchhoff Equations, Telescoping Proof of $b_N$, Koopman-Walsh Detail Subspaces, and Infinite Family of Periodic Cycles in $\mathbb{Z}_2$ vs. $\mathbb{Z}$.
12. **Part XII:** Backward Dynamics of the Chain $Y_j$ ($0 \le j \le N-1$), the Corrected Quadratic Autocorrelation Invariant ($+4X^2$), and Complete Proof of the Sieve $\Psi(P_K) \equiv 18 \pmod{36}$.
13. **Part XIII:** Exponential Generating Functions, Exact Branchwise Multiplicative Quotients, Infinite Product for $\alpha$, and Inhomogeneous Recurrence at Cube Roots of Unity.
14. **Part XIV:** Ternary Symbolic Dynamics, Carry Transducer and Populations ($U_n, D_n, V_n, K_n$), Explicit Step-by-Step Example, the Universal Tail $\frac{3^m+3}{2}$, Relation to Mahler's Problem, and Bibliographical References.
15. **Part XV:** Exact Quadratic Telescoping of Step-Times $\Delta t_n$ and the Cumulative Turing Machine Action Law ($T_N$).
16. **Part XVI:** 2-Adic Bernoulli Isomorphism, Fuss-Catalan Halting Measure $\varphi^{-1}$, and Integer Fibonacci Conservation Laws.
17. **Part XVII:** The Tri-Local Adelic Bridge Series $\mathcal{S}(p)$ Across $(\mathbb{R}, \mathbb{Z}_2, \mathbb{Z}_3)$ and the Cubic Virial Theorem.
18. **Part XVIII:** The 3-Adic Ballot Sieve, Unconditional Modulo-54 Strengthening of $\Psi(P)$, and Closed-Form Enumeration of Terminal Halting Classes Modulo $3^M$.
19. **Appendix A:** Complete Empirical Table of the First 20 Steps and Verification of Invariants.
20. **Appendix B:** Computational Verification Suite for Selected Identities in Python (12 Audited Test Blocks).
21. **Appendix C:** Final Mathematical Audit Report and Exhaustive Change Log.

## Part I: The Antihydra Turing Machine in $BB(6)$, Verifiable Reduction to the Arithmetic System $(a_n, b_n)$, Modular Sieve, and Triad Balance

### 1.0. Definition of the Antihydra Turing Machine and Verifiable Reduction to the Arithmetic System $(a_n, b_n)$

The $6$-state, $2$-symbol Turing machine known as **Antihydra** (discovered within *The Busy Beaver Challenge* project by `mxdys` and whose high-level rules were deduced by `Racheline` on June 28, 2024; see Ligocki [2024] and *BusyBeaverWiki* [2024]) has the standard code in `bbchallenge` format:

$$
\texttt{1RB1RA\_0LC1LE\_1LD1LC\_1LA0LB\_1LF1RE\_---0RA}
$$

Its explicit transition table over the state set $Q = \{A, B, C, D, E, F\}$ (with initial state $A$) and tape alphabet $\Sigma = \{0, 1\}$ (with initially blank tape $0^\infty$) is:

| State | Read symbol $0$ | Read symbol $1$ |
| --- | --- | --- |
| **A** | `1RB` (writes $1$, right, goes to $B$) | `1RA` (writes $1$, right, goes to $A$) |
| **B** | `0LC` (writes $0$, left, goes to $C$) | `1LE` (writes $1$, left, goes to $E$) |
| **C** | `1LD` (writes $1$, left, goes to $D$) | `1LC` (writes $1$, left, goes to $C$) |
| **D** | `1LA` (writes $1$, left, goes to $A$) | `0LB` (writes $0$, left, goes to $B$) |
| **E** | `1LF` (writes $1$, left, goes to $F$) | `1RE` (writes $1$, right, goes to $E$) |
| **F** | `---` (**HALT**) | `0RA` (writes $0$, right, goes to $A$) |

*(Fundamental remark: The only halting transition in the entire table is `F0`).*

**Theorem 1.0 (Exact Reduction of the Antihydra Turing Machine to the Dynamical System** $(a_n, b_n)$) [Proved]: *For any non-negative integers $b \ge 0$ and $h \ge 0$, let us define the canonical tape configuration:*

$$
\mathcal{A}(b, h) := 0^\infty \, 1^b \, 0 \, 1^h \, \mathbf{E>} \, 0^\infty
$$

*(where $\mathbf{E>}$ indicates that the head is in state $E$ scanning the first symbol $0$ to the right of the block $1^h$, and analogously $\mathbf{<S}$ indicates that the head scans the first symbol to its left). Then:*

1. **Initialization Phase ($11$ steps):** *Starting from the blank tape $0^\infty \mathbf{A>} 0^\infty$, in exactly $11$ machine steps the initial canonical configuration is reached:*

$$
0^\infty \mathbf{A>} 0^\infty \xrightarrow{11\text{ steps}} 0^\infty \, 1^0 \, 0 \, 1^4 \, \mathbf{E>} \, 0^\infty = \mathcal{A}(0, 4)
$$

2. **High-Level Transition Rules (for $h \ge 4$):** *Every canonical configuration $\mathcal{A}(b, h)$ with $h \ge 4$ evolves deterministically according to the parity of $h$:*

   - **If $h = 2k$ is even ($k \ge 2$):** *In $2b + 3k^2 + 12k + 11$ machine steps without ever visiting `F0`, it reaches:*

$$
\mathcal{A}(b, 2k) \longrightarrow \mathcal{A}(b + 2, \, 3k + 2) = \mathcal{A}\left(b + 2, \, \left\lfloor \frac{3h}{2} \right\rfloor + 2\right)
$$

   - **If $h = 2k + 1$ is odd ($k \ge 2$) and $b \ge 1$:** *In $3k^2 + 12k + 5$ machine steps without visiting `F0`, it reaches:*

$$
\mathcal{A}(b, 2k + 1) \longrightarrow \mathcal{A}(b - 1, \, 3k + 3) = \mathcal{A}\left(b - 1, \, \left\lfloor \frac{3h}{2} \right\rfloor + 2\right)
$$

   - **If $h = 2k + 1$ is odd ($k \ge 2$) and $b = 0$:** *In $3k^2 + 9k - 1$ machine steps, the head reaches the configuration $0^\infty \mathbf{<F} \, 1101^{3k} 0^\infty$, reading the symbol $0$ in state* $F$ *(`F0`) and **halting**.*
3. **Exact Conjugacy with the Shifted Sequence $a_n = h_n + 4$:** *Let $(h_n, b_n)_{n \ge 0}$ be the sequence of parameters of the canonical configurations $\mathcal{A}(b_n, h_n)$ visited successively starting from $(b_0, h_0) = (0, 4)$, with law $h_{n+1} = \lfloor \frac{3h_n}{2} \rfloor + 2$. Defining the translated change of variable:*

$$
a_n := h_n + 4
$$

   *one has $a_0 = 4 + 4 = 8$, the parity is identically preserved ($a_n \bmod 2 = (h_n + 4) \bmod 2 = h_n \bmod 2 =: p_n$), and the recurrence law transforms exactly into:*

$$
a_{n+1} = h_{n+1} + 4 = \left\lfloor \frac{3(a_n - 4)}{2} \right\rfloor + 6 = \left\lfloor \frac{3a_n}{2} - 6 \right\rfloor + 6 = \left\lfloor \frac{3a_n}{2} \right\rfloor
$$

   *while the counter $b_n$ (which represents the exponent of the left block $1^{b_n}$ on the tape) evolves according to $b_{n+1} = b_n + 2 - 3p_n$, with the Turing machine halting if and only if at some step $n$ one has $b_n = 0$ with $p_n = 1$, which is equivalent to the counter reaching the value $b_N = -1$ for the first time at $N = n + 1$.*

**Verifiable Step-by-Step Proof:**

1. *Initialization ($11$ steps):* From $0^\infty \mathbf{A>} 0^\infty$:

   - Step 1 (`A0 -> 1RB`): $0^\infty 1 \mathbf{B>} 0^\infty$.
   - Step 2 (`B0 -> 0LC`): $0^\infty \mathbf{<C} 1 0^\infty$.
   - Step 3 (`C1 -> 1LC`): $0^\infty \mathbf{<C} 0 1 0^\infty$.
   - Step 4 (`C0 -> 1LD`): $0^\infty \mathbf{<D} 1 1 0^\infty$.
   - Step 5 (`D0 -> 1LA`): $0^\infty \mathbf{<A} 0 1 1 1 0^\infty$.
   - Step 6 (`A0 -> 1RB`): $0^\infty 1 \mathbf{B>} 1 1 1 0^\infty$.
   - Step 7 (`B1 -> 1LE`): $0^\infty \mathbf{<E} 1 1 1 1 0^\infty$.
   - Steps 8 to 11 (shift rule `E1 -> 1RE` applied $4$ times across $1^4$): $0^\infty 1^0 0 1^4 \mathbf{E>} 0^\infty = \mathcal{A}(0, 4)$.
2. *Elementary shift rules and partial configuration $P(m, n)$:* From the transition table one immediately verifies three block shift rules for every integer $s \ge 0$:

$$
\mathbf{A>} 1^s \xrightarrow{s\text{ steps}} 1^s \mathbf{A>}, \qquad 1^s \mathbf{<C} \xrightarrow{s\text{ steps}} \mathbf{<C} 1^s, \qquad \mathbf{E>} 1^s \xrightarrow{s\text{ steps}} 1^s \mathbf{E>}
$$

   Let us consider the subconfiguration $P(m, n) := 0 1^m \mathbf{E>} 0 1^n 0^\infty$ with $m \ge 4$ and $n \ge 0$:
   *In 2 steps (`E0 -> 1LF`, `F1 -> 0RA`):* $0 1^{m-1} 0 \mathbf{A>} 1^{n+1} 0^\infty$.
   *In $n+1$ steps (shift `A>`):* $0 1^{m-1} 0 1^{n+1} \mathbf{A>} 0^\infty$.
   *In 2 steps (`A0 -> 1RB`, `B0 -> 0LC`):* $0 1^{m-1} 0 1^{n+2} \mathbf{<C} 0^\infty$.
   *In $n+2$ steps (shift `<C`):* $0 1^{m-1} \mathbf{<C} 0 1^{n+2} 0^\infty$.
   *In 5 steps (`C0 -> 1LD`, `D1 -> 0LB`, `B1 -> 1LE`, `E1 -> 1RE`, `E1 -> 1RE`):* $0 1^{m-2} \mathbf{E>} 0 1^{n+3} 0^\infty = P(m - 2, n + 3)$.
   Thus, each application consumes $2$ units from $m$ and adds $3$ units to $n$ in $2n + 12$ steps: $P(m, n) \to P(m - 2, n + 3)$.
   Starting from $\mathcal{A}(b, h) = 0^\infty 1^b P(h, 0)$, we apply this reduction $\lfloor h/2 \rfloor - 1$ times:

   - **Case $h = 2k$ even:** One arrives at $0^\infty 1^b 0 1^2 \mathbf{E>} 0 1^{3k - 3} 0^\infty$. Advancing $3h + 4$ steps reaches $0^\infty 1^b \mathbf{<C} 0 0 1^{3k} 0^\infty$, which crosses the block $1^b$ in $b$ steps up to $0^\infty \mathbf{<C} 1^b 0 0 1^{3k} 0^\infty$. In $5$ steps (`C0 -> 1LD`, `D0 -> 1LA`, `A0 -> 1RB`, `B1 -> 1LE`, `E1 -> 1RE`) one obtains $0^\infty 1 \mathbf{E>} 1^{b+2} 0 0 1^{3k} 0^\infty$, and after crossing $1^{b+2}$ and the double separator $00$ (in $b + 2 + 6 + 3k$ steps) one reconstructs exactly $0^\infty 1^{b+2} 0 1^{3k + 2} \mathbf{E>} 0^\infty = \mathcal{A}(b + 2, 3k + 2)$.
   - **Case $h = 2k + 1$ odd:** One arrives at $0^\infty 1^b 0 1^3 \mathbf{E>} 0 1^{3k - 3} 0^\infty$. In $3h + 2$ additional steps the head consumes the three central ones and emerges to the left of the separator in state $F$: $0^\infty 1^b \mathbf{<F} 1 1 0 1^{3k} 0^\infty$.

     - If $b = 0$, the symbol to the left of $\mathbf{<F}$ is a $0$ of the blank tape ($0^\infty \mathbf{<F} 1 1 0 1^{3k} 0^\infty$), executing the undefined transition `F0` (**HALT**).
     - If $b \ge 1$, the symbol to the left of $\mathbf{<F}$ is the last $1$ of the block $1^b$. The transition `F1 -> 0RA` erases that $1$ (reducing the left block to $1^{b-1}$) and in $6 + 3k$ additional steps shifts the head to the right end, resulting in $0^\infty 1^{b-1} 0 1^{3k + 3} \mathbf{E>} 0^\infty = \mathcal{A}(b - 1, 3k + 3)$. $\blacksquare$

### 1.1. The Iterated Antihydra Operator

By virtue of Theorem 1.0, the halting problem for Antihydra is rigorously equivalent to studying the coupled discrete arithmetic dynamical system $(a_n, b_n)$ over the integers, governed by the operator $T: \mathbb{Z} \to \mathbb{Z}$:

$$
T(x) = x + \left\lfloor \frac{x}{2} \right\rfloor = \left\lfloor \frac{3x}{2} \right\rfloor = \frac{3x - (x \bmod 2)}{2} = \begin{cases} \frac{3x}{2} & \text{if } x \equiv 0 \pmod 2 \quad (p = 0) \\ \frac{3x - 1}{2} & \text{if } x \equiv 1 \pmod 2 \quad (p = 1) \end{cases}
$$

Given the initial condition (seed) at time $n = 0$:

$$
a_0 = 8, \qquad b_0 = 0
$$

the main sequence of states $\{a_n\}_{n=0}^\infty$ and the sequence of parity bits $\{p_n\}_{n=0}^\infty$ with $p_n \in \{0, 1\}$ are defined by the step-by-step linear recurrence relation:

$$
p_n = a_n \bmod 2 = 3a_n - 2a_{n+1}
$$

$$
2a_{n+1} = 3a_n - p_n
$$

### 1.2. The Halting Counter $b_n$ and the Odd Step Accumulator $O_n$

Simultaneously, the balance accumulator register or halting counter $b_n \in \mathbb{Z}$ evolves step by step according to:

$$
b_{n+1} = b_n + 2 - 3p_n = \begin{cases} b_n + 2 & \text{if } p_n = 0 \text{ (even step)} \\ b_n - 1 & \text{if } p_n = 1 \text{ (odd step)} \end{cases}
$$

We define the **Odd Step Accumulator** $O_n$ and the **Even Step Accumulator** $E_n$ up to time $n-1$ as:

$$
O_n = \sum_{k=0}^{n-1} p_k, \qquad E_n = \sum_{k=0}^{n-1} (1 - p_k) = n - O_n
$$

Summing the difference equation for $b_n$ telescopically from $k = 0$ to $n - 1$, with $b_0 = 0$:

$$
b_n = \sum_{k=0}^{n-1} (2 - 3p_k) = 2n - 3 \sum_{k=0}^{n-1} p_k = 2n - 3O_n = 2E_n - O_n
$$

### 1.3. Temporal Congruence Lemma for Halting

**Halting Condition:** By Theorem 1.0(3), the Antihydra Turing machine halts if and only if there exists some integer $N \ge 1$ such that the counter reaches for the first time the critical value:

$$
b_N = -1
$$

**Lemma 1.1 (Modular Restriction on $N$ and** $O_N$) [Proved]: *For every $n \ge 0$, the counter invariably satisfies the congruence $b_n \equiv 2n \pmod 3$. Consequently, the machine can only halt at steps satisfying $N \equiv 1 \pmod 3$, that is, $N = 3P + 1$ for some integer $P \ge 0$, in which case the number of even and odd steps is rigidly fixed by:*

$$
E_N = P, \qquad O_N = 2P + 1, \qquad 3O_N = 2N + 1
$$

*Furthermore, for $N \ge 4$ ($P \ge 1$), the last two steps prior to the first halt are forced to be odd ($b_{N-2} = 1, b_{N-1} = 0, b_N = -1 \implies p_{N-2} = p_{N-1} = 1$).*

**Proof:**
Reducing $b_n = 2n - 3O_n$ modulo $3$, the term $-3O_n$ vanishes identically, yielding $b_n \equiv 2n \pmod 3$. If $b_N = -1 \equiv 2 \pmod 3$, then $2N \equiv 2 \pmod 3$. Multiplying by $2$ (the inverse of $2$ modulo $3$), we obtain $N \equiv 1 \pmod 3$. Writing $N = 3P + 1$, we substitute into $2N - 3O_N = -1$:

$$
2(3P + 1) - 3O_N = -1 \implies 6P + 3 = 3O_N \implies O_N = 2P + 1
$$

and the number of even steps is $E_N = N - O_N = (3P + 1) - (2P + 1) = P$. Since $N$ is the first time with $b_N = -1$, necessarily $b_{N-1} \ge 0$ and $b_{N-2} \ge 0$. Given that the step increment is $+2$ or $-1$, the only way to reach $-1$ from $\ge 0$ is $b_{N-1} = 0$ with $p_{N-1} = 1$; and since $b_{N-2} \equiv 2(3P-1) \equiv 1 \pmod 3$ with $b_{N-2} \ge 0$, the only way to descend to $b_{N-1} = 0$ is $b_{N-2} = 1$ with $p_{N-2} = 1$. $\blacksquare$

### 1.4. Decomposition into Aligned Triads and the Quasi-Constant Invariant $\Omega_k$

**Theorem 1.2 (Triad Balance and Two-Sided Bound on** $\Omega_k$) [Proved]: *Dividing the trajectory up to step $3M$ into $M$ disjoint triads $B_k = (3k, 3k+1, 3k+2)$ with $e_k = p_{3k} + p_{3k+1} + p_{3k+2} \in \{0, 1, 2, 3\}$:*

1. *The change of the counter in each triad is $\Delta^{(3)} b_{3k} = b_{3k+3} - b_{3k} = 3(2 - e_k) \in \{+6, +3, 0, -3\}$. If $T_j$ denotes the number of triads with $e_k = j$, then $\frac{b_{3M}}{3} = 2T_0 + T_1 - T_3$, and the necessary halting condition $b_{3M} = 0$ requires $T_3 = 2T_0 + T_1$.*
2. *The triad weight $W_k = 27a_{3k} - 8a_{3k+3} = 9p_{3k} + 6p_{3k+1} + 4p_{3k+2}$ decomposes exactly by eliminating the central bit $p_{3k+1}$ as:*

$$
W_k = 6e_k + (3p_{3k} - 2p_{3k+2}) = 12 - 2\Delta^{(3)} b_{3k} + 3p_{3k} - 2p_{3k+2}
$$

3. *Consequently, the linear combination $\Omega_k := (27a_{3k} - 8a_{3k+3}) + 2(b_{3k+3} - b_{3k}) = 12 + 3p_{3k} - 2p_{3k+2}$ can only take values in the finite set $\{10, 12, 13, 15\}$.*

**Proof:**
Unrolling $2a_{n+1} = 3a_n - p_n$ three times yields $8a_{3k+3} = 27a_{3k} - (9p_{3k} + 6p_{3k+1} + 4p_{3k+2})$. Since $6(p_{3k} + p_{3k+1} + p_{3k+2}) + 3p_{3k} - 2p_{3k+2} = 9p_{3k} + 6p_{3k+1} + 4p_{3k+2}$ and $6e_k = 12 - 2\Delta^{(3)}b_{3k}$, solving for $W_k + 2\Delta^{(3)}b_{3k}$ results in $12 + 3p_{3k} - 2p_{3k+2} \in \{10, 12, 13, 15\}$. $\blacksquare$

### 1.5. Closed-Form Step-by-Step Linear Trajectory Formula

Multiplying $a_{k+1} = \frac{3}{2}a_k - \frac{1}{2}p_k$ by $2^{k+1} 3^{n-1-k}$ and summing telescopically from $k = 0$ to $n - 1$, we obtain the **Fundamental Trajectory Identity** [Proved]:

$$
2^n a_n = 3^n a_0 - \sum_{k=0}^{n-1} 3^{n-1-k} 2^k p_k = 8 \cdot 3^n - \sum_{k=0}^{n-1} 3^{n-1-k} 2^k p_k
$$

## Part II: Spin Duality, Dirichlet Character $\chi_4$, Modulo 8 Relations, Reflection $\mathcal{J}(a) = 1 - a$, and Boolean Cubic Identity

### 2.1. Fixed Points in $\mathbb{Z}_2$, the Odd Dual Coordinate $u_n$, Character $\chi_4$, and Modulo 8 Classification

In the ring of 2-adic integers $\mathbb{Z}_2$, the two affine branches of the operator $T$ possess two fixed points:

- Even branch ($p = 0$): $T_0(x) = \frac{3x}{2} = x \implies x = 0$.
- Odd branch ($p = 1$): $T_1(x) = \frac{3x - 1}{2} = x \implies x = 1$.

To symmetrize both branches with respect to their center $1/2$, we introduce the **Shifted Dual Sequence** $u_n$ and the **Parity Spin** $\sigma_n$:

$$
u_n = 2a_n - 1, \qquad \sigma_n = 1 - 2p_n \in \{-1, +1\}
$$

Theorem 2.1 (Symmetric Spin Equation, Modulo 4 Character, and Exhaustive Modulo 8 Relations) [Proved]: *For every $n \ge 0$, the integer $u_n$ is strictly odd ($u_n \equiv 1 \pmod 2$), starts from the seed $u_0 = 15$, and evolves via the symmetric law:*

$$
u_{n+1} = \frac{3u_n + \sigma_n}{2} \iff 2u_{n+1} - 3u_n = \sigma_n
$$

*Moreover, the spin $\sigma_n$, its transition $\sigma_{n+1}$, and the pair $(p_n, p_{n+1})$ are intrinsically determined by the residue classes of $a_n$ modulo $4$ and modulo $8$ (equivalently, of $u_n$ modulo $8$ and modulo $16$):*

1. **Modulo 4 Character Law:** $u_n + \sigma_n \equiv 0 \pmod 4 \iff \sigma_n = -\chi_4(u_n) = -(-1)^{(u_n - 1)/2}$. In terms of $a_n = 4q + r_4$ ($r_4 \in \{0,1,2,3\}$), the parity change $p_n \oplus p_{n+1}$ satisfies exactly:

$$
p_{n+1} \equiv p_n + \left\lfloor \frac{a_n \bmod 4}{2} \right\rfloor \pmod 2 \iff \sigma_{n+1} = (-1)^{\lfloor (a_n \bmod 4)/2 \rfloor} \sigma_n
$$

2. **Modulo 8 Spin Transition Equivalence:** $\sigma_{n+1} = \sigma_n \iff u_n + \sigma_n \equiv 0 \pmod 8 \iff a_n \bmod 4 \in \{0, 1\}$, and $\sigma_{n+1} = -\sigma_n \iff u_n + \sigma_n \equiv 4 \pmod 8 \iff a_n \bmod 4 \in \{2, 3\}$.

**Exhaustive Explicit Proof (All Residues Modulo 4 and Modulo 8):**
Substituting $a_{n+1} = \frac{3a_n - p_n}{2}$ and $a_n = \frac{u_n + 1}{2}$ into $u_{n+1} = 2a_{n+1} - 1$:

$$
u_{n+1} = 3\left(\frac{u_n + 1}{2}\right) - p_n - 1 = \frac{3u_n + (1 - 2p_n)}{2} = \frac{3u_n + \sigma_n}{2}
$$

Subtracting $u_n$ from both sides yields the key identity:

$$
u_{n+1} - u_n = \frac{u_n + \sigma_n}{2}
$$

Since $u_n = 2a_n - 1$ and $u_{n+1} = 2a_{n+1} - 1$ are both odd for all $n \ge 0$, their difference $u_{n+1} - u_n = 2(a_{n+1} - a_n)$ is always even. Therefore, $\frac{u_n + \sigma_n}{2}$ is an even integer, which is equivalent to $u_n + \sigma_n \equiv 0 \pmod 4$. Since $\sigma_n \in \{-1, +1\}$, if $u_n \equiv 1 \pmod 4$ then $\sigma_n = -1 = -\chi_4(u_n)$, and if $u_n \equiv 3 \pmod 4$ then $\sigma_n = +1 = -\chi_4(u_n)$.

For the transition to the next step, we reduce the identity $u_{n+1} - u_n = \frac{u_n + \sigma_n}{2}$ modulo $4$:

- By part (1) applied to $n+1$, we have $\sigma_{n+1} = -\chi_4(u_{n+1})$, hence $\sigma_{n+1} = \sigma_n \iff u_{n+1} \equiv u_n \pmod 4 \iff 4 \mid (u_{n+1} - u_n) \iff 4 \mid \frac{u_n + \sigma_n}{2} \iff u_n + \sigma_n \equiv 0 \pmod 8$.
- Analogously, $\sigma_{n+1} = -\sigma_n \iff u_{n+1} - u_n \equiv 2 \pmod 4 \iff \frac{u_n + \sigma_n}{2} \equiv 2 \pmod 4 \iff u_n + \sigma_n \equiv 4 \pmod 8$.

Let us explicitly check the 8 possible residues of $a_n = 8k + r_8$ ($r_8 \in \{0, 1, \dots, 7\}$) without omitting any case:

| Class $a_n \bmod 8$ | $u_n = 2a_n - 1 \bmod 16$ | $(p_n, \sigma_n)$ | $u_n + \sigma_n \bmod 8$ | Exact expression $a_{n+1}$ | Class $a_{n+1} \bmod 4$ | $(p_{n+1}, \sigma_{n+1})$ | Triplet $(p_n, p_{n+1}, p_{n+2})$ |
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

Substituting $O_n = \frac{n - M_n^{(\sigma)}}{2}$ into $b_n = 2n - 3O_n$, we obtain $b_n = \frac{n + 3M_n^{(\sigma)}}{2}$, so that the halting condition $b_N = -1$ is equivalent to $3M_N^{(\sigma)} = -(N + 2)$.

Theorem 2.2 (Boolean Cubic Identity of Spin Triads) [Proved]: *In any block of three consecutive steps $(n, n+1, n+2)$, let $W_n^{(\sigma)} = 8u_{n+3} - 27u_n = 9\sigma_n + 6\sigma_{n+1} + 4\sigma_{n+2} \in \{\pm 1, \pm 7, \pm 11, \pm 19\}$. Then:*

1. $(8u_{n+3} - 27u_n)^2 = 133 + 108\sigma_n\sigma_{n+1} + 72\sigma_n\sigma_{n+2} + 48\sigma_{n+1}\sigma_{n+2}$.
2. *The sign $\operatorname{sgn}(8u_{n+3} - 27u_n)$ always coincides with the majority sign* $\operatorname{sgn}(\sigma_n + \sigma_{n+1} + \sigma_{n+2}) \in \{-1, +1\}$*, and the **Exact Boolean Cubic Identity** holds:*

$$
\sigma_n + \sigma_{n+1} + \sigma_{n+2} = 2\operatorname{sgn}(8u_{n+3} - 27u_n) + \sigma_n \sigma_{n+1} \sigma_{n+2}
$$

**Proof:**
Since $6 + 4 = 10 > 9$, if at least two spins in the triad equal $+1$, then $9\sigma_n + 6\sigma_{n+1} + 4\sigma_{n+2} \ge -9 + 6 + 4 = +1 > 0$; and if at least two equal $-1$, the sum is $\le +9 - 6 - 4 = -1 < 0$. Evaluating $\sigma_n + \sigma_{n+1} + \sigma_{n+2} - \sigma_n\sigma_{n+1}\sigma_{n+2}$ on the 8 triads of $\{-1, +1\}^3$, it equals $+2$ when there are two or three $+1$'s and equals $-2$ when there are two or three $-1$'s, coinciding identically with $2\operatorname{sgn}(8u_{n+3} - 27u_n)$. $\blacksquare$

### 2.3. Self-Duality Theorem via Affine Reflection $\mathcal{J}(a) = 1 - a$

**Theorem 2.3 (Conjugacy by Inversion** $\mathcal{J}$) [Proved]: *Let $\mathcal{J}: \mathbb{Z}_2 \to \mathbb{Z}_2$ be the affine involution defined by $\mathcal{J}(a) = 1 - a$. Then:*

1. $\mathcal{J}$ *inverts the parity of every state:* $(1 - a) \bmod 2 = 1 - (a \bmod 2)$.
2. $\mathcal{J}$ *commutes exactly with the Antihydra operator $T$:*

$$
T(1 - a) = 1 - T(a) \qquad \forall a \in \mathbb{Z}_2
$$

3. *For every $k \ge 1$, $T^k(1 - a) = 1 - T^k(a)$. If a state $a \in \mathbb{Z}_2$ generates the infinite sequence of parity bits $(p_0, p_1, p_2, \dots)$, the reflected state $1 - a$ generates the exact complementary sequence $(1 - p_0, 1 - p_1, 1 - p_2, \dots)$.*

**Proof:**
Let $p = a \bmod 2 \in \{0, 1\}$. The integer $\tilde{a} = 1 - a$ has parity $\tilde{p} = 1 - p$. Applying $T$:

$$
T(1 - a) = \frac{3(1 - a) - (1 - p)}{2} = \frac{2 - 3a + p}{2} = 1 - \frac{3a - p}{2} = 1 - T(a) \quad \blacksquare
$$

## Part III: Macro-Cycle Renormalization, Cumulative Even Count $P_K$, the Four Valuation Laws, and the Universal Floor Formula

### 3.1. Well-Defined Decomposition of the Orbit into Even ($r_i$) and Odd ($m_i$) Runs and Notation $P_K$

*(Notational remark: To avoid any symbolic collision with the Archimedean residual defect $R_n = a_n - \alpha(3/2)^n$ of Part IV, throughout the treatise we denote by $P_K$ the cumulative number of even steps at the close of macro-cycle $K$).*

**Proposition 3.0 (Finiteness of Runs and Well-Definedness of Macro-Cycles in** $\mathbb{Z}_{\ge 2}$) [Proved]: *For any even integer seed $a_0 \ge 2$ (in particular $a_0 = 8$), every phase of consecutive even steps and every phase of consecutive odd steps has finite length:*

1. *If $a_n \ge 2$ is even, let $r = v_2(a_n) \ge 1$ be its exact 2-adic valuation ($a_n = 2^r c$ with $c \ge 1$ odd). Then for $0 \le j < r$, $a_{n+j} = 3^j 2^{r-j} c$ is even, and at $j = r$ the odd integer $a_{n+r} = 3^r c$ is reached.*
2. *If $a_t \ge 3$ is odd, then $a_t - 1 \ge 2$ is a non-zero positive even integer. Let $m = v_2(a_t - 1) \ge 1$ be its exact 2-adic valuation ($a_t - 1 = 2^m d$ with $d \ge 1$ odd). Since $a_{k+1} - 1 = \frac{3}{2}(a_k - 1)$ when $a_k$ is odd, for $0 \le j < m$ one has $a_{t+j} = 3^j 2^{m-j} d + 1 \equiv 1 \pmod 2$, and at $j = m$ the even integer $a_{t+m} = 3^m d + 1 \equiv 0 \pmod 2$ is reached.*

Consequently, the Antihydra trajectory starting from $a_0 = 8$ partitions uniquely and infinitely into macro-cycles $i = 1, 2, \dots$. Each cycle $i \ge 1$ consists of:

1. A maximal **even pumping** phase of finite duration $r_i \in \mathbb{Z}_{\ge 1}$ consecutive steps with $p_n = 0$ (where the counter rises by $+2r_i$).
2. Followed by a maximal **odd drop** phase of finite duration $m_i \in \mathbb{Z}_{\ge 1}$ consecutive steps with $p_n = 1$ (where the counter falls by $-m_i$).

We define the cumulative times up to the end of cycle $K$:

$$
P_K := \sum_{i=1}^{K} r_i, \qquad M_K := \sum_{i=1}^{K} m_i, \qquad N_K := P_K + M_K, \qquad t_i := P_i + M_{i-1} \quad (M_0 := 0, N_0 := 0)
$$

### 3.2. Internal Dynamics of a Cycle and Domain of the Odd Cores $(c_i, d_i)$

- **During even phase $i$ (of duration $r_i \ge 1$):**
  The state at the start of the cycle at step $N_{i-1}$ factors uniquely in $\mathbb{Z}_{\ge 2}$ by extracting its maximal power of $2$:

$$
a_{N_{i-1}} = 2^{r_i} c_i, \qquad \text{with } c_i \in \mathbb{Z}_{\ge 1}, \quad c_i \equiv 1 \pmod 2 \text{ (entry odd core)}
$$

  After $r_i$ multiplications by $3/2$, the state at the peak of the cycle (step $t_i$) is the odd integer:

$$
a_{t_i} = 3^{r_i} c_i
$$

- **During odd phase $i$ (of duration $m_i \ge 1$):**
  Factoring the positive even integer $a_{t_i} - 1 = 3^{r_i} c_i - 1 \ge 26$:

$$
a_{t_i} - 1 = 3^{r_i} c_i - 1 = 2^{m_i} d_i, \qquad \text{with } d_i \in \mathbb{Z}_{\ge 1}, \quad d_i \equiv 1 \pmod 2 \text{ (valley odd core)}
$$

  After these $m_i$ odd steps, at time $N_i = t_i + m_i$, the state reaches the even number that initiates cycle $i+1$:

$$
a_{N_i} = 3^{m_i} d_i + 1 = 2^{r_{i+1}} c_{i+1}
$$

### 3.3. Theorem of the Four Exact Valuation Laws (2-adic and 3-adic Symmetry)

Theorem 3.1 (The Four Macro-Cycle Valuation Laws) [Proved]: *For every cycle $i \ge 1$, the cores $c_i, d_i \in \mathbb{Z}_{\ge 1}$ are odd and coprime to $3$ ($3 \nmid c_i$ and $3 \nmid d_i$, since for $i=1$, $c_1 = 1 \not\equiv 0 \pmod 3$, $2^{m_i} d_i = 3^{r_i}c_i - 1 \equiv -1 \pmod 3 \implies 3 \nmid d_i$, and $2^{r_{i+1}}c_{i+1} = 3^{m_i}d_i + 1 \equiv 1 \pmod 3 \implies 3 \nmid c_{i+1}$). Consequently, the durations $r_i$ and $m_i$ simultaneously satisfy the four exact identities:*

1. **2-adic Even Pumping Law:** $r_i = v_2(3^{m_{i-1}} d_{i-1} + 1)$ *(for $i \ge 2$, with $r_1 = v_2(8) = 3$).*
2. **3-adic Even Pumping Law:** $r_i = v_3(2^{m_i} d_i + 1)$ *(for all $i \ge 1$).*
3. **2-adic Odd Drop Law:** $m_i = v_2(3^{r_i} c_i - 1)$ *(for all $i \ge 1$).*
4. **3-adic Odd Drop Law:** $m_i = v_3(2^{r_{i+1}} c_{i+1} - 1)$ *(for all $i \ge 1$).*

**Proof:**
From $3^{r_i} c_i = 2^{m_i} d_i + 1$ with $2 \nmid d_i$ and $3 \nmid c_i$, taking $p$-adic valuations yields $v_2(3^{r_i} c_i - 1) = v_2(2^{m_i} d_i) = m_i + v_2(d_i) = m_i$, and $v_3(2^{m_i} d_i + 1) = v_3(3^{r_i} c_i) = r_i + v_3(c_i) = r_i$. Analogously, from $2^{r_{i+1}} c_{i+1} = 3^{m_i} d_i + 1$ with $2 \nmid c_{i+1}$ and $3 \nmid d_i$, taking $v_2$ and $v_3$ yields laws (1) and (4). $\blacksquare$

### 3.4. The Double Bridge Identity and the Universal Floor Formula for Odd Cores

Theorem 3.2 (Universal Floor Formula between Consecutive Cores) [Proved]: *Consecutive odd cores $d_i$ and $d_{i+1}$ are directly coupled without passing through $c_{i+1}$ via the exact Diophantine equation:*

$$
3^{m_i + r_{i+1}} d_i + 3^{r_{i+1}} - 2^{r_{i+1}} = 2^{r_{i+1} + m_{i+1}} d_{i+1}
$$

*Solving for $d_i$ in terms of $d_{i+1}$, for every cycle $i \ge 1$ the exact floor identity (free of integer boundary cases) holds:*

$$
d_i = \left\lfloor \frac{2^{r_{i+1} + m_{i+1}}}{3^{m_i + r_{i+1}}} d_{i+1} \right\rfloor
$$

*whose fractional part belongs strictly to the open interval $(0, 1/3)$ and equals:*

$$
\left\{ \frac{2^{r_{i+1} + m_{i+1}}}{3^{m_i + r_{i+1}}} d_{i+1} \right\} = \frac{3^{r_{i+1}} - 2^{r_{i+1}}}{3^{m_i + r_{i+1}}} = \frac{1 - (2/3)^{r_{i+1}}}{3^{m_i}} \in \left(0, \frac{1}{3}\right)
$$

*Furthermore, in every cycle $i \ge 1$ one has $(2^{m_i} d_i + 1) \bmod 9 \in \{0, 6\}$.*

**Proof:**
Equating the two expressions for $c_{i+1} = \frac{3^{m_i} d_i + 1}{2^{r_{i+1}}} = \frac{2^{m_{i+1}} d_{i+1} + 1}{3^{r_{i+1}}}$ and dividing by $3^{m_i}$:

$$
\frac{2^{r_{i+1} + m_{i+1}}}{3^{m_i + r_{i+1}}} d_{i+1} = d_i + \frac{1 - (2/3)^{r_{i+1}}}{3^{m_i}}
$$

Given that $r_{i+1} \ge 1$ and $m_i \ge 1$, we have $(2/3)^{r_{i+1}} \in (0, 2/3]$ and $3^{m_i} \ge 3$, so that the fractional remainder strictly satisfies:

$$
0 < \frac{1 - 2/3}{3^{m_i}} \le \frac{1 - (2/3)^{r_{i+1}}}{3^{m_i}} < \frac{1}{3^{m_i}} \le \frac{1}{3} < 1
$$

In particular, the rational quotient $\frac{2^{r_{i+1} + m_{i+1}}}{3^{m_i + r_{i+1}}} d_{i+1}$ is never an integer, and since $d_i \in \mathbb{Z}$, its floor is exactly $d_i$. Finally, since $2^{m_i} d_i + 1 = 3^{r_i} c_i$, if $r_i \ge 2$ it is $\equiv 0 \pmod 9$, and if $r_i = 1$ (which can only occur for $i \ge 2$) then $2 c_i = 3^{m_{i-1}} d_{i-1} + 1 \equiv 1 \pmod 3 \implies c_i \equiv 2 \pmod 3 \implies 3c_i \equiv 6 \pmod 9$. $\blacksquare$

### 3.5. Audited Table of the First 10 Macro-Cycles of Antihydra

Computing with exact integer precision from $a_0 = 8 = 2^3 \cdot 1$ ($r_1 = 3, c_1 = 1$), we obtain the exact parameters of the first 10 macro-cycles (where $B_i = b_{N_i} = \sum_{j=1}^i (2r_j - m_j)$) [Computationally Verified in Finite Range $1 \le i \le 10$]:

| Cycle ($i$) | Even pumping ($r_i$) | Odd drop ($m_i$) | Cumulative even ($P_i$) | Even core ($c_i$) | Odd core ($d_i$) | Jump $\Delta B_i = 2r_i - m_i$ | Counter ($B_i$) | Step ($N_i$) |
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

## Part IV: Archimedean Domain, the Antihydra Constant $\alpha$, Non-Integrality $R_n \in (0,1)$, and the SWRO

### 4.1. Construction, Rigorous Truncation Bound, and Certified Exact Value of $\alpha$

Dividing the Fundamental Trajectory Identity $2^n a_n = 8 \cdot 3^n - \sum_{k=0}^{n-1} 3^{n-1-k} 2^k p_k$ by $3^n$, we define the monotonically non-increasing rational sequence:

$$
\alpha_n := \left(\frac{2}{3}\right)^n a_n = 8 - \sum_{k=0}^{n-1} \frac{2^k}{3^{k+1}} p_k
$$

**Theorem 4.1 (Absolute Convergence, Truncation Bound of $\alpha$, and Strict Confinement** $R_n \in (0,1)$) [Proved]: 

1. *The series $\sum_{k=0}^{\infty} \frac{2^k}{3^{k+1}} p_k$ is dominated term-by-term by the convergent geometric series $\frac{1}{3}\sum_{k=0}^\infty (2/3)^k = 1$, so it converges absolutely to a real number* $\alpha = \lim_{n\to\infty} \alpha_n \in [7, 8]$ *(the **Antihydra Constant**).*
2. *For any integer truncation horizon $M \ge 1$, the excess error $\alpha_M - \alpha$ satisfies the rigorous bound:*

$$
0 < \alpha_M - \alpha = \sum_{k=M}^{\infty} \frac{2^k}{3^{k+1}} p_k < \frac{1}{3} \sum_{k=M}^{\infty} \left(\frac{2}{3}\right)^k = \left(\frac{2}{3}\right)^M
$$

   *In particular, for $M = 300$, the exact value of the geometric bound is:*

$$
\left(\frac{2}{3}\right)^{300} \approx 1.4880663064957113 \times 10^{-53} < 1.49 \times 10^{-53}
$$

   *Evaluating $\alpha_{300} = (2/3)^{300} a_{300}$ with exact rational arithmetic yields:*

$$
\alpha_{300} = 7.8641772620566189724051685296822813853074242517735940028\dots
$$

   *Since $\alpha_{300} - 1.49 \times 10^{-53} < \alpha < \alpha_{300}$ and the decimal digits from position $1$ to position $52$ after the decimal point of $\alpha_{300}$ (`...735940...`) undergo no borrows when subtracting $1.49 \times 10^{-53}$ (which affects only from decimal position* $53$ *onward), the first **50 decimal digits after the decimal point** are rigorously certified and immutable as:*

$$
\alpha = 8 - \sum_{k=0}^{\infty} \frac{2^k}{3^{k+1}} p_k = 7.86417726205661897240516852968228138530742425177359\dots
$$

3. *For every integer $n \ge 0$, the Archimedean residual defect:*

$$
R_n := a_n - \alpha\left(\frac{3}{2}\right)^n = \sum_{j=0}^{\infty} \frac{2^j}{3^{j+1}} p_{n+j}
$$

   *satisfies the strict inequality $0 < R_n < 1$. In particular, $\alpha(3/2)^n \notin \mathbb{Z}$ for all $n \ge 0$, so the integer boundary values are never attained, and the exact identities hold simultaneously for all $n \ge 0$:*

$$
a_n = \left\lceil \alpha \left(\frac{3}{2}\right)^n \right\rceil, \qquad a_n - 1 = \left\lfloor \alpha \left(\frac{3}{2}\right)^n \right\rfloor
$$

**Proof of (3) (Rigorous Exclusion of the Endpoints $R_n = 0$ and $R_n = 1$):**
Since $p_{n+j} \in \{0, 1\}$ and $\sum_{j=0}^\infty \frac{2^j}{3^{j+1}} = 1$, we have $0 \le R_n \le 1$.

- If $R_n = 0$, then since each summand is non-negative we would have $p_{n+j} = 0$ for all $j \ge 0$. However, by Proposition 3.0(1), since $a_n \ge a_0 = 8 > 0$, the valuation $r = v_2(a_n) < \infty$ is finite and $p_{n+r} = 1$, a contradiction. Hence $R_n > 0$.
- If $R_n = 1$, then $1 - R_n = \sum_{j=0}^\infty \frac{2^j}{3^{j+1}}(1 - p_{n+j}) = 0 \implies p_{n+j} = 1$ for all $j \ge 0$. However, by Proposition 3.0(2), since $a_n \ge 8 > 1$, the valuation $m = v_2(a_n - 1) < \infty$ is finite and after at most $m$ steps an even state with $p_{n+m} = 0$ is reached, a contradiction. Hence $R_n < 1$.
  Since $a_n \in \mathbb{Z}$ and $a_n - 1 < a_n - R_n = \alpha(3/2)^n < a_n$, the ceiling and floor formulas are proved for all $n \ge 0$. $\blacksquare$

### 4.2. Ergodic Equation of $R_n$ and the Sliding Window Operator

**Corollary 4.2 (Recurrence of $R_n$ and Decomposition of** $b_N$) [Proved]: *For all $n \ge 0$:*

1. *The exponential part $\alpha(3/2)^n$ vanishes identically in the difference operator $2a_{n+1} - 3a_n = -p_n$, leaving:*

$$
2R_{n+1} - 3R_n = -p_n \iff R_n = \frac{p_n}{3} + \frac{2}{3}R_{n+1}
$$

   *which partitions the interval $(0, 1)$ into two regimes: if $p_n = 0 \implies R_n \in (0, 2/3)$, and if $p_n = 1 \implies R_n \in (1/3, 1)$.*
2. *Substituting $p_k = 3R_k - 2R_{k+1}$ into $b_N = \sum_{k=0}^{N-1}(2 - 3p_k)$, the counter satisfies the exact identity:*

$$
b_N = \sum_{k=0}^{N-1} (2 - 3R_k) + 6(R_N - R_0) > \sum_{k=0}^{N-1} (2 - 3R_k) - 1
$$

   *(where the last inequality uses $R_0 = 8 - \alpha \approx 0.1358227379\dots < 1/6$ and $R_N > 0$, whence $6(R_N - R_0) > -6R_0 > -1$).*

## Part V: The Exact Integral Invariant ($44 \cdot 3^n$), the Dual Identities ($O_n, E_n$), the Corrected Identity for $b_N$ in Terms of $Z_k$, and Convergence of Weighted Series

### 5.1. Diophantine Integral Invariant Theorem and the Exact Identities for $O_n$, $E_n$, and $b_N$

Let us define the **Auxiliary Charge Sequence** $Q_n$ and the **Master Control Variable** $Z_n$:

$$
Q_n = 6a_n - b_n - 4, \qquad Z_n = \frac{Q_n + b_n}{2} = 3a_n - 2 \qquad (Q_0 = 44, \; Z_0 = 22)
$$

**Theorem 5.1 (Integral Conservation Laws for $b_n$, $O_n$, $E_n$ and Area-Parity Relation in** $Z_k$) [Proved]: *For every step $n \ge 1$ and every $N \ge 1$, the complete history of the accumulators $b_k$, $O_k$, and $E_k$ satisfies the exact Diophantine identities in $\mathbb{Z}$:*

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

4. **Area-Parity Relation Theorem (with initial term $Z_0 = 22$ included):**

$$
O_N = 24 - 2a_N + \sum_{k=1}^{N-1} a_k = 16 - 2a_N + \sum_{k=0}^{N-1} a_k
$$

$$
b_N = 2N + 6(a_N - 8) - 3 \sum_{k=0}^{N-1} a_k = 2Z_N - 44 - \sum_{k=0}^{N-1} Z_k = 2Z_N - 66 - \sum_{k=1}^{N-1} Z_k
$$

**Complete Proof (including the derivation in terms of $Z_k$ and check at $N = 1$):**
Eliminating $p_k$ between $3a_k - 2a_{k+1} = p_k$ and $b_{k+1} - b_k = 2 - 3p_k$, we obtain $2Q_{k+1} - 3Q_k = b_k$ with $Q_0 = 44$. Multiplying by $3^{n-1-k} 2^k$ and summing from $k = 0$ to $n - 1$ (with $b_0 = 0$) yields (1). Substituting $b_k = 2k - 3O_k$ and $b_k = 3E_k - k$ together with the geometric identity $\sum_{k=1}^{n-1} 3^{n-1-k} 2^k k = 2 \cdot 3^n - 2^n(n + 2)$ yields (2) and (3).

To prove (4) directly from the definitions of $Z_k = 3a_k - 2$ and $b_N$:
Summing $p_k = 3a_k - 2a_{k+1}$ from $k = 0$ to $N - 1$:

$$
O_N = \sum_{k=0}^{N-1} (3a_k - 2a_{k+1}) = 3a_0 - 2a_N + \sum_{k=1}^{N-1} a_k = 24 - 2a_N + \sum_{k=1}^{N-1} a_k = 16 - 2a_N + \sum_{k=0}^{N-1} a_k
$$

Substituting $O_N$ into $b_N = 2N - 3O_N$:

$$
b_N = 2N - 3\left(16 - 2a_N + \sum_{k=0}^{N-1} a_k\right) = 2N + 6a_N - 48 - 3\sum_{k=0}^{N-1} a_k
$$

Since $3a_k = Z_k + 2$ for all $k \ge 0$ (and in particular $6a_N = 2Z_N + 4$), we substitute $3\sum_{k=0}^{N-1} a_k = \sum_{k=0}^{N-1} (Z_k + 2) = \sum_{k=0}^{N-1} Z_k + 2N$:

$$
b_N = 2N + (2Z_N + 4) - 48 - \left(\sum_{k=0}^{N-1} Z_k + 2N\right) = 2Z_N - 44 - \sum_{k=0}^{N-1} Z_k
$$

Separating the $k = 0$ term ($Z_0 = 3(8) - 2 = 22$), this is written equivalently as:

$$
b_N = 2Z_N - 44 - Z_0 - \sum_{k=1}^{N-1} Z_k = 2Z_N - 66 - \sum_{k=1}^{N-1} Z_k
$$

*Explicit verification at $N = 1$:* For $N = 1$, we have $Z_0 = 22$, $a_1 = 12 \implies Z_1 = 3(12) - 2 = 34$, and $b_1 = 2$. The formula with the sum starting at $k = 0$ gives $2Z_1 - 44 - Z_0 = 68 - 44 - 22 = 2 = b_1$, and the form with the sum starting at $k = 1$ (empty sum $= 0$) gives $2Z_1 - 66 - 0 = 68 - 66 = 2 = b_1$. $\blacksquare$

### 5.2. The Autonomous System of $Z_n$ and Absolute Convergence of the Future-Tail Weighted Series

Since $Z_n = 3a_n - 2 \equiv a_n \equiv p_n \pmod 2$, $Z_n$ forms an autonomous dynamical system:

$$
Z_{n+1} = \frac{3Z_n + 2 - 3p_n}{2} = \begin{cases} \frac{3}{2}Z_n + 1 & \text{if } Z_n \text{ is even } (p_n = 0) \\ \frac{3}{2}Z_n - \frac{1}{2} & \text{if } Z_n \text{ is odd } (p_n = 1) \end{cases}
$$

**Theorem 5.2 (Absolute Convergence of the Weighted Series of** $b_k, O_k, E_k$ and Future-Tail Identity) [Proved]: *For all $n \ge 0$, the weighted infinite series $\sum_{k=1}^\infty \left(\frac{2}{3}\right)^k b_k$, $\sum_{k=1}^\infty \left(\frac{2}{3}\right)^k O_k$, $\sum_{k=1}^\infty \left(\frac{2}{3}\right)^k E_k$, and* $\sum_{j=1}^\infty \left(\frac{2}{3}\right)^j b_{n+j}$ ***converge absolutely** in* $\mathbb{R}$*, and satisfy the exact identities:*

$$
\alpha = 8 - \frac{1}{3}\sum_{k=0}^{\infty} \left(\frac{2}{3}\right)^k p_k = \frac{22}{3} + \frac{1}{18}\sum_{k=1}^{\infty} \left(\frac{2}{3}\right)^k b_k
$$

$$
2b_n + 12 - 18R_n = \sum_{j=1}^{\infty} \left(\frac{2}{3}\right)^j b_{n+j}
$$

**Proof of Absolute Convergence and Passage to the Limit:**

1. **Explicit dominating bound and comparison/ratio test:** By definition, for all $k \ge 1$, since $p_m \in \{0, 1\}$, the accumulators satisfy the deterministic linear bounds:

$$
0 \le O_k \le k, \qquad 0 \le E_k \le k, \qquad |b_k| = |2E_k - O_k| \le 2k
$$

   Consequently, the general term in absolute value of the series is explicitly majorized by:

$$
\left| \left(\frac{2}{3}\right)^k b_k \right| \le 2k \left(\frac{2}{3}\right)^k, \qquad \left| \left(\frac{2}{3}\right)^j b_{n+j} \right| \le 2(n + j) \left(\frac{2}{3}\right)^j
$$

   Applying **D'Alembert's ratio test** to the majorizing series of positive terms $\sum_{k=1}^\infty 2k(2/3)^k$:

$$
\lim_{k \to \infty} \frac{2(k+1)(2/3)^{k+1}}{2k(2/3)^k} = \frac{2}{3} \lim_{k \to \infty} \left(1 + \frac{1}{k}\right) = \frac{2}{3} < 1
$$

   By the Weierstrass comparison test, all series considered are **absolutely convergent** (with majorizing sum $\sum_{k=1}^\infty 2k(2/3)^k = 2 \cdot \frac{2/3}{(1 - 2/3)^2} = 12 < \infty$).
2. **Proof of the identities:** Dividing the Integral Invariant (Theorem 5.1(1)) by $6 \cdot 3^n$:

$$
\frac{22}{3} + \frac{1}{18} \sum_{k=1}^{n-1} \left(\frac{2}{3}\right)^k b_k = \left(\frac{2}{3}\right)^n a_n - \frac{b_n + 4}{6}\left(\frac{2}{3}\right)^n
$$

   Since $|b_n + 4| \le 2n + 4$, we have $\lim_{n\to\infty} \frac{b_n + 4}{6}(2/3)^n = 0$ and $\lim_{n\to\infty} (2/3)^n a_n = \alpha$, obtaining the first identity. Subtracting its partial sum up to $n$ from the infinite series and multiplying by $18 \cdot (3/2)^n$, since $18\left(\alpha(3/2)^n - a_n\right) = -18R_n$, we obtain $2b_n + 12 - 18R_n = \sum_{j=1}^\infty (2/3)^j b_{n+j}$. $\blacksquare$

## Part VI: The Quadratic Virial Theorem and Nonlinear Constraints

### 6.1. Linearization of the Boolean Square and the Second Moment of $b_n$

Exploiting the Boolean idempotence $p_m^2 = p_m$ for all $m \ge 0$, we nonlinearly couple $b_m$ with $p_m$:

Theorem 6.1 (Antihydra Quadratic Virial Theorem) [Proved]: *For every integer $N \ge 1$, the correlation between the counter $b_m$ and the parity $p_m$ satisfies the exact quadratic identity:*

$$
6 \sum_{m=0}^{N-1} b_m p_m = 4 \sum_{m=0}^{N-1} b_m + 2N - b_N(b_N - 1)
$$

**Proof:**
Squaring $b_{m+1} = b_m + (2 - 3p_m)$ and using $p_m^2 = p_m$:

$$
(2 - 3p_m)^2 = 4 - 12p_m + 9p_m^2 = 4 - 3p_m = 2 + (2 - 3p_m) = 2 + b_{m+1} - b_m
$$

Therefore, $b_{m+1}^2 - b_m^2 = 4b_m - 6b_m p_m + 2 + b_{m+1} - b_m$. Summing telescopically from $m = 0$ to $N - 1$ with $b_0 = 0$ yields $b_N^2 = 4\sum_{m=0}^{N-1} b_m - 6\sum_{m=0}^{N-1} b_m p_m + 2N + b_N$. $\blacksquare$

### 6.2. Sum Partition Corollary at a Halting Instant

**Corollary 6.2 (Weight Balance Between Even and Odd Steps at** $b_N = -1$) [Proved]: *Let $\mathcal{E}_N = \{0 \le m < N : p_m = 0\}$ and $\mathcal{O}_N = \{0 \le m < N : p_m = 1\}$ be the disjoint sets of even and odd instants prior to $N$. If halting were to occur at instant $N \ge 1$ ($b_N = -1$), then:*

$$
\sum_{m \in \mathcal{O}_N} b_m = 2 \sum_{m \in \mathcal{E}_N} b_m + N - 1
$$

**Proof:**
Since $\{0, 1, \dots, N-1\} = \mathcal{E}_N \sqcup \mathcal{O}_N$ and $p_m = 0$ for $m \in \mathcal{E}_N$ whereas $p_m = 1$ for $m \in \mathcal{O}_N$, we have:

$$
\sum_{m=0}^{N-1} b_m p_m = \sum_{m \in \mathcal{O}_N} b_m, \qquad \sum_{m=0}^{N-1} b_m = \sum_{m \in \mathcal{E}_N} b_m + \sum_{m \in \mathcal{O}_N} b_m
$$

Substituting both expressions and the halting condition $b_N = -1$ (which gives $b_N(b_N - 1) = (-1)(-2) = 2$) into the identity of Theorem 6.1:

$$
6 \sum_{m \in \mathcal{O}_N} b_m = 4 \left( \sum_{m \in \mathcal{E}_N} b_m + \sum_{m \in \mathcal{O}_N} b_m \right) + 2N - 2
$$

Subtracting $4\sum_{m \in \mathcal{O}_N} b_m$ from both sides yields $2\sum_{m \in \mathcal{O}_N} b_m = 4\sum_{m \in \mathcal{E}_N} b_m + 2N - 2$, and dividing by $2$ gives exactly $\sum_{m \in \mathcal{O}_N} b_m = 2\sum_{m \in \mathcal{E}_N} b_m + N - 1$. $\blacksquare$

## Part VII: Elimination of the Conditional (*If/Else*): The Pure Affine Algebraic Variety and the Dyadic Rigidity Theorem

### 7.1. The Antihydra Algebraic Curve in $\mathbb{Z}^2$

Theorem 7.1 (Equation of the Pure Affine Curve of Antihydra) [Proved]: *A sequence of integers $\{a_n\}_{n=0}^N$ with $a_0 = 8$ is the true trajectory of Antihydra if and only if it satisfies at each step the conditional-free quadratic polynomial equation:*

$$
(3a_n - 2a_{n+1})(3a_n - 2a_{n+1} - 1) = 0 \iff 9a_n^2 - 12a_n a_{n+1} + 4a_{n+1}^2 - 3a_n + 2a_{n+1} = 0
$$

**Proof:**
For any fixed integer $a_n \in \mathbb{Z}$, the integers $3a_n$ and $3a_n - 1$ are consecutive, so that exactly one of them is divisible by $2$ in $\mathbb{Z}$. The branch whose division by $2$ is an integer coincides with $a_{n+1} = \frac{3a_n - (a_n \bmod 2)}{2}$, while the false branch falls in $\mathbb{Z} + \frac{1}{2}$ and has no solution in $\mathbb{Z}$. $\blacksquare$

### 7.2. Dyadic Rigidity Theorem on the Spin Variety $u_n$ (Prefix Uniqueness and Terminal Bifurcation)

Theorem 7.2 (Prefix Dyadic Rigidity and Terminal Ambiguity in the Spin Variety) [Proved]: *For any integer horizon $N \ge 1$, let $\mathcal{V}_N \subset \mathbb{Z}^{N+1}$ be the affine algebraic variety of all integer tuples $(u_0, u_1, \dots, u_N) \in \mathbb{Z}^{N+1}$ such that:*

$$
u_0 = 15, \qquad (2u_{n+1} - 3u_n)^2 - 1 = 0 \quad \forall n \in \{0, 1, \dots, N-1\}
$$

*Then:*

1. **Parity Obstruction for Non-Terminal States:** *For any $n \in \{0, 1, \dots, N-1\}$, the equation $(2u_{n+1} - 3u_n)^2 = 1$ possesses at least one integer solution $u_{n+1} \in \mathbb{Z}$ if and only if* $u_n$ *is **odd** (*$u_n \equiv 1 \pmod 2$*).*
2. **Exact Uniqueness of the Prefix $(u_0, u_1, \dots, u_{N-1})$:** *At every interior step $n \in \{0, 1, \dots, N-2\}$, the requirement that $u_{n+1}$ be extendable one further step to $u_{n+2} \in \mathbb{Z}$ forces $u_{n+1}$ to be odd, which rules out exactly one of the two branches $\frac{3u_n \pm 1}{2}$ and forces the sign $\sigma_n = -\chi_4(u_n)$. Consequently, the first $N$ coordinates* $(u_0, u_1, \dots, u_{N-1})$ *are **uniquely determined** and coincide with the true Antihydra trajectory* $u_n = 2a_n - 1$ *for all $0 \le n \le N-1$.*
3. **Exact Bifurcation in the Terminal Coordinate $u_N$:** *Since no equation toward a step $N+1$ within $\mathcal{V}_N$ constrains the last state $u_N$, the set* $\mathcal{V}_N$ *consists of **exactly two integer tuples**, which share the same prefix* $(u_0, \dots, u_{N-1})$ *and differ solely in that the terminal coordinate $u_N$ may take the true odd value $u_N^+ = \frac{3u_{N-1} + \sigma_{N-1}}{2} = 2a_N - 1$ or the spurious even value $u_N^- = \frac{3u_{N-1} - \sigma_{N-1}}{2} = u_N^+ - \sigma_{N-1}$. By contrast, in the infinite projective limit $\mathcal{V}_\infty \subset \mathbb{Z}^{\mathbb{N}_0}$ (or upon adding the boundary condition $u_N \equiv 1 \pmod 2$), the integer solution is globally unique.*

**Proof by Induction and Modulo 4 Congruences:**

1. At any step $n \in \{0, \dots, N-1\}$, the equation $(2u_{n+1} - 3u_n)^2 - 1 = 0$ in $\mathbb{Z}$ is equivalent to $2u_{n+1} = 3u_n + s_n$ with $s_n \in \{-1, +1\}$. Reducing modulo $2$: $0 \equiv u_n + 1 \pmod 2 \iff u_n \equiv 1 \pmod 2$. Therefore, if some $u_n$ with $0 \le n \le N-1$ were even, $3u_n \pm 1$ would be odd and no $u_{n+1} \in \mathbb{Z}$ would exist.
2. We proceed by induction on $n \in \{0, 1, \dots, N-1\}$ to prove that $u_n = 2a_n - 1$:

   - *Base case ($n = 0$):* By hypothesis, $u_0 = 15 = 2(8) - 1 = 2a_0 - 1$, which is odd.
   - *Inductive step ($0 \le n \le N-2$):* Suppose it is proved that $u_n = 2a_n - 1$ (odd). The two rational solutions of $(2u_{n+1} - 3u_n)^2 = 1$ are:

$$
u_{n+1}^{(+)} = \frac{3u_n + 1}{2}, \qquad u_{n+1}^{(-)} = \frac{3u_n - 1}{2} = u_{n+1}^{(+)} - 1
$$

     Since $u_n$ is odd, both $3u_n + 1$ and $3u_n - 1$ are even, so $u_{n+1}^{(+)}$ and $u_{n+1}^{(-)}$ are **two consecutive integers** in $\mathbb{Z}$. Being consecutive, exactly one of them is odd and the other is even. Since $n \le N-2$, the index $n+1$ satisfies $n+1 \le N-1$, so the equation of the next step $(2u_{n+2} - 3u_{n+1})^2 = 1$ requires, by part (1), that $u_{n+1}$ be **odd**.
     Specifically, for $\frac{3u_n + s_n}{2} \equiv 1 \pmod 2$ to hold, we require $3u_n + s_n \equiv 2 \pmod 4 \iff u_n + s_n \equiv 0 \pmod 4 \iff s_n = -\chi_4(u_n) = \sigma_n$ (by Theorem 2.1). Thus, $u_{n+1}$ is uniquely forced to be $u_{n+1} = \frac{3u_n + \sigma_n}{2} = 2a_{n+1} - 1$.
3. Finally, upon reaching the last step $n = N - 1$, we already have $u_{N-1} = 2a_{N-1} - 1$ odd. The equation $(2u_N - 3u_{N-1})^2 = 1$ admits in $\mathbb{Z}$ the two consecutive integers $u_N = \frac{3u_{N-1} \pm 1}{2}$, one odd ($2a_N - 1$) and the other even ($2a_N - 1 - \sigma_{N-1}$), both valid in $\mathcal{V}_N$ as no constraint exists at $n = N$. $\blacksquare$

## Part VIII: Adelic Space $\mathcal{E}_S$, Local Topologies, Continuity of Operators, and Difference Transform $\Delta^L$

### 8.1. Rigorous Definition of the Adelic Space $\mathcal{E}_S$, Topologies, and Continuity of Local Operators

**Definition 8.0 (Integral S-Adelic Phase Space $\mathcal{E}_S$ and Metric Topologies):**
We consider the set of places $S = \{2, 3, \infty\}$ of $\mathbb{Q}$ and define the integral adelic phase space:

$$
\mathcal{E}_S := \mathbb{Z}_2 \times \mathbb{Z}_3 \times \mathbb{R}
$$

endowed with the product topology induced by the three complete local metrics:

1. **2-adic component $(\mathbb{Z}_2, |\cdot|_2)$:** The compact, totally disconnected ring of 2-adic integers $\mathbb{Z}_2 = \varprojlim \mathbb{Z}/2^k\mathbb{Z}$, with the ultrametric norm $|x|_2 = 2^{-v_2(x)}$ ($|0|_2 = 0$).
2. **3-adic component $(\mathbb{Z}_3, |\cdot|_3)$:** The compact, totally disconnected ring of 3-adic integers $\mathbb{Z}_3 = \varprojlim \mathbb{Z}/3^k\mathbb{Z}$, with the ultrametric norm $|y|_3 = 3^{-v_3(y)}$ ($|0|_3 = 0$).
3. **Archimedean component $(\mathbb{R}, |\cdot|_\infty)$:** The real line with the ordinary Euclidean absolute value.
   The ring of rational integers $\mathbb{Z}$ embeds diagonally as a discrete subring via $\iota: \mathbb{Z} \hookrightarrow \mathcal{E}_S$, $\iota(a) = (a, a, a)$.

Proposition 8.1 (Domains of Definition and Continuity of the Local Operators) [Proved]: 

1. **2-adic Dynamical Operator $T_2: \mathbb{Z}_2 \to \mathbb{Z}_2$:** The parity function $p_2: \mathbb{Z}_2 \to \{0, 1\} \subset \mathbb{Z}_2$, $p_2(x) = x \bmod 2$, is constant on the clopen balls $2\mathbb{Z}_2$ and $1 + 2\mathbb{Z}_2$ of radius $2^{-1}$, and is therefore continuous. For all $x \in \mathbb{Z}_2$, we have $3x - p_2(x) \in 2\mathbb{Z}_2$, so $T_2(x) = \frac{3x - p_2(x)}{2}$ is well-defined from $\mathbb{Z}_2$ into $\mathbb{Z}_2$. Moreover, if $|x - x'|_2 \le 2^{-k}$ ($k \ge 1$), then $p_2(x) = p_2(x')$ and:

$$
|T_2(x) - T_2(x')|_2 = \left|\frac{3(x - x')}{2}\right|_2 = \frac{|3|_2}{|2|_2}|x - x'|_2 = 2|x - x'|_2 \le 2^{-(k-1)}
$$

   Therefore, $T_2$ is **uniformly continuous** (locally $2$-Lipschitz) on $(\mathbb{Z}_2, |\cdot|_2)$.
2. **Affine Branch Operators on $\mathbb{Z}_3$ and Inverse Operator $S_3$:** Since $2 \in \mathbb{Z}_3^\times$ is a 3-adic unit ($|2|_3 = 1$, with inverse $2^{-1} = \frac{1}{2} = \sum_{j=0}^\infty 3^j \in \mathbb{Z}_3$), for each fixed $p \in \{0, 1\}$ the affine branch operator $T_{3,p}: \mathbb{Z}_3 \to \mathbb{Z}_3$, $T_{3,p}(y) = 2^{-1}(3y - p)$, is well-defined on all of $\mathbb{Z}_3$ and is a **strict contraction** with Lipschitz constant $\frac{1}{3}$:

$$
|T_{3,p}(y) - T_{3,p}(y')|_3 = |2^{-1} \cdot 3(y - y')|_3 = \frac{1}{3}|y - y'|_3
$$

   Conversely, on the compact open (clopen) subset of admissible states $\mathcal{U}_3 := 3\mathbb{Z}_3 \cup (1 + 3\mathbb{Z}_3) \subset \mathbb{Z}_3$, defining the continuous selector $r_3(y) \in \{0, 1\}$ by $y \equiv r_3(y) \pmod{3\mathbb{Z}_3}$, we have $2y + r_3(y) \in 3\mathbb{Z}_3$, and the inverse operator $S_3: \mathcal{U}_3 \to \mathbb{Z}_3$, $S_3(y) = \frac{2y + r_3(y)}{3}$, is **uniformly continuous** ($|S_3(y) - S_3(y')|_3 = 3|y - y'|_3$ for $|y - y'|_3 \le 3^{-1}$).
3. **Compatibility on $\mathbb{Z}$ and Projective Matrix Representation:** For all $n \ge 0$, on the integer orbit $\iota(a_n) = (a_n, a_n, a_n)$ we have $T_2(a_n) = T_{3, p_n}(a_n) = a_{n+1}$ and $S_3(a_{n+1}) = a_n$. The homogeneous step is written in matrix form in $\operatorname{GL}_2(\mathbb{Q}_2) \times \operatorname{GL}_2(\mathbb{Q}_3)$ as:

$$
\begin{pmatrix} 2^n a_n \\ 2^n \end{pmatrix} = A_{p_{n-1}} A_{p_{n-2}} \cdots A_{p_0} \begin{pmatrix} 8 \\ 1 \end{pmatrix}, \qquad A_p = \begin{pmatrix} 3 & -p \\ 0 & 2 \end{pmatrix}
$$

### 8.2. Finite-Difference Binomial Transform $\Delta^L$ (Mahler-Newton Filter)

**Theorem 8.1 (Finite-Difference Integer Identity and Exponential Annihilation** $(3/4)^m$) [Proved]: *Let $\Delta$ be the forward difference operator defined on any sequence $(x_m)_{m \ge 0}$ by $(\Delta x)_m = x_{m+1} - x_m$, and let $\Delta^0 x_m = x_m$, $\Delta^L x_m = \Delta(\Delta^{L-1} x)_m = \sum_{j=0}^L (-1)^{L-j}\binom{L}{j} x_{m+j}$ be its iterated powers. Then, for every order $L \ge 1$ and every instant $m \ge 0$:*

1. $2^L (\Delta^L a)_m = a_m - \sum_{r=0}^{L-1} 2^r (\Delta^r p)_m$.
2. *Applied to the Archimedean decomposition $a_m = \alpha(3/2)^m + R_m$ in $(\mathbb{R}, |\cdot|_\infty)$, the operator $\Delta^L$ divides the exponential component by $2^L$:*

$$
(\Delta^L a)_m = \alpha \frac{3^m}{2^{m+L}} + (\Delta^L R)_m
$$

   *In particular, evaluated at $m = 0$ it decays with base $\frac{1}{2}$ as $(\Delta^L a)_0 = \alpha\left(\frac{1}{2}\right)^L + (\Delta^L R)_0$, whereas along the diagonal $L = m$ (at instant $m$) the leading term decays geometrically with base $\frac{3}{4} < 1$: $(\Delta^m a)_m = \alpha\left(\frac{3}{4}\right)^m + (\Delta^m R)_m$.*

**Proof by Induction on $L \ge 1$:**

1. *Base case ($L = 1$):* From $2a_{m+1} = 3a_m - p_m$, subtracting $2a_m$ from both sides gives:

$$
2(\Delta a)_m = 2(a_{m+1} - a_m) = a_m - p_m = a_m - 2^0(\Delta^0 p)_m
$$

   which verifies (1) for $L = 1$.
   *Inductive step ($L \to L + 1$):* Suppose the identity $2^L(\Delta^L a)_m = a_m - \sum_{r=0}^{L-1} 2^r(\Delta^r p)_m$ holds for all $m \ge 0$. Applying the linear operator $\Delta$ to both sides and multiplying by $2$:

$$
2^{L+1}(\Delta^{L+1} a)_m = 2(\Delta a)_m - \sum_{r=0}^{L-1} 2^{r+1}(\Delta^{r+1} p)_m
$$

   Substituting $2(\Delta a)_m = a_m - p_m = a_m - 2^0(\Delta^0 p)_m$ and reindexing the sum with $j = r + 1 \in \{1, \dots, L\}$:

$$
2^{L+1}(\Delta^{L+1} a)_m = a_m - 2^0(\Delta^0 p)_m - \sum_{j=1}^L 2^j(\Delta^j p)_m = a_m - \sum_{j=0}^L 2^j(\Delta^j p)_m
$$

   which completes the induction.
2. For the geometric sequence $g_m = (3/2)^m$, we have $(\Delta g)_m = (3/2)^{m+1} - (3/2)^m = \frac{1}{2}(3/2)^m = \frac{1}{2}g_m$. By immediate induction, $(\Delta^L g)_m = 2^{-L} g_m = \frac{3^m}{2^{m+L}}$. By linearity of $\Delta^L$ applied to $a_m = \alpha g_m + R_m$, we obtain $(\Delta^L a)_m = \alpha \frac{3^m}{2^{m+L}} + (\Delta^L R)_m$. Evaluating at $m = 0$ yields $(\Delta^L a)_0 = \alpha\left(\frac{1}{2}\right)^L + (\Delta^L R)_0$, while along the diagonal $L = m$ at instant $m$ we obtain $(\Delta^m a)_m = \alpha \frac{3^m}{2^{2m}} + (\Delta^m R)_m = \alpha\left(\frac{3}{4}\right)^m + (\Delta^m R)_m$. $\blacksquare$

## Part IX: Strict 3-adic Contraction, Injectivity via 2-adic Valuation of Residual Sets, and Haar Measure of the 3-adic Cantor Set

### 9.1. 3-adic Contraction Theorem and Finite Memory

**Theorem 9.1 (Strict Contraction in $\mathbb{Z}_3$ and Block Polynomial** $W_{k, M}$) [Proved]: *In $(\mathbb{Z}_3, |\cdot|_3)$, each branch $T_{3,p}(x) = \frac{3x - p}{2}$ is a strict contraction by a factor of $\frac{1}{3}$. For all $k \ge 0$ and* $M \ge 1$*, defining the **Bimodular Block Polynomial**:*

$$
W_{k, M} := \sum_{i=0}^{M-1} 3^{M-1-i} 2^i p_{k+i}
$$

*the following exact properties hold:*

1. **$M$-Step Block Identity:** $2^M a_{k+M} = 3^M a_k - W_{k, M}$.
2. **Strict Boundedness in $[0, 3^M - 2^M]$:** $0 \le W_{k, M} \le 3^M - 2^M < 3^M$.
3. **Bimodular Coupling Without Representative Ambiguity:**

$$
W_{k, M} = \left( -2^M a_{k+M} \right) \bmod 3^M \qquad \text{and} \qquad W_{k, M} \equiv 3^M a_k \pmod{2^M}
$$

**Complete Proof:**

1. We proceed by induction on $M \ge 1$. For $M = 1$, $W_{k, 1} = p_k$ and the equation $2a_{k+1} = 3a_k - p_k$ is the definition of the operator. Suppose that $2^M a_{k+M} = 3^M a_k - W_{k, M}$. Multiplying by $3$ and substituting $3a_{k+M} = 2a_{k+M+1} + p_{k+M}$:

$$
2^M (2a_{k+M+1} + p_{k+M}) = 3^{M+1} a_k - 3W_{k, M} \implies 2^{M+1} a_{k+M+1} = 3^{M+1} a_k - \left(3W_{k, M} + 2^M p_{k+M}\right)
$$

   Since $3W_{k, M} + 2^M p_{k+M} = \sum_{i=0}^{M-1} 3^{M-i} 2^i p_{k+i} + 3^0 2^M p_{k+M} = W_{k, M+1}$, (1) is proved.
2. Since $p_{k+i} \in \{0, 1\}$ for all $i$, we have $W_{k, M} \ge 0$ and:

$$
W_{k, M} \le \sum_{i=0}^{M-1} 3^{M-1-i} 2^i = 3^{M-1} \sum_{i=0}^{M-1} \left(\frac{2}{3}\right)^i = 3^{M-1} \frac{1 - (2/3)^M}{1 - 2/3} = 3^M - 2^M < 3^M
$$

3. Reducing the integer equality $W_{k, M} = 3^M a_k - 2^M a_{k+M}$ modulo $3^M$, the term $3^M a_k$ vanishes and we are left with $W_{k, M} \equiv -2^M a_{k+M} \pmod{3^M}$. Since by part (2) the integer $W_{k, M}$ belongs to the canonical remainder interval $[0, 3^M - 2^M] \subset [0, 3^M - 1]$, $W_{k, M}$ is the exact canonical remainder $(-2^M a_{k+M}) \bmod 3^M$. Reducing the same equality modulo $2^M$, the term $-2^M a_{k+M}$ vanishes and we obtain $W_{k, M} \equiv 3^M a_k \pmod{2^M}$. $\blacksquare$

### 9.2. The Base $2 \leftrightarrow$ Base $3$ Reciprocity Identity, Injectivity via 2-adic Valuation, and 3-adic Measure

**Theorem 9.2 (Base 2 $\leftrightarrow$ Base 3 Reciprocity, Injectivity of** $\mathcal{R}_M$, and Haar Measure of the 3-adic Cantor Set) [Proved]: *Let $\mu_3$ be the unique translation-invariant Haar probability measure on the Borel $\sigma$-algebra $\mathcal{B}(\mathbb{Z}_3)$ of the compact group $(\mathbb{Z}_3, +)$, normalized by $\mu_3(\mathbb{Z}_3) = 1$, so that every cylinder ball $c + 3^M\mathbb{Z}_3$ is measurable with $\mu_3(c + 3^M\mathbb{Z}_3) = 3^{-M}$. Then:*

1. **Exact Reciprocity and Extinction of the Class $2 \pmod 3$:** *For every step $n \ge 1$, since $3a_{n-1} - 2a_n = p_{n-1} \implies a_n \equiv -2a_n \equiv p_{n-1} \pmod 3$, the residue modulo $3$ of the current state $a_n$ is identical to the binary parity bit of the previous step $a_{n-1}$:*

$$
a_n \bmod 3 = a_{n-1} \bmod 2 = p_{n-1} \in \{0, 1\} \qquad \forall n \ge 1
$$

   *Consequently, the residue class $a_n \equiv 2 \pmod 3$ is permanently extinguished for all $n \ge 1$, and $O_N = \sum_{n=0}^{N-1} (a_n \bmod 2) = \sum_{n=1}^{N} (a_n \bmod 3)$.*
2. **Formal Definition, Injectivity via 2-adic Valuation, and Exact Cardinality $|\mathcal{R}_M| = 2^M$:** *For each integer $M \ge 1$, let $\Phi_M: \{0, 1\}^M \to \mathbb{Z}$ be the polynomial map defined on binary words $\mathbf{q} = (q_0, q_1, \dots, q_{M-1}) \in \{0, 1\}^M$ by:*

$$
\Phi_M(\mathbf{q}) := \sum_{i=0}^{M-1} 3^{M-1-i} 2^i q_i \in [0, 3^M - 2^M]
$$

   *and let $\Psi_M: \{0, 1\}^M \to \mathbb{Z}/3^M\mathbb{Z}$ be the modular map* $\Psi_M(\mathbf{q}) := (-2^M)^{-1} \Phi_M(\mathbf{q}) \bmod 3^M$*, whose image is the **set of admissible residue classes of level*** $M$*:*

$$
\mathcal{R}_M := \operatorname{Im}(\Psi_M) = \left\{ (-2^M)^{-1} \Phi_M(\mathbf{q}) \bmod 3^M : \mathbf{q} \in \{0, 1\}^M \right\} \subset \mathbb{Z}/3^M\mathbb{Z}
$$

   *Then $\Phi_M$ and* $\Psi_M$ *are **strictly injective**, and the cardinality of* $\mathcal{R}_M$ *is exactly:*

$$
|\mathcal{R}_M| = 2^M \quad \text{(of the } 3^M \text{ possible congruence classes in } \mathbb{Z}/3^M\mathbb{Z}\text{)}
$$

   *with $(a_n \bmod 3^M) \in \mathcal{R}_M$ holding for all $n \ge M$.*
3. **3-adic Haar Measure vs. Cardinality of the Cylinder Sets $\mathcal{C}_M$ and the Limit $\mathcal{C}_\infty \subset \mathbb{Z}_3$:** *Let $\pi_M: \mathbb{Z}_3 \to \mathbb{Z}/3^M\mathbb{Z}$ be the continuous canonical projection. We define the compact open (clopen) cylinder of level $M$ in $\mathbb{Z}_3$ as $\mathcal{C}_M := \pi_M^{-1}(\mathcal{R}_M) = \bigsqcup_{r \in \mathcal{R}_M} (r + 3^M\mathbb{Z}_3)$ and the 3-adic Cantor Set as the decreasing intersection $\mathcal{C}_\infty := \bigcap_{M=1}^\infty \mathcal{C}_M \subset \mathbb{Z}_3$. Then:*

   - **Haar Measure:** *Since $\mathcal{C}_M$ is the disjoint union of $|\mathcal{R}_M| = 2^M$ balls of measure $3^{-M}$, its measure is $\mu_3(\mathcal{C}_M) = 2^M \cdot 3^{-M} = (2/3)^M$. By upper continuity of the Borel measure on the nested sequence $\mathcal{C}_{M+1} \subset \mathcal{C}_M$:*

$$
\mu_3(\mathcal{C}_\infty) = \lim_{M \to \infty} \mu_3(\mathcal{C}_M) = \lim_{M \to \infty} \left(\frac{2}{3}\right)^M = 0
$$

   - **Asymptotic Density in $\mathbb{Z}$:** *For each fixed $M \ge 1$, the periodic set of ordinary integers $\mathcal{C}_M \cap \mathbb{Z}$ consists of $2^M$ classes modulo $3^M$, and therefore has natural (asymptotic) density in $\mathbb{Z}$ equal to $(2/3)^M$.*
   - **Cardinality:** *Whereas the tail of the integer trajectory $\{a_n\}_{n \ge M} \subset \mathcal{C}_M \cap \mathbb{Z}$ is a countably infinite set ($\operatorname{card} = \aleph_0$), the 3-adic limit set $\mathcal{C}_\infty = \varprojlim \mathcal{R}_M \cong \{0, 1\}^{\mathbb{N}_0}$ is homeomorphic to the ternary Cantor space and has the cardinality of the continuum ($\operatorname{card}(\mathcal{C}_\infty) = 2^{\aleph_0} = \mathfrak{c}$), despite having zero Haar measure $\mu_3(\mathcal{C}_\infty) = 0$.*

**Rigorous Proof of Part (2) (Injectivity of $\Phi_M$ and $\Psi_M$ via 2-adic Valuation):**
Let $\mathbf{q} = (q_0, \dots, q_{M-1}) \in \{0, 1\}^M$ and $\mathbf{q}' = (q_0', \dots, q_{M-1}') \in \{0, 1\}^M$ be two distinct binary sequences ($\mathbf{q} \neq \mathbf{q}'$), and let $W = \Phi_M(\mathbf{q})$ and $W' = \Phi_M(\mathbf{q}')$.

1. **Injectivity in $\mathbb{Z}$ via 2-adic valuation:** Since $\mathbf{q} \neq \mathbf{q}'$, there exists a smallest index $i_0 \in \{0, 1, \dots, M-1\}$ such that $q_{i_0} \neq q_{i_0}'$ (while $q_i = q_i'$ for all $0 \le i < i_0$). Subtracting $W$ and $W'$, all terms with $0 \le i < i_0$ cancel identically:

$$
W - W' = 3^{M-1-i_0} 2^{i_0} (q_{i_0} - q_{i_0}') + \sum_{i = i_0 + 1}^{M-1} 3^{M-1-i} 2^i (q_i - q_i')
$$

   Factoring out the common factor $2^{i_0}$, we may write:

$$
W - W' = 2^{i_0} \left[ 3^{M-1-i_0}(q_{i_0} - q_{i_0}') + 2 \sum_{i = i_0 + 1}^{M-1} 3^{M-1-i} 2^{i - 1 - i_0}(q_i - q_i') \right] = 2^{i_0} \left( 3^{M-1-i_0}(\pm 1) + 2t \right)
$$

   where $t \in \mathbb{Z}$ is an integer and $q_{i_0} - q_{i_0}' \in \{-1, +1\}$. Since $3^{M-1-i_0}$ is odd, the parenthesized factor $3^{M-1-i_0}(\pm 1) + 2t \equiv 1 \pmod 2$ is an **odd integer** (hence non-zero). Consequently, the exact 2-adic valuation of the difference is:

$$
v_2(W - W') = i_0 < \infty \implies W - W' \neq 0 \implies W \neq W'
$$

   Therefore, $\Phi_M$ is injective in $\mathbb{Z}$.
2. **Passage from equality modulo $3^M$ to equality in $\mathbb{Z}$:** Suppose now that $\Psi_M(\mathbf{q}) \equiv \Psi_M(\mathbf{q}') \pmod{3^M}$, that is:

$$
(-2^M)^{-1} W \equiv (-2^M)^{-1} W' \pmod{3^M}
$$

   Since $\gcd(-2^M, 3^M) = 1$, multiplication by $-2^M$ is an automorphism of $\mathbb{Z}/3^M\mathbb{Z}$, so multiplying both sides by $-2^M$ yields:

$$
W \equiv W' \pmod{3^M} \iff 3^M \mid (W - W')
$$

   Now, by Theorem 9.1(2), both $W$ and $W'$ belong to the interval $[0, 3^M - 2^M] \subset [0, 3^M - 1]$. Therefore, the integer difference satisfies $|W - W'| \le 3^M - 2^M < 3^M$. The only integer multiple of $3^M$ with absolute value strictly less than $3^M$ is $0$, which forces ordinary equality in $\mathbb{Z}$:

$$
W - W' = 0 \implies W = W' \implies \mathbf{q} = \mathbf{q}'
$$

   This proves that $\Psi_M: \{0, 1\}^M \to \mathbb{Z}/3^M\mathbb{Z}$ is injective, and since the domain $\{0, 1\}^M$ has $2^M$ elements, we conclude that $|\mathcal{R}_M| = |\operatorname{Im}(\Psi_M)| = 2^M$. $\blacksquare$

## Part X: Unambiguous Time Reversal via Ternary Ceilings and Fractional Representation

### 10.1. Exact Time Reversal Theorem (Absence of Past Branching)

Theorem 10.1 (Time Reversal Formula via Ceiling Function) [Proved]: *For any integers $n \ge M \ge 1$, the state of Antihydra $M$ steps in the past is recovered exactly and uniquely from the present state $a_n$ via:*

$$
a_{n-M} = \left\lceil \left(\frac{2}{3}\right)^M a_n \right\rceil
$$

**Proof:**
By Theorem 9.1(1) and (2) with $k = n - M$, we have $3^M a_{n-M} = 2^M a_n + W_{n-M, M}$ with $0 \le W_{n-M, M} \le 3^M - 2^M < 3^M$. Dividing by $3^M$ yields $0 \le a_{n-M} - (2/3)^M a_n = \frac{W_{n-M, M}}{3^M} < 1$. Since $a_{n-M} \in \mathbb{Z}$, it is identically equal to $\lceil (2/3)^M a_n \rceil$. $\blacksquare$

### 10.2. Exact 3-adic Fractional Representation of $O_N$ and $b_N$

Theorem 10.2 (Sum of 3-adic Fractional Parts Formula) [Proved]: *For all $N \ge 1$ and all $j \in \{1, 2, \dots, N\}$, let us define the normalized fractional residue in base $3$ as:*

$$
\theta_j(a_N) := \left\{ -\left(\frac{2}{3}\right)^j a_N \right\} = \frac{(-2^j a_N) \bmod 3^j}{3^j} = \frac{W_{N-j, j}}{3^j} \in \left[0, \, 1 - \left(\frac{2}{3}\right)^j\right]
$$

*Then the odd-step accumulator $O_N$ and the halting counter $b_N$ satisfy exactly and unconditionally:*

$$
O_N = 3\theta_N(a_N) + \sum_{j=1}^{N-1} \theta_j(a_N)
$$

$$
b_N = 2N - 9\theta_N(a_N) - 3 \sum_{j=1}^{N-1} \theta_j(a_N)
$$

**Complete Proof:**

1. By Theorem 9.1(1) applied with $k = N - j$ and horizon $j \in \{1, \dots, N\}$, we have:

$$
3^j a_{N-j} - 2^j a_N = W_{N-j, j} \in [0, 3^j - 2^j]
$$

   Dividing both sides by $3^j$:

$$
a_{N-j} - \left(\frac{2}{3}\right)^j a_N = \frac{W_{N-j, j}}{3^j} \in \left[0, \, 1 - \left(\frac{2}{3}\right)^j\right] \subset [0, 1)
$$

   Since $a_{N-j} \in \mathbb{Z}$, the difference $a_{N-j} - (2/3)^j a_N \in [0, 1)$ coincides exactly with the fractional part of $-(2/3)^j a_N$:

$$
\theta_j(a_N) = \left\{ -\left(\frac{2}{3}\right)^j a_N \right\} = \frac{W_{N-j, j}}{3^j} = a_{N-j} - \left(\frac{2}{3}\right)^j a_N \qquad (\forall j \in \{1, \dots, N\})
$$

2. From the definition of $W_{N-j, j} = \sum_{i=0}^{j-1} 3^{j-1-i} 2^i p_{N-j+i}$, we observe the recurrence relation between $\theta_j(a_N)$ and $\theta_{j-1}(a_N)$ (with the convention $\theta_0(a_N) := 0$):
   Substituting $a_{N-j+1} = (2/3)^{j-1} a_N + \theta_{j-1}(a_N)$ and $a_{N-j} = (2/3)^j a_N + \theta_j(a_N)$ into the step equation $3a_{N-j} - 2a_{N-j+1} = p_{N-j}$:

$$
3\left(\left(\frac{2}{3}\right)^j a_N + \theta_j(a_N)\right) - 2\left(\left(\frac{2}{3}\right)^{j-1} a_N + \theta_{j-1}(a_N)\right) = p_{N-j}
$$

   The terms involving $a_N$ cancel identically ($3(2/3)^j a_N - 2(2/3)^{j-1} a_N = 0$), leaving for all $j \in \{1, 2, \dots, N\}$ the clean identity:

$$
p_{N-j} = 3\theta_j(a_N) - 2\theta_{j-1}(a_N)
$$

3. Summing this identity from $j = 1$ to $N$ (with $\theta_0(a_N) = 0$):

$$
O_N = \sum_{j=1}^{N} p_{N-j} = 3\sum_{j=1}^{N} \theta_j(a_N) - 2\sum_{j=1}^{N-1} \theta_j(a_N) = 3\theta_N(a_N) + \sum_{j=1}^{N-1} \theta_j(a_N)
$$

   Finally, substituting $O_N$ into $b_N = 2N - 3O_N$, we immediately obtain $b_N = 2N - 9\theta_N(a_N) - 3\sum_{j=1}^{N-1} \theta_j(a_N)$. $\blacksquare$

## Part XI: Arithmetic Kirchhoff Equations, Telescoping Proof of $b_N$, Koopman-Walsh Subspaces, and Infinite Family of Cycles in $\mathbb{Z}_2$

### 11.1. Flow Conservation Theorem on the 2-adic Tree and Complete Proof of the Formula for $b_N$

For every level $L \ge 1$ and every residue $r \in \{0, 1, \dots, 2^L - 1\}$, let the class occupancy counter up to time $N-1$ be:

$$
C_r^{(L)}(N) := \sum_{n=0}^{N-1} \mathbf{1}_{a_n \equiv r \pmod{2^L}}
$$

**Theorem 11.1 (Arithmetic Kirchhoff Law, Pole Anchoring, and Telescoping Formula for** $b_N$) [Proved]: *Each class $r \in \mathbb{Z}/2^L\mathbb{Z}$ possesses a unique even preimage $s_0(r, L) = 2(3^{-1} r \bmod 2^L)$ and a unique odd preimage $s_1(r, L) = 2(3^{-1}(r - 1) \bmod 2^L) + 1$ in $\mathbb{Z}/2^{L+1}\mathbb{Z}$, satisfying for all $N \ge 1$:*

$$
C_r^{(L)}(N) = C_r^{(L+1)}(N) + C_{r + 2^L}^{(L+1)}(N) = C_{s_0(r, L)}^{(L+1)}(N) + C_{s_1(r, L)}^{(L+1)}(N) - \delta_r^{(L)}(N)
$$

*where the boundary defect is $\delta_r^{(L)}(N) := \mathbf{1}_{a_N \equiv r \pmod{2^L}} - \mathbf{1}_{a_0 \equiv r \pmod{2^L}}$. Consequently, for all $N \ge 1$ and every level $M \ge 4$ (in particular for $2^M > a_N$):*

1. *At $L = 1$ (with $a_0 = 8 \equiv 0 \pmod 2$ and $\delta_1^{(1)}(N) = p_N - 0 = p_N$), for the odd pole $r = 1$ we have $s_0(1, 1) = 2$ and $s_1(1, 1) = 1$, whence:*

$$
C_2^{(2)}(N) - C_3^{(2)}(N) = p_N
$$

2. *For the odd pole $r = 1$ at any level $L \ge 2$, since $a_0 = 8 \equiv 0 \not\equiv 1 \pmod{2^L}$, we have $\delta_1^{(L)}(N) = \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}$ and $s_1(1, L) = 1$, which induces the exact telescoping cancellation:*

$$
C_{1 + 2^L}^{(L+1)}(N) = C_{s_0(1, L)}^{(L+1)}(N) - \mathbf{1}_{a_N \equiv 1 \pmod{2^L}} \qquad (\forall L \ge 2)
$$

3. *The counter $b_N = 2E_N - O_N$ satisfies for all $M \ge 2$ the exact closed-form identity:*

$$
b_N = 2C_0^{(2)}(N) + C_3^{(2)}(N) - \sum_{L=2}^{M-1} C_{s_0(1, L)}^{(L+1)}(N) - C_1^{(M)}(N) + 2p_N + \sum_{L=2}^{M-1} \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

   *Moreover, since $a_n \ge a_0 = 8 > 1$ for all $n \ge 0$, if one chooses any horizon $M \ge 4$ such that $2^M > a_N$ (whereby no $a_n$ with $0 \le n < N$ can satisfy $a_n \equiv 1 \pmod{2^M}$, as $a_n \ge 8 > 1$ and $a_n < a_N < 2^M$), the residual term vanishes identically ($C_1^{(M)}(N) = 0$), leaving:*

$$
b_N = 2C_0^{(2)}(N) + C_3^{(2)}(N) - \sum_{L=2}^{M-1} C_{s_0(1, L)}^{(L+1)}(N) + 2p_N + \sum_{L=2}^{M-1} \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

**Complete Step-by-Step Proof:**

1. **Kirchhoff flow equation:** On the one hand, each class modulo $2^L$ splits into two classes modulo $2^{L+1}$, so $C_r^{(L)}(N) = C_r^{(L+1)}(N) + C_{r + 2^L}^{(L+1)}(N)$. On the other hand, for each $0 \le n \le N-1$, we have $a_{n+1} \equiv r \pmod{2^L} \iff a_n \equiv s_0(r, L) \pmod{2^{L+1}}$ (if $a_n$ is even) or $a_n \equiv s_1(r, L) \pmod{2^{L+1}}$ (if $a_n$ is odd). Therefore:

$$
\sum_{n=0}^{N-1} \mathbf{1}_{a_{n+1} \equiv r \pmod{2^L}} = C_{s_0(r, L)}^{(L+1)}(N) + C_{s_1(r, L)}^{(L+1)}(N)
$$

   Since $\sum_{n=0}^{N-1} \mathbf{1}_{a_{n+1} \equiv r \pmod{2^L}} = C_r^{(L)}(N) + \mathbf{1}_{a_N \equiv r \pmod{2^L}} - \mathbf{1}_{a_0 \equiv r \pmod{2^L}} = C_r^{(L)}(N) + \delta_r^{(L)}(N)$, solving for $C_r^{(L)}(N)$ proves the master equation.
2. **Case $L = 1, r = 1$:** Since $3^{-1} \equiv 1 \pmod 2$, $s_0(1, 1) = 2(1) = 2$ and $s_1(1, 1) = 2(0) + 1 = 1$. Moreover, $a_0 = 8 \equiv 0 \pmod 2$ and $\mathbf{1}_{a_N \equiv 1 \pmod 2} = p_N$, so $\delta_1^{(1)}(N) = p_N$. Equating both decompositions of $O_N = C_1^{(1)}(N)$:

$$
C_1^{(2)}(N) + C_3^{(2)}(N) = C_2^{(2)}(N) + C_1^{(2)}(N) - p_N \implies C_2^{(2)}(N) = C_3^{(2)}(N) + p_N
$$

3. **Telescoping at the pole $r = 1$ for $L \ge 2$:** For $r = 1$, the odd preimage is always $s_1(1, L) = 2(3^{-1}(0) \bmod 2^L) + 1 = 1$. Furthermore, since $a_0 = 8$ is even, $\mathbf{1}_{a_0 \equiv 1 \pmod{2^L}} = 0$ for all $L \ge 1$, so $\delta_1^{(L)}(N) = \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}$. Equating the fiber partition with the preimage equation for $r = 1$:

$$
C_1^{(L)}(N) = C_1^{(L+1)}(N) + C_{1 + 2^L}^{(L+1)}(N) = C_{s_0(1, L)}^{(L+1)}(N) + C_1^{(L+1)}(N) - \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

   From this follows the recursive relation for $C_1^{(L)}(N)$:

$$
C_1^{(L)}(N) - C_1^{(L+1)}(N) = C_{1 + 2^L}^{(L+1)}(N) = C_{s_0(1, L)}^{(L+1)}(N) - \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

   Summing telescopically from $L = 2$ to $M - 1$:

$$
C_1^{(2)}(N) - C_1^{(M)}(N) = \sum_{L=2}^{M-1} C_{s_0(1, L)}^{(L+1)}(N) - \sum_{L=2}^{M-1} \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

4. **Substitution into $b_N = 2E_N - O_N$:** Since $E_N = C_0^{(1)}(N) = C_0^{(2)}(N) + C_2^{(2)}(N)$ and $O_N = C_1^{(1)}(N) = C_1^{(2)}(N) + C_3^{(2)}(N)$, we substitute $C_2^{(2)}(N) = C_3^{(2)}(N) + p_N$:

$$
b_N = 2\left(C_0^{(2)}(N) + C_3^{(2)}(N) + p_N\right) - \left(C_1^{(2)}(N) + C_3^{(2)}(N)\right) = 2C_0^{(2)}(N) + C_3^{(2)}(N) + 2p_N - C_1^{(2)}(N)
$$

   Substituting the telescoping expression for $C_1^{(2)}(N)$ proved in step (3) yields the exact formula of the statement. Finally, if $2^M > a_N$, since $8 = a_0 \le a_n < a_N < 2^M$ for all $0 \le n < N$, we have $C_1^{(M)}(N) = 0$. $\blacksquare$

### 11.2. Koopman-Walsh Detail Subspaces and Infinite Family of Periodic Cycles in $\mathbb{Z}_2$ vs. $\mathbb{Z}$

**Theorem 11.2 (Haar-Walsh Detail Subspace** $\mathcal{W}_L$ and Koopman Action) [Proved]: *Let $\mathcal{H}_L := \mathcal{F}(\mathbb{Z}/2^L\mathbb{Z}, \mathbb{C})$ be the Hilbert space of all complex-valued functions on $\mathbb{Z}/2^L\mathbb{Z}$ ($L \ge 1$) equipped with the inner product $\langle f, g \rangle = 2^{-L}\sum_{a=0}^{2^L-1} f(a)\overline{g(a)}$, of dimension $\dim_{\mathbb{C}}(\mathcal{H}_L) = 2^L$. For each residue $v \in \{0, 1, \dots, 2^{L-1}-1\}$, we define the level-$L$ detail wavelet:*

$$
w_v^{(L)}(a) := (-1)^{\lfloor (a \bmod 2^L)/2^{L-1} \rfloor} \,\mathbf{1}_{a \equiv v \pmod{2^{L-1}}}
$$

1. **Basis of the Detail Subspace $\mathcal{W}_L$ (Dimension $2^{L-1}$):** *The $2^{L-1}$ functions* $\{w_v^{(L)}\}_{v=0}^{2^{L-1}-1}$ *form an orthogonal basis of the **level-***$L$ ***detail subspace***, $\mathcal{W}_L := \operatorname{span}_{\mathbb{C}}\{w_v^{(L)} : 0 \le v < 2^{L-1}\}$, with $\langle w_v^{(L)}, w_{v'}^{(L)} \rangle = 2^{-(L-1)}\delta_{v,v'}$ and $\dim_{\mathbb{C}}(\mathcal{W}_L) = 2^{L-1}$. The full space decomposes as $\mathcal{H}_L = \operatorname{span}\{\mathbf{1}\} \oplus \bigoplus_{\ell=1}^{L} \mathcal{W}_\ell$.*
2. **Level Ascent and Fiber Bifurcation under the Koopman Operator $\mathcal{K}$:** *For every $w_v^{(L)} \in \mathcal{W}_L$, the function $(\mathcal{K}w_v^{(L)})(a) := w_v^{(L)}(T(a))$ belongs to $\mathcal{W}_{L+1}$ and expands into exactly two preimage fibers (the even one $s_0(v, L-1)$ and the odd one $s_1(v, L-1)$ modulo $2^L$):*

$$
\mathcal{K}w_v^{(L)} = \varepsilon_0(v) w_{s_0(v, L-1)}^{(L+1)} + \varepsilon_1(v) w_{s_1(v, L-1)}^{(L+1)} \in \mathcal{W}_{L+1}
$$

   *where $\varepsilon_0(v), \varepsilon_1(v) \in \{-1, +1\}$ are the signs given by $(-1)^{\lfloor (T(s_i(v, L-1)) \bmod 2^L)/2^{L-1} \rfloor}$.*

**Complete Proof of Theorem 11.2:**

1. For each $v \in \{0, \dots, 2^{L-1}-1\}$, the only elements of $\mathbb{Z}/2^L\mathbb{Z}$ congruent to $v \pmod{2^{L-1}}$ are $a_0 = v$ (where $\lfloor v/2^{L-1} \rfloor = 0 \implies w_v^{(L)}(v) = +1$) and $a_1 = v + 2^{L-1}$ (where $\lfloor (v+2^{L-1})/2^{L-1} \rfloor = 1 \implies w_v^{(L)}(v+2^{L-1}) = -1$). Therefore, for $v \neq v'$ the supports $\{v, v+2^{L-1}\}$ and $\{v', v'+2^{L-1}\}$ are disjoint, which implies $\langle w_v^{(L)}, w_{v'}^{(L)} \rangle = 0$; and for $v = v'$, $\langle w_v^{(L)}, w_v^{(L)} \rangle = 2^{-L}(1^2 + (-1)^2) = 2^{-(L-1)} \neq 0$. Being orthogonal and nonzero, the $2^{L-1}$ functions are linearly independent and span $\mathcal{W}_L$ of dimension $2^{L-1}$. Furthermore, every function $f \in \mathcal{H}_L$ decomposes uniquely on each fiber $\{v, v+2^{L-1}\}$ as the sum of its mean $\frac{f(v)+f(v+2^{L-1})}{2} \in \mathcal{H}_{L-1}$ and its half-difference $\frac{f(v)-f(v+2^{L-1})}{2} w_v^{(L)} \in \mathcal{W}_L$, proving by induction that $\mathcal{H}_L = \operatorname{span}\{\mathbf{1}\} \oplus \bigoplus_{\ell=1}^L \mathcal{W}_\ell$.
2. Let $a \in \{0, \dots, 2^L - 1\}$. Since $L \ge 1$, $(a + 2^L) \bmod 2 = a \bmod 2 = p$, hence:

$$
T(a + 2^L) = \frac{3(a + 2^L) - p}{2} = T(a) + 3 \cdot 2^{L-1} \equiv T(a) + 2^{L-1} \pmod{2^L}
$$

   Consequently, $T(a + 2^L) \equiv T(a) \pmod{2^{L-1}}$, while the $(L-1)$-th bit of $T(a)$ is flipped upon adding $2^{L-1} \pmod{2^L}$, which implies:

$$
(\mathcal{K}w_v^{(L)})(a + 2^L) = w_v^{(L)}(T(a + 2^L)) = -w_v^{(L)}(T(a)) = -(\mathcal{K}w_v^{(L)})(a)
$$

   Thus, on each fiber $\{a, a+2^L\}$ of $\mathbb{Z}/2^{L+1}\mathbb{Z}$ over $\mathbb{Z}/2^L\mathbb{Z}$, the function $\mathcal{K}w_v^{(L)}$ takes opposite values (zero mean), so it belongs to $\mathcal{W}_{L+1}$. Finally, $(\mathcal{K}w_v^{(L)})(a) \neq 0 \iff T(a) \equiv v \pmod{2^{L-1}} \iff a \equiv s_0(v, L-1) \pmod{2^L}$ or $a \equiv s_1(v, L-1) \pmod{2^L}$. Evaluating at the representatives $a = s_i(v, L-1) \in \{0, \dots, 2^L-1\}$ (where $w_{s_i(v, L-1)}^{(L+1)}(s_i(v, L-1)) = +1$), the coefficient is exactly $\varepsilon_i(v) = w_v^{(L)}(T(s_i(v, L-1))) = (-1)^{\lfloor (T(s_i(v, L-1)) \bmod 2^L)/2^{L-1} \rfloor}$. $\blacksquare$

**Theorem 11.3 (Classification of Periodic Cycles in $\mathbb{Z}_2$ vs. $\mathbb{Z}$ and Infinite Family of Cycles of Minimal Period** $m$) [Proved]: 

1. **Rational Formula for Periodic Points in $\mathbb{Z}_2$:** *Every periodic point $x_0 \in \mathbb{Z}_2$ of period $m \ge 1$ under $T_2(x) = \frac{3x - (x \bmod 2)}{2}$ with parity word $(p_0, \dots, p_{m-1}) \in \{0, 1\}^m$ satisfies $2^m x_0 = 3^m x_0 - W$, so it is necessarily a rational number with odd denominator belonging to $[0, 1] \cap \mathbb{Q}$:*

$$
x_0 = \frac{W}{3^m - 2^m} \in \mathbb{Z}_2 \cap [0, 1] \cap \mathbb{Q}, \qquad \text{where } W = \sum_{j=0}^{m-1} 3^{m-1-j} 2^j p_j \in [0, 3^m - 2^m]
$$

2. **Explicit Infinite Family of Non-Integer Rational Cycles in $\mathbb{Z}_2$ of Minimal Period $m \ge 2$:** *For each integer $m \ge 2$, let us define the rational number:*

$$
x_0^{(m)} := \frac{2^{m-1}}{3^m - 2^m} \in (0, 1) \cap \mathbb{Q}
$$

   *Then $x_0^{(m)} \in \mathbb{Z}_2 \setminus \mathbb{Z}$, and its orbit under $T_2$ is given for $0 \le k \le m-1$ by:*

$$
x_k^{(m)} = T_2^k(x_0^{(m)}) = \frac{3^k 2^{m-1-k}}{3^m - 2^m} \in \mathbb{Z}_2 \setminus \mathbb{Z}
$$

   *which follows the exact parity word $(p_0, p_1, \dots, p_{m-2}, p_{m-1}) = (\underbrace{0, 0, \dots, 0}_{m-1\text{ zeros}}, 1)$, returns to* $T_2^m(x_0^{(m)}) = x_0^{(m)}$*, and has **exact minimal period equal to*** $m$*. Consequently, for distinct values of* $m \ge 2$ *these orbits are disjoint and there exist **infinitely many distinct non-integer rational periodic cycles** in* $\mathbb{Z}_2$ *(with $m = 2$ being the special case $\frac{2}{5} \leftrightarrow \frac{3}{5}$).*
3. **Uniqueness of the Fixed Points $\{0, 1\}$ in the Ordinary Integers $\mathbb{Z}$:** *Restricting the domain to the ordinary integers $\mathbb{Z} \subset \mathbb{Z}_2$, since every periodic point satisfies $x_0 \in [0, 1]$ and* $\mathbb{Z} \cap [0, 1] = \{0, 1\}$*, the **only periodic cycles in*** $\mathbb{Z}$ *are the two trivial fixed points $x_0 = 0$ ($W = 0$) and $x_0 = 1$ ($W = 3^m - 2^m$), which are inaccessible from $a_0 = 8$ because the integer orbit is strictly increasing ($a_{n+1} > a_n \ge 8$).*

**Complete Proof of Part (2) (Algebraic Verification of the Infinite Family $x_0^{(m)}$):**
Let $m \ge 2$ be fixed and let $D_m := 3^m - 2^m$.

1. **Membership in $\mathbb{Z}_2 \setminus \mathbb{Z}$:** Since $m \ge 2$, $3^m$ is odd and $2^m$ is even, so the denominator $D_m = 3^m - 2^m \equiv 1 - 0 \equiv 1 \pmod 2$ is strictly **odd**. Therefore, $D_m \in \mathbb{Z}_2^\times$ is invertible in $\mathbb{Z}_2$ (with $D_m^{-1} \equiv 1 \pmod 2$), which guarantees that $x_k^{(m)} = \frac{3^k 2^{m-1-k}}{D_m} \in \mathbb{Z}_2$ for all $0 \le k \le m-1$. Furthermore, for $m \ge 2$ we have $3^m - 2^m \ge 9 - 4 = 5 > 0$ and, for all $0 \le k \le m-1$:

$$
0 < 3^k 2^{m-1-k} \le 3^{m-1} < 3^m - 2^m \quad (\text{since } 2 \cdot 3^{m-1} + 2^m \le 2 \cdot 3^{m-1} + 3^{m-1} = 3^m)
$$

   Hence $0 < x_k^{(m)} < 1$, which proves that $x_k^{(m)} \notin \mathbb{Z}$ for all $0 \le k \le m-1$.
2. **Exact parities and evolution during the first $m-1$ steps ($0 \le k \le m-2$):** In $\mathbb{Z}_2$, since $D_m^{-1} \equiv 1 \pmod 2$, the 2-adic parity of a fraction $\frac{N}{D_m}$ coincides with the parity of the integer numerator $N$:

$$
p_2\left(\frac{N}{D_m}\right) = (N \cdot D_m^{-1}) \bmod 2 = N \bmod 2
$$

   For $0 \le k \le m-2$, the exponent of $2$ in the numerator $N_k = 3^k 2^{m-1-k}$ satisfies $m - 1 - k \ge 1$, so $N_k$ is **even** and $p_2(x_k^{(m)}) = 0$. Applying the even branch $T_0(x) = \frac{3x}{2}$ by induction from $k = 0$ to $k = m-2$:

$$
T_2(x_k^{(m)}) = \frac{3}{2} \left(\frac{3^k 2^{m-1-k}}{3^m - 2^m}\right) = \frac{3^{k+1} 2^{m-1-(k+1)}}{3^m - 2^m} = x_{k+1}^{(m)}
$$

3. **Final step ($k = m - 1$) and cycle closure:** Upon reaching $k = m - 1$, the state is:

$$
x_{m-1}^{(m)} = \frac{3^{m-1} 2^0}{3^m - 2^m} = \frac{3^{m-1}}{3^m - 2^m}
$$

   Whose numerator $N_{m-1} = 3^{m-1}$ is **odd**, so $p_2(x_{m-1}^{(m)}) = 1$. Applying the odd branch $T_1(x) = \frac{3x - 1}{2}$:

$$
T_2(x_{m-1}^{(m)}) = \frac{3\left(\frac{3^{m-1}}{3^m - 2^m}\right) - 1}{2} = \frac{3^m - (3^m - 2^m)}{2(3^m - 2^m)} = \frac{2^m}{2(3^m - 2^m)} = \frac{2^{m-1}}{3^m - 2^m} = x_0^{(m)}
$$

   which proves that $T_2^m(x_0^{(m)}) = x_0^{(m)}$.
4. **Minimality of period $m$:** In a complete cycle of $m$ steps $\{x_0^{(m)}, x_1^{(m)}, \dots, x_{m-1}^{(m)}\}$, the parity bit equals $0$ exactly $m-1$ times (for $0 \le k \le m-2$) and equals $1$ **only once** (at $k = m-1$). Since in $\mathbb{R}$ the finite sequence $x_0^{(m)} < x_1^{(m)} < \dots < x_{m-1}^{(m)}$ is strictly increasing (as $x_{k+1}^{(m)} = \frac{3}{2}x_k^{(m)} > x_k^{(m)}$ for $0 \le k \le m-2$), the $m$ elements $\{x_0^{(m)}, \dots, x_{m-1}^{(m)}\}$ are all pairwise distinct. Therefore, the minimal period of $x_0^{(m)}$ is exactly $m$, and for $m \neq m'$ the associated cycles have different cardinalities and are disjoint. $\blacksquare$

## Part XII: The Ternary Ceiling Chain Criterion $Y_j$, the Corrected Autocorrelation Invariant ($+4X^2$), and the Sieve $\Psi(P_K) \equiv 18 \pmod{36}$

### 12.1. Complete Characterization Theorem of a Final State $X = a_N$ (With Exact Range $0 \le j \le N-1$)

Theorem 12.1 (Ternary Ceiling Chain Criterion and Autocorrelation Invariant) [Proved]: *A positive integer $X \in \mathbb{Z}^+$ is equal to the state $a_N$ of Antihydra (with seed $a_0 = 8$ and $N \ge 1$) if and only if the finite reverse sequence of $N + 1$ terms $(Y_0, Y_1, \dots, Y_N)$ defined by $Y_0 = X$ and the recurrence:*

$$
Y_{j+1} = \left\lceil \frac{2}{3} Y_j \right\rceil \qquad \text{for } j \in \{0, 1, \dots, N-1\}
$$

*simultaneously satisfies:*

1. **Boundary Condition:** $Y_N = 8$.
2. **3-adic Cantor Condition:** $r_j := Y_j \bmod 3 \in \{0, 1\}$ *(that is, $Y_j \not\equiv 2 \pmod 3$)* for all $j \in \{0, 1, \dots, N - 1\}$.

*Over any admissible chain $(Y_0, \dots, Y_N)$:*

- *For all $j \in \{0, 1, \dots, N-1\}$, the ceiling function is eliminated exactly via the inverse linear law:*

$$
3Y_{j+1} - 2Y_j = r_j = p_{N-1-j} \in \{0, 1\}
$$

  *which is equivalent to the **Dual Affine Algebraic Curve*** $(3Y_{j+1} - 2Y_j)(3Y_{j+1} - 2Y_j - 1) = 0$*.*
- *The linear sum satisfies the **Inverse Linear Invariant**:*

$$
24 - 2X + \sum_{j=1}^{N-1} Y_j = O_N
$$

- *The quadratic sum satisfies the **Autocorrelation Invariant of the Inverse Chain**:*

$$
\mathbf{576 + 4X^2 + 13 \sum_{j=1}^{N-1} Y_j^2 - 12 \sum_{j=0}^{N-1} Y_j Y_{j+1} = O_N}
$$

**Proof (with explicit breakdown of the endpoints $j=0$ and $j=N$):**
For each $j \in \{0, 1, \dots, N-1\}$, writing $Y_j = 3q_j + r_j$ with $r_j \in \{0, 1\}$, we have $\lceil \frac{2}{3}Y_j \rceil = 2q_j + r_j = \frac{2Y_j + r_j}{3} \implies 3Y_{j+1} - 2Y_j = r_j$.
Squaring both sides of $3Y_{j+1} - 2Y_j = r_j$ and applying Boolean idempotence $r_j^2 = r_j$ for each $j \in \{0, 1, \dots, N-1\}$:

$$
9Y_{j+1}^2 - 12Y_j Y_{j+1} + 4Y_j^2 = r_j^2 = r_j
$$

Summing from $j = 0$ to $N - 1$, the right-hand side equals $\sum_{j=0}^{N-1} r_j = O_N$. On the left-hand side we carefully separate the boundary terms $Y_N = 8$ and $Y_0 = X$:

1. In the first quadratic sum:

$$
\sum_{j=0}^{N-1} 9Y_{j+1}^2 = 9Y_N^2 + 9\sum_{j=1}^{N-1} Y_j^2 = 9(8^2) + 9\sum_{j=1}^{N-1} Y_j^2 = 576 + 9\sum_{j=1}^{N-1} Y_j^2
$$

2. In the second quadratic sum:

$$
\sum_{j=0}^{N-1} 4Y_j^2 = +4Y_0^2 + 4\sum_{j=1}^{N-1} Y_j^2 = +4X^2 + 4\sum_{j=1}^{N-1} Y_j^2
$$

   Adding both contributions together with $-12\sum_{j=0}^{N-1} Y_j Y_{j+1}$, the interior squares ($1 \le j \le N-1$) combine with coefficient $9 + 4 = 13$ and both boundary terms ($576$ and $+4X^2$) carry a positive sign:

$$
576 + 4X^2 + 13 \sum_{j=1}^{N-1} Y_j^2 - 12 \sum_{j=0}^{N-1} Y_j Y_{j+1} = O_N \quad \blacksquare
$$

### 12.2. The Modular Sieve $\Psi(P_K) \equiv 18 \pmod{36}$ and its Exact Archimedean Representation

**Theorem 12.2 (Modular Invariant** $\Psi(P_K) \equiv 18 \pmod{36}$ at Macro-Cycle Closures and Sieve at a Halting Time) [Proved]: 

1. **Diophantine Identity and Modulo 36 Sieve at the Closure of Every Macro-Cycle with $m_K \ge 2$ (100% independent of $\alpha$):**
   *In any macro-cycle $K \ge 1$ whose odd descent phase has length $m_K \ge 2$ and odd core $d_K \in \mathbb{Z}_{\ge 1}$ ($d_K \equiv 1 \pmod 2$), the even integer at the closure time $N_K = P_K + M_K$:*

$$
\Psi_{\text{cycle}}(K) := 2(a_{N_K} - 1) = 2 \cdot 3^{m_K} d_K
$$

   *simultaneously satisfies the three arithmetic exclusion filters:*

   - **2-adic Filter ($\bmod 4$):** $2(a_{N_K} - 1) \equiv 2 \pmod 4$.
   - **3-adic Filter ($\bmod 9$):** $2(a_{N_K} - 1) \equiv 0 \pmod 9$.
   - **Modulo 36 Combination and Cantor Filter:**

$$
2(a_{N_K} - 1) \equiv 18 \pmod{36} \qquad \text{and} \qquad (2^{m_K} d_K + 1) \bmod 9 \in \{0, 6\}
$$

2. **General Sieve and Exact Archimedean Representation at a First Halting Time $N = 3P + 1 \ge 4$:**
   *Suppose that Antihydra halts for the first time at step $N \ge 4$ (that is, $b_N = -1$ and $b_n \ge 0$ for all $0 \le n < N$). By Lemma 1.1, we have $N = 3P + 1$ (where $P = E_N \ge 1$ is the total number of even steps prior to $N$) and the last two steps prior to $N$ are forced to be odd ($p_{N-2} = p_{N-1} = 1$). Defining for all $P \ge 1$ the functional:*

$$
\Psi(P) := 2(a_{3P+1} - 1) = 2\left( \left\lceil \frac{3\alpha}{2} \left(\frac{27}{8}\right)^{P} \right\rceil - 1 \right) = 2 \left\lfloor \frac{3\alpha}{2} \left(\frac{27}{8}\right)^{P} \right\rfloor
$$

   *then at every first halting time* $N = 3P + 1$ *it holds **unconditionally** that* $9 \mid (a_N - 1)$*, that is:*

$$
\Psi(P) \equiv 0 \pmod{18}
$$

   *breaking down into exactly two subcases according to the parity of $a_N$:*

   - **Subcase 2a (Exact halting at the closure of macro-cycle $K$, i.e., $N = N_K$, $P = P_K$, $B_K = -1$, and $a_N$ even):** *We have $m_K \ge 2$ and the sieve holds with exactness:*

$$
\Psi(P_K) = 2 \left\lfloor \frac{3\alpha}{2} \left(\frac{27}{8}\right)^{P_K} \right\rfloor = 2 \cdot 3^{m_K} d_K \equiv 18 \pmod{36}
$$

   - **Subcase 2b (Halting in the interior of the odd phase of macro-cycle $K$, i.e., $N < N_K$, $B_K \le -2$, and $a_N$ odd):** *Since $a_N - 1$ is even and a multiple of $9$, we have $\Psi(P) \equiv 0 \pmod{36}$ at step $N = 3P + 1$, whereas upon completion of the odd run at $N_K$ it continues to satisfy $2(a_{N_K} - 1) = 2 \cdot 3^{m_K} d_K \equiv 18 \pmod{36}$.*

**Complete Step-by-Step Proof (Separating the Diophantine Proof from the Archimedean Representation):**

1. **Proof of the Sieve $2(a_{N_K} - 1) \equiv 18 \pmod{36}$ via the Chinese Remainder Theorem (Part 1):**
   By the cycle closure identity (Section 3.2), at the conclusion of any macro-cycle $K$ we have $a_{N_K} = 3^{m_K} d_K + 1$ with $d_K \equiv 1 \pmod 2$, whence $2(a_{N_K} - 1) = 2 \cdot 3^{m_K} d_K$.

   - **Modulo $4$:** Since $d_K \equiv 1 \pmod 2$ and $3^{m_K} \equiv 1 \pmod 2$, the product $3^{m_K} d_K$ is odd: $3^{m_K} d_K \equiv 1 \pmod 2$. Multiplying by $2$ yields $2(a_{N_K} - 1) = 2(3^{m_K} d_K) \equiv 2 \pmod 4$.
   - **Modulo $9$:** Since $m_K \ge 2$, we have $m_K - 2 \ge 0$, so $3^{m_K} = 9 \cdot 3^{m_K - 2}$ is a multiple of $9$, that is, $2(a_{N_K} - 1) = 9 \cdot (2 \cdot 3^{m_K - 2} d_K) \equiv 0 \pmod 9$.
   - **Application of the Chinese Remainder Theorem:** Since $\gcd(4, 9) = 1$, the system of simultaneous congruences $\equiv 2 \pmod 4$ and $\equiv 0 \pmod 9$ possesses a unique solution modulo $4 \times 9 = 36$, which is $18 \pmod{36}$. Furthermore, by Theorem 3.2, the core $d_K$ satisfies $(2^{m_K} d_K + 1) \bmod 9 \in \{0, 6\}$. Note that this entire proof of (1) uses solely integer arithmetic, without involving $\alpha$.
2. **Proof of Part 2 (Halting at $N = 3P + 1 \ge 4$ and Archimedean Representation):**

   - Since $b_0 = 0, b_1 = 2, b_2 = 4, b_3 = 6, b_4 = 5$, the first halting time $b_N = -1$ must satisfy $N > 4$. By Lemma 1.1, $N = 3P + 1$ with $P = E_N \ge 1$, and the two steps immediately preceding $N$ are forced to be odd: $p_{N-2} = 1$ and $p_{N-1} = 1$ (passing through $b_{N-2} = 1 \to b_{N-1} = 0 \to b_N = -1$).
   - Applying the odd transition law $a_{k+1} - 1 = \frac{3}{2}(a_k - 1)$ at steps $N - 2$ and $N - 1$:

$$
a_{N-1} - 1 = \frac{3}{2}(a_{N-2} - 1), \qquad a_N - 1 = \frac{3}{2}(a_{N-1} - 1) = \frac{9}{4}(a_{N-2} - 1)
$$

     Since $a_{N-2}, a_{N-1}, a_N \in \mathbb{Z}$ and $\gcd(9, 4) = 1$, the integer $a_{N-2} - 1$ is divisible by $4$, and therefore $a_N - 1 = 9 \cdot \frac{a_{N-2} - 1}{4}$ is **always a multiple of** $9$, regardless of the parity of $a_N$. Multiplying by $2$ yields $\Psi(P) = 2(a_N - 1) \equiv 0 \pmod{18}$.
   - If the first crossing $b_N = -1$ occurs at the conclusion of the odd phase of macro-cycle $K$ ($N = N_K$, hence $P = P_K$, $B_K = -1$, and $a_N = a_{N_K}$ is even), since the last two steps were odd we have $m_K \ge 2$, and by Part (1) it satisfies $\Psi(P_K) \equiv 18 \pmod{36}$. If instead the odd run had length $m_K > b_{t_K} + 1$, at the time $N = 3P + 1$ where $b_N = -1$ the state $a_N$ remains odd ($a_N - 1$ is even), so $2(a_N - 1)$ is a multiple of $4$ and of $9$, giving $\Psi(P) \equiv 0 \pmod{36}$.
   - Finally, by Theorem 4.1(3), for every integer $N \ge 0$ we have $\alpha(3/2)^N \notin \mathbb{Z}$ and $a_N - 1 = \lfloor \alpha(3/2)^N \rfloor = \lceil \alpha(3/2)^N \rceil - 1$. Evaluating at $N = 3P + 1$:

$$
\alpha\left(\frac{3}{2}\right)^{3P + 1} = \frac{3\alpha}{2} \left(\left(\frac{3}{2}\right)^3\right)^{P} = \frac{3\alpha}{2}\left(\frac{27}{8}\right)^{P}
$$

     Substituting into $\Psi(P) = 2(a_{3P+1} - 1)$ yields $\Psi(P) = 2\left(\left\lceil \frac{3\alpha}{2}(27/8)^{P} \right\rceil - 1\right) = 2\left\lfloor \frac{3\alpha}{2}(27/8)^{P} \right\rfloor$. $\blacksquare$

## Part XIII: Exponential Generating Functions, Infinite Product for $\alpha$, and Recurrence at Cube Roots of Unity

For every nonzero complex parameter $z \in \mathbb{C}^\times$, let us consider the exponential factor $z^{b_n}$ and the coupled functional:

$$
F_n(z) := a_n z^{b_n}
$$

**Theorem 13.1 (Exact Multiplicative Quotient of $F_n(z)$, Infinite Product for $\alpha$, and Inhomogeneous Equation at** $z^3 = 1$) [Proved]: 

1. **Exponential Evolution of $z^{b_n}$:** *For all $z \in \mathbb{C}^\times$ and $n \ge 0$:*

$$
z^{b_{n+1}} = z^{b_n} \Big[ z^2 (1 - p_n) + z^{-1} p_n \Big] = z^{b_n} \Big[ z^2 - (z^2 - z^{-1})(3a_n - 2a_{n+1}) \Big]
$$

2. **Exact Branchwise Multiplicative Quotient:** *Since $a_{n+1} = \frac{3a_n - p_n}{2}$ and $b_{n+1} - b_n = 2 - 3p_n$, the step-by-step quotient of $F_n(z) = a_n z^{b_n}$ is exactly:*

$$
\frac{F_{n+1}(z)}{F_n(z)} = \frac{a_{n+1}}{a_n} z^{2 - 3p_n} = \left(\frac{3a_n - p_n}{2a_n}\right) z^{2 - 3p_n} = \begin{cases} \frac{3}{2} z^2 & \text{if } p_n = 0 \quad (a_n \text{ even}), \\[6pt] \frac{3a_n - 1}{2a_n} z^{-1} = \frac{3}{2}\left(1 - \frac{1}{3a_n}\right) z^{-1} & \text{if } p_n = 1 \quad (a_n \text{ odd}). \end{cases}
$$

   *In particular, owing to the multiplicative defect factor $\left(1 - \frac{1}{3a_n}\right) < 1$ in the odd branch, the quotients* $\frac{F_{n+1}(z)}{F_n(z)}$ *of the two branches **do not coincide** when* $z^3 = 1$*. Unrolling the telescoping product from $n = 0$ to $N - 1$:*

$$
F_N(z) = a_N z^{b_N} = 8 \left(\frac{3}{2}\right)^N z^{b_N} \prod_{\substack{k=0 \\ p_k = 1}}^{N-1} \left(1 - \frac{1}{3a_k}\right)
$$

   *Dividing by $(3/2)^N z^{b_N}$ and taking the limit $N \to \infty$ (which converges because $\sum_{k=0}^\infty \frac{1}{3a_k} < \infty$ as* $a_k$ *grows exponentially), we obtain the **Infinite Product Representation of the Antihydra Constant**:*

$$
\alpha = 8 \prod_{\substack{k=0 \\ p_k = 1}}^{\infty} \left(1 - \frac{1}{3a_k}\right)
$$

3. **Exact Inhomogeneous Linear Recurrence at the Cube Roots of Unity ($z^3 = 1$):** *Additively separating the linear term $3a_n$ from the defect $-p_n$ in $2a_{n+1} = 3a_n - p_n$, for all $z \in \mathbb{C}^\times$ it holds that:*

$$
2F_{n+1}(z) = (3a_n - p_n) z^{b_n + 2 - 3p_n} = 3z^{2 - 3p_n} F_n(z) - p_n z^{b_n - 1}
$$

   *(since the term $-p_n z^{b_n + 2 - 3p_n}$ is nonzero only when $p_n = 1$, in which case $b_n + 2 - 3p_n = b_n - 1$). When $z$ is any of the three cube roots of unity ($z^3 = 1$, that is, $z \in \{1, \omega, \omega^2\}$ with $\omega = e^{2\pi i/3}$), we have $z^{-3p_n} = (z^3)^{-p_n} = 1$ for both $p_n = 0$ and* $p_n = 1$*, whereby the **homogeneous coefficients** of both branches do become equal to* $3z^2$*, yielding the exact inhomogeneous linear difference equation:*

$$
2F_{n+1}(z) - 3z^2 F_n(z) = -p_n z^{b_n - 1} \qquad (\forall z \in \{1, \omega, \omega^2\})
$$

## Part XIV: Ternary Symbolic Dynamics, Carry Transducer and Populations ($U_n, D_n, V_n, K_n$), the Universal Tail, Mahler's Problem, and Bibliographical References

### 14.1. Operational Definition of the Carry Transducer and Base-3 Populations (with Collision-Free Notation $V_n$)

*(Notation note: To avoid any ambiguity with the master variable $Z_n = 3a_n - 2$ from Part V, throughout the treatise we denote by $V_n$ the count of digits $0$ in the base-$3$ expansion of $a_n$).*

**Definition 14.0 (Base-3 Expansion, Left-to-Right Phase Scan, and Subpopulations):**
Let $a_n \ge 8$ be the state of Antihydra at step $n \ge 0$, and let $L_n = \lfloor \log_3 a_n \rfloor \ge 1$ be the index of its most significant digit in base $3$. We write the standard base-$3$ expansion of $a_n$ from the units position ($k = 0$) up to the leading position ($k = L_n$):

$$
a_n = \sum_{k=0}^{L_n} \tau_{n, k} 3^k, \qquad \tau_{n, k} \in \{0, 1, 2\}, \quad \tau_{n, L_n} \in \{1, 2\}
$$

We define the global counts of digits $0$, $1$, and $2$ in the support $\{0, 1, \dots, L_n\}$:

$$
V_n := \#\{0 \le k \le L_n : \tau_{n, k} = 0\}, \quad U_n := \#\{0 \le k \le L_n : \tau_{n, k} = 1\}, \quad D_n := \#\{0 \le k \le L_n : \tau_{n, k} = 2\}
$$

so that $V_n + U_n + D_n = L_n + 1$. Since $3^k \equiv 1 \pmod 2$, the sum of digits is $\Sigma_3(a_n) := \sum_{k=0}^{L_n} \tau_{n, k} = U_n + 2D_n$ and the parity bit is:

$$
p_n = a_n \bmod 2 = \Sigma_3(a_n) \bmod 2 = U_n \bmod 2 \in \{0, 1\}
$$

**Operational Rule of the Carry Scan (from left to right, $k = L_n, L_n - 1, \dots, 0$):**
In the exact division by $2$ given by $a_{n+1} = \frac{3a_n - p_n}{2} = \frac{\sum_{k=0}^{L_n} \tau_{n, k} 3^{k+1} - p_n}{2}$, long division in base $3$ proceeds from the most significant column toward the units. We define the **vector of phase states (or carries)** $(c_{n, L_n+1}, c_{n, L_n}, \dots, c_{n, 0}) \in \{0, 1\}^{L_n+2}$ by:

1. **Initial state (to the left of the leading digit):** $c_{n, L_n + 1} := 0$.
2. **Local transition recurrence (for $k = L_n, L_n - 1, \dots, 0$):**

$$
c_{n, k} := (c_{n, k+1} + \tau_{n, k}) \bmod 2 = \left( \sum_{j=k}^{L_n} \tau_{n, j} \right) \bmod 2 = \#\{k \le j \le L_n : \tau_{n, j} = 1\} \bmod 2 \in \{0, 1\}
$$

   That is, when scanning from left to right, the phase state toggles ($0 \leftrightarrow 1$) if and only if a digit $\tau_{n, k} = 1$ is read, and remains invariant ($c_{n, k} = c_{n, k+1}$) when $\tau_{n, k} \in \{0, 2\}$ is read.
3. **Final state (at the right boundary $k = 0$):**

$$
c_{n, 0} = \left( \sum_{j=0}^{L_n} \tau_{n, j} \right) \bmod 2 = U_n \bmod 2 = p_n
$$

   In the units column ($j = 0$) of $3a_n - p_n$, this incoming remainder $3c_{n, 0} = 3p_n$ combines with $-p_n$, producing the units digit of $a_{n+1}$ with no outgoing remainder: $\tau_{n+1, 0} = \frac{3c_{n, 0} - p_n}{2} = p_n \in \{0, 1\}$.
4. **Column-by-column Euclidean division equation:** In each column $j = k + 1$ ($0 \le k \le L_n$) of $3a_n$, the carry $c_{n, k+1}$ enters from the left, the digit $\tau_{n, k}$ is added, and the remainder $c_{n, k} = (3c_{n, k+1} + \tau_{n, k}) \bmod 2$ exits to the right, determining the $(k+1)$-th digit of $a_{n+1}$ via the closed formula:

$$
\tau_{n+1, k+1} = \frac{3c_{n, k+1} + \tau_{n, k} - c_{n, k}}{2} \in \{0, 1, 2\} \qquad (0 \le k \le L_n), \qquad \tau_{n+1, 0} = p_n
$$

**Classification of the Four Subpopulations by Phase ($V_n^{(0)}, V_n^{(1)}, D_n^{(0)}, D_n^{(1)}$) and Active Volume $K_n$:**
Since for every position $k$ with $\tau_{n, k} \in \{0, 2\}$ the incoming and outgoing carries coincide ($c_{n, k+1} = c_{n, k}$), we unambiguously classify each digit $0$ and each digit $2$ of $a_n$ according to the value of its phase $c_{n, k} \in \{0, 1\}$:

- **In Inactive Phase ($c_{n, k} = 0$):**

$$
V_n^{(0)} := \#\{0 \le k \le L_n : \tau_{n, k} = 0 \text{ and } c_{n, k} = 0\}, \qquad D_n^{(0)} := \#\{0 \le k \le L_n : \tau_{n, k} = 2 \text{ and } c_{n, k} = 0\}
$$

- **In Active Phase ($c_{n, k} = 1$):**

$$
V_n^{(1)} := \#\{0 \le k \le L_n : \tau_{n, k} = 0 \text{ and } c_{n, k} = 1\}, \qquad D_n^{(1)} := \#\{0 \le k \le L_n : \tau_{n, k} = 2 \text{ and } c_{n, k} = 1\}
$$

  satisfying $V_n = V_n^{(0)} + V_n^{(1)}$ and $D_n = D_n^{(0)} + D_n^{(1)}$. Likewise, among the $U_n$ digits equal to $1$ (read from left to right at positions $k_1 > k_2 > \dots > k_{U_n} \ge 0$), exactly $\frac{U_n + p_n}{2}$ have odd reading index $j$ (toggling the carry from $c_{n, k+1} = 0$ to $c_{n, k} = 1$) and exactly $\frac{U_n - p_n}{2}$ have even reading index $j$ (toggling from $c_{n, k+1} = 1$ to $c_{n, k} = 0$). The total number of positions $k \in \{0, \dots, L_n\}$ that receive an active incoming carry $c_{n, k+1} = 1$ is:

$$
K_n := \#\{0 \le k \le L_n : c_{n, k+1} = 1\} = \frac{U_n - p_n}{2} + D_n^{(1)} + V_n^{(1)}
$$

Theorem 14.1 (Master Equations of the Ternary Automaton and Phase Balance) [Proved]: *For every step $n \ge 0$, the counts of digits $1$ and $2$ of $a_{n+1}$ and the sum of digits $\Sigma_3(a_{n+1})$ obey the exact laws:*

1. **Evolution of digits 2 ($D_{n+1}$):**

$$
D_{n+1} = \frac{U_n - p_n}{2} + D_n^{(1)} = K_n - V_n^{(1)}
$$

2. **Evolution of digits 1 ($U_{n+1}$):**

$$
U_{n+1} = D_n^{(0)} + V_n^{(1)} + p_n = D_n - 2D_n^{(1)} + p_n - \frac{U_n - p_n}{2} + K_n
$$

3. **Evolution of the Sum of Digits ($\Delta \Sigma_3$):**

$$
\Sigma_3(a_{n+1}) - \Sigma_3(a_n) = V_n^{(1)} - D_n^{(0)}
$$

   *Summing from $n = 0$ to $N - 1$ (with* $\Sigma_3(a_0) = \Sigma_3(22_3) = 4$*), we obtain the **Ternary Phase Balance Theorem**:*

$$
\sum_{n=0}^{N-1} \left( V_n^{(1)} - D_n^{(0)} \right) = \Sigma_3(a_N) - 4
$$

4. **Universal Tail Theorem after an Odd Run:** *Upon completion of any odd run of length $m \ge 2$ at the even state $a_{t+m} = 3^m d + 1$, the first subsequent even step generates the state:*

$$
a_{t+m+1} = 3^m \left(\frac{3d - 1}{2}\right) + \frac{3^m + 3}{2}
$$

   *whose last $m$ digits in base $3$ form the universal buffer independent of $d$:*

$$
a_{t+m+1} \bmod 3^m = \frac{3^m + 3}{2} = \underbrace{11\dots 1}_{m-2 \text{ ones}} 20_3
$$

**Complete Proof of Theorem 14.1:**
We evaluate the exact formula $\tau_{n+1, k+1} = \frac{3c_{n, k+1} + \tau_{n, k} - c_{n, k}}{2}$ across the six exhaustive and mutually exclusive classes of positions $k \in \{0, 1, \dots, L_n\}$:

1. $\tau_{n, k} = 0$ in Inactive Phase ($c_{n, k+1} = c_{n, k} = 0$, there are $V_n^{(0)}$ positions): $\tau_{n+1, k+1} = \frac{0 + 0 - 0}{2} = 0$.
2. $\tau_{n, k} = 0$ in Active Phase ($c_{n, k+1} = c_{n, k} = 1$, there are $V_n^{(1)}$ positions): $\tau_{n+1, k+1} = \frac{3 + 0 - 1}{2} = 1$.
3. $\tau_{n, k} = 2$ in Inactive Phase ($c_{n, k+1} = c_{n, k} = 0$, there are $D_n^{(0)}$ positions): $\tau_{n+1, k+1} = \frac{0 + 2 - 0}{2} = 1$.
4. $\tau_{n, k} = 2$ in Active Phase ($c_{n, k+1} = c_{n, k} = 1$, there are $D_n^{(1)}$ positions): $\tau_{n+1, k+1} = \frac{3 + 2 - 1}{2} = 2$.
5. $\tau_{n, k} = 1$ of odd order ($c_{n, k+1} = 0 \to c_{n, k} = 1$, there are $\frac{U_n + p_n}{2}$ positions): $\tau_{n+1, k+1} = \frac{0 + 1 - 1}{2} = 0$.
6. $\tau_{n, k} = 1$ of even order ($c_{n, k+1} = 1 \to c_{n, k} = 0$, there are $\frac{U_n - p_n}{2}$ positions): $\tau_{n+1, k+1} = \frac{3 + 1 - 0}{2} = 2$.

Adding the units digit $\tau_{n+1, 0} = p_n \in \{0, 1\}$ (which contributes $+p_n$ to the count of digits $1$ and $0$ to that of digits $2$):

- The digits equal to $2$ in $a_{n+1}$ arise exclusively from cases (4) and (6), so $D_{n+1} = \frac{U_n - p_n}{2} + D_n^{(1)}$.
- The digits equal to $1$ in $a_{n+1}$ arise exclusively from cases (2), (3), and from $\tau_{n+1, 0} = p_n$, so $U_{n+1} = D_n^{(0)} + V_n^{(1)} + p_n$.
- Computing $\Sigma_3(a_{n+1}) = U_{n+1} + 2D_{n+1} = \Sigma_3(a_n) + V_n^{(1)} - D_n^{(0)}$.
  Finally, for (4), if $a_{t+m} = 3^m d + 1$ with $d$ odd, $a_{t+m}$ is even and $a_{t+m+1} = \frac{3(3^m d + 1)}{2} = 3^m\left(\frac{3d-1}{2}\right) + \frac{3^m + 3}{2}$, where $\frac{3^m + 3}{2} = \sum_{k=2}^{m-1} 3^k + 2 \cdot 3^1 + 0 \cdot 3^0$. $\blacksquare$

**Explicit Example Computed Step by Step ($n = 8 \to n = 9$, from $a_8 = 202$ to $a_9 = 303$):**

1. **Base-3 expansion of $a_8 = 202$:** $202 = [21111]_3 \implies (\tau_{8,4}, \tau_{8,3}, \tau_{8,2}, \tau_{8,1}, \tau_{8,0}) = (2, 1, 1, 1, 1)$. Global counts: $V_8 = 0$, $U_8 = 4$, $D_8 = 1$, $\Sigma_3(a_8) = 6$, $p_8 = 0$.
2. **Left-to-right phase scan ($k = 4, 3, 2, 1, 0$) with $c_{8, 5} = 0$:**

   - $k = 4$ ($\tau_{8,4} = 2$): $c_{8,4} = 0 \implies$ counts toward $D_8^{(0)}$. Generated digit: $\tau_{9,5} = 1$.
   - $k = 3$ ($\tau_{8,3} = 1$, 1st one, odd): $c_{8,3} = 1$. Generated digit: $\tau_{9,4} = 0$.
   - $k = 2$ ($\tau_{8,2} = 1$, 2nd one, even): $c_{8,2} = 0$. Generated digit: $\tau_{9,3} = 2$.
   - $k = 1$ ($\tau_{8,1} = 1$, 3rd one, odd): $c_{8,1} = 1$. Generated digit: $\tau_{9,2} = 0$.
   - $k = 0$ ($\tau_{8,0} = 1$, 4th one, even): $c_{8,0} = 0 = p_8$. Generated digit: $\tau_{9,1} = 2$.
   - Units column ($j = 0$): $\tau_{9,0} = p_8 = 0$.
3. **Subpopulations at $n = 8$ and prediction of $n = 9$:** $D_8^{(0)} = 1, D_8^{(1)} = 0, V_8^{(0)} = 0, V_8^{(1)} = 0, \frac{U_8 - p_8}{2} = 2, K_8 = 2 \implies D_9 = 2, U_9 = 1, \Sigma_3(a_9) = 5$.
4. **Direct verification on $a_9 = 303$:** $a_9 = [102020]_3 = 243 + 54 + 6 = 303$, with $U_9 = 1, D_9 = 2, V_9 = 3, \Sigma_3(303) = 5$.

### 14.2. Rigorous Distinction between the Antihydra Problem, the Sequence $\{\alpha(3/2)^n\}$, and Mahler's Problem

In order to establish with precision the scope of this work and what remains open, we formally distinguish four separate mathematical questions:

1. The Halting Problem of Antihydra [Global Open Problem]: Consists in determining whether there exists any integer $N \ge 1$ such that $b_N = -1$ for the orbit $a_0 = 8, a_{n+1} = \lfloor 3a_n / 2 \rfloor$. As we proved in Theorems 1.0, 5.1(4), and 12.1, this question is **logically equivalent** to deciding whether there exists any integer $P \ge 1$ for which the Diophantine polynomial system over $(Y_0, Y_1, \dots, Y_{3P+1}) \in (\mathbb{Z}_{\ge 1})^{3P+2}$:

$$
\begin{cases} (3Y_{j+1} - 2Y_j)(3Y_{j+1} - 2Y_j - 1) = 0 & \forall j \in \{0, 1, \dots, 3P\} \\ Y_{3P+1} = 8 \\ \sum_{j=1}^{3P} Y_j - 2Y_0 = 2P - 23 \end{cases}
$$

   admits an integer solution. This problem remains open.
2. **Mahler's Classical Problem on** $Z$**-Numbers** (Mahler [1968]):
   Formulated by Kurt Mahler in 1968, it asks whether there exists any nonzero real number $\xi > 0$ (called a $Z$*-number*) such that for every integer $n \ge 0$ the fractional part $\{\xi(3/2)^n\}$ satisfies $0 \le \{\xi(3/2)^n\} < \frac{1}{2}$ (which, for $\xi$ associated with a recurrence of the type $x_{n+1} = \lfloor 3x_n/2 \rfloor$ or $D_{n+1} = \lceil 3D_n/2 \rceil$ studied by Odlyzko and Wilf [1991], translates into prescribing the parity of all iterates). Mahler conjectured that no $Z$-numbers exist, which remains open.
3. **The Behavior of the Specific Sequence $\{\alpha(3/2)^n\}$ of Antihydra:**
   By Theorem 4.1(3) and Corollary 4.2(1), for the specific constant $\alpha \approx 7.8641772620566189724\dots$, we have $R_n = a_n - \alpha(3/2)^n = 1 - \{\alpha(3/2)^n\} \in (0, 1)$, and the parity $p_n \in \{0, 1\}$ is determined by the threshold $1/3$:

$$
p_n = 0 \iff R_n \in \left(0, \frac{2}{3}\right) \iff \left\{\alpha\left(\frac{3}{2}\right)^n\right\} \in \left(\frac{1}{3}, 1\right), \qquad p_n = 1 \iff R_n \in \left(\frac{1}{3}, 1\right) \iff \left\{\alpha\left(\frac{3}{2}\right)^n\right\} \in \left(0, \frac{1}{3}\right)
$$

4. **What Distribution Result Would Be Needed by the Specific Strategy of Corollary 4.2(2) (and why there is no proved equivalence):**

   - *Dependence within the Archimedean approach:* In Corollary 4.2(2) we proved the exact identity:

$$
b_N = \sum_{k=0}^{N-1} (2 - 3R_k) + 6(R_N - R_0) = 3\sum_{k=0}^{N-1} \left(\left\{\alpha\left(\frac{3}{2}\right)^k\right\} - \frac{1}{3}\right) + 6(R_N - R_0)
$$

     For **this specific analytic strategy** alone to prove the non-halting of Antihydra (that is, $b_N \ge 0$ for all $N \ge 1$), one does not even need full Weyl equidistribution in $[0, 1]$ (which would give $\lim_{N\to\infty} \frac{1}{N}\sum_{k=0}^{N-1} R_k = \frac{1}{2}$ and $b_N \sim \frac{N}{2} \to +\infty$), but solely the one-sided bound on the Cesàro means:

$$
\frac{1}{N}\sum_{k=0}^{N-1} R_k \le \frac{2}{3} - \frac{6R_0}{3N} \qquad \text{(or } \frac{1}{N}\sum_{k=0}^{N-1} \mathbf{1}_{\{\alpha(3/2)^k\} \in (0, 1/3)} \le \frac{2}{3}\text{ for all } N \ge 1\text{)}
$$

   - *Absence of proved logical equivalence:* It is essential to record that:

     1. Resolving Mahler's classical problem (on $Z$-numbers with threshold $1/2$ for all $\xi$) **is not equivalent** to resolving Antihydra (which concerns a single explicit constant $\alpha$ with threshold $1/3$ in the cumulative mean).
     2. Nor has it been proved that the equidistribution of $\{\alpha(3/2)^k\}$ is a necessary condition for the non-halting of Antihydra: $b_N$ could never reach $-1$ due to Diophantine or 2-adic/3-adic obstructions even without knowing the asymptotic distribution of $\{\alpha(3/2)^k\}$.

### 14.3. Verifiable Bibliographical References

1. **Dubickas, A. (2009):** "On integer sequences generated by linear maps", *Glasgow Mathematical Journal*, Vol. 51, No. 2, pp. 243–252. `doi:10.1017/S0017089508004655`. *(Study of iterated integer sequences of the type $\lfloor \frac{p}{q} x_n \rfloor$ and non-generation of Sturmian words).*
2. **Flatto, L., Lagarias, J. C., & Pollington, A. D. (1995):** "On the range of fractional parts $\{\xi(p/q)^n\}$", *Acta Arithmetica*, Vol. 70, No. 2, pp. 125–147. *(Bounds on the length of intervals free of fractional parts of powers of $p/q$, in particular $3/2$).*
3. **Lagarias, J. C. (1985):** "The $3x + 1$ problem and its generalizations", *The American Mathematical Monthly*, Vol. 92, No. 1, pp. 3–23. *(2-adic analysis, Haar measure, and rational cycles in piecewise affine operators).*
4. **Ligocki, S. (2024):** "BB(6) is Hard (Antihydra)", *sligocki.com* (published July 6, 2024). *(Original derivation of the high-level rules of the Antihydra Turing machine `1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA`).*
5. **Mahler, K. (1968):** "An unsolved problem on the powers of $3/2$", *Journal of the Australian Mathematical Society*, Vol. 8, No. 2, pp. 313–321. `doi:10.1017/S1446788700005371`. *(Original formulation of Mahler's problem on $Z$-numbers and powers of $3/2$ modulo $1$).*
6. **Odlyzko, A. M., & Wilf, H. S. (1991):** "Functional iteration and the Josephus problem", *Glasgow Mathematical Journal*, Vol. 33, No. 2, pp. 235–240. `doi:10.1017/S0017089500008272`. *(Existence of the real ceiling/floor representation constant in iterations of $\lfloor \frac{3}{2}x \rfloor$ and $\lceil \frac{3}{2}x \rceil$).*
7. **The Busy Beaver Challenge Contributors (2024):** "Antihydra", *BusyBeaverWiki* (`https://wiki.bbchallenge.org/wiki/Antihydra`), together with the associated sequences in *The On-Line Encyclopedia of Integer Sequences (OEIS)*: **A386792** (values of $a_n$ from $a_0 = 8$) and **A385902** (values of the counter $b_n$).

## Part XV: Exact Quadratic Telescoping of Step-Times $\Delta t_n$ and the Cumulative Turing Machine Action Law ($T_N$)

### 15.1. Elimination of the Bilinear Cross-Term $a_n p_n$ in the Bit-Level Step Duration $\Delta t_n$

In Theorem 1.0(2), we proved that the Antihydra Turing machine transitions from the canonical configuration $\mathcal{A}(b_n, a_n - 4)$ to $\mathcal{A}(b_{n+1}, a_{n+1} - 4)$ in an exact number of bit-level Turing machine steps $\Delta t_n$ given by:

$$
\Delta t_n = \begin{cases} 2b_n + 3k_n^2 + 12k_n + 11 & \text{if } p_n = 0 \quad (a_n - 4 = 2k_n), \\ 3k_n^2 + 12k_n + 5 & \text{if } p_n = 1 \quad (a_n - 4 = 2k_n + 1), \end{cases}
$$

where $k_n = \frac{a_n - 4 - p_n}{2}$. Substituting $k_n$ directly produces a bilinear cross-term $-\frac{3}{2}a_n p_n$. We now prove that the affine curve identity from Part VII eliminates this cross-term identically and converts $3k_n^2 + 12k_n$ into an exact quadratic telescope $a_{n+1}^2 - \frac{3}{2}a_n^2$.

**Theorem 15.1 (Quadratic Telescoping of the Macro-Step Duration $\Delta t_n$)** [Proved]: *For every macro-step $n \ge 0$ of the Antihydra system, the bit-level Turing machine step count $\Delta t_n$ satisfies the exact identity:*

$$
\Delta t_n = a_{n+1}^2 - \frac{3}{2}a_n^2 + 2(1 - p_n)b_n - 1 - \frac{11}{2}p_n
$$

*Proof:*
1. Substituting $2k_n = a_n - 4 - p_n$ into $3k_n^2 + 12k_n = \frac{3}{4}(2k_n)(2k_n + 8)$ and using $p_n^2 = p_n$:

$$
3k_n^2 + 12k_n = \frac{3}{4}(a_n - 4 - p_n)(a_n + 4 - p_n) = \frac{3}{4}\big((a_n - p_n)^2 - 16\big) = \frac{3}{4}a_n^2 - \frac{3}{2}a_n p_n + \frac{3}{4}p_n - 12.
$$

2. On the other hand, from the fundamental recurrence $2a_{n+1} = 3a_n - p_n$, squaring both sides yields:

$$
4a_{n+1}^2 = (3a_n - p_n)^2 = 9a_n^2 - 6a_n p_n + p_n \implies -\frac{3}{2}a_n p_n = a_{n+1}^2 - \frac{9}{4}a_n^2 - \frac{1}{4}p_n.
$$

3. Substituting this expression for $-\frac{3}{2}a_n p_n$ into step 1 eliminates the cross-term completely:

$$
3k_n^2 + 12k_n = \frac{3}{4}a_n^2 + \left(a_{n+1}^2 - \frac{9}{4}a_n^2 - \frac{1}{4}p_n\right) + \frac{3}{4}p_n - 12 = a_{n+1}^2 - \frac{3}{2}a_n^2 + \frac{1}{2}p_n - 12.
$$

4. Combining both branches of Theorem 1.0(2) via $\Delta t_n = 2(1 - p_n)b_n + (3k_n^2 + 12k_n) + 11 - 6p_n$, we obtain:

$$
\Delta t_n = a_{n+1}^2 - \frac{3}{2}a_n^2 + 2(1 - p_n)b_n - 1 - \frac{11}{2}p_n. \quad \blacksquare
$$

---

### 15.2. The Cumulative Turing Machine Action Law ($T_N$)

Let $T_N$ denote the total number of individual Turing machine steps elapsed from the blank tape $0^\infty \mathbf{A>} 0^\infty$ up to the $N$-th canonical configuration $\mathcal{A}(b_N, a_N - 4)$:

$$
T_0 = 11, \qquad T_N = 11 + \sum_{n=0}^{N-1} \Delta t_n \qquad (N \ge 1).
$$

**Theorem 15.2 (Global Parity-Free Action Law for $T_N$)** [Proved]: *For every $N \ge 1$, the cumulative Turing machine step count $T_N$ satisfies the exact polynomial conservation law:*

$$
6 T_N + 3 \sum_{n=0}^{N-1} a_n^2 - 4 \sum_{n=0}^{N-1} b_n = 6 a_N^2 + b_N(2b_N + 9) - 32N - 318
$$

*Equivalently, if $N = 3P + 1$ is a hypothetical halting horizon ($b_N = -1$, preceding the final $2b_N + 3 = 1$ step to `F0`), then:*

$$
6 T_{3P+1} + 3 \sum_{n=0}^{3P} a_n^2 - 4 \sum_{n=0}^{3P} b_n = 6 a_{3P+1}^2 - 96P - 357.
$$

*Proof:*
1. Summing Theorem 15.1 over $n = 0, \dots, N-1$ and noting that $\sum_{n=0}^{N-1} (a_{n+1}^2 - \frac{3}{2}a_n^2) = a_N^2 - a_0^2 - \frac{1}{2}\sum_{n=0}^{N-1} a_n^2$ (with $a_0^2 = 64$) gives:

$$
T_N - 11 = a_N^2 - 64 - \frac{1}{2}\sum_{n=0}^{N-1} a_n^2 + 2\sum_{n=0}^{N-1} b_n - 2\sum_{n=0}^{N-1} b_n p_n - N - \frac{11}{2}O_N.
$$

2. Multiply by $6$ and substitute both the Quadratic Virial Theorem (Theorem 6.1: $-12\sum_{n=0}^{N-1} b_n p_n = -8\sum_{n=0}^{N-1} b_n - 4N + 2b_N(b_N - 1)$) and the triad identity $3O_N = 2N - b_N$:

$$
6T_N - 66 = 6a_N^2 - 384 - 3\sum_{n=0}^{N-1} a_n^2 + 12\sum_{n=0}^{N-1} b_n + \left(-8\sum_{n=0}^{N-1} b_n - 4N + 2b_N^2 - 2b_N\right) - 6N - 11(2N - b_N).
$$

3. Collecting terms yields $6T_N + 3\sum_{n=0}^{N-1} a_n^2 - 4\sum_{n=0}^{N-1} b_n = 6a_N^2 + 2b_N^2 + 9b_N - 32N - 318$. $\blacksquare$

---

## Part XVI: 2-Adic Bernoulli Isomorphism, Fuss-Catalan Halting Measure $\varphi^{-1}$, and Integer Fibonacci Conservation Laws

### 16.1. Explicit 2-Adic Inverse Map and Measure-Preserving Conjugacy

**Theorem 16.1 (Explicit 2-Adic Seed Formula for Any Parity Prefix)** [Proved]: *For every level $L \ge 1$, the map $\Phi_L: \mathbb{Z}/2^L\mathbb{Z} \to \{0, 1\}^L$ assigning to each initial seed $x_0 \bmod 2^L$ its first $L$ parity bits $(p_0, p_1, \dots, p_{L-1})$ under $T(x) = \frac{3x - (x \bmod 2)}{2}$ is a bijection whose explicit inverse is:*

$$
\Phi_L^{-1}(p_0, \dots, p_{L-1}) \equiv \sum_{k=0}^{L-1} \big(3^{-(k+1)} \bmod 2^L\big) 2^k p_k \pmod{2^L}.
$$

*In the projective limit $L \to \infty$, $\Phi_\infty: (\mathbb{Z}_2, \mu_2) \to (\{0, 1\}^{\mathbb{N}}, \mu_{1/2})$ is a measure-preserving topological conjugacy between $T$ and the unilateral Bernoulli shift, with inverse $\Phi_\infty^{-1}((p_k)_{k \ge 0}) = \sum_{k=0}^\infty 3^{-(k+1)} 2^k p_k \in \mathbb{Z}_2$.*

*Proof:*
For any $x_0 \in \mathbb{Z}_2$, iterating $2x_{k+1} = 3x_k - p_k$ for $L$ steps gives $2^L x_L = 3^L x_0 - \sum_{k=0}^{L-1} 3^{L-1-k} 2^k p_k$. Since $3$ is a unit in $\mathbb{Z}_2$, multiplying by $3^{-L}$ yields $x_0 - \sum_{k=0}^{L-1} 3^{-(k+1)} 2^k p_k = 2^L 3^{-L} x_L \equiv 0 \pmod{2^L}$. Moreover, the $k$-th term of the sum is a multiple of $2^k$, so the series converges in the $2$-adic norm $|\cdot|_2$ for any sequence $(p_k)_{k \ge 0} \in \{0, 1\}^{\mathbb{N}}$. $\blacksquare$

---

### 16.2. Fuss-Catalan Halting Cylinder Enumeration and the Golden-Ratio Haar Measure $\varphi^{-1}$

In $\mathbb{Z}_2$, every seed $x_0 \in \mathbb{Z}_2$ defines a parity sequence $p_n(x_0) \in \{0, 1\}$ and a counter trajectory $b_{n+1}(x_0) = b_n(x_0) + 2 - 3p_n(x_0)$ starting at $b_0 \ge 0$. Let $\mathcal{H}_{\text{all}}(b_0) \subset \mathbb{Z}_2$ denote the set of 2-adic seeds $x_0 \in \mathbb{Z}_2$ for which the counter ever reaches $-1$ ($\exists N \ge 1$ with $b_N(x_0) = -1$).

**Theorem 16.2 (Fuss-Catalan Enumeration of First-Halting Cylinders and Golden-Ratio Haar Measure)** [Proved]:
1. *For $b_0 = 0$ and any integer $P \ge 0$, a seed $x_0 \in \mathbb{Z}_2$ hits $b_N = -1$ for the **first time** at step $N$ ($b_n \ge 0$ for $0 \le n < N$ and $b_N = -1$) if and only if $N = 3P + 1$ for some $P \ge 0$ and its prefix $(p_0, \dots, p_{3P}) \in \{0, 1\}^{3P+1}$ is a Raney ballot word of $P$ zeros and $2P + 1$ ones. The exact number of such residue classes modulo $2^{3P+1}$ is the Fuss-Catalan number:*

$$
|\mathcal{H}_P| = C_P^{(3)} := \frac{1}{3P + 1}\binom{3P + 1}{P} = \frac{1}{2P + 1}\binom{3P}{P}, \qquad \mu_2(\mathcal{H}_P) = \frac{C_P^{(3)}}{2^{3P+1}}.
$$

   *(Specifically, for $P = 0, 1, 2, 3, 4$, there are $C_P^{(3)} = 1, 1, 3, 12, 55$ halting residue classes out of $2, 16, 128, 1024, 8192$ classes modulo $2^{3P+1}$, respectively).*
2. *Summing over all disjoint first-hitting horizons $P \ge 0$, the exact 2-adic Haar measure of the set of all halting seeds $\mathcal{H}_{\text{all}}(b_0) \subset \mathbb{Z}_2$ from any initial counter $b_0 \ge 0$ is a power of the inverse Golden Ratio $\varphi^{-1} = \frac{\sqrt{5} - 1}{2}$:*

$$
\mu_2\big(\mathcal{H}_{\text{all}}(b_0)\big) = \sum_{P=0}^\infty \frac{C_P^{(3)}}{2^{3P+1}} \quad (b_0 = 0) \implies \mu_2\big(\mathcal{H}_{\text{all}}(b_0)\big) = \left(\frac{\sqrt{5} - 1}{2}\right)^{b_0 + 1} = \varphi^{-(b_0 + 1)}.
$$

   *Consequently, for $b_0 = 0$, the set of non-halting 2-adic seeds has strictly positive Haar measure $\mu_2(\mathbb{Z}_2 \setminus \mathcal{H}_{\text{all}}(0)) = 1 - \varphi^{-1} = \varphi^{-2} = \frac{3 - \sqrt{5}}{2} \approx 0.381966$.*

*Proof:*
1. Since $b_{n+1} - b_n \in \{+2, -1\}$ only steps downward by $-1$, the first passage from $b_0 = 0$ to $-1$ must occur at $-1 = 2N - 3O_N$, so $N = 3P + 1$ with $P = N - O_N$ zeros and $O_N = 2P + 1$ ones. By Raney's Lemma (the Fuss-Catalan Ballot Theorem), among the $\binom{3P+1}{P}$ cyclic shifts of a word with $P$ steps of $+2$ and $2P+1$ steps of $-1$ (total sum $-1$), exactly $1$ shift stays $\ge 0$ until the final step $3P + 1$. Thus the number of valid words is $\frac{1}{3P+1}\binom{3P+1}{P} = C_P^{(3)}$. By Theorem 16.1, each word of length $3P + 1$ corresponds to a unique cylinder modulo $2^{3P+1}$ of Haar measure $2^{-(3P+1)}$.
2. By Lagrange inversion, the Fuss-Catalan generating function $w(z) = \sum_{P=0}^\infty C_P^{(3)} z^P$ satisfies $z w(z)^3 - w(z) + 1 = 0$. Since the series $\sum_{P=0}^\infty \frac{C_P^{(3)}}{2^{3P+1}} = \frac{1}{2}w(1/8)$ has positive terms and represents a probability $\rho = \frac{1}{2}w(1/8) \in (0, 1]$, substituting $w = 2\rho$ and $z = 1/8$ into $z w^3 - w + 1 = 0$ yields:

$$
\rho^3 - 2\rho + 1 = (\rho - 1)(\rho^2 + \rho - 1) = 0.
$$

   Since $\sum_{P=0}^\infty C_P^{(3)} z^P$ is strictly increasing on $[0, 4/27]$ (with critical point at $z_c = 4/27 > 1/8 = 3.375/27$, where $w(4/27) = 3/2$), we have $w(1/8) < 3/2 < 2$, so $\rho < 3/4 < 1$. The unique root of $(\rho - 1)(\rho^2 + \rho - 1) = 0$ in $(0, 1)$ is $\rho = \frac{\sqrt{5} - 1}{2} = \varphi^{-1}$. Since a downward step is $-1$, hitting $-1$ from $b_0 \ge 0$ requires $b_0 + 1$ independent first-passage descents of $-1$, giving $\mu_2(\mathcal{H}_{\text{all}}(b_0)) = \rho^{b_0 + 1} = \varphi^{-(b_0 + 1)}$. $\blacksquare$

---

### 16.3. The Deterministic Golden Exponential Identity and Dual Integer Fibonacci Conservation Laws

Even for a **single deterministic orbit** (such as the Antihydra orbit starting from $a_0 = 8, b_0 = 0$), the algebraic relation $\varphi^{-2} + \varphi^{-1} = 1$ induces two exact integer Fibonacci conservation laws along the trajectory. Recall that the Fibonacci numbers $F_m$ are defined for all $m \in \mathbb{Z}$ by $F_0 = 0, F_1 = 1$, and $F_{m+1} = F_m + F_{m-1}$ (so $F_{-1} = 1$).

**Theorem 16.3 (Deterministic Golden Difference Identity and Dual Integer Fibonacci Conservation Laws)** [Proved]: *Along any trajectory of the Antihydra system $(a_n, b_n)$ starting from $b_0 = 0$:*
1. **Golden Difference Identity:** *For every $n \ge 0$, the quantity $\varphi^{-b_n} \in \mathbb{Z}[\varphi]$ satisfies:*

$$
\varphi^{-b_{n+1}} - \varphi^{-b_n} = (2p_n - 1)\varphi^{-(b_n + 1)}.
$$

2. **Dual Integer Fibonacci Conservation Laws:** *For every $N \ge 1$, separating the rational and $\varphi$-components in $\mathbb{Z}[\varphi]$ yields two exact integer identities:*

$$
(-1)^{b_N} F_{b_N} = \sum_{n=0}^{N-1} (2p_n - 1)(-1)^{b_n + 1} F_{b_n + 1},
$$

$$
(-1)^{b_N} F_{b_N + 1} - 1 = \sum_{n=0}^{N-1} (2p_n - 1)(-1)^{b_n + 1} F_{b_n + 2}.
$$

   *In particular, at any hypothetical halting horizon $b_N = -1$ ($F_{-1} = 1, F_0 = 0$), these specialize to $\sum_{n=0}^{N-1} (2p_n - 1)(-1)^{b_n + 1} F_{b_n + 1} = -1$ and $\sum_{n=0}^{N-1} (2p_n - 1)(-1)^{b_n + 1} F_{b_n + 2} = -1$.*

*Proof:*
1. If $p_n = 0$, then $b_{n+1} = b_n + 2$, and since $\varphi^{-2} - 1 = -\varphi^{-1}$, we have $\varphi^{-(b_n+2)} - \varphi^{-b_n} = \varphi^{-b_n}(\varphi^{-2} - 1) = -\varphi^{-(b_n+1)}$. If $p_n = 1$, then $b_{n+1} = b_n - 1$, and since $\varphi - 1 = \varphi^{-1}$, we have $\varphi^{-(b_n-1)} - \varphi^{-b_n} = \varphi^{-b_n}(\varphi - 1) = +\varphi^{-(b_n+1)}$. In both cases, $\varphi^{-b_{n+1}} - \varphi^{-b_n} = (2p_n - 1)\varphi^{-(b_n+1)}$.
2. Summing from $n = 0$ to $N - 1$ with $\varphi^{-b_0} = 1$ gives $\varphi^{-b_N} - 1 = \sum_{n=0}^{N-1} (2p_n - 1)\varphi^{-(b_n+1)}$. By induction on $m \in \mathbb{Z}$, $\varphi^{-m} = (-1)^m(F_m \varphi - F_{m+1})$. Since $\{1, \varphi\}$ is a $\mathbb{Z}$-basis of $\mathbb{Z}[\varphi]$ ($\varphi \notin \mathbb{Q}$), equating the coefficients of $\varphi$ and $1$ on both sides yields the two stated integer identities. $\blacksquare$

---

## Part XVII: The Tri-Local Adelic Bridge Series $\mathcal{S}(p)$ Across $(\mathbb{R}, \mathbb{Z}_2, \mathbb{Z}_3)$ and the Cubic Virial Theorem

### 17.1. The Tri-Local Adelic Bridge Identity

In Part IV we defined the Archimedean constant $\alpha = 8 - \sum_{k=0}^\infty \frac{2^k}{3^{k+1}}p_k \in \mathbb{R}$, while in Part XVI we proved that the 2-adic inverse map is $\Phi_\infty^{-1}(p) = \sum_{k=0}^\infty 3^{-(k+1)} 2^k p_k \in \mathbb{Z}_2$. Strikingly, **these two series have the exact same rational general term** $\frac{2^k}{3^{k+1}}p_k \in \mathbb{Q}$.

**Theorem 17.1 (The Tri-Local Adelic Bridge Theorem)** [Proved]: *For the Antihydra parity sequence $(p_k)_{k \ge 0}$, define the rational partial sums:*

$$
\mathcal{S}_N(p) := \sum_{k=0}^{N-1} \frac{2^k}{3^{k+1}} p_k = 8 - \left(\frac{2}{3}\right)^N a_N \in \mathbb{Q} \qquad (N \ge 1).
$$

*Then the single formal series $\mathcal{S}(p) = \sum_{k=0}^\infty \frac{2^k}{3^{k+1}}p_k$ links all three local completions of $\mathcal{E}_S = \mathbb{R} \times \mathbb{Z}_2 \times \mathbb{Z}_3$ simultaneously:*
1. **In the Archimedean topology $\mathbb{R}$ ($|\cdot|_\infty$):** *Since $|2/3|_\infty = 2/3 < 1$, $\mathcal{S}_N(p)$ converges geometrically to the initial fractional shift $R_0$:*

$$
\lim_{N \to \infty}^{\mathbb{R}} \mathcal{S}_N(p) = 8 - \alpha = R_0 \approx 0.135822737943381\dots \in (0, 1).
$$

2. **In the 2-adic topology $\mathbb{Z}_2$ ($|\cdot|_2$):** *Since $|2/3|_2 = 1/2 < 1$ and $a_N \in \mathbb{Z} \subset \mathbb{Z}_2$, the remainder satisfies $|8 - \mathcal{S}_N(p)|_2 = |(2/3)^N a_N|_2 \le 2^{-N} \to 0$, so the exact same series converges 2-adically to the integer seed $a_0 = 8$:*

$$
\lim_{N \to \infty}^{\mathbb{Z}_2} \mathcal{S}_N(p) = 8 = a_0 \in \mathbb{Z}_2.
$$

3. **In the 3-adic topology $\mathbb{Z}_3$ ($|\cdot|_3$):** *Clearing the denominator $3^N$ projects $\mathcal{S}_N(p)$ directly onto the 3-adic Cantor residue class of $a_N$:*

$$
3^N \mathcal{S}_N(p) = 8 \cdot 3^N - 2^N a_N \equiv -2^N a_N \pmod{3^N}.
$$

*Proof:*
From $2a_{k+1} = 3a_k - p_k$, dividing by $3^{k+1}/2^k$ telescopes $\sum_{k=0}^{N-1} \frac{2^k}{3^{k+1}}p_k = a_0 - \left(\frac{2}{3}\right)^N a_N = 8 - \left(\frac{2}{3}\right)^N a_N$. Taking limits in $|\cdot|_\infty$ (Theorem 4.1), in $|\cdot|_2$ (where $|3^{-N}|_2 = 1$ and $|2^N a_N|_2 \le 2^{-N}$), and reducing $3^N \mathcal{S}_N(p) \pmod{3^N}$ establishes (1), (2), and (3). $\blacksquare$

---

### 17.2. The Cubic Virial Theorem

In Part VI (Theorem 6.1) we established the Quadratic Virial Theorem expressing $\sum_{n=0}^{N-1} b_n p_n$ in terms of $\sum_{n=0}^{N-1} b_n$. By telescoping the cubic potential $b_{n+1}^3 - b_n^3$, we obtain the exact third-order moment law.

**Theorem 17.2 (The Cubic Virial Theorem)** [Proved]: *For every $N \ge 1$, the quadratic parity-weighted sum $\sum_{n=0}^{N-1} b_n^2 p_n$ satisfies the exact identity:*

$$
18 \sum_{n=0}^{N-1} b_n^2 p_n = 12 \sum_{n=0}^{N-1} (b_n^2 + b_n) - b_N(2b_N^2 - 3b_N - 3) - 2N.
$$

*At any hypothetical halting horizon $b_N = -1$ ($b_N(2b_N^2 - 3b_N - 3) = (-1)(2) = -2$), this specializes to the exact Cubic Halting Partition Law:*

$$
9 \sum_{n=0}^{N-1} b_n^2 p_n = 6 \sum_{n=0}^{N-1} (b_n^2 + b_n) - N + 1.
$$

*Proof:*
1. Let $\delta_n = b_{n+1} - b_n = 2 - 3p_n$. Since $p_n^2 = p_n$ and $p_n^3 = p_n$, the powers of $\delta_n$ are linear in $p_n$:

$$
\delta_n = 2 - 3p_n, \qquad \delta_n^2 = 4 - 12p_n + 9p_n = 4 - 3p_n, \qquad \delta_n^3 = 8 - 9p_n.
$$

2. Expanding $b_{n+1}^3 - b_n^3 = 3b_n^2 \delta_n + 3b_n \delta_n^2 + \delta_n^3$ gives:

$$
b_{n+1}^3 - b_n^3 = 6b_n^2 - 9b_n^2 p_n + 12b_n - 9b_n p_n + 8 - 9p_n.
$$

3. Summing from $n = 0$ to $N - 1$ (with $b_0 = 0$) and multiplying by $2$:

$$
18\sum_{n=0}^{N-1} b_n^2 p_n = 12\sum_{n=0}^{N-1} b_n^2 + 24\sum_{n=0}^{N-1} b_n - 18\sum_{n=0}^{N-1} b_n p_n + 16N - 18O_N - 2b_N^3.
$$

4. Substituting $-18\sum_{n=0}^{N-1} b_n p_n = -12\sum_{n=0}^{N-1} b_n - 6N + 3b_N(b_N - 1)$ (from Theorem 6.1) and $-18O_N = -12N + 6b_N$ yields:

$$
18\sum_{n=0}^{N-1} b_n^2 p_n = 12\sum_{n=0}^{N-1} (b_n^2 + b_n) - 2b_N^3 + 3b_N^2 + 3b_N - 2N. \quad \blacksquare
$$

---

## Part XVIII: The 3-Adic Ballot Sieve, Unconditional Modulo-54 Strengthening of $\Psi(P)$, and Closed-Form Enumeration of Terminal Halting Classes Modulo $3^M$

### 18.1. Unconditional Modulo-27 and Modulo-54 Strengthening at a First Halting Horizon

In Part XII (Theorem 12.2), we proved that if $N = 3P + 1 \ge 4$ ($P \ge 1$) is the **first** step at which $b_N = -1$ (so $b_n \ge 0$ for all $0 \le n < N$), then $p_{N-1} = p_{N-2} = 1$, which implies $a_N \equiv 1 \pmod 9$ and $\Psi(P) = 2(a_{3P+1} - 1) \equiv 0 \pmod{18}$. We now show that extending the non-negativity condition by one further backward step to $b_{N-3} \ge 0$ unconditionally forces a **third** consecutive odd step $p_{N-3} = 1$, multiplying the modulus by $3$.

**Theorem 18.1 (Unconditional Modulo-27 / Modulo-54 First-Halting Sieve)** [Proved]: *Let $N = 3P + 1 \ge 4$ ($P \ge 1$) be the first halting step ($b_n \ge 0$ for $0 \le n < N$ and $b_N = -1$). Then:*
1. **Triple Odd Terminal Suffix:** *The final three steps before $N$ are unconditionally odd:*

$$
(p_{N-3}, p_{N-2}, p_{N-1}) = (1, 1, 1), \qquad (b_{N-3}, b_{N-2}, b_{N-1}, b_N) = (2, 1, 0, -1).
$$

2. **Unconditional Modulo-27 and Modulo-54 Sieve:** *Every first halting state $a_{3P+1}$ ($P \ge 1$) satisfies unconditionally:*

$$
a_{3P+1} \equiv 1 \pmod{27}, \qquad \Psi(P) = 2(a_{3P+1} - 1) \equiv 0 \pmod{54}.
$$

   *Moreover, splitting by the parity of $a_{3P+1}$:*
   - *If halting occurs at the closure of a macro-cycle ($a_{3P+1}$ even, $B_K = -1$), then $m_K \ge 3$ and:*

$$
\Psi(P_K) = 2(a_{3P_K + 1} - 1) \equiv 54 \pmod{108}.
$$

   - *If halting occurs in the interior of an odd run ($a_{3P+1}$ odd, $B_K \le -2$), then:*

$$
\Psi(P) = 2(a_{3P+1} - 1) \equiv 0 \pmod{108}.
$$

*Proof:*
1. By Theorem 12.2, $b_N = -1$ and $b_{N-1}, b_{N-2} \ge 0$ force $p_{N-1} = 1$ ($b_{N-1} = 0$) and $p_{N-2} = 1$ ($b_{N-2} = 1$). At step $N - 3 \ge 1$, we have $b_{N-2} = b_{N-3} + 2 - 3p_{N-3} = 1$. If $p_{N-3} = 0$, then $b_{N-3} = 1 - 2 = -1$, contradicting that $N$ is the **first** step at which the counter reaches $-1$. Therefore $p_{N-3} = 1$ and $b_{N-3} = 2$.
2. Applying the backward chain $3Y_{j+1} = 2Y_j + r_j$ from $Y_0 = a_N$ with $r_0 = p_{N-1} = 1$, $r_1 = p_{N-2} = 1$, $r_2 = p_{N-3} = 1$ yields $27 Y_3 - 8 a_N = 9 r_0 + 6 r_1 + 4 r_2 = 9 + 6 + 4 = 19$. Hence $8(a_N - 1) = 27(Y_3 - 1) \equiv 0 \pmod{27}$, and since $\gcd(8, 27) = 1$, $a_N \equiv 1 \pmod{27}$ and $\Psi(P) = 2(a_N - 1) \equiv 0 \pmod{54}$. Combining with $a_N \bmod 2 \in \{0, 1\}$ gives $\Psi(P) \equiv 54$ or $0 \pmod{108}$. $\blacksquare$

---

### 18.2. The General 3-Adic Ballot Sieve Modulo $3^M$

More generally, at any first halting step $N = 3P + 1 \ge M$, the condition that the counter never hit $-1$ during the last $M$ steps ($b_{N-k} \ge 0$ for $1 \le k \le M$, with $b_N = -1$) restricts the parity suffix $(p_{N-M}, \dots, p_{N-1}) \in \{0, 1\}^M$. By Theorem 9.2 (Injectivity of $\Psi_M$), each suffix $(p_{N-M}, \dots, p_{N-1})$ maps injectively to a unique terminal residue class $X = a_N \bmod 3^M \in \mathcal{R}_M \subset \mathbb{Z}/3^M\mathbb{Z}$.

**Theorem 18.2 (Closed-Form Ballot Enumeration of Admissible Terminal Classes Modulo $3^M$)** [Proved]: *For any depth $M \ge 1$ and any first halting step $N = 3P + 1 \ge M$, let $\mathcal{A}_M \subset \mathcal{R}_M \subset \mathbb{Z}/3^M\mathbb{Z}$ denote the set of terminal residue classes $a_N \bmod 3^M$ compatible with $b_{N-k} \ge 0$ ($1 \le k \le M$) and $b_N = -1$. Then:*
1. **Exact Closed-Form Cardinality $B_M$:** *The number of suffix-admissible residue classes modulo $3^M$ is given in closed form by:*

$$
|\mathcal{A}_M| = B_M := \sum_{k=0}^{\lfloor (M-1)/3 \rfloor} \frac{M - 3k}{M}\binom{M}{k} = \sum_{k=0}^{\lfloor (M-1)/3 \rfloor} \left[\binom{M-1}{k} - 2\binom{M-1}{k-1}\right],
$$

   *where $\binom{M-1}{-1} := 0$.*
2. **Explicit Sieve Table for $1 \le M \le 9$:** *The exact counts $B_M$ and residue classes $\mathcal{A}_M \pmod{3^M}$ for small $M$ are:*

| Depth $M$ | Modulus $3^M$ | Total Cantor classes $2^M$ | Ballot-admissible classes $B_M = \lvert\mathcal{A}_M\rvert$ | Explicit admissible residues $a_N \bmod 3^M$ |
| --- | --- | --- | --- | --- |
| **1** | $3$ | $2$ | **1** | $\{1\}$ |
| **2** | $9$ | $4$ | **1** | $\{1\}$ |
| **3** | $27$ | $8$ | **1** | $\{1\}$ |
| **4** | $81$ | $16$ | **2** | $\{1, 42\}$ |
| **5** | $243$ | $32$ | **3** | $\{1, 123, 184\}$ |
| **6** | $729$ | $64$ | **4** | $\{1, 184, 366, 640\}$ |
| **7** | $2187$ | $128$ | **8** | $\{1, 276, 549, 960, 1095, 1369, 1642, 2053\}$ |
| **8** | $6561$ | $256$ | **13** | $13$ classes out of $6561$ ($99.80\%$ excluded) |
| **9** | $19683$ | $512$ | **19** | $19$ classes out of $19683$ ($99.903\%$ excluded) |

3. **3-Adic Measure Zero:** *In the projective limit $M \to \infty$, the fraction of 3-adic integers in $\mathbb{Z}_3$ whose backward chain satisfies the ballot condition vanishes exponentially: $B_M / 3^M \le (2/3)^M \to 0$.*

*Proof:*
Reading the last $M$ steps backward from $b_N = -1$, let $s_m = b_{N-m}$ for $1 \le m \le M$. Since $p_{N-1} = 1$, we have $s_1 = 0$, and at each backward step $s_{m+1} - s_m = 3p_{N-1-m} - 2 \in \{+1, -2\}$. The condition $s_m \ge 0$ for all $1 \le m \le M$ means that in the word of $M - 1$ backward steps (after the forced step $p_{N-1} = 1$), every prefix has at least twice as many $+1$ steps ($p = 1$) as $-2$ steps ($p = 0$). If the word of length $M$ (including $p_{N-1} = 1$) contains $k$ zeros ($0 \le k \le \lfloor (M-1)/3 \rfloor$) and $M - k$ ones, the classical generalized ballot theorem (Barbier [1887]) states that the number of lattice paths of $M - k$ unit rises and $k$ drops of size $2$ starting at the origin that stay strictly above $-1$ is $\frac{(M - k) - 2k}{M}\binom{M}{k} = \frac{M - 3k}{M}\binom{M}{k} = \binom{M-1}{k} - 2\binom{M-1}{k-1}$. Summing over all $0 \le k \le \lfloor (M-1)/3 \rfloor$ and applying the injectivity of $\Psi_M: \{0, 1\}^M \hookrightarrow \mathbb{Z}/3^M\mathbb{Z}$ (Theorem 9.2) gives $|\mathcal{A}_M| = B_M$. Evaluating $-2^{-M} \sum_{j=0}^{M-1} 3^{M-1-j} 2^j r_j \pmod{3^M}$ on the admissible suffixes produces the explicit table. $\blacksquare$

## Appendix A: Complete Empirical Table of the Trajectory ($n = 0 \dots 20$) [Computationally Verified]

The following table verifies step by step the exact values of $a_n$, its binary representation, its residue modulo $3$ (verifying $a_n \bmod 3 = p_{n-1}$ for all $n \ge 1$), the spin $u_n = 2a_n - 1$, the master variable $Z_n = 3a_n - 2$, the charge $Q_n = 6a_n - b_n - 4$, the counter $b_n$, and the odd-step accumulator $O_n$:

| Step ($n$) | $a_n$ | Binary of $a_n$ | $a_n \bmod 3$ ($= p_{n-1}$) | $p_n$ | $\sigma_n$ | $u_n = 2a_n-1$ | $b_n$ | $O_n$ | $Z_n = 3a_n-2$ | $Q_n = 6a_n-b_n-4$ | Threshold $(2n+1)/3$ |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **0** | 8 | `1000` | 2 *(Seed)* | 0 | $+1$ | 15 | 0 | 0 | 22 | 44 | 0.33 |
| **1** | 12 | `1100` | **0** | 0 | $+1$ | 23 | 2 | 0 | 34 | 66 | **1.00** |
| **2** | 18 | `10010` | **0** | 0 | $+1$ | 35 | 4 | 0 | 52 | 100 | 1.67 |
| **3** | 27 | `11011` | **0** | 1 | $-1$ | 53 | 6 | 0 | 79 | 152 | 2.33 |
| **4** | 40 | `101000` | **1** | 0 | $+1$ | 79 | 5 | 1 | 118 | 231 | **3.00** |
| **5** | 60 | `111100` | **0** | 0 | $+1$ | 119 | 7 | 1 | 178 | 349 | 3.67 |
| **6** | 90 | `1011010` | **0** | 0 | $+1$ | 179 | 9 | 1 | 268 | 527 | 4.33 |
| **7** | 135 | `10000111` | **0** | 1 | $-1$ | 269 | 11 | 1 | 403 | 795 | **5.00** |
| **8** | 202 | `11001010` | **1** | 0 | $+1$ | 403 | 10 | 2 | 604 | 1198 | 5.67 |
| **9** | 303 | `100101111` | **0** | 1 | $-1$ | 605 | 12 | 2 | 907 | 1802 | 6.33 |
| **10** | 454 | `111000110` | **1** | 0 | $+1$ | 907 | 11 | 3 | 1360 | 2709 | **7.00** |
| **11** | 681 | `1010101001` | **0** | 1 | $-1$ | 1361 | 13 | 3 | 2041 | 4069 | 7.67 |
| **12** | 1021 | `1111111101` | **1** | 1 | $-1$ | 2041 | 12 | 4 | 3061 | 6110 | 8.33 |
| **13** | 1531 | `10111111011` | **1** | 1 | $-1$ | 3061 | 11 | 5 | 4591 | 9171 | **9.00** |
| **14** | 2296 | `100011111000` | **1** | 0 | $+1$ | 4591 | 10 | 6 | 6886 | 13762 | 9.67 |
| **15** | 3444 | `110101110100` | **0** | 0 | $+1$ | 6887 | 12 | 6 | 10330 | 20648 | 10.33 |
| **16** | 5166 | `1010000101110` | **0** | 0 | $+1$ | 10331 | 14 | 6 | 15496 | 30978 | **11.00** |
| **17** | 7749 | `1111001000101` | **0** | 1 | $-1$ | 15497 | 16 | 6 | 23245 | 46474 | 11.67 |
| **18** | 11623 | `10110101100111` | **1** | 1 | $-1$ | 23245 | 15 | 7 | 34867 | 69719 | 12.33 |
| **19** | 17434 | `100010000011010` | **1** | 0 | $+1$ | 34867 | 14 | 8 | 52300 | 104586 | **13.00** |
| **20** | 26151 | `110011000100111` | **0** | 1 | $-1$ | 52301 | 16 | 8 | 78451 | 156886 | 13.67 |

## Appendix B: Computational Verification Suite for Selected Identities

### B.1. Scope, Detailed Specification of the 12 Tests, and Limitations

The Python program in Section B.2 executes a **computational verification over a finite range** ($N_{\text{steps}} = 300$ steps and $15$ macro-cycles, plus bit-level Turing machine simulation) employing exact integer and rational arithmetic (`fractions.Fraction` and `decimal.Decimal` with 80 digits of precision).

**Essential Methodological Rule:** A finite computational verification confirms algebraic exactness within the examined range and rules out typographical or indexing errors, but **never substitutes for a general mathematical proof** (which are developed in the text of Parts I through XVIII). Below, the 12 implemented tests are documented in accordance with the 5 audit criteria:

| Test | 1. Identity / Property Verified | 2. Evaluated Range | 3. Computation Performed | 4. Expected Result | 5. Limitations |
| --- | --- | --- | --- | --- | --- |
| **Test 1** *(Part IV)* | Certified value of $\alpha$, bound $(2/3)^{300} < 1.49 \times 10^{-53}$, and formulas $a_n = \lceil \alpha(3/2)^n \rceil$, $a_n - 1 = \lfloor \alpha(3/2)^n \rfloor$. | Truncation at $M = 300$; formulas on $0 \le n \le 200$. | Computes the exact interval $[\alpha_{\min}, \alpha_{\max}] = [\alpha_{300} - (2/3)^{300}, \alpha_{300}]$ and verifies that $\lfloor \alpha_{\min}(3/2)^n \rfloor = \lfloor \alpha_{\max}(3/2)^n \rfloor = a_n - 1$ (the error interval never crosses an integer). | Exact prefix `7.86417726205661897240516852968228138530742425177359` and agreement on $0 \le n \le 200$. | Certifies $50$ decimal places and verifies up to $n = 200$; for $n \to \infty$ general validity follows from the proof of Theorem 4.1(3). |
| **Test 2** *(Parts II and VII)* | Affine Curve, spin variety, character $\chi_4$, **exhaustive modulo 8 table**, **reflection** $\mathcal{J}(a) = 1 - a$, and Boolean Cubic Identity. | $0 \le n < 300$ along the orbit and the $8$ residues $r_8 \in \{0,\dots,7\}$ with $k \in [0, 20]$; reflection on $a \in [-50, 50]$. | Algebraically evaluates each row of the table in Theorem 2.1, verifies $T(1-a) = 1-T(a)$, and checks the cubic identity for triples. | Exact equality across all $8$ residue classes modulo $8$, commutation of $\mathcal{J}$, and triple identity. | Verification over a finite set of integers; the general proof for all $k \in \mathbb{Z}$ is given in Part II. |
| **Test 3** *(Parts V and VI)* | Integral invariants ($44\cdot 3^n, 16\cdot 3^n, 14\cdot 3^n$), **corrected formula** $b_N = 2Z_N - 44 - \sum_{k=0}^{N-1} Z_k = 2Z_N - 66 - \sum_{k=1}^{N-1} Z_k$ (including $N = 1$), and Quadratic Virial. | $1 \le N \le 300$ (with explicit assertion at $N = 1$). | Evaluates both sides of the three integral laws, the two equivalent forms of $b_N$ in terms of $Z_k$, and Theorem 6.1. | At $N = 1$, $2(34)-44-22 = 2 = b_1$, and exact agreement for all $1 \le N \le 300$. | Finite range $N \le 300$; does not evaluate the infinite limit of the series in Section 5.2. |
| **Test 4** *(Parts IX, X, and XII.1)* | Reciprocity $a_n \bmod 3 = p_{n-1}$, injectivity of $\Psi_M$ on $\{0,1\}^M$, inversion $Y_{j+1} = \lceil 2Y_j/3 \rceil$ ($0 \le j \le N-1$), fractional parts $\theta_j(a_N)$, and Autocorrelation ($+4X^2$). | Reciprocity on $1 \le n \le 300$; injectivity on $1 \le M \le 8$; inverse chain at $N \in \{1, 10, 50, 200\}$. | Reconstructs $(Y_0, \dots, Y_N)$ from $X = a_N$, verifies $\lvert\mathcal{R}_M\rvert = 2^M$, and evaluates the linear, quadratic, and fractional invariants. |
| **Test 5** *(Parts III and XII.2)* | The 4 Valuation Laws, Universal Floor Formula, sieve $2(a_{N_i}-1) \equiv 18 \pmod{36}$ for $m_i \ge 2$, and Archimedean formula $\Psi(P) = 2\lfloor \frac{3\alpha}{2}(27/8)^P \rfloor$. | First $15$ macro-cycles of the orbit and $1 \le P \le 60$. | Extracts $(r_i, m_i, c_i, d_i)$ exactly and certifies the Archimedean floor using the interval $[\alpha_{\min}, \alpha_{\max}]$. | Fulfillment of the 4 valuations, remainder in $(0, 1/3)$, and $2(a_{N_i}-1) \equiv 18 \pmod{36}$ whenever $m_i \ge 2$. | Covers a finite number ($15$) of macro-cycles; does not constitute a universal proof of non-halting. |
| **Test 6** *(Part XI)* | Kirchhoff's telescoping equation for $b_N$, **Koopman-Walsh orthogonality and level-lifting** $\mathcal{K}: \mathcal{W}_L \to \mathcal{W}_{L+1}$, and **family of cycles** $x_0^{(m)} = \frac{2^{m-1}}{3^m - 2^m}$ in $\mathbb{Z}_2$. | Kirchhoff at $N \in \{4, 10, 25, 50\}$; Koopman-Walsh at $L \in \{1, 2, 3, 4\}$; cycles at $2 \le m \le 12$. | Numerically evaluates the inner product $\langle w_v^{(L)}, w_{v'}^{(L)} \rangle$, the two-fiber expansion of $\mathcal{K}w_v^{(L)}$, and the $m$ rational steps of $x_0^{(m)}$. | Exact orthogonality, lifting to $\mathcal{W}_{L+1}$, and minimal period $m$ with parity word $(0^{m-1}, 1)$. | Verifies finite dimensions $L \le 4$ and periods $m \le 12$. |
| **Test 7** *(Part XIII)* | Ratios of $F_n(z)$, telescoping product with $(1 - \frac{1}{3a_k})$, and **recurrence** $2F_{n+1}(z) - 3z^2 F_n(z) = -p_n z^{b_n-1}$ **at all three cube roots of unity** $z \in \{1, \omega, \omega^2\}$. | $0 \le n < 150$ in the exact cyclotomic ring $\mathbb{Q}(\omega) \cong \mathbb{Q}[x]/(x^2 + x + 1)$. | Represents each element of $\mathbb{Q}(\omega)$ as a rational pair $(u + v\omega)$ with $\omega^2 = -1 - \omega$ and verifies the exact identity for $z = 1, \omega, \omega^2$. | Remainder identically $(0, 0) \in \mathbb{Q}(\omega)$ at all three cube roots of unity. | Verification up to $n = 150$; the infinite product is evaluated on its finite partial products. |
| **Test 8** *(Part XIV)* | Base-$3$ carry transducer, population laws $U_{n+1}, D_{n+1}, \Delta\Sigma_3$, and **explicit verification of the Universal Tail** $a_{t+m+1} \bmod 3^m = \frac{3^m+3}{2}$. | Transducer on $0 \le n < 200$; Universal Tail at all odd-run closures with $m_i \ge 2$ within the first $15$ macro-cycles and for synthetic seeds $3^m d + 1$ ($2 \le m \le 10$). | Decomposes $a_n$ in base $3$, executes the phase scan, and checks the last $m$ ternary digits of $a_{t+m+1}$. | Exact agreement of $U_{n+1}, D_{n+1}, \Sigma_3$ and ternary suffix $1^{m-2}20_3$. | Verifies the first $200$ steps and runs up to $m = 10$. |
| **Test 9** *(Part XV)* | Quadratic telescoping of $\Delta t_n$, bit-level TM step match, and **Cumulative Turing Machine Action Law** $6T_N + 3\sum a_n^2 - 4\sum b_n = 6a_N^2 + b_N(2b_N+9) - 32N - 318$. | Direct bit-level TM simulation for $0 \le N \le 12$; Action Law for $1 \le N \le 300$. | Simulates `1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA` step-by-step on tape and compares with Theorem 15.1 and Theorem 15.2. | Exact bit-for-bit match of $T_N$ with the TM and exact equality of Action Law for all $1 \le N \le 300$. | Finite verification up to $N = 300$; general validity proved in Theorems 15.1 and 15.2. |
| **Test 10** *(Part XVI)* | Explicit 2-adic inverse $\Phi_L^{-1}$, **Fuss-Catalan halting cylinder count** $C_P^{(3)} = \frac{1}{2P+1}\binom{3P}{P}$, and **Dual Integer Fibonacci Conservation Laws**. | Inverse map on $1 \le L \le 10$; Fuss-Catalan on $0 \le P \le 3$ ($N \le 10$); Fibonacci laws on $1 \le N \le 300$. | Enumerates all $2^L$ residue classes, counts first-halting seeds modulo $2^{3P+1}$, and evaluates both Fibonacci sums. | Exact bijection, exact counts $C_P^{(3)} = 1, 1, 3, 12$, and exact Fibonacci conservation at every step. | Finite $L \le 10, P \le 3, N \le 300$; infinite Haar measure $\varphi^{-1}$ proved via Lagrange's cubic in Theorem 16.2. |
| **Test 11** *(Part XVII)* | **Tri-Local Adelic Bridge Identity** $\mathcal{S}_N(p) = 8 - (2/3)^N a_N$, 2-adic divisibility $2^N \mid (8 - \mathcal{S}_N(p))$, and **Cubic Virial Theorem**. | $1 \le N \le 300$. | Computes rational partial sums $\mathcal{S}_N(p)$, checks 2-adic valuation of the numerator of $8 - \mathcal{S}_N(p)$, and verifies Theorem 17.2. | Exact rational equality, 2-adic convergence to $8$, and exact third-order moment balance across all $N$. | Finite range $N \le 300$; general proof in Theorems 17.1 and 17.2. |
| **Test 12** *(Part XVIII)* | **Unconditional mod 27 / mod 54 sieve** and **Closed-Form 3-Adic Ballot Sieve** $\lvert\mathcal{A}_M\rvert = B_M$ modulo $3^M$. | Suffix depths $1 \le M \le 9$ (moduli up to $3^9 = 19683$). | Generates all ballot-admissible parity suffixes of length $M$, maps them modulo $3^M$, and compares against the closed-form formula $B_M$. | Exact counts $(1, 1, 1, 2, 3, 4, 8, 13, 19)$ and exact residue sets $\{1\} \pmod{27}$, $\{1, 42\} \pmod{81}$, $\{1, 123, 184\} \pmod{243}$, $\{1, 184, 366, 640\} \pmod{729}$. | Finite suffix depth $M \le 9$; general ballot theorem proved for all $M \ge 1$ in Theorem 18.2. |

### B.2. Audited and Verified Python Source Code

```python
from collections import defaultdict
from fractions import Fraction
from decimal import Decimal, getcontext
from math import comb

# Configure 80 decimal digits of precision for Archimedean verifications
getcontext().prec = 80

def v_p(n: int, p: int) -> int:
    """Computes the exact p-adic valuation of a non-zero integer n."""
    if n == 0:
        raise ValueError("v_p(0) is infinite")
    k = 0
    while n % p == 0:
        n //= p
        k += 1
    return k

def base3_digits_and_phases(val: int):
    """
    Decomposes an integer val >= 1 in base 3 (from units k=0 up to leading digit k=L)
    and executes the left-to-right phase scan (Definition 14.0).
    """
    taus = []
    temp = val
    while temp > 0:
        taus.append(temp % 3)
        temp //= 3
    L = len(taus) - 1

    # Left-to-right scan: c_{L+1} = 0, c_k = (c_{k+1} + tau_k) mod 2
    c = [0] * (L + 2)
    for k in range(L, -1, -1):
        c[k] = (c[k + 1] + taus[k]) % 2

    V0 = sum(1 for k in range(L + 1) if taus[k] == 0 and c[k] == 0)
    V1 = sum(1 for k in range(L + 1) if taus[k] == 0 and c[k] == 1)
    D0 = sum(1 for k in range(L + 1) if taus[k] == 2 and c[k] == 0)
    D1 = sum(1 for k in range(L + 1) if taus[k] == 2 and c[k] == 1)
    U = sum(1 for k in range(L + 1) if taus[k] == 1)
    K = sum(1 for k in range(L + 1) if c[k + 1] == 1)
    sigma3 = U + 2 * (D0 + D1)
    return U, D0, D1, V0, V1, K, sigma3, c[0]

def cyclotomic_mul(x, y):
    """Exact multiplication in Q(omega) with omega^2 = -1 - omega: (a + b*w)*(c + d*w)."""
    a, b = x
    c, d = y
    return (a * c - b * d, a * d + b * c - b * d)

def cyclotomic_pow_unit(root_idx: int, exp: int):
    """
    Evaluates z^exp in Q(omega) for the three cube roots of unity:
    root_idx = 0 -> z = 1 = (1, 0)
    root_idx = 1 -> z = omega = (0, 1)
    root_idx = 2 -> z = omega^2 = (-1, -1)
    """
    r = (root_idx * exp) % 3
    if r == 0:
        return (Fraction(1), Fraction(0))
    elif r == 1:
        return (Fraction(0), Fraction(1))
    else:
        return (Fraction(-1), Fraction(-1))

def verify_antihydra_selected_identities(N_steps: int = 300, num_ciclos: int = 15):
    # 0. Generation of the exact integer trajectory up to N_steps
    a = [8]
    b = [0]
    p = []
    O = [0]
    E = [0]

    for n in range(N_steps):
        pn = a[n] % 2
        p.append(pn)
        a_next = (3 * a[n] - pn) // 2
        b_next = b[n] + 2 - 3 * pn
        a.append(a_next)
        b.append(b_next)
        O.append(O[n] + pn)
        E.append(E[n] + (1 - pn))

    # =========================================================================
    # TEST 1 (Part IV): Exact value of alpha at M=300, bound < 1.49e-53,
    # and interval certification [alpha_min, alpha_max] for ceiling and floor
    # =========================================================================
    alpha_max = Fraction(1 << N_steps, 3 ** N_steps) * a[N_steps]
    error_bound = Fraction(1 << N_steps, 3 ** N_steps)
    alpha_min = alpha_max - error_bound

    # Verify that (2/3)^300 approx 1.4880663e-53 < 1.49e-53
    err_dec = Decimal(error_bound.numerator) / Decimal(error_bound.denominator)
    assert Decimal("1.488e-53") < err_dec < Decimal("1.49e-53"), f"Incorrect bound: {err_dec}"

    alpha_min_dec = Decimal(alpha_min.numerator) / Decimal(alpha_min.denominator)
    alpha_max_dec = Decimal(alpha_max.numerator) / Decimal(alpha_max.denominator)
    expected_prefix = "7.86417726205661897240516852968228138530742425177359"
    assert str(alpha_min_dec).startswith(expected_prefix), f"Min mismatch: {alpha_min_dec}"
    assert str(alpha_max_dec).startswith(expected_prefix), f"Max mismatch: {alpha_max_dec}"

    # Verify that on [alpha_min, alpha_max] the interval multiplied by (3/2)^n
    # never crosses an integer for 0 <= n <= 200, certifying ceiling and floor for the limit alpha
    for n in range(201):
        scale = Fraction(3 ** n, 1 << n)
        low_val = alpha_min * scale
        high_val = alpha_max * scale
        floor_low = low_val.numerator // low_val.denominator
        floor_high = high_val.numerator // high_val.denominator
        assert floor_low == floor_high == a[n] - 1, f"Interval crosses an integer at n={n}"
        assert floor_low + 1 == a[n], f"Certified ceiling failure at n={n}"

    # =========================================================================
    # TEST 2 (Parts II and VII): Affine Curve, Spin u_n, Exhaustive mod 8 table,
    # Reflection J(a) = 1 - a, and Boolean Cubic Identity
    # =========================================================================
    for n in range(N_steps):
        assert (3 * a[n] - 2 * a[n + 1]) * (3 * a[n] - 2 * a[n + 1] - 1) == 0
        un = 2 * a[n] - 1
        un_next = 2 * a[n + 1] - 1
        sigma_n = 1 - 2 * p[n]
        assert 2 * un_next - 3 * un == sigma_n
        assert (2 * un_next - 3 * un) ** 2 == 1
        assert (un + sigma_n) % 4 == 0
        if n < N_steps - 1:
            assert p[n + 1] == (p[n] + ((a[n] % 4) // 2)) % 2

    # Exhaustive verification of the 8 residue classes modulo 8 (Theorem 2.1)
    expected_mod8_table = {
        0: (15, 0, +1, 0, 0, (0, 0, 0)),
        1: (1, 1, -1, 0, 1, (1, 1, 1)),
        2: (3, 0, +1, 4, 3, (0, 1, 0)),
        3: (5, 1, -1, 4, 0, (1, 0, 0)),
        4: (7, 0, +1, 0, 2, (0, 0, 1)),
        5: (9, 1, -1, 0, 3, (1, 1, 0)),
        6: (11, 0, +1, 4, 1, (0, 1, 1)),
        7: (13, 1, -1, 4, 2, (1, 0, 1)),
    }
    for r8, (u_mod16, p0, sig0, usig_mod8, a1_mod4, trip) in expected_mod8_table.items():
        for k in range(20):
            a0_val = 8 * k + r8
            u0_val = 2 * a0_val - 1
            p0_val = a0_val % 2
            sig0_val = 1 - 2 * p0_val
            a1_val = (3 * a0_val - p0_val) // 2
            p1_val = a1_val % 2
            a2_val = (3 * a1_val - p1_val) // 2
            p2_val = a2_val % 2
            assert u0_val % 16 == u_mod16
            assert (p0_val, sig0_val) == (p0, sig0)
            assert (u0_val + sig0_val) % 8 == usig_mod8
            assert a1_val % 4 == a1_mod4
            assert (p0_val, p1_val, p2_val) == trip

    # Verification of the reflection J(x) = 1 - x: T(1 - x) == 1 - T(x) (Theorem 2.3)
    for x_val in range(-50, 51):
        T_x = (3 * x_val - (x_val % 2)) // 2
        J_x = 1 - x_val
        T_Jx = (3 * J_x - (J_x % 2)) // 2
        assert T_Jx == 1 - T_x, f"Reflection J failure for x={x_val}"

    for n in range(N_steps - 3):
        un = 2 * a[n] - 1
        un3 = 2 * a[n + 3] - 1
        s0, s1, s2 = 1 - 2 * p[n], 1 - 2 * p[n + 1], 1 - 2 * p[n + 2]
        W_sigma = 8 * un3 - 27 * un
        assert W_sigma == 9 * s0 + 6 * s1 + 4 * s2
        assert W_sigma ** 2 == 133 + 108 * s0 * s1 + 72 * s0 * s2 + 48 * s1 * s2
        sgn_W = 1 if W_sigma > 0 else -1
        assert s0 + s1 + s2 == 2 * sgn_W + (s0 * s1 * s2)

    # =========================================================================
    # TEST 3 (Parts V and VI): Integral Invariants, Corrected Identity for b_N
    # in terms of Z_k (including N=1), and Quadratic Virial Theorem
    # =========================================================================
    Z = [3 * x - 2 for x in a]
    # Explicit check at N = 1
    assert Z[0] == 22 and Z[1] == 34 and b[1] == 2
    assert 2 * Z[1] - 44 - sum(Z[0:1]) == 2 == b[1]
    assert 2 * Z[1] - 66 - sum(Z[1:1]) == 2 == b[1]

    suma_b = suma_O = suma_E = 0
    acum_b = acum_bp = 0
    acum_Z_from_0 = 0
    for n in range(1, N_steps + 1):
        if n >= 2:
            suma_b = 3 * suma_b + (1 << (n - 1)) * b[n - 1]
            suma_O = 3 * suma_O + (1 << (n - 1)) * O[n - 1]
            suma_E = 3 * suma_E + (1 << (n - 1)) * E[n - 1]
        assert 44 * (3 ** n) + suma_b == (1 << n) * (6 * a[n] - b[n] - 4)
        assert 16 * (3 ** n) == (1 << n) * (2 * a[n] + O[n]) + suma_O
        assert 14 * (3 ** n) + suma_E == (1 << n) * (2 * a[n] - E[n] - 2)

        # Verify both corrected forms of b_n in terms of Z_k
        acum_Z_from_0 += Z[n - 1]
        acum_Z_from_1 = acum_Z_from_0 - Z[0]
        assert b[n] == 2 * Z[n] - 44 - acum_Z_from_0, f"Failure in b_n with Z_0 at n={n}"
        assert b[n] == 2 * Z[n] - 66 - acum_Z_from_1, f"Failure in b_n with -66 at n={n}"

        acum_b += b[n - 1]
        acum_bp += b[n - 1] * p[n - 1]
        assert 6 * acum_bp == 4 * acum_b + 2 * n - b[n] * (b[n] - 1)

    # =========================================================================
    # TEST 4 (Parts IX, X, and XII.1): Reciprocity mod 3, Injectivity of R_M,
    # Chain Y_j (0 <= j <= N-1), Fractional Parts, and Autocorrelation
    # =========================================================================
    for n in range(1, N_steps + 1):
        assert a[n] % 3 == p[n - 1]
        assert a[n] % 3 != 2

    # Verify injectivity of Psi_M and cardinality |R_M| = 2^M for 1 <= M <= 8
    for M_lvl in range(1, 9):
        mod3M = 3 ** M_lvl
        inv_neg2M = pow(-(1 << M_lvl), -1, mod3M)
        res_set = set()
        for mask in range(1 << M_lvl):
            W_val = sum((3 ** (M_lvl - 1 - i)) * (1 << i) * ((mask >> i) & 1) for i in range(M_lvl))
            assert 0 <= W_val <= mod3M - (1 << M_lvl)
            res_set.add((inv_neg2M * W_val) % mod3M)
        assert len(res_set) == (1 << M_lvl), f"Cardinality |R_M| failure at M={M_lvl}"

    for N_test in (1, 10, 50, 200):
        X = a[N_test]
        Y = [X]
        for j in range(N_test):  # j ranges over 0, 1, ..., N_test - 1
            Y_next = (2 * Y[-1] + 2) // 3
            Y.append(Y_next)
            assert Y_next == a[N_test - 1 - j]
            assert 3 * Y_next - 2 * Y[-2] == (Y[-2] % 3)

        assert len(Y) == N_test + 1 and Y[N_test] == 8
        assert 24 - 2 * X + sum(Y[1:N_test]) == O[N_test]

        autocorr_lhs = (
            576
            + 4 * (X ** 2)
            + 13 * sum(Y[j] ** 2 for j in range(1, N_test))
            - 12 * sum(Y[j] * Y[j + 1] for j in range(N_test))
        )
        assert autocorr_lhs == O[N_test]

        theta_sum = sum(Fraction((-((1 << j) * X)) % (3 ** j), 3 ** j) for j in range(1, N_test))
        theta_N = Fraction((-((1 << N_test) * X)) % (3 ** N_test), 3 ** N_test)
        assert 3 * theta_N + theta_sum == O[N_test]

    # =========================================================================
    # TEST 5 (Parts III and XII.2): Macro-Cycles, 4 Valuation Laws,
    # Universal Floor Formula, mod 36 Sieve, and Archimedean Formula for Psi(P)
    # =========================================================================
    c, r, B_ciclo, P_acum, M_acum = 1, 3, 0, 0, 0
    ciclos = []
    for i in range(1, num_ciclos + 1):
        P_acum += r
        t_idx = P_acum + M_acum
        val_impar = (3 ** r) * c - 1
        m = v_p(val_impar, 2)
        d = val_impar >> m
        B_ciclo += 2 * r - m
        M_acum += m
        N_idx = P_acum + M_acum

        val_par = (3 ** m) * d + 1
        assert val_par == a[N_idx]
        r_next = v_p(val_par, 2)
        c_next = val_par >> r_next

        assert r == v_p((1 << m) * d + 1, 3)
        assert m == v_p((1 << r_next) * c_next - 1, 3)
        assert (((1 << m) * d + 1) % 9) in (0, 6)

        if m >= 2:
            psi_val = 2 * (val_par - 1)
            assert psi_val == 2 * (3 ** m) * d
            assert psi_val % 36 == 18

        ciclos.append((i, r, m, P_acum, c, d, B_ciclo, t_idx, N_idx))
        if i >= 2:
            _, r_prev, m_prev, _, _, d_prev, _, _, _ = ciclos[-2]
            frac = Fraction((1 << (r + m)) * d, 3 ** (m_prev + r))
            assert int(frac) == d_prev
            parte_frac = frac - d_prev
            assert parte_frac == Fraction((3 ** r) - (1 << r), 3 ** (m_prev + r))
            assert 0 < parte_frac < Fraction(1, 3)

        r, c = r_next, c_next

    # Certify by interval that Psi(P) = 2*(a_{3P+1}-1) = 2*floor((3*alpha/2)*(27/8)^P)
    for P_val in range(1, 60):
        N_idx = 3 * P_val + 1
        psi_exact = 2 * (a[N_idx] - 1)
        factor_P = Fraction(3, 2) * Fraction(27 ** P_val, 8 ** P_val)
        floor_min = (alpha_min * factor_P).numerator // (alpha_min * factor_P).denominator
        floor_max = (alpha_max * factor_P).numerator // (alpha_max * factor_P).denominator
        assert 2 * floor_min == 2 * floor_max == psi_exact

    # =========================================================================
    # TEST 6 (Part XI): Kirchhoff's Formula, Koopman-Walsh Orthogonality
    # and Level-Lifting, and Infinite Family of Cycles x_0^{(m)} in Z_2
    # =========================================================================
    # 6a. Verify the family of cycles x_0^{(m)} = 2^{m-1} / (3^m - 2^m) for 2 <= m <= 12
    for m_per in range(2, 13):
        denom = (3 ** m_per) - (1 << m_per)
        assert denom % 2 == 1  # Odd denominator -> belongs to Z_2
        x_curr = Fraction(1 << (m_per - 1), denom)
        visited = []
        parities = []
        for step in range(m_per):
            assert 0 < x_curr < 1  # Non-integer
            visited.append(x_curr)
            # Parity in Z_2 = parity of the numerator (since denom is odd)
            p_curr = x_curr.numerator % 2
            parities.append(p_curr)
            if p_curr == 0:
                x_curr = Fraction(3, 2) * x_curr
            else:
                x_curr = (3 * x_curr - 1) / 2
        assert x_curr == visited[0], f"Cycle did not close for m={m_per}"
        assert parities == [0] * (m_per - 1) + [1], f"Incorrect parity word at m={m_per}"
        assert len(set(visited)) == m_per, f"Minimal period is not {m_per}"

    # 6b. Verify orthogonality of W_L and lifting K(W_L) subset W_{L+1} for L in {1, 2, 3, 4}
    def w_wavelet(L, v, a_val):
        if (a_val % (1 << (L - 1))) != v:
            return 0
        bit = ((a_val % (1 << L)) >> (L - 1)) & 1
        return -1 if bit else 1

    for L in range(1, 5):
        mod_2L = 1 << L
        mod_2L1 = 1 << (L + 1)
        dim_W = 1 << (L - 1)
        # Orthogonality in H_L
        for v1 in range(dim_W):
            for v2 in range(dim_W):
                inner_num = sum(w_wavelet(L, v1, x) * w_wavelet(L, v2, x) for x in range(mod_2L))
                if v1 == v2:
                    assert inner_num == 2  # 2 / 2^L = 2^{-(L-1)}
                else:
                    assert inner_num == 0

        # Exact level-lifting K w_v^{(L)} = eps_0 w_{s_0}^{(L+1)} + eps_1 w_{s_1}^{(L+1)}
        for v in range(dim_W):
            mod_prev = 1 << (L - 1)
            inv3 = pow(3, -1, mod_prev)
            s0 = 2 * ((inv3 * v) % mod_prev)
            s1 = 2 * ((inv3 * (v - 1)) % mod_prev) + 1
            T_s0 = (3 * s0) // 2
            T_s1 = (3 * s1 - 1) // 2
            eps0 = w_wavelet(L, v, T_s0)
            eps1 = w_wavelet(L, v, T_s1)
            assert eps0 in (-1, 1) and eps1 in (-1, 1)
            for x in range(mod_2L1):
                Tx = (3 * x - (x % 2)) // 2
                lhs_koopman = w_wavelet(L, v, Tx)
                rhs_wavelet = eps0 * w_wavelet(L + 1, s0, x) + eps1 * w_wavelet(L + 1, s1, x)
                assert lhs_koopman == rhs_wavelet, f"Koopman-Walsh lifting failure at L={L}, v={v}"

    # 6c. Kirchhoff's telescoping equation for b_N
    for N_k in (4, 10, 25, 50):
        M_level = a[N_k].bit_length() + 2
        def C_count(res, L_lvl):
            mod = 1 << L_lvl
            return sum(1 for n in range(N_k) if a[n] % mod == res)

        sum_s0 = 0
        sum_ind = 0
        for L_lvl in range(2, M_level):
            s0_1_L = 2 * (pow(3, -1, 1 << L_lvl) % (1 << L_lvl))
            sum_s0 += C_count(s0_1_L, L_lvl + 1)
            if a[N_k] % (1 << L_lvl) == 1:
                sum_ind += 1

        b_kirchhoff = 2 * C_count(0, 2) + C_count(3, 2) - sum_s0 + 2 * p[N_k] + sum_ind
        assert b_kirchhoff == b[N_k], f"Kirchhoff's formula failure at N={N_k}"

    # =========================================================================
    # TEST 7 (Part XIII): Telescoping Product and Recurrence 2*F_{n+1} - 3*z^2*F_n
    # at ALL THREE cube roots of unity z in {1, omega, omega^2} in Q(omega)
    # =========================================================================
    prod_impar = Fraction(1, 1)
    for n in range(150):
        ratio_a = Fraction(a[n + 1], a[n])
        if p[n] == 0:
            assert ratio_a == Fraction(3, 2)
        else:
            assert ratio_a == Fraction(3 * a[n] - 1, 2 * a[n])
            assert ratio_a == Fraction(3, 2) * (1 - Fraction(1, 3 * a[n]))
            prod_impar *= (1 - Fraction(1, 3 * a[n]))
        assert Fraction(a[n + 1], 8) == Fraction(3 ** (n + 1), 1 << (n + 1)) * prod_impar

        # Verify 2*F_{n+1}(z) - 3*z^2*F_n(z) == -p_n * z^{b_n - 1} for root_idx in (0, 1, 2)
        for root_idx in (0, 1, 2):
            z_bn = cyclotomic_pow_unit(root_idx, b[n])
            z_bn1 = cyclotomic_pow_unit(root_idx, b[n + 1])
            z_sq = cyclotomic_pow_unit(root_idx, 2)
            z_bn_minus_1 = cyclotomic_pow_unit(root_idx, b[n] - 1)

            Fn = (a[n] * z_bn[0], a[n] * z_bn[1])
            Fn1 = (a[n + 1] * z_bn1[0], a[n + 1] * z_bn1[1])
            z2_Fn = cyclotomic_mul(z_sq, Fn)

            lhs_0 = 2 * Fn1[0] - 3 * z2_Fn[0]
            lhs_1 = 2 * Fn1[1] - 3 * z2_Fn[1]
            rhs_0 = -p[n] * z_bn_minus_1[0]
            rhs_1 = -p[n] * z_bn_minus_1[1]
            assert (lhs_0, lhs_1) == (rhs_0, rhs_1), f"Cube root {root_idx} failure at n={n}"

    # =========================================================================
    # TEST 8 (Part XIV): Base-3 Transducer, Populations U_n, D_n, V_n,
    # and Explicit Verification of the Universal Tail (3^m + 3)/2
    # =========================================================================
    for n in range(200):
        U_n, D0_n, D1_n, V0_n, V1_n, K_n, sig_n, c0_n = base3_digits_and_phases(a[n])
        U_next, D0_next, D1_next, _, _, _, sig_next, _ = base3_digits_and_phases(a[n + 1])
        D_next = D0_next + D1_next
        assert c0_n == p[n]
        assert D_next == (U_n - p[n]) // 2 + D1_n == K_n - V1_n
        assert U_next == D0_n + V1_n + p[n]
        assert sig_next - sig_n == V1_n - D0_n

    # Verify the Universal Tail after each odd-run closure with m_i >= 2 along the actual orbit
    for _, _, m_val, _, _, d_val, _, _, N_idx in ciclos:
        if m_val >= 2 and N_idx + 1 <= N_steps:
            assert a[N_idx] == (3 ** m_val) * d_val + 1
            tail_expected = ((3 ** m_val) + 3) // 2
            assert a[N_idx + 1] % (3 ** m_val) == tail_expected
            assert a[N_idx + 1] == (3 ** m_val) * ((3 * d_val - 1) // 2) + tail_expected

    # Verify the Universal Tail for all 2 <= m <= 10 and odd cores d
    for m_val in range(2, 11):
        tail_expected = ((3 ** m_val) + 3) // 2
        for d_val in (1, 3, 5, 13, 85, 1937):
            state_even = (3 ** m_val) * d_val + 1
            state_next = (3 * state_even) // 2
            assert state_next % (3 ** m_val) == tail_expected

    # =========================================================================
    # TEST 9 (Part XV): Quadratic Telescoping of dt_n, Bit-Level TM Match,
    # and Cumulative Turing Machine Action Law for T_N
    # =========================================================================
    tm_table = {
        ('A', 0): (1, 1, 'B'), ('A', 1): (1, 1, 'A'),
        ('B', 0): (0, -1, 'C'), ('B', 1): (1, -1, 'E'),
        ('C', 0): (1, -1, 'D'), ('C', 1): (1, -1, 'C'),
        ('D', 0): (1, -1, 'A'), ('D', 1): (0, -1, 'B'),
        ('E', 0): (1, -1, 'F'), ('E', 1): (1, 1, 'E'),
        ('F', 0): (1, 0, 'HALT'), ('F', 1): (0, 1, 'A'),
    }
    tape = defaultdict(int)
    head = min_i = max_i = t_sim = 0
    st_tm = 'A'
    T_sim = []
    while len(T_sim) <= 12:
        v = tape[head]
        w, mv, st_tm = tm_table[(st_tm, v)]
        tape[head] = w
        if head < min_i: min_i = head
        if head > max_i: max_i = head
        head += mv
        t_sim += 1
        if head > max_i: max_i = head
        if st_tm == 'E' and head == max_i and tape[head] == 0:
            cur = min_i
            while cur < head and tape[cur] == 0: cur += 1
            o1 = 0
            while cur < head and tape[cur] == 1: o1 += 1; cur += 1
            z1 = 0
            while cur < head and tape[cur] == 0: z1 += 1; cur += 1
            o2 = 0
            while cur < head and tape[cur] == 1: o2 += 1; cur += 1
            if cur == head and ((z1 == 0 and o2 == 0 and o1 >= 4) or (z1 == 1 and o2 >= 4)):
                T_sim.append(t_sim)
    assert T_sim[0] == 11

    T_calc = 11
    sum_a2 = 0
    sum_b_act = 0
    for N_act in range(1, N_steps + 1):
        n_idx = N_act - 1
        dt_n = (a[n_idx + 1] ** 2) - Fraction(3, 2) * (a[n_idx] ** 2) + 2 * (1 - p[n_idx]) * b[n_idx] - 1 - Fraction(11, 2) * p[n_idx]
        assert dt_n.denominator == 1
        T_calc += int(dt_n)
        sum_a2 += a[n_idx] ** 2
        sum_b_act += b[n_idx]
        if N_act <= 12:
            assert T_calc == T_sim[N_act]
        assert 6 * T_calc + 3 * sum_a2 - 4 * sum_b_act == 6 * (a[N_act] ** 2) + b[N_act] * (2 * b[N_act] + 9) - 32 * N_act - 318

    # =========================================================================
    # TEST 10 (Part XVI): 2-Adic Inverse Map, Fuss-Catalan Ballot Count,
    # and Dual Integer Fibonacci Conservation Laws
    # =========================================================================
    for L_inv in range(1, 11):
        mod2L = 1 << L_inv
        for x0 in range(mod2L):
            curr = x0
            w_bits = []
            for _ in range(L_inv):
                pk = curr % 2
                w_bits.append(pk)
                curr = (3 * curr - pk) // 2
            inv_x0 = sum(pow(3, -(k + 1), mod2L) * (1 << k) * w_bits[k] for k in range(L_inv)) % mod2L
            assert inv_x0 == x0

    for P_fc in range(4):
        N_halt = 3 * P_fc + 1
        halt_cnt = 0
        for x0 in range(1 << N_halt):
            curr, b_curr, first_hit = x0, 0, None
            for step in range(1, N_halt + 1):
                pk = curr % 2
                curr = (3 * curr - pk) // 2
                b_curr += 2 - 3 * pk
                if b_curr == -1:
                    first_hit = step
                    break
            if first_hit == N_halt:
                halt_cnt += 1
        assert halt_cnt == comb(3 * P_fc, P_fc) // (2 * P_fc + 1)

    def fib_int(m: int) -> int:
        if m == 0: return 0
        if m > 0:
            f0, f1 = 0, 1
            for _ in range(m): f0, f1 = f1, f0 + f1
            return f0
        return ((-1) ** (-m + 1)) * fib_int(-m)

    sum_fib1 = sum_fib2 = 0
    for n_idx in range(N_steps):
        sgn_f = (2 * p[n_idx] - 1) * ((-1) ** (b[n_idx] + 1))
        sum_fib1 += sgn_f * fib_int(b[n_idx] + 1)
        sum_fib2 += sgn_f * fib_int(b[n_idx] + 2)
        N_f = n_idx + 1
        assert ((-1) ** b[N_f]) * fib_int(b[N_f]) == sum_fib1
        assert ((-1) ** b[N_f]) * fib_int(b[N_f] + 1) - 1 == sum_fib2

    # =========================================================================
    # TEST 11 (Part XVII): Tri-Local Adelic Bridge Series S_N(p)
    # and the Cubic Virial Theorem
    # =========================================================================
    sum_b1 = sum_b2 = sum_b2p = 0
    S_N = Fraction(0, 1)
    for n_idx in range(N_steps):
        S_N += Fraction(1 << n_idx, 3 ** (n_idx + 1)) * p[n_idx]
        sum_b1 += b[n_idx]
        sum_b2 += b[n_idx] ** 2
        sum_b2p += (b[n_idx] ** 2) * p[n_idx]
        N_c = n_idx + 1
        assert S_N == 8 - Fraction(1 << N_c, 3 ** N_c) * a[N_c]
        assert (8 - S_N).numerator % (1 << N_c) == 0
        assert 18 * sum_b2p == 12 * (sum_b2 + sum_b1) - b[N_c] * (2 * (b[N_c] ** 2) - 3 * b[N_c] - 3) - 2 * N_c

    # =========================================================================
    # TEST 12 (Part XVIII): Closed-Form 3-Adic Ballot Sieve B_M and
    # Terminal Halting Residue Classes Modulo 3^M (1 <= M <= 9)
    # =========================================================================
    for M_sieve in range(1, 10):
        states = [(0, (1,))]
        for _ in range(M_sieve - 1):
            nxt = []
            for b_val, suf in states:
                nxt.append((b_val + 1, (1,) + suf))
                if b_val >= 2:
                    nxt.append((b_val - 2, (0,) + suf))
            states = nxt
        mod3M = 3 ** M_sieve
        inv_neg2M = pow(-(1 << M_sieve), -1, mod3M)
        adm_res = sorted(
            (inv_neg2M * sum((3 ** (M_sieve - 1 - j)) * (1 << j) * suf[M_sieve - 1 - j] for j in range(M_sieve))) % mod3M
            for _, suf in states
        )
        expected_BM = sum(
            comb(M_sieve - 1, k) - (2 * comb(M_sieve - 1, k - 1) if k >= 1 else 0)
            for k in range((M_sieve - 1) // 3 + 1)
        )
        assert len(adm_res) == len(set(adm_res)) == expected_BM
        if M_sieve == 3: assert adm_res == [1]
        elif M_sieve == 4: assert adm_res == [1, 42]
        elif M_sieve == 5: assert adm_res == [1, 123, 184]
        elif M_sieve == 6: assert adm_res == [1, 184, 366, 640]

    print(f"[OK] All 12 test blocks passed without errors (N={N_steps} steps, {num_ciclos} macro-cycles).")
    print(f"     Certified constant: alpha = {str(alpha_min_dec)[:56]}...")
    print(f"     Bound at M=300: (2/3)^300 = {str(err_dec)[:22]}e-53 < 1.49e-53")
    print(f"     State at N={N_steps}: a_N = {a[N_steps]}, b_N = {b[N_steps]}, O_N = {O[N_steps]}")

if __name__ == "__main__":
    verify_antihydra_selected_identities(300, 15)
```

## Appendix C: Final Mathematical Audit Report and Exhaustive Change Log

This appendix documents both the prior structural corrections and the four final corrections concerning mathematical rigor, notation, and code:

### C.1. Mathematical, Code, and Notational Errors Corrected

1. **Correction of `IndentationError` in the Python validation suite (Appendix B, Section B.2):**

   - Corrected the indentation of the line `a0_val = 8 * k + r8` inside the loop `for k in range(20):` of `TEST 2` (changing from 13 to 12 spaces), allowing the script to compile and cleanly pass all 8 computational test blocks.
2. **Harmonization of the statement and proof of Theorem 8.1(2) (Part VIII, Section 8.2):**

   - Corrected the statement of Theorem 8.1(2) to distinguish precisely between evaluation at $m = 0$, where $(\Delta^L a)_0 = \alpha(1/2)^L + (\Delta^L R)_0$, and evaluation along the diagonal $L = m$ at step $m$, where the leading term decays with base $3/4 < 1$: $(\Delta^m a)_m = \alpha(3/4)^m + (\Delta^m R)_m$.
3. **Rigorous case distinction in Theorem 12.2 (Part XII, Section 12.2):**

   - Rigorously separated the Diophantine sieve at the closure of any macro-cycle with $m_K \ge 2$ —where $2(a_{N_K} - 1) = 2 \cdot 3^{m_K} d_K \equiv 18 \pmod{36}$ unconditionally— from the analysis of a general first halting step $N = 3P + 1 \ge 4$ ($b_N = -1$). In the latter, the condition $p_{N-2} = p_{N-1} = 1$ always guarantees that $9 \mid (a_N - 1)$ and $\Psi(P) = 2(a_{3P+1} - 1) \equiv 0 \pmod{18}$, splitting into $\Psi(P_K) \equiv 18 \pmod{36}$ when halting coincides with the closure of the macro-cycle ($a_N$ even, $B_K = -1$) and $\Psi(P) \equiv 0 \pmod{36}$ if the crossing of $-1$ were to occur in the interior of the odd phase ($a_N$ odd, $B_K \le -2$). Furthermore, the contradictory sentence in step 1 of the proof was removed.
4. **Typographical correction in the Turing machine tape trace (Part I, Proof of Theorem 1.0):**

   - In the even case $h = 2k$, when crossing the block $1^b$ to the left via $1^b \mathbf{<C} \to \mathbf{<C} 1^b$, the resulting configuration was corrected to $0^\infty \mathbf{<C} 1^b 0 0 1^{3k} 0^\infty$ (removing the superfluous $0$ between $\mathbf{<C}$ and $1^b$).
5. **Certified decimal value of the constant $\alpha$ and bound $(2/3)^{300}$ (Part IV, Section 4.1 and Appendix B):**

   - Certified the first 50 decimal digits after the decimal point of $\alpha = 7.86417726205661897240516852968228138530742425177359\dots$ with the exact bound $\left(\frac{2}{3}\right)^{300} \approx 1.4880663064957113 \times 10^{-53} < 1.49 \times 10^{-53}$.
6. **Identity for $b_N$ in terms of $Z_k = 3a_k - 2$ (Part V, Theorem 5.1):**

   - Included the initial term $Z_0 = 22$ in the two equivalent forms $b_N = 2Z_N - 44 - \sum_{k=0}^{N-1} Z_k = 2Z_N - 66 - \sum_{k=1}^{N-1} Z_k$.
7. **Elimination of notational collisions ($P_K$ and $V_n$):**

   - Reserved $P_K = \sum_{i=1}^K r_i$ for the cumulative count of even steps in macro-cycles (avoiding collision with $R_n = a_n - \alpha(3/2)^n$) and $V_n$ for the count of $0$ digits in base $3$ (avoiding collision with $Z_n = 3a_n - 2$).
8. **Expansion of the Treatise with Parts XV, XVI, XVII, and XVIII (and Tests 9–12 in Appendix B):**

   - **Part XV:** Proved the quadratic elimination of the $a_n p_n$ cross-term in $\Delta t_n$ (Theorem 15.1) and the global Cumulative Turing Machine Action Law for $T_N$ (Theorem 15.2), verified against a direct bit-level Antihydra Turing machine simulator.
   - **Part XVI:** Proved the explicit 2-adic seed inverse $\Phi_L^{-1}$ (Theorem 16.1), the Fuss-Catalan enumeration $C_P^{(3)} = \frac{1}{2P+1}\binom{3P}{P}$ and Golden-Ratio Haar measure $\mu_2(\mathcal{H}_{\text{all}}(b_0)) = \varphi^{-(b_0+1)}$ via Lagrange's cubic (Theorem 16.2), and the Dual Integer Fibonacci Conservation Laws (Theorem 16.3).
   - **Part XVII:** Proved the Tri-Local Adelic Bridge Identity linking $(\mathbb{R}, \mathbb{Z}_2, \mathbb{Z}_3)$ through the single series $\mathcal{S}(p) = \sum_{k=0}^\infty \frac{2^k}{3^{k+1}}p_k$ (Theorem 17.1) and the Cubic Virial Theorem (Theorem 17.2).
   - **Part XVIII:** Proved the unconditional modulo-27 / modulo-54 first-halting strengthening $a_{3P+1} \equiv 1 \pmod{27}$, $\Psi(P) \equiv 0 \pmod{54}$ (Theorem 18.1) and the closed-form 3-adic ballot sieve $|\mathcal{A}_M| = B_M$ modulo $3^M$ (Theorem 18.2).

### C.2. Remaining Open Results (Open Problems)

1. **Global Halting Problem for Antihydra:** Prove that for no $P \ge 1$ does there exist an integer solution to the Diophantine system of the inverse chain $Y_j$ with $b_{3P+1} = -1$.
2. **Archimedean Ergodic Bound / Mahler's Problem:** Bound the Cesàro mean $\frac{1}{N}\sum_{k=0}^{N-1} R_k$ strictly away from $\frac{2}{3}$ from above (or determine the distribution of $\{\alpha(3/2)^k\}$ in $(0, 1)$).