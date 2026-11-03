# Antihydra Treatise — Volume 4: Turing Action Law, Fuss-Catalan Haar Measure & 3-Adic Ballot Sieve (Parts XV–XVIII & Appendices)

## Part XV: Exact Quadratic Telescoping of Step-Times $\Delta t _ n$ and the Cumulative Turing Machine Action Law ($T _ N$)

### 15.1. Elimination of the Bilinear Cross-Term $a _ n p _ n$ in the Bit-Level Step Duration $\Delta t _ n$

In Theorem 1.0(2), we proved that the Antihydra Turing machine transitions from the canonical configuration $\mathcal{A}(b _ n, a _ n - 4)$ to $\mathcal{A}(b _ {n+1}, a _ {n+1} - 4)$ in an exact number of bit-level Turing machine steps $\Delta t _ n$ given by:

$$
\Delta t_n = \begin{cases} 2b_n + 3k_n^2 + 12k_n + 11 & \text{if } p_n = 0 \quad (a_n - 4 = 2k_n), \cr 3k_n^2 + 12k_n + 5 & \text{if } p_n = 1 \quad (a_n - 4 = 2k_n + 1), \end{cases}
$$

where $k _ n = \frac{a _ n - 4 - p _ n}{2}$. Substituting $k _ n$ directly produces a bilinear cross-term $-\frac{3}{2}a _ n p _ n$. We now prove that the affine curve identity from Part VII eliminates this cross-term identically and converts $3k _ n^2 + 12k _ n$ into an exact quadratic telescope $a _ {n+1}^2 - \frac{3}{2}a _ n^2$.

**Theorem 15.1 (Quadratic Telescoping of the Macro-Step Duration $\Delta t _ n$)** [Proved]: For every macro-step $n \ge 0$ of the Antihydra system, the bit-level Turing machine step count $\Delta t _ n$ satisfies the exact identity:

$$
\Delta t_n = a_{n+1}^2 - \frac{3}{2}a_n^2 + 2(1 - p_n)b_n - 1 - \frac{11}{2}p_n
$$

*Proof:*
1. Substituting $2k _ n = a _ n - 4 - p _ n$ into $3k _ n^2 + 12k _ n = \frac{3}{4}(2k _ n)(2k _ n + 8)$ and using $p _ n^2 = p _ n$:

$$
3k_n^2 + 12k_n = \frac{3}{4}(a_n - 4 - p_n)(a_n + 4 - p_n) = \frac{3}{4}\big((a_n - p_n)^2 - 16\big) = \frac{3}{4}a_n^2 - \frac{3}{2}a_n p_n + \frac{3}{4}p_n - 12.
$$

2. On the other hand, from the fundamental recurrence $2a _ {n+1} = 3a _ n - p _ n$, squaring both sides yields:

$$
4a_{n+1}^2 = (3a_n - p_n)^2 = 9a_n^2 - 6a_n p_n + p_n \implies -\frac{3}{2}a_n p_n = a_{n+1}^2 - \frac{9}{4}a_n^2 - \frac{1}{4}p_n.
$$

3. Substituting this expression for $-\frac{3}{2}a _ n p _ n$ into step 1 eliminates the cross-term completely:

$$
3k_n^2 + 12k_n = \frac{3}{4}a_n^2 + \left(a_{n+1}^2 - \frac{9}{4}a_n^2 - \frac{1}{4}p_n\right) + \frac{3}{4}p_n - 12 = a_{n+1}^2 - \frac{3}{2}a_n^2 + \frac{1}{2}p_n - 12.
$$

4. Combining both branches of Theorem 1.0(2) via $\Delta t _ n = 2(1 - p _ n)b _ n + (3k _ n^2 + 12k _ n) + 11 - 6p _ n$, we obtain:

$$
\Delta t_n = a_{n+1}^2 - \frac{3}{2}a_n^2 + 2(1 - p_n)b_n - 1 - \frac{11}{2}p_n. \quad \blacksquare
$$

---

### 15.2. The Cumulative Turing Machine Action Law ($T _ N$)

Let $T _ N$ denote the total number of individual Turing machine steps elapsed from the blank tape $0^\infty \mathbf{A>} 0^\infty$ up to the $N$-th canonical configuration $\mathcal{A}(b _ N, a _ N - 4)$:

$$
T_0 = 11, \qquad T_N = 11 + \sum_{n=0}^{N-1} \Delta t_n \qquad (N \ge 1).
$$

**Theorem 15.2 (Global Parity-Free Action Law for $T _ N$)** [Proved]: For every $N \ge 1$, the cumulative Turing machine step count $T _ N$ satisfies the exact polynomial conservation law:

$$
6 T_N + 3 \sum_{n=0}^{N-1} a_n^2 - 4 \sum_{n=0}^{N-1} b_n = 6 a_N^2 + b_N(2b_N + 9) - 32N - 318
$$

Equivalently, if $N = 3P + 1$ is a hypothetical halting horizon ($b _ N = -1$, preceding the final $2b _ N + 3 = 1$ step to `F0`), then:

$$
6 T_{3P+1} + 3 \sum_{n=0}^{3P} a_n^2 - 4 \sum_{n=0}^{3P} b_n = 6 a_{3P+1}^2 - 96P - 357.
$$

*Proof:*
1. Summing Theorem 15.1 over $n = 0, \dots, N-1$ and noting that $\sum _ {n=0}^{N-1} (a _ {n+1}^2 - \frac{3}{2}a _ n^2) = a _ N^2 - a _ 0^2 - \frac{1}{2}\sum _ {n=0}^{N-1} a _ n^2$ (with $a _ 0^2 = 64$) gives:

$$
T_N - 11 = a_N^2 - 64 - \frac{1}{2}\sum_{n=0}^{N-1} a_n^2 + 2\sum_{n=0}^{N-1} b_n - 2\sum_{n=0}^{N-1} b_n p_n - N - \frac{11}{2}O_N.
$$

2. Multiply by $6$ and substitute both the Quadratic Virial Theorem (Theorem 6.1: $-12\sum _ {n=0}^{N-1} b _ n p _ n = -8\sum _ {n=0}^{N-1} b _ n - 4N + 2b _ N(b _ N - 1){}$) and the triad identity $3O _ N = 2N - b _ N$:

$$
6T_N - 66 = 6a_N^2 - 384 - 3\sum_{n=0}^{N-1} a_n^2 + 12\sum_{n=0}^{N-1} b_n + \left(-8\sum_{n=0}^{N-1} b_n - 4N + 2b_N^2 - 2b_N\right) - 6N - 11(2N - b_N).
$$

