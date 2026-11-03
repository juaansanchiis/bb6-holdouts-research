# Antihydra Treatise — Volume 2: Virial Theorems, Adelic Space & 3-Adic Contraction (Parts VI–IX)

## Part VI: The Quadratic Virial Theorem and Nonlinear Constraints

### 6.1. Linearization of the Boolean Square and the Second Moment of $b _ n$

Exploiting the Boolean idempotence $p _ m^2 = p _ m$ for all $m \ge 0$, we nonlinearly couple $b _ m$ with $p _ m$:

Theorem 6.1 (Antihydra Quadratic Virial Theorem) [Proved]: For every integer $N \ge 1$, the correlation between the counter $b _ m$ and the parity $p _ m$ satisfies the exact quadratic identity:

$$
6 \sum_{m=0}^{N-1} b_m p_m = 4 \sum_{m=0}^{N-1} b_m + 2N - b_N(b_N - 1)
$$

**Proof:**
Squaring $b _ {m+1} = b _ m + (2 - 3p _ m)$ and using $p _ m^2 = p _ m$:

$$
(2 - 3p_m)^2 = 4 - 12p_m + 9p_m^2 = 4 - 3p_m = 2 + (2 - 3p_m) = 2 + b_{m+1} - b_m
$$

Therefore, $b _ {m+1}^2 - b _ m^2 = 4b _ m - 6b _ m p _ m + 2 + b _ {m+1} - b _ m$. Summing telescopically from $m = 0$ to $N - 1$ with $b _ 0 = 0$ yields $b _ N^2 = 4\sum _ {m=0}^{N-1} b _ m - 6\sum _ {m=0}^{N-1} b _ m p _ m + 2N + b _ N$. $\blacksquare$

### 6.2. Sum Partition Corollary at a Halting Instant

**Corollary 6.2 (Weight Balance Between Even and Odd Steps at** $b _ N = -1$) [Proved]: Let $\mathcal{E} _ N = \lbrace 0 \le m < N : p _ m = 0\rbrace$ and $\mathcal{O} _ N = \lbrace 0 \le m < N : p _ m = 1\rbrace$ be the disjoint sets of even and odd instants prior to $N$. If halting were to occur at instant $N \ge 1$ ($b _ N = -1$), then:

$$
\sum_{m \in \mathcal{O}_N} b_m = 2 \sum_{m \in \mathcal{E}_N} b_m + N - 1
$$

**Proof:**
Since $\lbrace 0, 1, \dots, N-1\rbrace = \mathcal{E} _ N \sqcup \mathcal{O} _ N$ and $p _ m = 0$ for $m \in \mathcal{E} _ N$ whereas $p _ m = 1$ for $m \in \mathcal{O} _ N$, we have:

$$
\sum_{m=0}^{N-1} b_m p_m = \sum_{m \in \mathcal{O}_N} b_m, \qquad \sum_{m=0}^{N-1} b_m = \sum_{m \in \mathcal{E}_N} b_m + \sum_{m \in \mathcal{O}_N} b_m
$$

Substituting both expressions and the halting condition $b _ N = -1$ (which gives $b _ N(b _ N - 1) = (-1)(-2) = 2$) into the identity of Theorem 6.1:

$$
6 \sum_{m \in \mathcal{O}_N} b_m = 4 \left( \sum_{m \in \mathcal{E}_N} b_m + \sum_{m \in \mathcal{O}_N} b_m \right) + 2N - 2
$$

Subtracting $4\sum _ {m \in \mathcal{O} _ N} b _ m$ from both sides yields $2\sum _ {m \in \mathcal{O} _ N} b _ m = 4\sum _ {m \in \mathcal{E} _ N} b _ m + 2N - 2$, and dividing by $2$ gives exactly $\sum _ {m \in \mathcal{O} _ N} b _ m = 2\sum _ {m \in \mathcal{E} _ N} b _ m + N - 1$. $\blacksquare$

## Part VII: Elimination of the Conditional (*If/Else*): The Pure Affine Algebraic Variety and the Dyadic Rigidity Theorem

### 7.1. The Antihydra Algebraic Curve in $\mathbb{Z}^2$

Theorem 7.1 (Equation of the Pure Affine Curve of Antihydra) [Proved]: A sequence of integers $\lbrace a _ n\rbrace _ {n=0}^N$ with $a _ 0 = 8$ is the true trajectory of Antihydra if and only if it satisfies at each step the conditional-free quadratic polynomial equation:

