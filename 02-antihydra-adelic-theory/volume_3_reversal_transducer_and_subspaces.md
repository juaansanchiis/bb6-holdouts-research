# Antihydra Treatise — Volume 3: Time Reversal, Koopman Subspaces & Ternary Symbolic Dynamics (Parts X–XIV)

## Part X: Unambiguous Time Reversal via Ternary Ceilings and Fractional Representation

### 10.1. Exact Time Reversal Theorem (Absence of Past Branching)

Theorem 10.1 (Time Reversal Formula via Ceiling Function) [Proved]: For any integers $n \ge M \ge 1$, the state of Antihydra $M$ steps in the past is recovered exactly and uniquely from the present state $a _ n$ via:

$$
a_{n-M} = \left\lceil \left(\frac{2}{3}\right)^M a_n \right\rceil
$$

**Proof:**
By Theorem 9.1(1) and (2) with $k = n - M$, we have $3^M a _ {n-M} = 2^M a _ n + W _ {n-M, M}$ with $0 \le W _ {n-M, M} \le 3^M - 2^M < 3^M$. Dividing by $3^M$ yields $0 \le a _ {n-M} - (2/3)^M a _ n = \frac{W _ {n-M, M}}{3^M} < 1$. Since $a _ {n-M} \in \mathbb{Z}$, it is identically equal to $\lceil (2/3)^M a _ n \rceil$. $\blacksquare$

### 10.2. Exact 3-adic Fractional Representation of $O _ N$ and $b _ N$

Theorem 10.2 (Sum of 3-adic Fractional Parts Formula) [Proved]: For all $N \ge 1$ and all $j \in \lbrace 1, 2, \dots, N\rbrace$, let us define the normalized fractional residue in base $3$ as:

$$
\theta_j(a_N) := \left\lbrace -\left(\frac{2}{3}\right)^j a_N \right\rbrace = \frac{(-2^j a_N) \bmod 3^j}{3^j} = \frac{W_{N-j, j}}{3^j} \in \left[0, \thinspace  1 - \left(\frac{2}{3}\right)^j\right]
$$

Then the odd-step accumulator $O _ N$ and the halting counter $b _ N$ satisfy exactly and unconditionally:

$$
O_N = 3\theta_N(a_N) + \sum_{j=1}^{N-1} \theta_j(a_N)
$$

$$
b_N = 2N - 9\theta_N(a_N) - 3 \sum_{j=1}^{N-1} \theta_j(a_N)
$$

**Complete Proof:**

1. By Theorem 9.1(1) applied with $k = N - j$ and horizon $j \in \lbrace 1, \dots, N\rbrace$, we have:

$$
3^j a_{N-j} - 2^j a_N = W_{N-j, j} \in [0, 3^j - 2^j]
$$

   Dividing both sides by $3^j$:

$$
a_{N-j} - \left(\frac{2}{3}\right)^j a_N = \frac{W_{N-j, j}}{3^j} \in \left[0, \thinspace  1 - \left(\frac{2}{3}\right)^j\right] \subset [0, 1)
$$

   Since $a _ {N-j} \in \mathbb{Z}$, the difference $a _ {N-j} - (2/3)^j a _ N \in [0, 1)$ coincides exactly with the fractional part of $-(2/3)^j a _ N$:

$$
\theta_j(a_N) = \left\lbrace -\left(\frac{2}{3}\right)^j a_N \right\rbrace = \frac{W_{N-j, j}}{3^j} = a_{N-j} - \left(\frac{2}{3}\right)^j a_N \qquad (\forall j \in \lbrace 1, \dots, N\rbrace )
$$

2. From the definition of $W _ {N-j, j} = \sum _ {i=0}^{j-1} 3^{j-1-i} 2^i p _ {N-j+i}$, we observe the recurrence relation between $\theta _ j(a _ N)$ and $\theta _ {j-1}(a _ N)$ (with the convention $\theta _ 0(a _ N) := 0$):
   Substituting $a _ {N-j+1} = (2/3)^{j-1} a _ N + \theta _ {j-1}(a _ N)$ and $a _ {N-j} = (2/3)^j a _ N + \theta _ j(a _ N)$ into the step equation $3a _ {N-j} - 2a _ {N-j+1} = p _ {N-j}$:

$$
3\left(\left(\frac{2}{3}\right)^j a_N + \theta_j(a_N)\right) - 2\left(\left(\frac{2}{3}\right)^{j-1} a_N + \theta_{j-1}(a_N)\right) = p_{N-j}
$$

   The terms involving $a _ N$ cancel identically ($3(2/3)^j a _ N - 2(2/3)^{j-1} a _ N = 0$), leaving for all $j \in \lbrace 1, 2, \dots, N\rbrace$ the clean identity:

$$
p_{N-j} = 3\theta_j(a_N) - 2\theta_{j-1}(a_N)
$$

3. Summing this identity from $j = 1$ to $N$ (with $\theta _ 0(a _ N) = 0$):

$$
O_N = \sum_{j=1}^{N} p_{N-j} = 3\sum_{j=1}^{N} \theta_j(a_N) - 2\sum_{j=1}^{N-1} \theta_j(a_N) = 3\theta_N(a_N) + \sum_{j=1}^{N-1} \theta_j(a_N)
$$

   Finally, substituting $O _ N$ into $b _ N = 2N - 3O _ N$, we immediately obtain $b _ N = 2N - 9\theta _ N(a _ N) - 3\sum _ {j=1}^{N-1} \theta _ j(a _ N)$. $\blacksquare$

## Part XI: Arithmetic Kirchhoff Equations, Telescoping Proof of $b _ N$, Koopman-Walsh Subspaces, and Infinite Family of Cycles in $\mathbb{Z} _ 2$

### 11.1. Flow Conservation Theorem on the 2-adic Tree and Complete Proof of the Formula for $b _ N$

For every level $L \ge 1$ and every residue $r \in \lbrace 0, 1, \dots, 2^L - 1\rbrace$, let the class occupancy counter up to time $N-1$ be:

$$
C_r^{(L)}(N) := \sum_{n=0}^{N-1} \mathbf{1}_{a_n \equiv r \pmod{2^L}}
$$

**Theorem 11.1 (Arithmetic Kirchhoff Law, Pole Anchoring, and Telescoping Formula for** $b _ N$) [Proved]: Each class $r \in \mathbb{Z}/2^L\mathbb{Z}$ possesses a unique even preimage $s _ 0(r, L) = 2(3^{-1} r \bmod 2^L)$ and a unique odd preimage $s _ 1(r, L) = 2(3^{-1}(r - 1) \bmod 2^L) + 1$ in $\mathbb{Z}/2^{L+1}\mathbb{Z}$, satisfying for all $N \ge 1$:

$$
C_r^{(L)}(N) = C_r^{(L+1)}(N) + C_{r + 2^L}^{(L+1)}(N) = C_{s_0(r, L)}^{(L+1)}(N) + C_{s_1(r, L)}^{(L+1)}(N) - \delta_r^{(L)}(N)
$$

where the boundary defect is $\delta _ r^{(L)}(N) := \mathbf{1} _ {a _ N \equiv r \pmod{2^L}} - \mathbf{1} _ {a _ 0 \equiv r \pmod{2^L}}$. Consequently, for all $N \ge 1$ and every level $M \ge 4$ (in particular for $2^M > a _ N$):

1. At $L = 1$ (with $a _ 0 = 8 \equiv 0 \pmod 2$ and $\delta _ 1^{(1)}(N) = p _ N - 0 = p _ N$), for the odd pole $r = 1$ we have $s _ 0(1, 1) = 2$ and $s _ 1(1, 1) = 1$, whence:

$$
C_2^{(2)}(N) - C_3^{(2)}(N) = p_N
$$

2. For the odd pole $r = 1$ at any level $L \ge 2$, since $a _ 0 = 8 \equiv 0 \not\equiv 1 \pmod{2^L}$, we have $\delta _ 1^{(L)}(N) = \mathbf{1} _ {a _ N \equiv 1 \pmod{2^L}}$ and $s _ 1(1, L) = 1$, which induces the exact telescoping cancellation:

$$
C_{1 + 2^L}^{(L+1)}(N) = C_{s_0(1, L)}^{(L+1)}(N) - \mathbf{1}_{a_N \equiv 1 \pmod{2^L}} \qquad (\forall L \ge 2)
$$

3. The counter $b _ N = 2E _ N - O _ N$ satisfies for all $M \ge 2$ the exact closed-form identity:

$$
b_N = 2C_0^{(2)}(N) + C_3^{(2)}(N) - \sum_{L=2}^{M-1} C_{s_0(1, L)}^{(L+1)}(N) - C_1^{(M)}(N) + 2p_N + \sum_{L=2}^{M-1} \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

   Moreover, since $a _ n \ge a _ 0 = 8 > 1$ for all $n \ge 0$, if one chooses any horizon $M \ge 4$ such that $2^M > a _ N$ (whereby no $a _ n$ with $0 \le n < N$ can satisfy $a _ n \equiv 1 \pmod{2^M}$, as $a _ n \ge 8 > 1$ and $a _ n < a _ N < 2^M$), the residual term vanishes identically ($C _ 1^{(M)}(N) = 0$), leaving:

$$
b_N = 2C_0^{(2)}(N) + C_3^{(2)}(N) - \sum_{L=2}^{M-1} C_{s_0(1, L)}^{(L+1)}(N) + 2p_N + \sum_{L=2}^{M-1} \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

**Complete Step-by-Step Proof:**

1. **Kirchhoff flow equation:** On the one hand, each class modulo $2^L$ splits into two classes modulo $2^{L+1}$, so $C _ r^{(L)}(N) = C _ r^{(L+1)}(N) + C _ {r + 2^L}^{(L+1)}(N)$. On the other hand, for each $0 \le n \le N-1$, we have $a _ {n+1} \equiv r \pmod{2^L} \iff a _ n \equiv s _ 0(r, L) \pmod{2^{L+1}}$ (if $a _ n$ is even) or $a _ n \equiv s _ 1(r, L) \pmod{2^{L+1}}$ (if $a _ n$ is odd). Therefore:

$$
\sum_{n=0}^{N-1} \mathbf{1}_{a_{n+1} \equiv r \pmod{2^L}} = C_{s_0(r, L)}^{(L+1)}(N) + C_{s_1(r, L)}^{(L+1)}(N)
$$

   Since $\sum _ {n=0}^{N-1} \mathbf{1} _ {a _ {n+1} \equiv r \pmod{2^L}} = C _ r^{(L)}(N) + \mathbf{1} _ {a _ N \equiv r \pmod{2^L}} - \mathbf{1} _ {a _ 0 \equiv r \pmod{2^L}} = C _ r^{(L)}(N) + \delta _ r^{(L)}(N)$, solving for $C _ r^{(L)}(N)$ proves the master equation.
2. **Case $L = 1, r = 1$:** Since $3^{-1} \equiv 1 \pmod 2$, $s _ 0(1, 1) = 2(1) = 2$ and $s _ 1(1, 1) = 2(0) + 1 = 1$. Moreover, $a _ 0 = 8 \equiv 0 \pmod 2$ and $\mathbf{1} _ {a _ N \equiv 1 \pmod 2} = p _ N$, so $\delta _ 1^{(1)}(N) = p _ N$. Equating both decompositions of $O _ N = C _ 1^{(1)}(N)$:

$$
C_1^{(2)}(N) + C_3^{(2)}(N) = C_2^{(2)}(N) + C_1^{(2)}(N) - p_N \implies C_2^{(2)}(N) = C_3^{(2)}(N) + p_N
$$

3. **Telescoping at the pole $r = 1$ for $L \ge 2$:** For $r = 1$, the odd preimage is always $s _ 1(1, L) = 2(3^{-1}(0) \bmod 2^L) + 1 = 1$. Furthermore, since $a _ 0 = 8$ is even, $\mathbf{1} _ {a _ 0 \equiv 1 \pmod{2^L}} = 0$ for all $L \ge 1$, so $\delta _ 1^{(L)}(N) = \mathbf{1} _ {a _ N \equiv 1 \pmod{2^L}}$. Equating the fiber partition with the preimage equation for $r = 1$:

$$
C_1^{(L)}(N) = C_1^{(L+1)}(N) + C_{1 + 2^L}^{(L+1)}(N) = C_{s_0(1, L)}^{(L+1)}(N) + C_1^{(L+1)}(N) - \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

   From this follows the recursive relation for $C _ 1^{(L)}(N)$:

$$
C_1^{(L)}(N) - C_1^{(L+1)}(N) = C_{1 + 2^L}^{(L+1)}(N) = C_{s_0(1, L)}^{(L+1)}(N) - \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

   Summing telescopically from $L = 2$ to $M - 1$:

$$
C_1^{(2)}(N) - C_1^{(M)}(N) = \sum_{L=2}^{M-1} C_{s_0(1, L)}^{(L+1)}(N) - \sum_{L=2}^{M-1} \mathbf{1}_{a_N \equiv 1 \pmod{2^L}}
$$

4. **Substitution into $b _ N = 2E _ N - O _ N$:** Since $E _ N = C _ 0^{(1)}(N) = C _ 0^{(2)}(N) + C _ 2^{(2)}(N)$ and $O _ N = C _ 1^{(1)}(N) = C _ 1^{(2)}(N) + C _ 3^{(2)}(N)$, we substitute $C _ 2^{(2)}(N) = C _ 3^{(2)}(N) + p _ N$:

$$
b_N = 2\left(C_0^{(2)}(N) + C_3^{(2)}(N) + p_N\right) - \left(C_1^{(2)}(N) + C_3^{(2)}(N)\right) = 2C_0^{(2)}(N) + C_3^{(2)}(N) + 2p_N - C_1^{(2)}(N)
$$

   Substituting the telescoping expression for $C _ 1^{(2)}(N)$ proved in step (3) yields the exact formula of the statement. Finally, if $2^M > a _ N$, since $8 = a _ 0 \le a _ n < a _ N < 2^M$ for all $0 \le n < N$, we have $C _ 1^{(M)}(N) = 0$. $\blacksquare$

### 11.2. Koopman-Walsh Detail Subspaces and Infinite Family of Periodic Cycles in $\mathbb{Z} _ 2$ vs. $\mathbb{Z}$

**Theorem 11.2 (Haar-Walsh Detail Subspace** $\mathcal{W} _ L$ and Koopman Action) [Proved]: Let $\mathcal{H} _ L := \mathcal{F}(\mathbb{Z}/2^L\mathbb{Z}, \mathbb{C})$ be the Hilbert space of all complex-valued functions on $\mathbb{Z}/2^L\mathbb{Z}$ ($L \ge 1$) equipped with the inner product $\langle f, g \rangle = 2^{-L}\sum _ {a=0}^{2^L-1} f(a)\overline{g(a)}$, of dimension $\dim _ {\mathbb{C}}(\mathcal{H} _ L) = 2^L$. For each residue $v \in \lbrace 0, 1, \dots, 2^{L-1}-1\rbrace$, we define the level $L$ detail wavelet:

$$
w_v^{(L)}(a) := (-1)^{\lfloor (a \bmod 2^L)/2^{L-1} \rfloor} \thinspace \mathbf{1}_{a \equiv v \pmod{2^{L-1}}}
$$

1. **Basis of the Detail Subspace $\mathcal{W} _ L$ (Dimension $2^{L-1}$):** The $2^{L-1}$ functions $\lbrace w _ v^{(L)}\rbrace _ {v=0}^{2^{L-1}-1}$ form an orthogonal basis of the **level $L$ detail subspace**, $\mathcal{W} _ L := \operatorname{span} _ {\mathbb{C}}\lbrace w _ v^{(L)} : 0 \le v < 2^{L-1}\rbrace$, with $\langle w _ v^{(L)}, w _ {v'}^{(L)} \rangle = 2^{-(L-1)}\delta _ {v,v'}$ and $\dim _ {\mathbb{C}}(\mathcal{W} _ L) = 2^{L-1}$. The full space decomposes as $\mathcal{H} _ L = \operatorname{span}\lbrace \mathbf{1}\rbrace \oplus \bigoplus _ {\ell=1}^{L} \mathcal{W} _ \ell$.
2. **Level Ascent and Fiber Bifurcation under the Koopman Operator $\mathcal{K}$:** For every $w _ v^{(L)} \in \mathcal{W} _ L$, the function $(\mathcal{K}w _ v^{(L)})(a) := w _ v^{(L)}(T(a))$ belongs to $\mathcal{W} _ {L+1}$ and expands into exactly two preimage fibers (the even one $s _ 0(v, L-1)$ and the odd one $s _ 1(v, L-1)$ modulo $2^L$):

$$
\mathcal{K}w_v^{(L)} = \varepsilon_0(v) w_{s_0(v, L-1)}^{(L+1)} + \varepsilon_1(v) w_{s_1(v, L-1)}^{(L+1)} \in \mathcal{W}_{L+1}
$$

   where $\varepsilon _ 0(v), \varepsilon _ 1(v) \in \lbrace -1, +1\rbrace$ are the signs given by $(-1)^{\lfloor (T(s _ i(v, L-1)) \bmod 2^L)/2^{L-1} \rfloor}$.

**Complete Proof of Theorem 11.2:**