3. Collecting terms yields $6T _ N + 3\sum _ {n=0}^{N-1} a _ n^2 - 4\sum _ {n=0}^{N-1} b _ n = 6a _ N^2 + 2b _ N^2 + 9b _ N - 32N - 318$. $\blacksquare$

---

## Part XVI: 2-Adic Bernoulli Isomorphism, Fuss-Catalan Halting Measure $\varphi^{-1}$, and Integer Fibonacci Conservation Laws

### 16.1. Explicit 2-Adic Inverse Map and Measure-Preserving Conjugacy

**Theorem 16.1 (Explicit 2-Adic Seed Formula for Any Parity Prefix)** [Proved]: For every level $L \ge 1$, the map $\Phi _ L: \mathbb{Z}/2^L\mathbb{Z} \to \lbrace 0, 1\rbrace ^L$ assigning to each initial seed $x _ 0 \bmod 2^L$ its first $L$ parity bits $(p _ 0, p _ 1, \dots, p _ {L-1})$ under $T(x) = \frac{3x - (x \bmod 2)}{2}$ is a bijection whose explicit inverse is:

$$
\Phi_L^{-1}(p_0, \dots, p_{L-1}) \equiv \sum_{k=0}^{L-1} \big(3^{-(k+1)} \bmod 2^L\big) 2^k p_k \pmod{2^L}.
$$

In the projective limit $L \to \infty$, $\Phi _ \infty: (\mathbb{Z} _ 2, \mu _ 2) \to (\lbrace 0, 1\rbrace ^{\mathbb{N}}, \mu _ {1/2})$ is a measure-preserving topological conjugacy between $T$ and the unilateral Bernoulli shift, with inverse $\Phi _ \infty^{-1}((p _ k) _ {k \ge 0}) = \sum _ {k=0}^\infty 3^{-(k+1)} 2^k p _ k \in \mathbb{Z} _ 2$.

*Proof:*
For any $x _ 0 \in \mathbb{Z} _ 2$, iterating $2x _ {k+1} = 3x _ k - p _ k$ for $L$ steps gives $2^L x _ L = 3^L x _ 0 - \sum _ {k=0}^{L-1} 3^{L-1-k} 2^k p _ k$. Since $3$ is a unit in $\mathbb{Z} _ 2$, multiplying by $3^{-L}$ yields $x _ 0 - \sum _ {k=0}^{L-1} 3^{-(k+1)} 2^k p _ k = 2^L 3^{-L} x _ L \equiv 0 \pmod{2^L}$. Moreover, the $k$-th term of the sum is a multiple of $2^k$, so the series converges in the $2$-adic norm $|\cdot| _ 2$ for any sequence $(p _ k) _ {k \ge 0} \in \lbrace 0, 1\rbrace ^{\mathbb{N}}$. $\blacksquare$

---

### 16.2. Fuss-Catalan Halting Cylinder Enumeration and the Golden-Ratio Haar Measure $\varphi^{-1}$

In $\mathbb{Z} _ 2$, every seed $x _ 0 \in \mathbb{Z} _ 2$ defines a parity sequence $p _ n(x _ 0) \in \lbrace 0, 1\rbrace$ and a counter trajectory $b _ {n+1}(x _ 0) = b _ n(x _ 0) + 2 - 3p _ n(x _ 0)$ starting at $b _ 0 \ge 0$. Let $\mathcal{H} _ {\text{all}}(b _ 0) \subset \mathbb{Z} _ 2$ denote the set of 2-adic seeds $x _ 0 \in \mathbb{Z} _ 2$ for which the counter ever reaches $-1$ ($\exists N \ge 1$ with $b _ N(x _ 0) = -1$).

**Theorem 16.2 (Fuss-Catalan Enumeration of First-Halting Cylinders and Golden-Ratio Haar Measure)** [Proved]:
1. For $b _ 0 = 0$ and any integer $P \ge 0$, a seed $x _ 0 \in \mathbb{Z} _ 2$ hits $b _ N = -1$ for the **first time** at step $N$ ($b _ n \ge 0$ for $0 \le n < N$ and $b _ N = -1$) if and only if $N = 3P + 1$ for some $P \ge 0$ and its prefix $(p _ 0, \dots, p _ {3P}) \in \lbrace 0, 1\rbrace ^{3P+1}$ is a Raney ballot word of $P$ zeros and $2P + 1$ ones. The exact number of such residue classes modulo $2^{3P+1}$ is the Fuss-Catalan number:

$$
|\mathcal{H}_P| = C_P^{(3)} := \frac{1}{3P + 1}\binom{3P + 1}{P} = \frac{1}{2P + 1}\binom{3P}{P}, \qquad \mu_2(\mathcal{H}_P) = \frac{C_P^{(3)}}{2^{3P+1}}.
$$

   (Specifically, for $P = 0, 1, 2, 3, 4$, there are $C _ P^{(3)} = 1, 1, 3, 12, 55$ halting residue classes out of $2, 16, 128, 1024, 8192$ classes modulo $2^{3P+1}$, respectively).
2. Summing over all disjoint first-hitting horizons $P \ge 0$, the exact 2-adic Haar measure of the set of all halting seeds $\mathcal{H} _ {\text{all}}(b _ 0) \subset \mathbb{Z} _ 2$ from any initial counter $b _ 0 \ge 0$ is a power of the inverse Golden Ratio $\varphi^{-1} = \frac{\sqrt{5} - 1}{2}$:

$$
\mu_2\big(\mathcal{H}_{\text{all}}(b_0)\big) = \sum_{P=0}^\infty \frac{C_P^{(3)}}{2^{3P+1}} \quad (b_0 = 0) \implies \mu_2\big(\mathcal{H}_{\text{all}}(b_0)\big) = \left(\frac{\sqrt{5} - 1}{2}\right)^{b_0 + 1} = \varphi^{-(b_0 + 1)}.
$$

   Consequently, for $b _ 0 = 0$, the set of non-halting 2-adic seeds has strictly positive Haar measure $\mu _ 2(\mathbb{Z} _ 2 \setminus \mathcal{H} _ {\text{all}}(0)) = 1 - \varphi^{-1} = \varphi^{-2} = \frac{3 - \sqrt{5}}{2} \approx 0.381966$.