$$
(3a_n - 2a_{n+1})(3a_n - 2a_{n+1} - 1) = 0 \iff 9a_n^2 - 12a_n a_{n+1} + 4a_{n+1}^2 - 3a_n + 2a_{n+1} = 0
$$

**Proof:**
For any fixed integer $a _ n \in \mathbb{Z}$, the integers $3a _ n$ and $3a _ n - 1$ are consecutive, so that exactly one of them is divisible by $2$ in $\mathbb{Z}$. The branch whose division by $2$ is an integer coincides with $a _ {n+1} = \frac{3a _ n - (a _ n \bmod 2)}{2}$, while the false branch falls in $\mathbb{Z} + \frac{1}{2}$ and has no solution in $\mathbb{Z}$. $\blacksquare$

### 7.2. Dyadic Rigidity Theorem on the Spin Variety $u _ n$ (Prefix Uniqueness and Terminal Bifurcation)

Theorem 7.2 (Prefix Dyadic Rigidity and Terminal Ambiguity in the Spin Variety) [Proved]: For any integer horizon $N \ge 1$, let $\mathcal{V} _ N \subset \mathbb{Z}^{N+1}$ be the affine algebraic variety of all integer tuples $(u _ 0, u _ 1, \dots, u _ N) \in \mathbb{Z}^{N+1}$ such that:

$$
u_0 = 15, \qquad (2u_{n+1} - 3u_n)^2 - 1 = 0 \quad \forall n \in \lbrace 0, 1, \dots, N-1\rbrace
$$

*Then:*

1. **Parity Obstruction for Non-Terminal States:** For any $n \in \lbrace 0, 1, \dots, N-1\rbrace$, the equation $(2u _ {n+1} - 3u _ n)^2 = 1$ possesses at least one integer solution $u _ {n+1} \in \mathbb{Z}$ if and only if $u _ n$ *is **odd** (*$u _ n \equiv 1 \pmod 2$*).*
2. **Exact Uniqueness of the Prefix $(u _ 0, u _ 1, \dots, u _ {N-1})$:** At every interior step $n \in \lbrace 0, 1, \dots, N-2\rbrace$, the requirement that $u _ {n+1}$ be extendable one further step to $u _ {n+2} \in \mathbb{Z}$ forces $u _ {n+1}$ to be odd, which rules out exactly one of the two branches $\frac{3u _ n \pm 1}{2}$ and forces the sign $\sigma _ n = -\chi _ 4(u _ n)$. Consequently, the first $N$ coordinates $(u _ 0, u _ 1, \dots, u _ {N-1})$ *are **uniquely determined** and coincide with the true Antihydra trajectory* $u _ n = 2a _ n - 1$ for all $0 \le n \le N-1$.
3. **Exact Bifurcation in the Terminal Coordinate $u _ N$:** Since no equation toward a step $N+1$ within $\mathcal{V} _ N$ constrains the last state $u _ N$, the set $\mathcal{V} _ N$ *consists of **exactly two integer tuples**, which share the same prefix* $(u _ 0, \dots, u _ {N-1})$ and differ solely in that the terminal coordinate $u _ N$ may take the true odd value $u _ N^+ = \frac{3u _ {N-1} + \sigma _ {N-1}}{2} = 2a _ N - 1$ or the spurious even value $u _ N^- = \frac{3u _ {N-1} - \sigma _ {N-1}}{2} = u _ N^+ - \sigma _ {N-1}$. By contrast, in the infinite projective limit $\mathcal{V} _ \infty \subset \mathbb{Z}^{\mathbb{N} _ 0}$ (or upon adding the boundary condition $u _ N \equiv 1 \pmod 2$), the integer solution is globally unique.

**Proof by Induction and Modulo 4 Congruences:**