1. For each $v \in \lbrace 0, \dots, 2^{L-1}-1\rbrace$, the only elements of $\mathbb{Z}/2^L\mathbb{Z}$ congruent to $v \pmod{2^{L-1}}$ are $a _ 0 = v$ (where $\lfloor v/2^{L-1} \rfloor = 0 \implies w _ v^{(L)}(v) = +1$) and $a _ 1 = v + 2^{L-1}$ (where $\lfloor (v+2^{L-1})/2^{L-1} \rfloor = 1 \implies w _ v^{(L)}(v+2^{L-1}) = -1$). Therefore, for $v \neq v'$ the supports $\lbrace v, v+2^{L-1}\rbrace$ and $\lbrace v', v'+2^{L-1}\rbrace$ are disjoint, which implies $\langle w _ v^{(L)}, w _ {v'}^{(L)} \rangle = 0$; and for $v = v'$, $\langle w _ v^{(L)}, w _ v^{(L)} \rangle = 2^{-L}(1^2 + (-1)^2) = 2^{-(L-1)} \neq 0$. Being orthogonal and nonzero, the $2^{L-1}$ functions are linearly independent and span $\mathcal{W} _ L$ of dimension $2^{L-1}$. Furthermore, every function $f \in \mathcal{H} _ L$ decomposes uniquely on each fiber $\lbrace v, v+2^{L-1}\rbrace$ as the sum of its mean $\frac{f(v)+f(v+2^{L-1})}{2} \in \mathcal{H} _ {L-1}$ and its half-difference $\frac{f(v)-f(v+2^{L-1})}{2} w _ v^{(L)} \in \mathcal{W} _ L$, proving by induction that $\mathcal{H} _ L = \operatorname{span}\lbrace \mathbf{1}\rbrace \oplus \bigoplus _ {\ell=1}^L \mathcal{W} _ \ell$.
2. Let $a \in \lbrace 0, \dots, 2^L - 1\rbrace$. Since $L \ge 1$, $(a + 2^L) \bmod 2 = a \bmod 2 = p$, hence:

$$
T(a + 2^L) = \frac{3(a + 2^L) - p}{2} = T(a) + 3 \cdot 2^{L-1} \equiv T(a) + 2^{L-1} \pmod{2^L}
$$

   Consequently, $T(a + 2^L) \equiv T(a) \pmod{2^{L-1}}$, while the $(L-1)$-th bit of $T(a)$ is flipped upon adding $2^{L-1} \pmod{2^L}$, which implies:

$$
(\mathcal{K}w_v^{(L)})(a + 2^L) = w_v^{(L)}(T(a + 2^L)) = -w_v^{(L)}(T(a)) = -(\mathcal{K}w_v^{(L)})(a)
$$

   Thus, on each fiber $\lbrace a, a+2^L\rbrace$ of $\mathbb{Z}/2^{L+1}\mathbb{Z}$ over $\mathbb{Z}/2^L\mathbb{Z}$, the function $\mathcal{K}w _ v^{(L)}$ takes opposite values (zero mean), so it belongs to $\mathcal{W} _ {L+1}$. Finally, $(\mathcal{K}w _ v^{(L)})(a) \neq 0 \iff T(a) \equiv v \pmod{2^{L-1}} \iff a \equiv s _ 0(v, L-1) \pmod{2^L}$ or $a \equiv s _ 1(v, L-1) \pmod{2^L}$. Evaluating at the representatives $a = s _ i(v, L-1) \in \lbrace 0, \dots, 2^L-1\rbrace$ (where $w _ {s _ i(v, L-1)}^{(L+1)}(s _ i(v, L-1)) = +1$), the coefficient is exactly $\varepsilon _ i(v) = w _ v^{(L)}(T(s _ i(v, L-1))) = (-1)^{\lfloor (T(s _ i(v, L-1)) \bmod 2^L)/2^{L-1} \rfloor}$. $\blacksquare$

**Theorem 11.3 (Classification of Periodic Cycles in $\mathbb{Z} _ 2$ vs. $\mathbb{Z}$ and Infinite Family of Cycles of Minimal Period** $m$) [Proved]: 

1. **Rational Formula for Periodic Points in $\mathbb{Z} _ 2$:** Every periodic point $x _ 0 \in \mathbb{Z} _ 2$ of period $m \ge 1$ under $T _ 2(x) = \frac{3x - (x \bmod 2)}{2}$ with parity word $(p _ 0, \dots, p _ {m-1}) \in \lbrace 0, 1\rbrace ^m$ satisfies $2^m x _ 0 = 3^m x _ 0 - W$, so it is necessarily a rational number with odd denominator belonging to $[0, 1] \cap \mathbb{Q}$:

$$
x_0 = \frac{W}{3^m - 2^m} \in \mathbb{Z}_2 \cap [0, 1] \cap \mathbb{Q}, \qquad \text{where } W = \sum_{j=0}^{m-1} 3^{m-1-j} 2^j p_j \in [0, 3^m - 2^m]
$$

2. **Explicit Infinite Family of Non-Integer Rational Cycles in $\mathbb{Z} _ 2$ of Minimal Period $m \ge 2$:** For each integer $m \ge 2$, let us define the rational number:

$$
x_0^{(m)} := \frac{2^{m-1}}{3^m - 2^m} \in (0, 1) \cap \mathbb{Q}
$$

   Then $x _ 0^{(m)} \in \mathbb{Z} _ 2 \setminus \mathbb{Z}$, and its orbit under $T _ 2$ is given for $0 \le k \le m-1$ by:

$$
x_k^{(m)} = T_2^k(x_0^{(m)}) = \frac{3^k 2^{m-1-k}}{3^m - 2^m} \in \mathbb{Z}_2 \setminus \mathbb{Z}
$$

   which follows the exact parity word $(p _ 0, p _ 1, \dots, p _ {m-2}, p _ {m-1}) = (\underbrace{0, 0, \dots, 0} _ {m-1\text{ zeros}}, 1)$, returns to $T _ 2^m(x _ 0^{(m)}) = x _ 0^{(m)}$*, and has **exact minimal period equal to*** $m$*. Consequently, for distinct values of* $m \ge 2$ *these orbits are disjoint and there exist **infinitely many distinct non-integer rational periodic cycles** in* $\mathbb{Z} _ 2$ (with $m = 2$ being the special case $\frac{2}{5} \leftrightarrow \frac{3}{5}$).
3. **Uniqueness of the Fixed Points $\lbrace 0, 1\rbrace$ in the Ordinary Integers $\mathbb{Z}$:** Restricting the domain to the ordinary integers $\mathbb{Z} \subset \mathbb{Z} _ 2$, since every periodic point satisfies $x _ 0 \in [0, 1]$ and $\mathbb{Z} \cap [0, 1] = \lbrace 0, 1\rbrace$*, the **only periodic cycles in*** $\mathbb{Z}$ are the two trivial fixed points $x _ 0 = 0$ ($W = 0$) and $x _ 0 = 1$ ($W = 3^m - 2^m$), which are inaccessible from $a _ 0 = 8$ because the integer orbit is strictly increasing ($a _ {n+1} > a _ n \ge 8$).

**Complete Proof of Part (2) (Algebraic Verification of the Infinite Family $x _ 0^{(m)}$):**
Let $m \ge 2$ be fixed and let $D _ m := 3^m - 2^m$.

1. **Membership in $\mathbb{Z} _ 2 \setminus \mathbb{Z}$:** Since $m \ge 2$, $3^m$ is odd and $2^m$ is even, so the denominator $D _ m = 3^m - 2^m \equiv 1 - 0 \equiv 1 \pmod 2$ is strictly **odd**. Therefore, $D _ m \in \mathbb{Z} _ 2^\times$ is invertible in $\mathbb{Z} _ 2$ (with $D _ m^{-1} \equiv 1 \pmod 2$), which guarantees that $x _ k^{(m)} = \frac{3^k 2^{m-1-k}}{D _ m} \in \mathbb{Z} _ 2$ for all $0 \le k \le m-1$. Furthermore, for $m \ge 2$ we have $3^m - 2^m \ge 9 - 4 = 5 > 0$ and, for all $0 \le k \le m-1$:

$$
0 < 3^k 2^{m-1-k} \le 3^{m-1} < 3^m - 2^m \quad (\text{since } 2 \cdot 3^{m-1} + 2^m \le 2 \cdot 3^{m-1} + 3^{m-1} = 3^m)
$$

   Hence $0 < x _ k^{(m)} < 1$, which proves that $x _ k^{(m)} \notin \mathbb{Z}$ for all $0 \le k \le m-1$.