*Proof:*
1. Since $b _ {n+1} - b _ n \in \lbrace +2, -1\rbrace$ only steps downward by $-1$, the first passage from $b _ 0 = 0$ to $-1$ must occur at $-1 = 2N - 3O _ N$, so $N = 3P + 1$ with $P = N - O _ N$ zeros and $O _ N = 2P + 1$ ones. By Raney's Lemma (the Fuss-Catalan Ballot Theorem), among the $\binom{3P+1}{P}$ cyclic shifts of a word with $P$ steps of $+2$ and $2P+1$ steps of $-1$ (total sum $-1$), exactly $1$ shift stays $\ge 0$ until the final step $3P + 1$. Thus the number of valid words is $\frac{1}{3P+1}\binom{3P+1}{P} = C _ P^{(3)}$. By Theorem 16.1, each word of length $3P + 1$ corresponds to a unique cylinder modulo $2^{3P+1}$ of Haar measure $2^{-(3P+1)}$.
2. By Lagrange inversion, the Fuss-Catalan generating function $w(z) = \sum _ {P=0}^\infty C _ P^{(3)} z^P$ satisfies $z w(z)^3 - w(z) + 1 = 0$. Since the series $\sum _ {P=0}^\infty \frac{C _ P^{(3)}}{2^{3P+1}} = \frac{1}{2}w(1/8)$ has positive terms and represents a probability $\rho = \frac{1}{2}w(1/8) \in (0, 1]$, substituting $w = 2\rho$ and $z = 1/8$ into $z w^3 - w + 1 = 0$ yields:

$$
\rho^3 - 2\rho + 1 = (\rho - 1)(\rho^2 + \rho - 1) = 0.
$$

   Since $\sum _ {P=0}^\infty C _ P^{(3)} z^P$ is strictly increasing on $[0, 4/27]$ (with critical point at $z _ c = 4/27 > 1/8 = 3.375/27$, where $w(4/27) = 3/2$), we have $w(1/8) < 3/2 < 2$, so $\rho < 3/4 < 1$. The unique root of $(\rho - 1)(\rho^2 + \rho - 1) = 0$ in $(0, 1)$ is $\rho = \frac{\sqrt{5} - 1}{2} = \varphi^{-1}$. Since a downward step is $-1$, hitting $-1$ from $b _ 0 \ge 0$ requires $b _ 0 + 1$ independent first-passage descents of $-1$, giving $\mu _ 2(\mathcal{H} _ {\text{all}}(b _ 0)) = \rho^{b _ 0 + 1} = \varphi^{-(b _ 0 + 1)}$. $\blacksquare$

---

### 16.3. The Deterministic Golden Exponential Identity and Dual Integer Fibonacci Conservation Laws

Even for a **single deterministic orbit** (such as the Antihydra orbit starting from $a _ 0 = 8, b _ 0 = 0$), the algebraic relation $\varphi^{-2} + \varphi^{-1} = 1$ induces two exact integer Fibonacci conservation laws along the trajectory. Recall that the Fibonacci numbers $F _ m$ are defined for all $m \in \mathbb{Z}$ by $F _ 0 = 0, F _ 1 = 1$, and $F _ {m+1} = F _ m + F _ {m-1}$ (so $F _ {-1} = 1$).

**Theorem 16.3 (Deterministic Golden Difference Identity and Dual Integer Fibonacci Conservation Laws)** [Proved]: Along any trajectory of the Antihydra system $(a _ n, b _ n)$ starting from $b _ 0 = 0$:
1. **Golden Difference Identity:** For every $n \ge 0$, the quantity $\varphi^{-b _ n} \in \mathbb{Z}[\varphi]$ satisfies:

$$
\varphi^{-b_{n+1}} - \varphi^{-b_n} = (2p_n - 1)\varphi^{-(b_n + 1)}.
$$

2. **Dual Integer Fibonacci Conservation Laws:** For every $N \ge 1$, separating the rational and $\varphi$-components in $\mathbb{Z}[\varphi]$ yields two exact integer identities:

$$
(-1)^{b_N} F_{b_N} = \sum_{n=0}^{N-1} (2p_n - 1)(-1)^{b_n + 1} F_{b_n + 1},
$$

$$
(-1)^{b_N} F_{b_N + 1} - 1 = \sum_{n=0}^{N-1} (2p_n - 1)(-1)^{b_n + 1} F_{b_n + 2}.
$$

   In particular, at any hypothetical halting horizon $b _ N = -1$ ($F _ {-1} = 1, F _ 0 = 0$), these specialize to $\sum _ {n=0}^{N-1} (2p _ n - 1)(-1)^{b _ n + 1} F _ {b _ n + 1} = -1$ and $\sum _ {n=0}^{N-1} (2p _ n - 1)(-1)^{b _ n + 1} F _ {b _ n + 2} = -1$.

*Proof:*
1. If $p _ n = 0$, then $b _ {n+1} = b _ n + 2$, and since $\varphi^{-2} - 1 = -\varphi^{-1}$, we have $\varphi^{-(b _ n+2)} - \varphi^{-b _ n} = \varphi^{-b _ n}(\varphi^{-2} - 1) = -\varphi^{-(b _ n+1)}$. If $p _ n = 1$, then $b _ {n+1} = b _ n - 1$, and since $\varphi - 1 = \varphi^{-1}$, we have $\varphi^{-(b _ n-1)} - \varphi^{-b _ n} = \varphi^{-b _ n}(\varphi - 1) = +\varphi^{-(b _ n+1)}$. In both cases, $\varphi^{-b _ {n+1}} - \varphi^{-b _ n} = (2p _ n - 1)\varphi^{-(b _ n+1)}$.
2. Summing from $n = 0$ to $N - 1$ with $\varphi^{-b _ 0} = 1$ gives $\varphi^{-b _ N} - 1 = \sum _ {n=0}^{N-1} (2p _ n - 1)\varphi^{-(b _ n+1)}$. By induction on $m \in \mathbb{Z}$, $\varphi^{-m} = (-1)^m(F _ m \varphi - F _ {m+1})$. Since $\lbrace 1, \varphi\rbrace$ is a $\mathbb{Z}$-basis of $\mathbb{Z}[\varphi]$ ($\varphi \notin \mathbb{Q}$), equating the coefficients of $\varphi$ and $1$ on both sides yields the two stated integer identities. $\blacksquare$

---

## Part XVII: The Tri-Local Adelic Bridge Series $\mathcal{S}(p)$ Across $(\mathbb{R}, \mathbb{Z} _ 2, \mathbb{Z} _ 3)$ and the Cubic Virial Theorem

### 17.1. The Tri-Local Adelic Bridge Identity

In Part IV we defined the Archimedean constant $\alpha = 8 - \sum _ {k=0}^\infty \frac{2^k}{3^{k+1}}p _ k \in \mathbb{R}$, while in Part XVI we proved that the 2-adic inverse map is $\Phi _ \infty^{-1}(p) = \sum _ {k=0}^\infty 3^{-(k+1)} 2^k p _ k \in \mathbb{Z} _ 2$. Strikingly, **these two series have the exact same rational general term** $\frac{2^k}{3^{k+1}}p _ k \in \mathbb{Q}$.