1. At any step $n \in \lbrace 0, \dots, N-1\rbrace$, the equation $(2u _ {n+1} - 3u _ n)^2 - 1 = 0$ in $\mathbb{Z}$ is equivalent to $2u _ {n+1} = 3u _ n + s _ n$ with $s _ n \in \lbrace -1, +1\rbrace$. Reducing modulo $2$: $0 \equiv u _ n + 1 \pmod 2 \iff u _ n \equiv 1 \pmod 2$. Therefore, if some $u _ n$ with $0 \le n \le N-1$ were even, $3u _ n \pm 1$ would be odd and no $u _ {n+1} \in \mathbb{Z}$ would exist.
2. We proceed by induction on $n \in \lbrace 0, 1, \dots, N-1\rbrace$ to prove that $u _ n = 2a _ n - 1$:

   - Base case ($n = 0$): By hypothesis, $u _ 0 = 15 = 2(8) - 1 = 2a _ 0 - 1$, which is odd.
   - Inductive step ($0 \le n \le N-2$): Suppose it is proved that $u _ n = 2a _ n - 1$ (odd). The two rational solutions of $(2u _ {n+1} - 3u _ n)^2 = 1$ are:

$$
u_{n+1}^{(+)} = \frac{3u_n + 1}{2}, \qquad u_{n+1}^{(-)} = \frac{3u_n - 1}{2} = u_{n+1}^{(+)} - 1
$$

Since $u _ n$ is odd, both $3u _ n + 1$ and $3u _ n - 1$ are even, so $u _ {n+1}^{(+)}$ and $u _ {n+1}^{(-)}$ are **two consecutive integers** in $\mathbb{Z}$. Being consecutive, exactly one of them is odd and the other is even. Since $n \le N-2$, the index $n+1$ satisfies $n+1 \le N-1$, so the equation of the next step $(2u _ {n+2} - 3u _ {n+1})^2 = 1$ requires, by part (1), that $u _ {n+1}$ be **odd**.
Specifically, for $\frac{3u _ n + s _ n}{2} \equiv 1 \pmod 2$ to hold, we require $3u _ n + s _ n \equiv 2 \pmod 4 \iff u _ n + s _ n \equiv 0 \pmod 4 \iff s _ n = -\chi _ 4(u _ n) = \sigma _ n$ (by Theorem 2.1). Thus, $u _ {n+1}$ is uniquely forced to be $u _ {n+1} = \frac{3u _ n + \sigma _ n}{2} = 2a _ {n+1} - 1$.
3. Finally, upon reaching the last step $n = N - 1$, we already have $u _ {N-1} = 2a _ {N-1} - 1$ odd. The equation $(2u _ N - 3u _ {N-1})^2 = 1$ admits in $\mathbb{Z}$ the two consecutive integers $u _ N = \frac{3u _ {N-1} \pm 1}{2}$, one odd ($2a _ N - 1$) and the other even ($2a _ N - 1 - \sigma _ {N-1}$), both valid in $\mathcal{V} _ N$ as no constraint exists at $n = N$. $\blacksquare$

## Part VIII: Adelic Space $\mathcal{E} _ S$, Local Topologies, Continuity of Operators, and Difference Transform $\Delta^L$

### 8.1. Rigorous Definition of the Adelic Space $\mathcal{E} _ S$, Topologies, and Continuity of Local Operators

**Definition 8.0 (Integral S-Adelic Phase Space $\mathcal{E} _ S$ and Metric Topologies):**
We consider the set of places $S = \lbrace 2, 3, \infty\rbrace$ of $\mathbb{Q}$ and define the integral adelic phase space:

$$
\mathcal{E}_S := \mathbb{Z}_2 \times \mathbb{Z}_3 \times \mathbb{R}
$$

endowed with the product topology induced by the three complete local metrics:

1. **2-adic component $(\mathbb{Z} _ 2, |\cdot| _ 2)$:** The compact, totally disconnected ring of 2-adic integers $\mathbb{Z} _ 2 = \varprojlim \mathbb{Z}/2^k\mathbb{Z}$, with the ultrametric norm $|x| _ 2 = 2^{-v _ 2(x)}$ ($|0| _ 2 = 0$).
2. **3-adic component $(\mathbb{Z} _ 3, |\cdot| _ 3)$:** The compact, totally disconnected ring of 3-adic integers $\mathbb{Z} _ 3 = \varprojlim \mathbb{Z}/3^k\mathbb{Z}$, with the ultrametric norm $|y| _ 3 = 3^{-v _ 3(y)}$ ($|0| _ 3 = 0$).
3. **Archimedean component $(\mathbb{R}, |\cdot| _ \infty)$:** The real line with the ordinary Euclidean absolute value.
   The ring of rational integers $\mathbb{Z}$ embeds diagonally as a discrete subring via $\iota: \mathbb{Z} \hookrightarrow \mathcal{E} _ S$, $\iota(a) = (a, a, a)$.