2. **Exact parities and evolution during the first $m-1$ steps ($0 \le k \le m-2$):** In $\mathbb{Z} _ 2$, since $D _ m^{-1} \equiv 1 \pmod 2$, the 2-adic parity of a fraction $\frac{N}{D _ m}$ coincides with the parity of the integer numerator $N$:

$$
p_2\left(\frac{N}{D_m}\right) = (N \cdot D_m^{-1}) \bmod 2 = N \bmod 2
$$

   For $0 \le k \le m-2$, the exponent of $2$ in the numerator $N _ k = 3^k 2^{m-1-k}$ satisfies $m - 1 - k \ge 1$, so $N _ k$ is **even** and $p _ 2(x _ k^{(m)}) = 0$. Applying the even branch $T _ 0(x) = \frac{3x}{2}$ by induction from $k = 0$ to $k = m-2$:

$$
T_2(x_k^{(m)}) = \frac{3}{2} \left(\frac{3^k 2^{m-1-k}}{3^m - 2^m}\right) = \frac{3^{k+1} 2^{m-1-(k+1)}}{3^m - 2^m} = x_{k+1}^{(m)}
$$

3. **Final step ($k = m - 1$) and cycle closure:** Upon reaching $k = m - 1$, the state is:

$$
x_{m-1}^{(m)} = \frac{3^{m-1} 2^0}{3^m - 2^m} = \frac{3^{m-1}}{3^m - 2^m}
$$

   Whose numerator $N _ {m-1} = 3^{m-1}$ is **odd**, so $p _ 2(x _ {m-1}^{(m)}) = 1$. Applying the odd branch $T _ 1(x) = \frac{3x - 1}{2}$:

$$
T_2(x_{m-1}^{(m)}) = \frac{3\left(\frac{3^{m-1}}{3^m - 2^m}\right) - 1}{2} = \frac{3^m - (3^m - 2^m)}{2(3^m - 2^m)} = \frac{2^m}{2(3^m - 2^m)} = \frac{2^{m-1}}{3^m - 2^m} = x_0^{(m)}
$$

   which proves that $T _ 2^m(x _ 0^{(m)}) = x _ 0^{(m)}$.
4. **Minimality of period $m$:** In a complete cycle of $m$ steps $\lbrace x _ 0^{(m)}, x _ 1^{(m)}, \dots, x _ {m-1}^{(m)}\rbrace$, the parity bit equals $0$ exactly $m-1$ times (for $0 \le k \le m-2$) and equals $1$ **only once** (at $k = m-1$). Since in $\mathbb{R}$ the finite sequence $x _ 0^{(m)} < x _ 1^{(m)} < \dots < x _ {m-1}^{(m)}$ is strictly increasing (as $x _ {k+1}^{(m)} = \frac{3}{2}x _ k^{(m)} > x _ k^{(m)}$ for $0 \le k \le m-2$), the $m$ elements $\lbrace x _ 0^{(m)}, \dots, x _ {m-1}^{(m)}\rbrace$ are all pairwise distinct. Therefore, the minimal period of $x _ 0^{(m)}$ is exactly $m$, and for $m \neq m'$ the associated cycles have different cardinalities and are disjoint. $\blacksquare$

## Part XII: The Ternary Ceiling Chain Criterion $Y _ j$, the Corrected Autocorrelation Invariant ($+4X^2$), and the Sieve $\Psi(P _ K) \equiv 18 \pmod{36}$

### 12.1. Complete Characterization Theorem of a Final State $X = a _ N$ (With Exact Range $0 \le j \le N-1$)

Theorem 12.1 (Ternary Ceiling Chain Criterion and Autocorrelation Invariant) [Proved]: A positive integer $X \in \mathbb{Z}^+$ is equal to the state $a _ N$ of Antihydra (with seed $a _ 0 = 8$ and $N \ge 1$) if and only if the finite reverse sequence of $N + 1$ terms $(Y _ 0, Y _ 1, \dots, Y _ N)$ defined by $Y _ 0 = X$ and the recurrence:

$$
Y_{j+1} = \left\lceil \frac{2}{3} Y_j \right\rceil \qquad \text{for } j \in \lbrace 0, 1, \dots, N-1\rbrace
$$

*simultaneously satisfies:*

1. **Boundary Condition:** $Y _ N = 8$.
2. **3-adic Cantor Condition:** $r _ j := Y _ j \bmod 3 \in \lbrace 0, 1\rbrace$ (that is, $Y _ j \not\equiv 2 \pmod 3$) for all $j \in \lbrace 0, 1, \dots, N - 1\rbrace$.

Over any admissible chain $(Y _ 0, \dots, Y _ N)$:

- For all $j \in \lbrace 0, 1, \dots, N-1\rbrace$, the ceiling function is eliminated exactly via the inverse linear law:

$$
3Y_{j+1} - 2Y_j = r_j = p_{N-1-j} \in \lbrace 0, 1\rbrace
$$

  *which is equivalent to the **Dual Affine Algebraic Curve*** $(3Y _ {j+1} - 2Y _ j)(3Y _ {j+1} - 2Y _ j - 1) = 0$*.*
- *The linear sum satisfies the **Inverse Linear Invariant**:*

$$
24 - 2X + \sum_{j=1}^{N-1} Y_j = O_N
$$

- *The quadratic sum satisfies the **Autocorrelation Invariant of the Inverse Chain**:*

$$
\mathbf{576 + 4X^2 + 13 \sum_{j=1}^{N-1} Y_j^2 - 12 \sum_{j=0}^{N-1} Y_j Y_{j+1} = O_N}
$$

**Proof (with explicit breakdown of the endpoints $j=0$ and $j=N$):**
For each $j \in \lbrace 0, 1, \dots, N-1\rbrace$, writing $Y _ j = 3q _ j + r _ j$ with $r _ j \in \lbrace 0, 1\rbrace$, we have $\lceil \frac{2}{3}Y _ j \rceil = 2q _ j + r _ j = \frac{2Y _ j + r _ j}{3} \implies 3Y _ {j+1} - 2Y _ j = r _ j$.
Squaring both sides of $3Y _ {j+1} - 2Y _ j = r _ j$ and applying Boolean idempotence $r _ j^2 = r _ j$ for each $j \in \lbrace 0, 1, \dots, N-1\rbrace$:

$$
9Y_{j+1}^2 - 12Y_j Y_{j+1} + 4Y_j^2 = r_j^2 = r_j
$$

Summing from $j = 0$ to $N - 1$, the right-hand side equals $\sum _ {j=0}^{N-1} r _ j = O _ N$. On the left-hand side we carefully separate the boundary terms $Y _ N = 8$ and $Y _ 0 = X$:

1. In the first quadratic sum:

$$
\sum_{j=0}^{N-1} 9Y_{j+1}^2 = 9Y_N^2 + 9\sum_{j=1}^{N-1} Y_j^2 = 9(8^2) + 9\sum_{j=1}^{N-1} Y_j^2 = 576 + 9\sum_{j=1}^{N-1} Y_j^2
$$

2. In the second quadratic sum:

$$
\sum_{j=0}^{N-1} 4Y_j^2 = +4Y_0^2 + 4\sum_{j=1}^{N-1} Y_j^2 = +4X^2 + 4\sum_{j=1}^{N-1} Y_j^2
$$

   Adding both contributions together with $-12\sum _ {j=0}^{N-1} Y _ j Y _ {j+1}$, the interior squares ($1 \le j \le N-1$) combine with coefficient $9 + 4 = 13$ and both boundary terms ($576$ and $+4X^2$) carry a positive sign:

$$
576 + 4X^2 + 13 \sum_{j=1}^{N-1} Y_j^2 - 12 \sum_{j=0}^{N-1} Y_j Y_{j+1} = O_N \quad \blacksquare
$$

### 12.2. The Modular Sieve $\Psi(P _ K) \equiv 18 \pmod{36}$ and its Exact Archimedean Representation

**Theorem 12.2 (Modular Invariant** $\Psi(P _ K) \equiv 18 \pmod{36}$ at Macro-Cycle Closures and Sieve at a Halting Time) [Proved]: 

1. **Diophantine Identity and Modulo 36 Sieve at the Closure of Every Macro-Cycle with $m _ K \ge 2$ (100% independent of $\alpha$):**
   In any macro-cycle $K \ge 1$ whose odd descent phase has length $m _ K \ge 2$ and odd core $d _ K \in \mathbb{Z} _ {\ge 1}$ ($d _ K \equiv 1 \pmod 2$), the even integer at the closure time $N _ K = P _ K + M _ K$:

$$
\Psi_{\text{cycle}}(K) := 2(a_{N_K} - 1) = 2 \cdot 3^{m_K} d_K
$$

   *simultaneously satisfies the three arithmetic exclusion filters:*

   - **2-adic Filter ($\bmod 4$):** $2(a _ {N _ K} - 1) \equiv 2 \pmod 4$.
   - **3-adic Filter ($\bmod 9$):** $2(a _ {N _ K} - 1) \equiv 0 \pmod 9$.
   - **Modulo 36 Combination and Cantor Filter:**

$$
2(a_{N_K} - 1) \equiv 18 \pmod{36} \qquad \text{and} \qquad (2^{m_K} d_K + 1) \bmod 9 \in \lbrace 0, 6\rbrace
$$

2. **General Sieve and Exact Archimedean Representation at a First Halting Time $N = 3P + 1 \ge 4$:**
   Suppose that Antihydra halts for the first time at step $N \ge 4$ (that is, $b _ N = -1$ and $b _ n \ge 0$ for all $0 \le n < N$). By Lemma 1.1, we have $N = 3P + 1$ (where $P = E _ N \ge 1$ is the total number of even steps prior to $N$) and the last two steps prior to $N$ are forced to be odd ($p _ {N-2} = p _ {N-1} = 1$). Defining for all $P \ge 1$ the functional:

$$
\Psi(P) := 2(a_{3P+1} - 1) = 2\left( \left\lceil \frac{3\alpha}{2} \left(\frac{27}{8}\right)^{P} \right\rceil - 1 \right) = 2 \left\lfloor \frac{3\alpha}{2} \left(\frac{27}{8}\right)^{P} \right\rfloor
$$

   *then at every first halting time* $N = 3P + 1$ *it holds **unconditionally** that* $9 \mid (a _ N - 1)$*, that is:*

$$
\Psi(P) \equiv 0 \pmod{18}
$$

   breaking down into exactly two subcases according to the parity of $a _ N$:

   - **Subcase 2a (Exact halting at the closure of macro-cycle $K$, i.e., $N = N _ K$, $P = P _ K$, $B _ K = -1$, and $a _ N$ even):** We have $m _ K \ge 2$ and the sieve holds with exactness:

$$
\Psi(P_K) = 2 \left\lfloor \frac{3\alpha}{2} \left(\frac{27}{8}\right)^{P_K} \right\rfloor = 2 \cdot 3^{m_K} d_K \equiv 18 \pmod{36}
$$

   - **Subcase 2b (Halting in the interior of the odd phase of macro-cycle $K$, i.e., $N < N _ K$, $B _ K \le -2$, and $a _ N$ odd):** Since $a _ N - 1$ is even and a multiple of $9$, we have $\Psi(P) \equiv 0 \pmod{36}$ at step $N = 3P + 1$, whereas upon completion of the odd run at $N _ K$ it continues to satisfy $2(a _ {N _ K} - 1) = 2 \cdot 3^{m _ K} d _ K \equiv 18 \pmod{36}$.

**Complete Step-by-Step Proof (Separating the Diophantine Proof from the Archimedean Representation):**

1. **Proof of the Sieve $2(a _ {N _ K} - 1) \equiv 18 \pmod{36}$ via the Chinese Remainder Theorem (Part 1):**
   By the cycle closure identity (Section 3.2), at the conclusion of any macro-cycle $K$ we have $a _ {N _ K} = 3^{m _ K} d _ K + 1$ with $d _ K \equiv 1 \pmod 2$, whence $2(a _ {N _ K} - 1) = 2 \cdot 3^{m _ K} d _ K$.

   - **Modulo $4$:** Since $d _ K \equiv 1 \pmod 2$ and $3^{m _ K} \equiv 1 \pmod 2$, the product $3^{m _ K} d _ K$ is odd: $3^{m _ K} d _ K \equiv 1 \pmod 2$. Multiplying by $2$ yields $2(a _ {N _ K} - 1) = 2(3^{m _ K} d _ K) \equiv 2 \pmod 4$.
   - **Modulo $9$:** Since $m _ K \ge 2$, we have $m _ K - 2 \ge 0$, so $3^{m _ K} = 9 \cdot 3^{m _ K - 2}$ is a multiple of $9$, that is, $2(a _ {N _ K} - 1) = 9 \cdot (2 \cdot 3^{m _ K - 2} d _ K) \equiv 0 \pmod 9$.
   - **Application of the Chinese Remainder Theorem:** Since $\gcd(4, 9) = 1$, the system of simultaneous congruences $\equiv 2 \pmod 4$ and $\equiv 0 \pmod 9$ possesses a unique solution modulo $4 \times 9 = 36$, which is $18 \pmod{36}$. Furthermore, by Theorem 3.2, the core $d _ K$ satisfies $(2^{m _ K} d _ K + 1) \bmod 9 \in \lbrace 0, 6\rbrace$. Note that this entire proof of (1) uses solely integer arithmetic, without involving $\alpha$.
2. **Proof of Part 2 (Halting at $N = 3P + 1 \ge 4$ and Archimedean Representation):**

   - Since $b _ 0 = 0, b _ 1 = 2, b _ 2 = 4, b _ 3 = 6, b _ 4 = 5$, the first halting time $b _ N = -1$ must satisfy $N > 4$. By Lemma 1.1, $N = 3P + 1$ with $P = E _ N \ge 1$, and the two steps immediately preceding $N$ are forced to be odd: $p _ {N-2} = 1$ and $p _ {N-1} = 1$ (passing through $b _ {N-2} = 1 \to b _ {N-1} = 0 \to b _ N = -1$).
   - Applying the odd transition law $a _ {k+1} - 1 = \frac{3}{2}(a _ k - 1)$ at steps $N - 2$ and $N - 1$:

$$
a_{N-1} - 1 = \frac{3}{2}(a_{N-2} - 1), \qquad a_N - 1 = \frac{3}{2}(a_{N-1} - 1) = \frac{9}{4}(a_{N-2} - 1)
$$

Since $a _ {N-2}, a _ {N-1}, a _ N \in \mathbb{Z}$ and $\gcd(9, 4) = 1$, the integer $a _ {N-2} - 1$ is divisible by $4$, and therefore $a _ N - 1 = 9 \cdot \frac{a _ {N-2} - 1}{4}$ is **always a multiple of** $9$, regardless of the parity of $a _ N$. Multiplying by $2$ yields $\Psi(P) = 2(a _ N - 1) \equiv 0 \pmod{18}$.
   - If the first crossing $b _ N = -1$ occurs at the conclusion of the odd phase of macro-cycle $K$ ($N = N _ K$, hence $P = P _ K$, $B _ K = -1$, and $a _ N = a _ {N _ K}$ is even), since the last two steps were odd we have $m _ K \ge 2$, and by Part (1) it satisfies $\Psi(P _ K) \equiv 18 \pmod{36}$. If instead the odd run had length $m _ K > b _ {t _ K} + 1$, at the time $N = 3P + 1$ where $b _ N = -1$ the state $a _ N$ remains odd ($a _ N - 1$ is even), so $2(a _ N - 1)$ is a multiple of $4$ and of $9$, giving $\Psi(P) \equiv 0 \pmod{36}$.
   - Finally, by Theorem 4.1(3), for every integer $N \ge 0$ we have $\alpha(3/2)^N \notin \mathbb{Z}$ and $a _ N - 1 = \lfloor \alpha(3/2)^N \rfloor = \lceil \alpha(3/2)^N \rceil - 1$. Evaluating at $N = 3P + 1$:

$$
\alpha\left(\frac{3}{2}\right)^{3P + 1} = \frac{3\alpha}{2} \left(\left(\frac{3}{2}\right)^3\right)^{P} = \frac{3\alpha}{2}\left(\frac{27}{8}\right)^{P}
$$

Substituting into $\Psi(P) = 2(a _ {3P+1} - 1)$ yields $\Psi(P) = 2\left(\left\lceil \frac{3\alpha}{2}(27/8)^{P} \right\rceil - 1\right) = 2\left\lfloor \frac{3\alpha}{2}(27/8)^{P} \right\rfloor$. $\blacksquare$

## Part XIII: Exponential Generating Functions, Infinite Product for $\alpha$, and Recurrence at Cube Roots of Unity

For every nonzero complex parameter $z \in \mathbb{C}^\times$, let us consider the exponential factor $z^{b _ n}$ and the coupled functional:

$$
F_n(z) := a_n z^{b_n}
$$

**Theorem 13.1 (Exact Multiplicative Quotient of $F _ n(z)$, Infinite Product for $\alpha$, and Inhomogeneous Equation at** $z^3 = 1$) [Proved]: 

1. **Exponential Evolution of $z^{b _ n}$:** For all $z \in \mathbb{C}^\times$ and $n \ge 0$:

$$
z^{b_{n+1}} = z^{b_n} \Big[ z^2 (1 - p_n) + z^{-1} p_n \Big] = z^{b_n} \Big[ z^2 - (z^2 - z^{-1})(3a_n - 2a_{n+1}) \Big]
$$