**Theorem 17.1 (The Tri-Local Adelic Bridge Theorem)** [Proved]: For the Antihydra parity sequence $(p _ k) _ {k \ge 0}$, define the rational partial sums:

$$
\mathcal{S}_N(p) := \sum_{k=0}^{N-1} \frac{2^k}{3^{k+1}} p_k = 8 - \left(\frac{2}{3}\right)^N a_N \in \mathbb{Q} \qquad (N \ge 1).
$$

Then the single formal series $\mathcal{S}(p) = \sum _ {k=0}^\infty \frac{2^k}{3^{k+1}}p _ k$ links all three local completions of $\mathcal{E} _ S = \mathbb{R} \times \mathbb{Z} _ 2 \times \mathbb{Z} _ 3$ simultaneously:
1. **In the Archimedean topology $\mathbb{R}$ ($|\cdot| _ \infty$):** Since $|2/3| _ \infty = 2/3 < 1$, $\mathcal{S} _ N(p)$ converges geometrically to the initial fractional shift $R _ 0$:

$$
\lim_{N \to \infty}^{\mathbb{R}} \mathcal{S}_N(p) = 8 - \alpha = R_0 \approx 0.135822737943381\dots \in (0, 1).
$$

2. **In the 2-adic topology $\mathbb{Z} _ 2$ ($|\cdot| _ 2$):** Since $|2/3| _ 2 = 1/2 < 1$ and $a _ N \in \mathbb{Z} \subset \mathbb{Z} _ 2$, the remainder satisfies $|8 - \mathcal{S} _ N(p)| _ 2 = |(2/3)^N a _ N| _ 2 \le 2^{-N} \to 0$, so the exact same series converges 2-adically to the integer seed $a _ 0 = 8$:

$$
\lim_{N \to \infty}^{\mathbb{Z}_2} \mathcal{S}_N(p) = 8 = a_0 \in \mathbb{Z}_2.
$$

3. **In the 3-adic topology $\mathbb{Z} _ 3$ ($|\cdot| _ 3$):** Clearing the denominator $3^N$ projects $\mathcal{S} _ N(p)$ directly onto the 3-adic Cantor residue class of $a _ N$:

$$
3^N \mathcal{S}_N(p) = 8 \cdot 3^N - 2^N a_N \equiv -2^N a_N \pmod{3^N}.
$$

*Proof:*
From $2a _ {k+1} = 3a _ k - p _ k$, dividing by $3^{k+1}/2^k$ telescopes $\sum _ {k=0}^{N-1} \frac{2^k}{3^{k+1}}p _ k = a _ 0 - \left(\frac{2}{3}\right)^N a _ N = 8 - \left(\frac{2}{3}\right)^N a _ N$. Taking limits in $|\cdot| _ \infty$ (Theorem 4.1), in $|\cdot| _ 2$ (where $|3^{-N}| _ 2 = 1$ and $|2^N a _ N| _ 2 \le 2^{-N}$), and reducing $3^N \mathcal{S} _ N(p) \pmod{3^N}$ establishes (1), (2), and (3). $\blacksquare$

---

### 17.2. The Cubic Virial Theorem

In Part VI (Theorem 6.1) we established the Quadratic Virial Theorem expressing $\sum _ {n=0}^{N-1} b _ n p _ n$ in terms of $\sum _ {n=0}^{N-1} b _ n$. By telescoping the cubic potential $b _ {n+1}^3 - b _ n^3$, we obtain the exact third-order moment law.

**Theorem 17.2 (The Cubic Virial Theorem)** [Proved]: For every $N \ge 1$, the quadratic parity-weighted sum $\sum _ {n=0}^{N-1} b _ n^2 p _ n$ satisfies the exact identity:

$$
18 \sum_{n=0}^{N-1} b_n^2 p_n = 12 \sum_{n=0}^{N-1} (b_n^2 + b_n) - b_N(2b_N^2 - 3b_N - 3) - 2N.
$$

At any hypothetical halting horizon $b _ N = -1$ ($b _ N(2b _ N^2 - 3b _ N - 3) = (-1)(2) = -2$), this specializes to the exact Cubic Halting Partition Law:

$$
9 \sum_{n=0}^{N-1} b_n^2 p_n = 6 \sum_{n=0}^{N-1} (b_n^2 + b_n) - N + 1.
$$

*Proof:*
1. Let $\delta _ n = b _ {n+1} - b _ n = 2 - 3p _ n$. Since $p _ n^2 = p _ n$ and $p _ n^3 = p _ n$, the powers of $\delta _ n$ are linear in $p _ n$:

$$
\delta_n = 2 - 3p_n, \qquad \delta_n^2 = 4 - 12p_n + 9p_n = 4 - 3p_n, \qquad \delta_n^3 = 8 - 9p_n.
$$

2. Expanding $b _ {n+1}^3 - b _ n^3 = 3b _ n^2 \delta _ n + 3b _ n \delta _ n^2 + \delta _ n^3$ gives:

$$
b_{n+1}^3 - b_n^3 = 6b_n^2 - 9b_n^2 p_n + 12b_n - 9b_n p_n + 8 - 9p_n.
$$

3. Summing from $n = 0$ to $N - 1$ (with $b _ 0 = 0$) and multiplying by $2$:

$$
18\sum_{n=0}^{N-1} b_n^2 p_n = 12\sum_{n=0}^{N-1} b_n^2 + 24\sum_{n=0}^{N-1} b_n - 18\sum_{n=0}^{N-1} b_n p_n + 16N - 18O_N - 2b_N^3.
$$

4. Substituting $-18\sum _ {n=0}^{N-1} b _ n p _ n = -12\sum _ {n=0}^{N-1} b _ n - 6N + 3b _ N(b _ N - 1)$ (from Theorem 6.1) and $-18O _ N = -12N + 6b _ N$ yields:

$$
18\sum_{n=0}^{N-1} b_n^2 p_n = 12\sum_{n=0}^{N-1} (b_n^2 + b_n) - 2b_N^3 + 3b_N^2 + 3b_N - 2N. \quad \blacksquare
$$

---

## Part XVIII: The 3-Adic Ballot Sieve, Unconditional Modulo-54 Strengthening of $\Psi(P)$, and Closed-Form Enumeration of Terminal Halting Classes Modulo $3^M$

### 18.1. Unconditional Modulo-27 and Modulo-54 Strengthening at a First Halting Horizon

In Part XII (Theorem 12.2), we proved that if $N = 3P + 1 \ge 4$ ($P \ge 1$) is the **first** step at which $b _ N = -1$ (so $b _ n \ge 0$ for all $0 \le n < N$), then $p _ {N-1} = p _ {N-2} = 1$, which implies $a _ N \equiv 1 \pmod 9$ and $\Psi(P) = 2(a _ {3P+1} - 1) \equiv 0 \pmod{18}$. We now show that extending the non-negativity condition by one further backward step to $b _ {N-3} \ge 0$ unconditionally forces a **third** consecutive odd step $p _ {N-3} = 1$, multiplying the modulus by $3$.