Proposition 8.1 (Domains of Definition and Continuity of the Local Operators) [Proved]: 

1. **2-adic Dynamical Operator $T _ 2: \mathbb{Z} _ 2 \to \mathbb{Z} _ 2$:** The parity function $p _ 2: \mathbb{Z} _ 2 \to \lbrace 0, 1\rbrace \subset \mathbb{Z} _ 2$, $p _ 2(x) = x \bmod 2$, is constant on the clopen balls $2\mathbb{Z} _ 2$ and $1 + 2\mathbb{Z} _ 2$ of radius $2^{-1}$, and is therefore continuous. For all $x \in \mathbb{Z} _ 2$, we have $3x - p _ 2(x) \in 2\mathbb{Z} _ 2$, so $T _ 2(x) = \frac{3x - p _ 2(x)}{2}$ is well-defined from $\mathbb{Z} _ 2$ into $\mathbb{Z} _ 2$. Moreover, if $|x - x'| _ 2 \le 2^{-k}$ ($k \ge 1$), then $p _ 2(x) = p _ 2(x')$ and:

$$
|T_2(x) - T_2(x')|_2 = \left|\frac{3(x - x')}{2}\right|_2 = \frac{|3|_2}{|2|_2}|x - x'|_2 = 2|x - x'|_2 \le 2^{-(k-1)}
$$

   Therefore, $T _ 2$ is **uniformly continuous** (locally $2$-Lipschitz) on $(\mathbb{Z} _ 2, |\cdot| _ 2)$.
2. **Affine Branch Operators on $\mathbb{Z} _ 3$ and Inverse Operator $S _ 3$:** Since $2 \in \mathbb{Z} _ 3^\times$ is a 3-adic unit ($|2| _ 3 = 1$, with inverse $2^{-1} = \frac{1}{2} = \sum _ {j=0}^\infty 3^j \in \mathbb{Z} _ 3$), for each fixed $p \in \lbrace 0, 1\rbrace$ the affine branch operator $T _ {3,p}: \mathbb{Z} _ 3 \to \mathbb{Z} _ 3$, $T _ {3,p}(y) = 2^{-1}(3y - p)$, is well-defined on all of $\mathbb{Z} _ 3$ and is a **strict contraction** with Lipschitz constant $\frac{1}{3}$:

$$
|T_{3,p}(y) - T_{3,p}(y')|_3 = |2^{-1} \cdot 3(y - y')|_3 = \frac{1}{3}|y - y'|_3
$$

   Conversely, on the compact open (clopen) subset of admissible states $\mathcal{U} _ 3 := 3\mathbb{Z} _ 3 \cup (1 + 3\mathbb{Z} _ 3) \subset \mathbb{Z} _ 3$, defining the continuous selector $r _ 3(y) \in \lbrace 0, 1\rbrace$ by $y \equiv r _ 3(y) \pmod{3\mathbb{Z} _ 3}$, we have $2y + r _ 3(y) \in 3\mathbb{Z} _ 3$, and the inverse operator $S _ 3: \mathcal{U} _ 3 \to \mathbb{Z} _ 3$, $S _ 3(y) = \frac{2y + r _ 3(y)}{3}$, is **uniformly continuous** ($|S _ 3(y) - S _ 3(y')| _ 3 = 3|y - y'| _ 3$ for $|y - y'| _ 3 \le 3^{-1}$).
3. **Compatibility on $\mathbb{Z}$ and Projective Matrix Representation:** For all $n \ge 0$, on the integer orbit $\iota(a _ n) = (a _ n, a _ n, a _ n)$ we have $T _ 2(a _ n) = T _ {3, p _ n}(a _ n) = a _ {n+1}$ and $S _ 3(a _ {n+1}) = a _ n$. The homogeneous step is written in matrix form in $\operatorname{GL} _ 2(\mathbb{Q} _ 2) \times \operatorname{GL} _ 2(\mathbb{Q} _ 3)$ as:

$$
\begin{pmatrix} 2^n a_n \cr 2^n \end{pmatrix} = A_{p_{n-1}} A_{p_{n-2}} \cdots A_{p_0} \begin{pmatrix} 8 \cr 1 \end{pmatrix}, \qquad A_p = \begin{pmatrix} 3 & -p \cr 0 & 2 \end{pmatrix}
$$

### 8.2. Finite-Difference Binomial Transform $\Delta^L$ (Mahler-Newton Filter)

**Theorem 8.1 (Finite-Difference Integer Identity and Exponential Annihilation** $(3/4)^m$) [Proved]: Let $\Delta$ be the forward difference operator defined on any sequence $(x _ m) _ {m \ge 0}$ by $(\Delta x) _ m = x _ {m+1} - x _ m$, and let $\Delta^0 x _ m = x _ m$, $\Delta^L x _ m = \Delta(\Delta^{L-1} x) _ m = \sum _ {j=0}^L (-1)^{L-j}\binom{L}{j} x _ {m+j}$ be its iterated powers. Then, for every order $L \ge 1$ and every instant $m \ge 0$:

1. $2^L (\Delta^L a) _ m = a _ m - \sum _ {r=0}^{L-1} 2^r (\Delta^r p) _ m$.
2. Applied to the Archimedean decomposition $a _ m = \alpha(3/2)^m + R _ m$ in $(\mathbb{R}, |\cdot| _ \infty)$, the operator $\Delta^L$ divides the exponential component by $2^L$:

$$
(\Delta^L a)_m = \alpha \frac{3^m}{2^{m+L}} + (\Delta^L R)_m
$$

   In particular, evaluated at $m = 0$ it decays with base $\frac{1}{2}$ as $(\Delta^L a) _ 0 = \alpha\left(\frac{1}{2}\right)^L + (\Delta^L R) _ 0$, whereas along the diagonal $L = m$ (at instant $m$) the leading term decays geometrically with base $\frac{3}{4} < 1$: $(\Delta^m a) _ m = \alpha\left(\frac{3}{4}\right)^m + (\Delta^m R) _ m$.

**Proof by Induction on $L \ge 1$:**

1. Base case ($L = 1$): From $2a _ {m+1} = 3a _ m - p _ m$, subtracting $2a _ m$ from both sides gives:

$$
2(\Delta a)_m = 2(a_{m+1} - a_m) = a_m - p_m = a_m - 2^0(\Delta^0 p)_m
$$

   which verifies (1) for $L = 1$.
   Inductive step ($L \to L + 1$): Suppose the identity $2^L(\Delta^L a) _ m = a _ m - \sum _ {r=0}^{L-1} 2^r(\Delta^r p) _ m$ holds for all $m \ge 0$. Applying the linear operator $\Delta$ to both sides and multiplying by $2$:

$$
2^{L+1}(\Delta^{L+1} a)_m = 2(\Delta a)_m - \sum_{r=0}^{L-1} 2^{r+1}(\Delta^{r+1} p)_m
$$

   Substituting $2(\Delta a) _ m = a _ m - p _ m = a _ m - 2^0(\Delta^0 p) _ m$ and reindexing the sum with $j = r + 1 \in \lbrace 1, \dots, L\rbrace$:

$$
2^{L+1}(\Delta^{L+1} a)_m = a_m - 2^0(\Delta^0 p)_m - \sum_{j=1}^L 2^j(\Delta^j p)_m = a_m - \sum_{j=0}^L 2^j(\Delta^j p)_m
$$

   which completes the induction.
2. For the geometric sequence $g _ m = (3/2)^m$, we have $(\Delta g) _ m = (3/2)^{m+1} - (3/2)^m = \frac{1}{2}(3/2)^m = \frac{1}{2}g _ m$. By immediate induction, $(\Delta^L g) _ m = 2^{-L} g _ m = \frac{3^m}{2^{m+L}}$. By linearity of $\Delta^L$ applied to $a _ m = \alpha g _ m + R _ m$, we obtain $(\Delta^L a) _ m = \alpha \frac{3^m}{2^{m+L}} + (\Delta^L R) _ m$. Evaluating at $m = 0$ yields $(\Delta^L a) _ 0 = \alpha\left(\frac{1}{2}\right)^L + (\Delta^L R) _ 0$, while along the diagonal $L = m$ at instant $m$ we obtain $(\Delta^m a) _ m = \alpha \frac{3^m}{2^{2m}} + (\Delta^m R) _ m = \alpha\left(\frac{3}{4}\right)^m + (\Delta^m R) _ m$. $\blacksquare$

## Part IX: Strict 3-adic Contraction, Injectivity via 2-adic Valuation of Residual Sets, and Haar Measure of the 3-adic Cantor Set

### 9.1. 3-adic Contraction Theorem and Finite Memory

**Theorem 9.1 (Strict Contraction in $\mathbb{Z} _ 3$ and Block Polynomial** $W _ {k, M}$) [Proved]: In $(\mathbb{Z} _ 3, |\cdot| _ 3)$, each branch $T _ {3,p}(x) = \frac{3x - p}{2}$ is a strict contraction by a factor of $\frac{1}{3}$. For all $k \ge 0$ and $M \ge 1$*, defining the **Bimodular Block Polynomial**:*

$$
W_{k, M} := \sum_{i=0}^{M-1} 3^{M-1-i} 2^i p_{k+i}
$$

*the following exact properties hold:*

1. **$M$-Step Block Identity:** $2^M a _ {k+M} = 3^M a _ k - W _ {k, M}$.
2. **Strict Boundedness in $[0, 3^M - 2^M]$:** $0 \le W _ {k, M} \le 3^M - 2^M < 3^M$.
3. **Bimodular Coupling Without Representative Ambiguity:**

$$
W_{k, M} = \left( -2^M a_{k+M} \right) \bmod 3^M \qquad \text{and} \qquad W_{k, M} \equiv 3^M a_k \pmod{2^M}
$$

**Complete Proof:**

1. We proceed by induction on $M \ge 1$. For $M = 1$, $W _ {k, 1} = p _ k$ and the equation $2a _ {k+1} = 3a _ k - p _ k$ is the definition of the operator. Suppose that $2^M a _ {k+M} = 3^M a _ k - W _ {k, M}$. Multiplying by $3$ and substituting $3a _ {k+M} = 2a _ {k+M+1} + p _ {k+M}$:

$$
2^M (2a_{k+M+1} + p_{k+M}) = 3^{M+1} a_k - 3W_{k, M} \implies 2^{M+1} a_{k+M+1} = 3^{M+1} a_k - \left(3W_{k, M} + 2^M p_{k+M}\right)
$$

   Since $3W _ {k, M} + 2^M p _ {k+M} = \sum _ {i=0}^{M-1} 3^{M-i} 2^i p _ {k+i} + 3^0 2^M p _ {k+M} = W _ {k, M+1}$, (1) is proved.
2. Since $p _ {k+i} \in \lbrace 0, 1\rbrace$ for all $i$, we have $W _ {k, M} \ge 0$ and:

$$
W_{k, M} \le \sum_{i=0}^{M-1} 3^{M-1-i} 2^i = 3^{M-1} \sum_{i=0}^{M-1} \left(\frac{2}{3}\right)^i = 3^{M-1} \frac{1 - (2/3)^M}{1 - 2/3} = 3^M - 2^M < 3^M
$$

3. Reducing the integer equality $W _ {k, M} = 3^M a _ k - 2^M a _ {k+M}$ modulo $3^M$, the term $3^M a _ k$ vanishes and we are left with $W _ {k, M} \equiv -2^M a _ {k+M} \pmod{3^M}$. Since by part (2) the integer $W _ {k, M}$ belongs to the canonical remainder interval $[0, 3^M - 2^M] \subset [0, 3^M - 1]$, $W _ {k, M}$ is the exact canonical remainder $(-2^M a _ {k+M}) \bmod 3^M$. Reducing the same equality modulo $2^M$, the term $-2^M a _ {k+M}$ vanishes and we obtain $W _ {k, M} \equiv 3^M a _ k \pmod{2^M}$. $\blacksquare$

### 9.2. The Base $2 \leftrightarrow$ Base $3$ Reciprocity Identity, Injectivity via 2-adic Valuation, and 3-adic Measure

**Theorem 9.2 (Base 2 $\leftrightarrow$ Base 3 Reciprocity, Injectivity of** $\mathcal{R} _ M$, and Haar Measure of the 3-adic Cantor Set) [Proved]: Let $\mu _ 3$ be the unique translation-invariant Haar probability measure on the Borel $\sigma$-algebra $\mathcal{B}(\mathbb{Z} _ 3)$ of the compact group $(\mathbb{Z} _ 3, +)$, normalized by $\mu _ 3(\mathbb{Z} _ 3) = 1$, so that every cylinder ball $c + 3^M\mathbb{Z} _ 3$ is measurable with $\mu _ 3(c + 3^M\mathbb{Z} _ 3) = 3^{-M}$. Then:

1. **Exact Reciprocity and Extinction of the Class $2 \pmod 3$:** For every step $n \ge 1$, since $3a _ {n-1} - 2a _ n = p _ {n-1} \implies a _ n \equiv -2a _ n \equiv p _ {n-1} \pmod 3$, the residue modulo $3$ of the current state $a _ n$ is identical to the binary parity bit of the previous step $a _ {n-1}$:

$$
a_n \bmod 3 = a_{n-1} \bmod 2 = p_{n-1} \in \lbrace 0, 1\rbrace \qquad \forall n \ge 1
$$

   Consequently, the residue class $a _ n \equiv 2 \pmod 3$ is permanently extinguished for all $n \ge 1$, and $O _ N = \sum _ {n=0}^{N-1} (a _ n \bmod 2) = \sum _ {n=1}^{N} (a _ n \bmod 3)$.
2. **Formal Definition, Injectivity via 2-adic Valuation, and Exact Cardinality $|\mathcal{R} _ M| = 2^M$:** For each integer $M \ge 1$, let $\Phi _ M: \lbrace 0, 1\rbrace ^M \to \mathbb{Z}$ be the polynomial map defined on binary words $\mathbf{q} = (q _ 0, q _ 1, \dots, q _ {M-1}) \in \lbrace 0, 1\rbrace ^M$ by:

$$
\Phi_M(\mathbf{q}) := \sum_{i=0}^{M-1} 3^{M-1-i} 2^i q_i \in [0, 3^M - 2^M]
$$

   and let $\Psi _ M: \lbrace 0, 1\rbrace ^M \to \mathbb{Z}/3^M\mathbb{Z}$ be the modular map $\Psi _ M(\mathbf{q}) := (-2^M)^{-1} \Phi _ M(\mathbf{q}) \bmod 3^M$*, whose image is the **set of admissible residue classes of level*** $M$*:*

$$
\mathcal{R}_M := \operatorname{Im}(\Psi_M) = \left\lbrace (-2^M)^{-1} \Phi_M(\mathbf{q}) \bmod 3^M : \mathbf{q} \in \lbrace 0, 1\rbrace ^M \right\rbrace \subset \mathbb{Z}/3^M\mathbb{Z}
$$

   Then $\Phi _ M$ and $\Psi _ M$ *are **strictly injective**, and the cardinality of* $\mathcal{R} _ M$ *is exactly:*

$$
|\mathcal{R}_M| = 2^M \quad \text{(of the } 3^M \text{ possible congruence classes in } \mathbb{Z}/3^M\mathbb{Z}\text{)}
$$

   with $(a _ n \bmod 3^M) \in \mathcal{R} _ M$ holding for all $n \ge M$.
3. **3-adic Haar Measure vs. Cardinality of the Cylinder Sets $\mathcal{C} _ M$ and the Limit $\mathcal{C} _ \infty \subset \mathbb{Z} _ 3$:** Let $\pi _ M: \mathbb{Z} _ 3 \to \mathbb{Z}/3^M\mathbb{Z}$ be the continuous canonical projection. We define the compact open (clopen) cylinder of level $M$ in $\mathbb{Z} _ 3$ as $\mathcal{C} _ M := \pi _ M^{-1}(\mathcal{R} _ M) = \bigsqcup _ {r \in \mathcal{R} _ M} (r + 3^M\mathbb{Z} _ 3)$ and the 3-adic Cantor Set as the decreasing intersection $\mathcal{C} _ \infty := \bigcap _ {M=1}^\infty \mathcal{C} _ M \subset \mathbb{Z} _ 3$. Then:

   - **Haar Measure:** Since $\mathcal{C} _ M$ is the disjoint union of $|\mathcal{R} _ M| = 2^M$ balls of measure $3^{-M}$, its measure is $\mu _ 3(\mathcal{C} _ M) = 2^M \cdot 3^{-M} = (2/3)^M$. By upper continuity of the Borel measure on the nested sequence $\mathcal{C} _ {M+1} \subset \mathcal{C} _ M$:

$$
\mu_3(\mathcal{C}_\infty) = \lim_{M \to \infty} \mu_3(\mathcal{C}_M) = \lim_{M \to \infty} \left(\frac{2}{3}\right)^M = 0
$$

   - **Asymptotic Density in $\mathbb{Z}$:** For each fixed $M \ge 1$, the periodic set of ordinary integers $\mathcal{C} _ M \cap \mathbb{Z}$ consists of $2^M$ classes modulo $3^M$, and therefore has natural (asymptotic) density in $\mathbb{Z}$ equal to $(2/3)^M$.
   - **Cardinality:** Whereas the tail of the integer trajectory $\lbrace a _ n\rbrace _ {n \ge M} \subset \mathcal{C} _ M \cap \mathbb{Z}$ is a countably infinite set ($\operatorname{card} = \aleph _ 0$), the 3-adic limit set $\mathcal{C} _ \infty = \varprojlim \mathcal{R} _ M \cong \lbrace 0, 1\rbrace ^{\mathbb{N} _ 0}$ is homeomorphic to the ternary Cantor space and has the cardinality of the continuum ($\operatorname{card}(\mathcal{C} _ \infty) = 2^{\aleph _ 0} = \mathfrak{c}$), despite having zero Haar measure $\mu _ 3(\mathcal{C} _ \infty) = 0$.

**Rigorous Proof of Part (2) (Injectivity of $\Phi _ M$ and $\Psi _ M$ via 2-adic Valuation):**
Let $\mathbf{q} = (q _ 0, \dots, q _ {M-1}) \in \lbrace 0, 1\rbrace ^M$ and $\mathbf{q}' = (q _ 0', \dots, q _ {M-1}') \in \lbrace 0, 1\rbrace ^M$ be two distinct binary sequences ($\mathbf{q} \neq \mathbf{q}'$), and let $W = \Phi _ M(\mathbf{q})$ and $W' = \Phi _ M(\mathbf{q}')$.