2. **Exact Branchwise Multiplicative Quotient:** Since $a _ {n+1} = \frac{3a _ n - p _ n}{2}$ and $b _ {n+1} - b _ n = 2 - 3p _ n$, the step-by-step quotient of $F _ n(z) = a _ n z^{b _ n}$ is exactly:

$$
\frac{F_{n+1}(z)}{F_n(z)} = \frac{a_{n+1}}{a_n} z^{2 - 3p_n} = \left(\frac{3a_n - p_n}{2a_n}\right) z^{2 - 3p_n} = \begin{cases} \frac{3}{2} z^2 & \text{if } p_n = 0 \quad (a_n \text{ even}), \cr \frac{3a_n - 1}{2a_n} z^{-1} = \frac{3}{2}\left(1 - \frac{1}{3a_n}\right) z^{-1} & \text{if } p_n = 1 \quad (a_n \text{ odd}). \end{cases}
$$

   In particular, owing to the multiplicative defect factor $\left(1 - \frac{1}{3a _ n}\right) < 1$ in the odd branch, the quotients $\frac{F _ {n+1}(z)}{F _ n(z)}$ *of the two branches **do not coincide** when* $z^3 = 1$. Unrolling the telescoping product from $n = 0$ to $N - 1$:

$$
F_N(z) = a_N z^{b_N} = 8 \left(\frac{3}{2}\right)^N z^{b_N} \prod_{\substack{k=0 \cr p_k = 1}}^{N-1} \left(1 - \frac{1}{3a_k}\right)
$$

   Dividing by $(3/2)^N z^{b _ N}$ and taking the limit $N \to \infty$ (which converges because $\sum _ {k=0}^\infty \frac{1}{3a _ k} < \infty$ as $a _ k$ *grows exponentially), we obtain the **Infinite Product Representation of the Antihydra Constant**:*

$$
\alpha = 8 \prod_{\substack{k=0 \cr p_k = 1}}^{\infty} \left(1 - \frac{1}{3a_k}\right)
$$

3. **Exact Inhomogeneous Linear Recurrence at the Cube Roots of Unity ($z^3 = 1$):** Additively separating the linear term $3a _ n$ from the defect $-p _ n$ in $2a _ {n+1} = 3a _ n - p _ n$, for all $z \in \mathbb{C}^\times$ it holds that:

$$
2F_{n+1}(z) = (3a_n - p_n) z^{b_n + 2 - 3p_n} = 3z^{2 - 3p_n} F_n(z) - p_n z^{b_n - 1}
$$

   (since the term $-p _ n z^{b _ n + 2 - 3p _ n}$ is nonzero only when $p _ n = 1$, in which case $b _ n + 2 - 3p _ n = b _ n - 1$). When $z$ is any of the three cube roots of unity ($z^3 = 1$, that is, $z \in \lbrace 1, \omega, \omega^2\rbrace$ with $\omega = e^{2\pi i/3}$), we have $z^{-3p _ n} = (z^3)^{-p _ n} = 1$ for both $p _ n = 0$ and $p _ n = 1$*, whereby the **homogeneous coefficients** of both branches do become equal to* $3z^2$*, yielding the exact inhomogeneous linear difference equation:*

$$
2F_{n+1}(z) - 3z^2 F_n(z) = -p_n z^{b_n - 1} \qquad (\forall z \in \lbrace 1, \omega, \omega^2\rbrace )
$$

## Part XIV: Ternary Symbolic Dynamics, Carry Transducer and Populations ($U _ n, D _ n, V _ n, K _ n$), the Universal Tail, Mahler's Problem, and Bibliographical References

### 14.1. Operational Definition of the Carry Transducer and Base-3 Populations (with Collision-Free Notation $V _ n$)

(Notation note: To avoid any ambiguity with the master variable $Z _ n = 3a _ n - 2$ from Part V, throughout the treatise we denote by $V _ n$ the count of digits $0$ in the base $3$ expansion of $a _ n$).

**Definition 14.0 (Base-3 Expansion, Left-to-Right Phase Scan, and Subpopulations):**
Let $a _ n \ge 8$ be the state of Antihydra at step $n \ge 0$, and let $L _ n = \lfloor \log _ 3 a _ n \rfloor \ge 1$ be the index of its most significant digit in base $3$. We write the standard base $3$ expansion of $a _ n$ from the units position ($k = 0$) up to the leading position ($k = L _ n$):

$$
a_n = \sum_{k=0}^{L_n} \tau_{n, k} 3^k, \qquad \tau_{n, k} \in \lbrace 0, 1, 2\rbrace , \quad \tau_{n, L_n} \in \lbrace 1, 2\rbrace
$$

We define the global counts of digits $0$, $1$, and $2$ in the support $\lbrace 0, 1, \dots, L _ n\rbrace$:

$$
V_n := \#\lbrace 0 \le k \le L_n : \tau_{n, k} = 0\rbrace , \quad U_n := \#\lbrace 0 \le k \le L_n : \tau_{n, k} = 1\rbrace , \quad D_n := \#\lbrace 0 \le k \le L_n : \tau_{n, k} = 2\rbrace
$$

so that $V _ n + U _ n + D _ n = L _ n + 1$. Since $3^k \equiv 1 \pmod 2$, the sum of digits is $\Sigma _ 3(a _ n) := \sum _ {k=0}^{L _ n} \tau _ {n, k} = U _ n + 2D _ n$ and the parity bit is:

$$
p_n = a_n \bmod 2 = \Sigma_3(a_n) \bmod 2 = U_n \bmod 2 \in \lbrace 0, 1\rbrace
$$

**Operational Rule of the Carry Scan (from left to right, $k = L _ n, L _ n - 1, \dots, 0$):**
In the exact division by $2$ given by $a _ {n+1} = \frac{3a _ n - p _ n}{2} = \frac{\sum _ {k=0}^{L _ n} \tau _ {n, k} 3^{k+1} - p _ n}{2}$, long division in base $3$ proceeds from the most significant column toward the units. We define the **vector of phase states (or carries)** $(c _ {n, L _ n+1}, c _ {n, L _ n}, \dots, c _ {n, 0}) \in \lbrace 0, 1\rbrace ^{L _ n+2}$ by:

1. **Initial state (to the left of the leading digit):** $c _ {n, L _ n + 1} := 0$.
2. **Local transition recurrence (for $k = L _ n, L _ n - 1, \dots, 0$):**

$$
c_{n, k} := (c_{n, k+1} + \tau_{n, k}) \bmod 2 = \left( \sum_{j=k}^{L_n} \tau_{n, j} \right) \bmod 2 = \#\lbrace k \le j \le L_n : \tau_{n, j} = 1\rbrace \bmod 2 \in \lbrace 0, 1\rbrace
$$

   That is, when scanning from left to right, the phase state toggles ($0 \leftrightarrow 1$) if and only if a digit $\tau _ {n, k} = 1$ is read, and remains invariant ($c _ {n, k} = c _ {n, k+1}$) when $\tau _ {n, k} \in \lbrace 0, 2\rbrace$ is read.
3. **Final state (at the right boundary $k = 0$):**

$$
c_{n, 0} = \left( \sum_{j=0}^{L_n} \tau_{n, j} \right) \bmod 2 = U_n \bmod 2 = p_n
$$

   In the units column ($j = 0$) of $3a _ n - p _ n$, this incoming remainder $3c _ {n, 0} = 3p _ n$ combines with $-p _ n$, producing the units digit of $a _ {n+1}$ with no outgoing remainder: $\tau _ {n+1, 0} = \frac{3c _ {n, 0} - p _ n}{2} = p _ n \in \lbrace 0, 1\rbrace$.
4. **Column-by-column Euclidean division equation:** In each column $j = k + 1$ ($0 \le k \le L _ n$) of $3a _ n$, the carry $c _ {n, k+1}$ enters from the left, the digit $\tau _ {n, k}$ is added, and the remainder $c _ {n, k} = (3c _ {n, k+1} + \tau _ {n, k}) \bmod 2$ exits to the right, determining the $(k+1)$-th digit of $a _ {n+1}$ via the closed formula:

$$
\tau_{n+1, k+1} = \frac{3c_{n, k+1} + \tau_{n, k} - c_{n, k}}{2} \in \lbrace 0, 1, 2\rbrace \qquad (0 \le k \le L_n), \qquad \tau_{n+1, 0} = p_n
$$