**Theorem 18.1 (Unconditional Modulo-27 / Modulo-54 First-Halting Sieve)** [Proved]: Let $N = 3P + 1 \ge 4$ ($P \ge 1$) be the first halting step ($b _ n \ge 0$ for $0 \le n < N$ and $b _ N = -1$). Then:
1. **Triple Odd Terminal Suffix:** The final three steps before $N$ are unconditionally odd:

$$
(p_{N-3}, p_{N-2}, p_{N-1}) = (1, 1, 1), \qquad (b_{N-3}, b_{N-2}, b_{N-1}, b_N) = (2, 1, 0, -1).
$$

2. **Unconditional Modulo-27 and Modulo-54 Sieve:** Every first halting state $a _ {3P+1}$ ($P \ge 1$) satisfies unconditionally:

$$
a_{3P+1} \equiv 1 \pmod{27}, \qquad \Psi(P) = 2(a_{3P+1} - 1) \equiv 0 \pmod{54}.
$$

   Moreover, splitting by the parity of $a _ {3P+1}$:
   - If halting occurs at the closure of a macro-cycle ($a _ {3P+1}$ even, $B _ K = -1$), then $m _ K \ge 3$ and:

$$
\Psi(P_K) = 2(a_{3P_K + 1} - 1) \equiv 54 \pmod{108}.
$$

   - If halting occurs in the interior of an odd run ($a _ {3P+1}$ odd, $B _ K \le -2$), then:

$$
\Psi(P) = 2(a_{3P+1} - 1) \equiv 0 \pmod{108}.
$$

*Proof:*
1. By Theorem 12.2, $b _ N = -1$ and $b _ {N-1}, b _ {N-2} \ge 0$ force $p _ {N-1} = 1$ ($b _ {N-1} = 0$) and $p _ {N-2} = 1$ ($b _ {N-2} = 1$). At step $N - 3 \ge 1$, we have $b _ {N-2} = b _ {N-3} + 2 - 3p _ {N-3} = 1$. If $p _ {N-3} = 0$, then $b _ {N-3} = 1 - 2 = -1$, contradicting that $N$ is the **first** step at which the counter reaches $-1$. Therefore $p _ {N-3} = 1$ and $b _ {N-3} = 2$.
2. Applying the backward chain $3Y _ {j+1} = 2Y _ j + r _ j$ from $Y _ 0 = a _ N$ with $r _ 0 = p _ {N-1} = 1$, $r _ 1 = p _ {N-2} = 1$, $r _ 2 = p _ {N-3} = 1$ yields $27 Y _ 3 - 8 a _ N = 9 r _ 0 + 6 r _ 1 + 4 r _ 2 = 9 + 6 + 4 = 19$. Hence $8(a _ N - 1) = 27(Y _ 3 - 1) \equiv 0 \pmod{27}$, and since $\gcd(8, 27) = 1$, $a _ N \equiv 1 \pmod{27}$ and $\Psi(P) = 2(a _ N - 1) \equiv 0 \pmod{54}$. Combining with $a _ N \bmod 2 \in \lbrace 0, 1\rbrace$ gives $\Psi(P) \equiv 54$ or $0 \pmod{108}$. $\blacksquare$

---

### 18.2. The General 3-Adic Ballot Sieve Modulo $3^M$

More generally, at any first halting step $N = 3P + 1 \ge M$, the condition that the counter never hit $-1$ during the last $M$ steps ($b _ {N-k} \ge 0$ for $1 \le k \le M$, with $b _ N = -1$) restricts the parity suffix $(p _ {N-M}, \dots, p _ {N-1}) \in \lbrace 0, 1\rbrace ^M$. By Theorem 9.2 (Injectivity of $\Psi _ M$), each suffix $(p _ {N-M}, \dots, p _ {N-1})$ maps injectively to a unique terminal residue class $X = a _ N \bmod 3^M \in \mathcal{R} _ M \subset \mathbb{Z}/3^M\mathbb{Z}$.

**Theorem 18.2 (Closed-Form Ballot Enumeration of Admissible Terminal Classes Modulo $3^M$)** [Proved]: For any depth $M \ge 1$ and any first halting step $N = 3P + 1 \ge M$, let $\mathcal{A} _ M \subset \mathcal{R} _ M \subset \mathbb{Z}/3^M\mathbb{Z}$ denote the set of terminal residue classes $a _ N \bmod 3^M$ compatible with $b _ {N-k} \ge 0$ ($1 \le k \le M$) and $b _ N = -1$. Then:
1. **Exact Closed-Form Cardinality $B _ M$:** The number of suffix-admissible residue classes modulo $3^M$ is given in closed form by:

$$
|\mathcal{A}_M| = B_M := \sum_{k=0}^{\lfloor (M-1)/3 \rfloor} \frac{M - 3k}{M}\binom{M}{k} = \sum_{k=0}^{\lfloor (M-1)/3 \rfloor} \left[\binom{M-1}{k} - 2\binom{M-1}{k-1}\right],
$$

   where $\binom{M-1}{-1} := 0$.
2. **Explicit Sieve Table for $1 \le M \le 9$:** The exact counts $B _ M$ and residue classes $\mathcal{A} _ M \pmod{3^M}$ for small $M$ are:

| Depth $M$ | Modulus $3^M$ | Total Cantor classes $2^M$ | Ballot-admissible classes $B _ M = \lvert\mathcal{A} _ M\rvert$ | Explicit admissible residues $a _ N \bmod 3^M$ |
| --- | --- | --- | --- | --- |
| **1** | $3$ | $2$ | **1** | $\lbrace 1\rbrace$ |
| **2** | $9$ | $4$ | **1** | $\lbrace 1\rbrace$ |
| **3** | $27$ | $8$ | **1** | $\lbrace 1\rbrace$ |
| **4** | $81$ | $16$ | **2** | $\lbrace 1, 42\rbrace$ |
| **5** | $243$ | $32$ | **3** | $\lbrace 1, 123, 184\rbrace$ |
| **6** | $729$ | $64$ | **4** | $\lbrace 1, 184, 366, 640\rbrace$ |
| **7** | $2187$ | $128$ | **8** | $\lbrace 1, 276, 549, 960, 1095, 1369, 1642, 2053\rbrace$ |
| **8** | $6561$ | $256$ | **13** | $13$ classes out of $6561$ ($99.80$% excluded) |
| **9** | $19683$ | $512$ | **19** | $19$ classes out of $19683$ ($99.903$% excluded) |