1. **Injectivity in $\mathbb{Z}$ via 2-adic valuation:** Since $\mathbf{q} \neq \mathbf{q}'$, there exists a smallest index $i _ 0 \in \lbrace 0, 1, \dots, M-1\rbrace$ such that $q _ {i _ 0} \neq q _ {i _ 0}'$ (while $q _ i = q _ i'$ for all $0 \le i < i _ 0$). Subtracting $W$ and $W'$, all terms with $0 \le i < i _ 0$ cancel identically:

$$
W - W' = 3^{M-1-i_0} 2^{i_0} (q_{i_0} - q_{i_0}') + \sum_{i = i_0 + 1}^{M-1} 3^{M-1-i} 2^i (q_i - q_i')
$$

   Factoring out the common factor $2^{i _ 0}$, we may write:

$$
W - W' = 2^{i_0} \left[ 3^{M-1-i_0}(q_{i_0} - q_{i_0}') + 2 \sum_{i = i_0 + 1}^{M-1} 3^{M-1-i} 2^{i - 1 - i_0}(q_i - q_i') \right] = 2^{i_0} \left( 3^{M-1-i_0}(\pm 1) + 2t \right)
$$

   where $t \in \mathbb{Z}$ is an integer and $q _ {i _ 0} - q _ {i _ 0}' \in \lbrace -1, +1\rbrace$. Since $3^{M-1-i _ 0}$ is odd, the parenthesized factor $3^{M-1-i _ 0}(\pm 1) + 2t \equiv 1 \pmod 2$ is an **odd integer** (hence non-zero). Consequently, the exact 2-adic valuation of the difference is:

$$
v_2(W - W') = i_0 < \infty \implies W - W' \neq 0 \implies W \neq W'
$$

   Therefore, $\Phi _ M$ is injective in $\mathbb{Z}$.
2. **Passage from equality modulo $3^M$ to equality in $\mathbb{Z}$:** Suppose now that $\Psi _ M(\mathbf{q}) \equiv \Psi _ M(\mathbf{q}') \pmod{3^M}$, that is:

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

   This proves that $\Psi _ M: \lbrace 0, 1\rbrace ^M \to \mathbb{Z}/3^M\mathbb{Z}$ is injective, and since the domain $\lbrace 0, 1\rbrace ^M$ has $2^M$ elements, we conclude that $|\mathcal{R} _ M| = |\operatorname{Im}(\Psi _ M)| = 2^M$. $\blacksquare$