**Classification of the Four Subpopulations by Phase ($V _ n^{(0)}, V _ n^{(1)}, D _ n^{(0)}, D _ n^{(1)}$) and Active Volume $K _ n$:**
Since for every position $k$ with $\tau _ {n, k} \in \lbrace 0, 2\rbrace$ the incoming and outgoing carries coincide ($c _ {n, k+1} = c _ {n, k}$), we unambiguously classify each digit $0$ and each digit $2$ of $a _ n$ according to the value of its phase $c _ {n, k} \in \lbrace 0, 1\rbrace$:

- **In Inactive Phase ($c _ {n, k} = 0$):**

$$
V_n^{(0)} := \#\lbrace 0 \le k \le L_n : \tau_{n, k} = 0 \text{ and } c_{n, k} = 0\rbrace , \qquad D_n^{(0)} := \#\lbrace 0 \le k \le L_n : \tau_{n, k} = 2 \text{ and } c_{n, k} = 0\rbrace
$$

- **In Active Phase ($c _ {n, k} = 1$):**

$$
V_n^{(1)} := \#\lbrace 0 \le k \le L_n : \tau_{n, k} = 0 \text{ and } c_{n, k} = 1\rbrace , \qquad D_n^{(1)} := \#\lbrace 0 \le k \le L_n : \tau_{n, k} = 2 \text{ and } c_{n, k} = 1\rbrace
$$

  satisfying $V _ n = V _ n^{(0)} + V _ n^{(1)}$ and $D _ n = D _ n^{(0)} + D _ n^{(1)}$. Likewise, among the $U _ n$ digits equal to $1$ (read from left to right at positions $k _ 1 > k _ 2 > \dots > k _ {U _ n} \ge 0$), exactly $\frac{U _ n + p _ n}{2}$ have odd reading index $j$ (toggling the carry from $c _ {n, k+1} = 0$ to $c _ {n, k} = 1$) and exactly $\frac{U _ n - p _ n}{2}$ have even reading index $j$ (toggling from $c _ {n, k+1} = 1$ to $c _ {n, k} = 0$). The total number of positions $k \in \lbrace 0, \dots, L _ n\rbrace$ that receive an active incoming carry $c _ {n, k+1} = 1$ is:

$$
K_n := \#\lbrace 0 \le k \le L_n : c_{n, k+1} = 1\rbrace = \frac{U_n - p_n}{2} + D_n^{(1)} + V_n^{(1)}
$$

Theorem 14.1 (Master Equations of the Ternary Automaton and Phase Balance) [Proved]: For every step $n \ge 0$, the counts of digits $1$ and $2$ of $a _ {n+1}$ and the sum of digits $\Sigma _ 3(a _ {n+1})$ obey the exact laws:

1. **Evolution of digits 2 ($D _ {n+1}$):**

$$
D_{n+1} = \frac{U_n - p_n}{2} + D_n^{(1)} = K_n - V_n^{(1)}
$$

2. **Evolution of digits 1 ($U _ {n+1}$):**

$$
U_{n+1} = D_n^{(0)} + V_n^{(1)} + p_n = D_n - 2D_n^{(1)} + p_n - \frac{U_n - p_n}{2} + K_n
$$

3. **Evolution of the Sum of Digits ($\Delta \Sigma _ 3$):**

$$
\Sigma_3(a_{n+1}) - \Sigma_3(a_n) = V_n^{(1)} - D_n^{(0)}
$$

   Summing from $n = 0$ to $N - 1$ (with $\Sigma _ 3(a _ 0) = \Sigma _ 3(22 _ 3) = 4$*), we obtain the **Ternary Phase Balance Theorem**:*

$$
\sum_{n=0}^{N-1} \left( V_n^{(1)} - D_n^{(0)} \right) = \Sigma_3(a_N) - 4
$$

4. **Universal Tail Theorem after an Odd Run:** Upon completion of any odd run of length $m \ge 2$ at the even state $a _ {t+m} = 3^m d + 1$, the first subsequent even step generates the state:

$$
a_{t+m+1} = 3^m \left(\frac{3d - 1}{2}\right) + \frac{3^m + 3}{2}
$$

   whose last $m$ digits in base $3$ form the universal buffer independent of $d$:

$$
a_{t+m+1} \bmod 3^m = \frac{3^m + 3}{2} = \underbrace{11\dots 1}_{m-2 \text{ ones}} 20_3
$$

**Complete Proof of Theorem 14.1:**
We evaluate the exact formula $\tau _ {n+1, k+1} = \frac{3c _ {n, k+1} + \tau _ {n, k} - c _ {n, k}}{2}$ across the six exhaustive and mutually exclusive classes of positions $k \in \lbrace 0, 1, \dots, L _ n\rbrace$:

1. $\tau _ {n, k} = 0$ in Inactive Phase ($c _ {n, k+1} = c _ {n, k} = 0$, there are $V _ n^{(0)}$ positions): $\tau _ {n+1, k+1} = \frac{0 + 0 - 0}{2} = 0$.
2. $\tau _ {n, k} = 0$ in Active Phase ($c _ {n, k+1} = c _ {n, k} = 1$, there are $V _ n^{(1)}$ positions): $\tau _ {n+1, k+1} = \frac{3 + 0 - 1}{2} = 1$.
3. $\tau _ {n, k} = 2$ in Inactive Phase ($c _ {n, k+1} = c _ {n, k} = 0$, there are $D _ n^{(0)}$ positions): $\tau _ {n+1, k+1} = \frac{0 + 2 - 0}{2} = 1$.
4. $\tau _ {n, k} = 2$ in Active Phase ($c _ {n, k+1} = c _ {n, k} = 1$, there are $D _ n^{(1)}$ positions): $\tau _ {n+1, k+1} = \frac{3 + 2 - 1}{2} = 2$.
5. $\tau _ {n, k} = 1$ of odd order ($c _ {n, k+1} = 0 \to c _ {n, k} = 1$, there are $\frac{U _ n + p _ n}{2}$ positions): $\tau _ {n+1, k+1} = \frac{0 + 1 - 1}{2} = 0$.
6. $\tau _ {n, k} = 1$ of even order ($c _ {n, k+1} = 1 \to c _ {n, k} = 0$, there are $\frac{U _ n - p _ n}{2}$ positions): $\tau _ {n+1, k+1} = \frac{3 + 1 - 0}{2} = 2$.

Adding the units digit $\tau _ {n+1, 0} = p _ n \in \lbrace 0, 1\rbrace$ (which contributes $+p _ n$ to the count of digits $1$ and $0$ to that of digits $2$):

- The digits equal to $2$ in $a _ {n+1}$ arise exclusively from cases (4) and (6), so $D _ {n+1} = \frac{U _ n - p _ n}{2} + D _ n^{(1)}$.
- The digits equal to $1$ in $a _ {n+1}$ arise exclusively from cases (2), (3), and from $\tau _ {n+1, 0} = p _ n$, so $U _ {n+1} = D _ n^{(0)} + V _ n^{(1)} + p _ n$.
- Computing $\Sigma _ 3(a _ {n+1}) = U _ {n+1} + 2D _ {n+1} = \Sigma _ 3(a _ n) + V _ n^{(1)} - D _ n^{(0)}$.
  Finally, for (4), if $a _ {t+m} = 3^m d + 1$ with $d$ odd, $a _ {t+m}$ is even and $a _ {t+m+1} = \frac{3(3^m d + 1)}{2} = 3^m\left(\frac{3d-1}{2}\right) + \frac{3^m + 3}{2}$, where $\frac{3^m + 3}{2} = \sum _ {k=2}^{m-1} 3^k + 2 \cdot 3^1 + 0 \cdot 3^0$. $\blacksquare$

**Explicit Example Computed Step by Step ($n = 8 \to n = 9$, from $a _ 8 = 202$ to $a _ 9 = 303$):**

1. **Base-3 expansion of $a _ 8 = 202$:** $202 = [21111] _ 3 \implies (\tau _ {8,4}, \tau _ {8,3}, \tau _ {8,2}, \tau _ {8,1}, \tau _ {8,0}) = (2, 1, 1, 1, 1)$. Global counts: $V _ 8 = 0$, $U _ 8 = 4$, $D _ 8 = 1$, $\Sigma _ 3(a _ 8) = 6$, $p _ 8 = 0$.
2. **Left-to-right phase scan ($k = 4, 3, 2, 1, 0$) with $c _ {8, 5} = 0$:**

   - $k = 4$ ($\tau _ {8,4} = 2$): $c _ {8,4} = 0 \implies$ counts toward $D _ 8^{(0)}$. Generated digit: $\tau _ {9,5} = 1$.
   - $k = 3$ ($\tau _ {8,3} = 1$, 1st one, odd): $c _ {8,3} = 1$. Generated digit: $\tau _ {9,4} = 0$.
   - $k = 2$ ($\tau _ {8,2} = 1$, 2nd one, even): $c _ {8,2} = 0$. Generated digit: $\tau _ {9,3} = 2$.
   - $k = 1$ ($\tau _ {8,1} = 1$, 3rd one, odd): $c _ {8,1} = 1$. Generated digit: $\tau _ {9,2} = 0$.
   - $k = 0$ ($\tau _ {8,0} = 1$, 4th one, even): $c _ {8,0} = 0 = p _ 8$. Generated digit: $\tau _ {9,1} = 2$.
   - Units column ($j = 0$): $\tau _ {9,0} = p _ 8 = 0$.