3. **3-Adic Measure Zero:** In the projective limit $M \to \infty$, the fraction of 3-adic integers in $\mathbb{Z} _ 3$ whose backward chain satisfies the ballot condition vanishes exponentially: $B _ M / 3^M \le (2/3)^M \to 0$.

*Proof:*
Reading the last $M$ steps backward from $b _ N = -1$, let $s _ m = b _ {N-m}$ for $1 \le m \le M$. Since $p _ {N-1} = 1$, we have $s _ 1 = 0$, and at each backward step $s _ {m+1} - s _ m = 3p _ {N-1-m} - 2 \in \lbrace +1, -2\rbrace$. The condition $s _ m \ge 0$ for all $1 \le m \le M$ means that in the word of $M - 1$ backward steps (after the forced step $p _ {N-1} = 1$), every prefix has at least twice as many $+1$ steps ($p = 1$) as $-2$ steps ($p = 0$). If the word of length $M$ (including $p _ {N-1} = 1$) contains $k$ zeros ($0 \le k \le \lfloor (M-1)/3 \rfloor$) and $M - k$ ones, the classical generalized ballot theorem (Barbier [1887]) states that the number of lattice paths of $M - k$ unit rises and $k$ drops of size $2$ starting at the origin that stay strictly above $-1$ is $\frac{(M - k) - 2k}{M}\binom{M}{k} = \frac{M - 3k}{M}\binom{M}{k} = \binom{M-1}{k} - 2\binom{M-1}{k-1}$. Summing over all $0 \le k \le \lfloor (M-1)/3 \rfloor$ and applying the injectivity of $\Psi _ M: \lbrace 0, 1\rbrace ^M \hookrightarrow \mathbb{Z}/3^M\mathbb{Z}$ (Theorem 9.2) gives $|\mathcal{A} _ M| = B _ M$. Evaluating $-2^{-M} \sum _ {j=0}^{M-1} 3^{M-1-j} 2^j r _ j \pmod{3^M}$ on the admissible suffixes produces the explicit table. $\blacksquare$

## Appendix A: Complete Empirical Table of the Trajectory ($n = 0 \dots 20$) [Computationally Verified]

The following table verifies step by step the exact values of $a _ n$, its binary representation, its residue modulo $3$ (verifying $a _ n \bmod 3 = p _ {n-1}$ for all $n \ge 1$), the spin $u _ n = 2a _ n - 1$, the master variable $Z _ n = 3a _ n - 2$, the charge $Q _ n = 6a _ n - b _ n - 4$, the counter $b _ n$, and the odd-step accumulator $O _ n$:

| Step ($n$) | $a _ n$ | Binary of $a _ n$ | $a _ n \bmod 3$ ($= p _ {n-1}$) | $p _ n$ | $\sigma _ n$ | $u _ n = 2a _ n-1$ | $b _ n$ | $O _ n$ | $Z _ n = 3a _ n-2$ | $Q _ n = 6a _ n-b _ n-4$ | Threshold $(2n+1)/3$ |
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

The Python program in Section B.2 executes a **computational verification over a finite range** ($N _ {\text{steps}} = 300$ steps and $15$ macro-cycles, plus bit-level Turing machine simulation) employing exact integer and rational arithmetic (`fractions.Fraction` and `decimal.Decimal` with 80 digits of precision).

**Essential Methodological Rule:** A finite computational verification confirms algebraic exactness within the examined range and rules out typographical or indexing errors, but **never substitutes for a general mathematical proof** (which are developed in the text of Parts I through XVIII). Below, the 12 implemented tests are documented in accordance with the 5 audit criteria:

| Test | 1. Identity / Property Verified | 2. Evaluated Range | 3. Computation Performed | 4. Expected Result | 5. Limitations |
| --- | --- | --- | --- | --- | --- |
| **Test 1** *(Part IV)* | Certified value of $\alpha$, bound $(2/3)^{300} < 1.49 \times 10^{-53}$, and formulas $a _ n = \lceil \alpha(3/2)^n \rceil$, $a _ n - 1 = \lfloor \alpha(3/2)^n \rfloor$. | Truncation at $M = 300$; formulas on $0 \le n \le 200$. | Computes the exact interval $[\alpha _ {\min}, \alpha _ {\max}] = [\alpha _ {300} - (2/3)^{300}, \alpha _ {300}]$ and verifies that $\lfloor \alpha _ {\min}(3/2)^n \rfloor = \lfloor \alpha _ {\max}(3/2)^n \rfloor = a _ n - 1$ (the error interval never crosses an integer). | Exact prefix `7.86417726205661897240516852968228138530742425177359` and agreement on $0 \le n \le 200$. | Certifies $50$ decimal places and verifies up to $n = 200$; for $n \to \infty$ general validity follows from the proof of Theorem 4.1(3). |
| **Test 2** *(Parts II and VII)* | Affine Curve, spin variety, character $\chi _ 4$, **exhaustive modulo 8 table**, **reflection** $\mathcal{J}(a) = 1 - a$, and Boolean Cubic Identity. | $0 \le n < 300$ along the orbit and the $8$ residues $r _ 8 \in \lbrace 0,\dots,7\rbrace$ with $k \in [0, 20]$; reflection on $a \in [-50, 50]$. | Algebraically evaluates each row of the table in Theorem 2.1, verifies $T(1-a) = 1-T(a)$, and checks the cubic identity for triples. | Exact equality across all $8$ residue classes modulo $8$, commutation of $\mathcal{J}$, and triple identity. | Verification over a finite set of integers; the general proof for all $k \in \mathbb{Z}$ is given in Part II. |
| **Test 3** *(Parts V and VI)* | Integral invariants ($44\cdot 3^n, 16\cdot 3^n, 14\cdot 3^n$), **corrected formula** $b _ N = 2Z _ N - 44 - \sum _ {k=0}^{N-1} Z _ k = 2Z _ N - 66 - \sum _ {k=1}^{N-1} Z _ k$ (including $N = 1$), and Quadratic Virial. | $1 \le N \le 300$ (with explicit assertion at $N = 1$). | Evaluates both sides of the three integral laws, the two equivalent forms of $b _ N$ in terms of $Z _ k$, and Theorem 6.1. | At $N = 1$, $2(34)-44-22 = 2 = b _ 1$, and exact agreement for all $1 \le N \le 300$. | Finite range $N \le 300$; does not evaluate the infinite limit of the series in Section 5.2. |
| **Test 4** *(Parts IX, X, and XII.1)* | Reciprocity $a _ n \bmod 3 = p _ {n-1}$, injectivity of $\Psi _ M$ on $\lbrace 0,1\rbrace ^M$, inversion $Y _ {j+1} = \lceil 2Y _ j/3 \rceil$ ($0 \le j \le N-1$), fractional parts $\theta _ j(a _ N)$, and Autocorrelation ($+4X^2$). | Reciprocity on $1 \le n \le 300$; injectivity on $1 \le M \le 8$; inverse chain at $N \in \lbrace 1, 10, 50, 200\rbrace$. | Reconstructs $(Y _ 0, \dots, Y _ N)$ from $X = a _ N$, verifies $\lvert\mathcal{R} _ M\rvert = 2^M$, and evaluates the linear, quadratic, and fractional invariants. |
| **Test 5** *(Parts III and XII.2)* | The 4 Valuation Laws, Universal Floor Formula, sieve $2(a _ {N _ i}-1) \equiv 18 \pmod{36}$ for $m _ i \ge 2$, and Archimedean formula $\Psi(P) = 2\lfloor \frac{3\alpha}{2}(27/8)^P \rfloor$. | First $15$ macro-cycles of the orbit and $1 \le P \le 60$. | Extracts $(r _ i, m _ i, c _ i, d _ i)$ exactly and certifies the Archimedean floor using the interval $[\alpha _ {\min}, \alpha _ {\max}]$. | Fulfillment of the 4 valuations, remainder in $(0, 1/3)$, and $2(a _ {N _ i}-1) \equiv 18 \pmod{36}$ whenever $m _ i \ge 2$. | Covers a finite number ($15$) of macro-cycles; does not constitute a universal proof of non-halting. |
| **Test 6** *(Part XI)* | Kirchhoff's telescoping equation for $b _ N$, **Koopman-Walsh orthogonality and level-lifting** $\mathcal{K}: \mathcal{W} _ L \to \mathcal{W} _ {L+1}$, and **family of cycles** $x _ 0^{(m)} = \frac{2^{m-1}}{3^m - 2^m}$ in $\mathbb{Z} _ 2$. | Kirchhoff at $N \in \lbrace 4, 10, 25, 50\rbrace$; Koopman-Walsh at $L \in \lbrace 1, 2, 3, 4\rbrace$; cycles at $2 \le m \le 12$. | Numerically evaluates the inner product $\langle w _ v^{(L)}, w _ {v'}^{(L)} \rangle$, the two-fiber expansion of $\mathcal{K}w _ v^{(L)}$, and the $m$ rational steps of $x _ 0^{(m)}$. | Exact orthogonality, lifting to $\mathcal{W} _ {L+1}$, and minimal period $m$ with parity word $(0^{m-1}, 1)$. | Verifies finite dimensions $L \le 4$ and periods $m \le 12$. |
| **Test 7** *(Part XIII)* | Ratios of $F _ n(z)$, telescoping product with $(1 - \frac{1}{3a _ k})$, and **recurrence** $2F _ {n+1}(z) - 3z^2 F _ n(z) = -p _ n z^{b _ n-1}$ **at all three cube roots of unity** $z \in \lbrace 1, \omega, \omega^2\rbrace$. | $0 \le n < 150$ in the exact cyclotomic ring $\mathbb{Q}(\omega) \cong \mathbb{Q}[x]/(x^2 + x + 1)$. | Represents each element of $\mathbb{Q}(\omega)$ as a rational pair $(u + v\omega)$ with $\omega^2 = -1 - \omega$ and verifies the exact identity for $z = 1, \omega, \omega^2$. | Remainder identically $(0, 0) \in \mathbb{Q}(\omega)$ at all three cube roots of unity. | Verification up to $n = 150$; the infinite product is evaluated on its finite partial products. |
| **Test 8** *(Part XIV)* | Base $3$ carry transducer, population laws $U _ {n+1}, D _ {n+1}, \Delta\Sigma _ 3$, and **explicit verification of the Universal Tail** $a _ {t+m+1} \bmod 3^m = \frac{3^m+3}{2}$. | Transducer on $0 \le n < 200$; Universal Tail at all odd-run closures with $m _ i \ge 2$ within the first $15$ macro-cycles and for synthetic seeds $3^m d + 1$ ($2 \le m \le 10$). | Decomposes $a _ n$ in base $3$, executes the phase scan, and checks the last $m$ ternary digits of $a _ {t+m+1}$. | Exact agreement of $U _ {n+1}, D _ {n+1}, \Sigma _ 3$ and ternary suffix $1^{m-2}20 _ 3$. | Verifies the first $200$ steps and runs up to $m = 10$. |
| **Test 9** *(Part XV)* | Quadratic telescoping of $\Delta t _ n$, bit-level TM step match, and **Cumulative Turing Machine Action Law** $6T _ N + 3\sum a _ n^2 - 4\sum b _ n = 6a _ N^2 + b _ N(2b _ N+9) - 32N - 318$. | Direct bit-level TM simulation for $0 \le N \le 12$; Action Law for $1 \le N \le 300$. | Simulates `1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA` step-by-step on tape and compares with Theorem 15.1 and Theorem 15.2. | Exact bit-for-bit match of $T _ N$ with the TM and exact equality of Action Law for all $1 \le N \le 300$. | Finite verification up to $N = 300$; general validity proved in Theorems 15.1 and 15.2. |
| **Test 10** *(Part XVI)* | Explicit 2-adic inverse $\Phi _ L^{-1}$, **Fuss-Catalan halting cylinder count** $C _ P^{(3)} = \frac{1}{2P+1}\binom{3P}{P}$, and **Dual Integer Fibonacci Conservation Laws**. | Inverse map on $1 \le L \le 10$; Fuss-Catalan on $0 \le P \le 3$ ($N \le 10$); Fibonacci laws on $1 \le N \le 300$. | Enumerates all $2^L$ residue classes, counts first-halting seeds modulo $2^{3P+1}$, and evaluates both Fibonacci sums. | Exact bijection, exact counts $C _ P^{(3)} = 1, 1, 3, 12$, and exact Fibonacci conservation at every step. | Finite $L \le 10, P \le 3, N \le 300$; infinite Haar measure $\varphi^{-1}$ proved via Lagrange's cubic in Theorem 16.2. |
| **Test 11** *(Part XVII)* | **Tri-Local Adelic Bridge Identity** $\mathcal{S} _ N(p) = 8 - (2/3)^N a _ N$, 2-adic divisibility $2^N \mid (8 - \mathcal{S} _ N(p))$, and **Cubic Virial Theorem**. | $1 \le N \le 300$. | Computes rational partial sums $\mathcal{S} _ N(p)$, checks 2-adic valuation of the numerator of $8 - \mathcal{S} _ N(p)$, and verifies Theorem 17.2. | Exact rational equality, 2-adic convergence to $8$, and exact third-order moment balance across all $N$. | Finite range $N \le 300$; general proof in Theorems 17.1 and 17.2. |
| **Test 12** *(Part XVIII)* | **Unconditional mod 27 / mod 54 sieve** and **Closed-Form 3-Adic Ballot Sieve** $\lvert\mathcal{A} _ M\rvert = B _ M$ modulo $3^M$. | Suffix depths $1 \le M \le 9$ (moduli up to $3^9 = 19683$). | Generates all ballot-admissible parity suffixes of length $M$, maps them modulo $3^M$, and compares against the closed-form formula $B _ M$. | Exact counts $(1, 1, 1, 2, 3, 4, 8, 13, 19)$ and exact residue sets $\lbrace 1\rbrace \pmod{27}$, $\lbrace 1, 42\rbrace \pmod{81}$, $\lbrace 1, 123, 184\rbrace \pmod{243}$, $\lbrace 1, 184, 366, 640\rbrace \pmod{729}$. | Finite suffix depth $M \le 9$; general ballot theorem proved for all $M \ge 1$ in Theorem 18.2. |

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

   - Corrected the statement of Theorem 8.1(2) to distinguish precisely between evaluation at $m = 0$, where $(\Delta^L a) _ 0 = \alpha(1/2)^L + (\Delta^L R) _ 0$, and evaluation along the diagonal $L = m$ at step $m$, where the leading term decays with base $3/4 < 1$: $(\Delta^m a) _ m = \alpha(3/4)^m + (\Delta^m R) _ m$.
3. **Rigorous case distinction in Theorem 12.2 (Part XII, Section 12.2):**

   - Rigorously separated the Diophantine sieve at the closure of any macro-cycle with $m _ K \ge 2$ —where $2(a _ {N _ K} - 1) = 2 \cdot 3^{m _ K} d _ K \equiv 18 \pmod{36}$ unconditionally— from the analysis of a general first halting step $N = 3P + 1 \ge 4$ ($b _ N = -1$). In the latter, the condition $p _ {N-2} = p _ {N-1} = 1$ always guarantees that $9 \mid (a _ N - 1)$ and $\Psi(P) = 2(a _ {3P+1} - 1) \equiv 0 \pmod{18}$, splitting into $\Psi(P _ K) \equiv 18 \pmod{36}$ when halting coincides with the closure of the macro-cycle ($a _ N$ even, $B _ K = -1$) and $\Psi(P) \equiv 0 \pmod{36}$ if the crossing of $-1$ were to occur in the interior of the odd phase ($a _ N$ odd, $B _ K \le -2$). Furthermore, the contradictory sentence in step 1 of the proof was removed.
4. **Typographical correction in the Turing machine tape trace (Part I, Proof of Theorem 1.0):**

   - In the even case $h = 2k$, when crossing the block $1^b$ to the left via $1^b \mathbf{<C} \to \mathbf{<C} 1^b$, the resulting configuration was corrected to $0^\infty \mathbf{<C} 1^b 0 0 1^{3k} 0^\infty$ (removing the superfluous $0$ between $\mathbf{<C}$ and $1^b$).
5. **Certified decimal value of the constant $\alpha$ and bound $(2/3)^{300}$ (Part IV, Section 4.1 and Appendix B):**

   - Certified the first 50 decimal digits after the decimal point of $\alpha = 7.86417726205661897240516852968228138530742425177359\dots$ with the exact bound $\left(\frac{2}{3}\right)^{300} \approx 1.4880663064957113 \times 10^{-53} < 1.49 \times 10^{-53}$.
6. **Identity for $b _ N$ in terms of $Z _ k = 3a _ k - 2$ (Part V, Theorem 5.1):**

   - Included the initial term $Z _ 0 = 22$ in the two equivalent forms $b _ N = 2Z _ N - 44 - \sum _ {k=0}^{N-1} Z _ k = 2Z _ N - 66 - \sum _ {k=1}^{N-1} Z _ k$.
7. **Elimination of notational collisions ($P _ K$ and $V _ n$):**

   - Reserved $P _ K = \sum _ {i=1}^K r _ i$ for the cumulative count of even steps in macro-cycles (avoiding collision with $R _ n = a _ n - \alpha(3/2)^n$) and $V _ n$ for the count of $0$ digits in base $3$ (avoiding collision with $Z _ n = 3a _ n - 2$).
8. **Expansion of the Treatise with Parts XV, XVI, XVII, and XVIII (and Tests 9–12 in Appendix B):**

   - **Part XV:** Proved the quadratic elimination of the $a _ n p _ n$ cross-term in $\Delta t _ n$ (Theorem 15.1) and the global Cumulative Turing Machine Action Law for $T _ N$ (Theorem 15.2), verified against a direct bit-level Antihydra Turing machine simulator.
   - **Part XVI:** Proved the explicit 2-adic seed inverse $\Phi _ L^{-1}$ (Theorem 16.1), the Fuss-Catalan enumeration $C _ P^{(3)} = \frac{1}{2P+1}\binom{3P}{P}$ and Golden-Ratio Haar measure $\mu _ 2(\mathcal{H} _ {\text{all}}(b _ 0)) = \varphi^{-(b _ 0+1)}$ via Lagrange's cubic (Theorem 16.2), and the Dual Integer Fibonacci Conservation Laws (Theorem 16.3).
   - **Part XVII:** Proved the Tri-Local Adelic Bridge Identity linking $(\mathbb{R}, \mathbb{Z} _ 2, \mathbb{Z} _ 3)$ through the single series $\mathcal{S}(p) = \sum _ {k=0}^\infty \frac{2^k}{3^{k+1}}p _ k$ (Theorem 17.1) and the Cubic Virial Theorem (Theorem 17.2).
   - **Part XVIII:** Proved the unconditional modulo-27 / modulo-54 first-halting strengthening $a _ {3P+1} \equiv 1 \pmod{27}$, $\Psi(P) \equiv 0 \pmod{54}$ (Theorem 18.1) and the closed-form 3-adic ballot sieve $|\mathcal{A} _ M| = B _ M$ modulo $3^M$ (Theorem 18.2).

### C.2. Remaining Open Results (Open Problems)

1. **Global Halting Problem for Antihydra:** Prove that for no $P \ge 1$ does there exist an integer solution to the Diophantine system of the inverse chain $Y _ j$ with $b _ {3P+1} = -1$.
2. **Archimedean Ergodic Bound / Mahler's Problem:** Bound the Cesàro mean $\frac{1}{N}\sum _ {k=0}^{N-1} R _ k$ strictly away from $\frac{2}{3}$ from above (or determine the distribution of $\lbrace \alpha(3/2)^k\rbrace$ in $(0, 1){}$).