3. **Subpopulations at $n = 8$ and prediction of $n = 9$:** $D _ 8^{(0)} = 1, D _ 8^{(1)} = 0, V _ 8^{(0)} = 0, V _ 8^{(1)} = 0, \frac{U _ 8 - p _ 8}{2} = 2, K _ 8 = 2 \implies D _ 9 = 2, U _ 9 = 1, \Sigma _ 3(a _ 9) = 5$.
4. **Direct verification on $a _ 9 = 303$:** $a _ 9 = [102020] _ 3 = 243 + 54 + 6 = 303$, with $U _ 9 = 1, D _ 9 = 2, V _ 9 = 3, \Sigma _ 3(303) = 5$.

### 14.2. Rigorous Distinction between the Antihydra Problem, the Sequence $\lbrace \alpha(3/2)^n\rbrace$, and Mahler's Problem

In order to establish with precision the scope of this work and what remains open, we formally distinguish four separate mathematical questions:

1. The Halting Problem of Antihydra [Global Open Problem]: Consists in determining whether there exists any integer $N \ge 1$ such that $b _ N = -1$ for the orbit $a _ 0 = 8, a _ {n+1} = \lfloor 3a _ n / 2 \rfloor$. As we proved in Theorems 1.0, 5.1(4), and 12.1, this question is **logically equivalent** to deciding whether there exists any integer $P \ge 1$ for which the Diophantine polynomial system over $(Y _ 0, Y _ 1, \dots, Y _ {3P+1}) \in (\mathbb{Z} _ {\ge 1})^{3P+2}$:

$$
\begin{cases} (3Y_{j+1} - 2Y_j)(3Y_{j+1} - 2Y_j - 1) = 0 & \forall j \in \lbrace 0, 1, \dots, 3P\rbrace \cr Y_{3P+1} = 8 \cr \sum_{j=1}^{3P} Y_j - 2Y_0 = 2P - 23 \end{cases}
$$

   admits an integer solution. This problem remains open.
2. **Mahler's Classical Problem on** $Z$**-Numbers** (Mahler [1968]):
   Formulated by Kurt Mahler in 1968, it asks whether there exists any nonzero real number $\xi > 0$ (called a $Z$*-number*) such that for every integer $n \ge 0$ the fractional part $\lbrace \xi(3/2)^n\rbrace$ satisfies $0 \le \lbrace \xi(3/2)^n\rbrace < \frac{1}{2}$ (which, for $\xi$ associated with a recurrence of the type $x _ {n+1} = \lfloor 3x _ n/2 \rfloor$ or $D _ {n+1} = \lceil 3D _ n/2 \rceil$ studied by Odlyzko and Wilf [1991], translates into prescribing the parity of all iterates). Mahler conjectured that no $Z$-numbers exist, which remains open.
3. **The Behavior of the Specific Sequence $\lbrace \alpha(3/2)^n\rbrace$ of Antihydra:**
   By Theorem 4.1(3) and Corollary 4.2(1), for the specific constant $\alpha \approx 7.8641772620566189724\dots$, we have $R _ n = a _ n - \alpha(3/2)^n = 1 - \lbrace \alpha(3/2)^n\rbrace \in (0, 1)$, and the parity $p _ n \in \lbrace 0, 1\rbrace$ is determined by the threshold $1/3$:

$$
p_n = 0 \iff R_n \in \left(0, \frac{2}{3}\right) \iff \left\lbrace \alpha\left(\frac{3}{2}\right)^n\right\rbrace \in \left(\frac{1}{3}, 1\right), \qquad p_n = 1 \iff R_n \in \left(\frac{1}{3}, 1\right) \iff \left\lbrace \alpha\left(\frac{3}{2}\right)^n\right\rbrace \in \left(0, \frac{1}{3}\right)
$$

4. **What Distribution Result Would Be Needed by the Specific Strategy of Corollary 4.2(2) (and why there is no proved equivalence):**

   - *Dependence within the Archimedean approach:* In Corollary 4.2(2) we proved the exact identity:

$$
b_N = \sum_{k=0}^{N-1} (2 - 3R_k) + 6(R_N - R_0) = 3\sum_{k=0}^{N-1} \left(\left\lbrace \alpha\left(\frac{3}{2}\right)^k\right\rbrace - \frac{1}{3}\right) + 6(R_N - R_0)
$$

For **this specific analytic strategy** alone to prove the non-halting of Antihydra (that is, $b _ N \ge 0$ for all $N \ge 1$), one does not even need full Weyl equidistribution in $[0, 1]$ (which would give $\lim _ {N\to\infty} \frac{1}{N}\sum _ {k=0}^{N-1} R _ k = \frac{1}{2}$ and $b _ N \sim \frac{N}{2} \to +\infty$), but solely the one-sided bound on the Cesàro means:

$$
\frac{1}{N}\sum_{k=0}^{N-1} R_k \le \frac{2}{3} - \frac{6R_0}{3N} \qquad \text{(or } \frac{1}{N}\sum_{k=0}^{N-1} \mathbf{1}_{\lbrace \alpha(3/2)^k\rbrace \in (0, 1/3)} \le \frac{2}{3}\text{ for all } N \ge 1\text{)}
$$

   - *Absence of proved logical equivalence:* It is essential to record that:

     1. Resolving Mahler's classical problem (on $Z$-numbers with threshold $1/2$ for all $\xi$) **is not equivalent** to resolving Antihydra (which concerns a single explicit constant $\alpha$ with threshold $1/3$ in the cumulative mean).
     2. Nor has it been proved that the equidistribution of $\lbrace \alpha(3/2)^k\rbrace$ is a necessary condition for the non-halting of Antihydra: $b _ N$ could never reach $-1$ due to Diophantine or 2-adic/3-adic obstructions even without knowing the asymptotic distribution of $\lbrace \alpha(3/2)^k\rbrace$.

### 14.3. Verifiable Bibliographical References

1. **Dubickas, A. (2009):** "On integer sequences generated by linear maps", *Glasgow Mathematical Journal*, Vol. 51, No. 2, pp. 243–252. `doi:10.1017/S0017089508004655`. (Study of iterated integer sequences of the type $\lfloor \frac{p}{q} x _ n \rfloor$ and non-generation of Sturmian words).
2. **Flatto, L., Lagarias, J. C., & Pollington, A. D. (1995):** "On the range of fractional parts $\lbrace \xi(p/q)^n\rbrace$", *Acta Arithmetica*, Vol. 70, No. 2, pp. 125–147. (Bounds on the length of intervals free of fractional parts of powers of $p/q$, in particular $3/2$).
3. **Lagarias, J. C. (1985):** "The $3x + 1$ problem and its generalizations", *The American Mathematical Monthly*, Vol. 92, No. 1, pp. 3–23. *(2-adic analysis, Haar measure, and rational cycles in piecewise affine operators).*
4. **Ligocki, S. (2024):** "BB(6) is Hard (Antihydra)", *sligocki.com* (published July 6, 2024). *(Original derivation of the high-level rules of the Antihydra Turing machine `1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA`).*
5. **Mahler, K. (1968):** "An unsolved problem on the powers of $3/2$", *Journal of the Australian Mathematical Society*, Vol. 8, No. 2, pp. 313–321. `doi:10.1017/S1446788700005371`. (Original formulation of Mahler's problem on $Z$-numbers and powers of $3/2$ modulo $1$).
6. **Odlyzko, A. M., & Wilf, H. S. (1991):** "Functional iteration and the Josephus problem", *Glasgow Mathematical Journal*, Vol. 33, No. 2, pp. 235–240. `doi:10.1017/S0017089500008272`. (Existence of the real ceiling/floor representation constant in iterations of $\lfloor \frac{3}{2}x \rfloor$ and $\lceil \frac{3}{2}x \rceil$).
7. **The Busy Beaver Challenge Contributors (2024):** "Antihydra", *BusyBeaverWiki* (`https://wiki.bbchallenge.org/wiki/Antihydra`), together with the associated sequences in *The On-Line Encyclopedia of Integer Sequences (OEIS)*: **A386792** (values of $a _ n$ from $a _ 0 = 8$) and **A385902** (values of the counter $b _ n$).

