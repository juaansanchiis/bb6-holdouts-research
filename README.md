# Busy Beaver $BB(6)$ Holdouts Research: Exact Algebraic Macro-Dynamics & Adelic Theory

This repository contains two comprehensive mathematical monographs investigating 6-state, 2-symbol Turing machines ($BB(6)$) from [**The Busy Beaver Challenge**](https://bbchallenge.org/):

1. **Exact Algebraic Macro-Dynamics, Two-Regime Symbolic Automaton, and Counter-Reservoir Coupling** for Holdout Turing Machine **`#1965`** (`1RB1RC_0LC1RE_1RA0LD_1LB0RD_0RF---_0RA0RF`), establishing the exact closed-form right-boundary transition engine (`macro_step`), the Universal Bit-Growth Law ($\Delta b_j = +8$ per $2^{j+1}$ cycles), the Causal Shielding Theorem, the exact Modulo-16 Collatz-like reservoir recurrence ($R_0^{\text{next}} = \frac{3}{2} R_0 + \{6, 10\}$), and the unconditional closure of the Two-Regime 15-Head Defect-Wave Automaton, verified over $500,000$ macro-cycles ($t = 161,807,060,367$ individual TM steps).
2. **An Extensive Algebraic-Adelic and Diophantine Treatise** on the **Antihydra** Turing Machine (`1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA`), establishing a 14-part theoretical framework—the *Calculus of Carry Defects on Bimodular Lattices (CCDBL)*—while rigorously delineating proved structural theorems from the remaining open problems required to settle its global halting conjecture.

---

## 📂 Repository Structure

```text
bb6-holdouts-research/
├── README.md
├── 01-tm-1965-ctl-proof/
│   └── formal_non_halting_proof_tm_1965.md
└── 02-antihydra-adelic-theory/
    └── complete_treatise_antihydra_bb6.md
```

| Directory & File | Target Machine ($BB(6)$) | Status | Nature of Contribution |
| :--- | :--- | :---: | :--- |
| [`01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md`](./01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md) | **TM `#1965`**<br>`1RB1RC_0LC1RE_1RA0LD_1LB0RD_0RF---_0RA0RF` | 🔬 **Exact Algebraic Reduction & Two-Regime Closure**<br>*(Verified to $t = 1.618 \times 10^{11}$)* | Exact closed-form macro-simulator, $+8$ bit-growth law, Causal Shielding, exact mod-16 Collatz-like reservoir recurrence, and Two-Regime 15-Head Automaton closure + Python verifier. |
| [`02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md`](./02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md) | **Antihydra**<br>`1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA` | 🔬 **Theoretical Advance**<br>*(Halting Conjecture Open)* | 14-part mathematical treatise proving exact algebraic, $p$-adic, Archimedean, and Diophantine invariants + 8-test Python verification suite. |

---

## 1. Exact Algebraic Macro-Dynamics & Two-Regime Automaton: Turing Machine `#1965`

📄 **Document:** [`01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md`](./01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md)

### Problem Statement & Peer-Review Revision
Machine `#1965` (`1RB1RC_0LC1RE_1RA0LD_1LB0RD_0RF---_0RA0RF`) couples a binary counter on the left tape with an exponentially growing unary reservoir $1^R [A] 0^\infty$ on the right boundary. Following peer review on the `bbchallenge` Discord by **Claude (Heron)**, who demonstrated that an earlier draft's naive 5-subtype regular CTL left $\mathcal{I}_A$ at $t = 3868 \to 3908$ (via a trailing $010 = (01)^1 0$ after $000$ at reservoir drain) and at $t = 13,978$ (when transient solitary zeroes `z = 1` first appear), this revised monograph establishes the complete closed-form algebraic theory of the machine and proves why *no* finite-state regular CTL that abstracts $R$ without counter-reservoir coupling can close.

### Main Proved Theorems & Verified Reduction
* **Theorem 1 — Exact Closed-Form Macro-Simulator (`macro_step`):** Derives the exact closed-form transition mapping any right-boundary configuration $\dots [A] 0^\infty$ to the next right-boundary configuration via Phase 1 ($C$-sweep parity dichotomy) and Phase 2 (**Rules A, B, and C**, including Rule C for trailing $(01)^1 0\ 0^\infty \to 00 [A] 0^\infty$ at $t = 3908$). Verified bit-for-bit across all $2,551$ right-boundary cycles in the first $5,000,000$ TM steps.
* **Theorem 2 — Solitary-Zero Creation & 4-Stage $+8$ Promotion Lifecycle:** Proves that a solitary zero (`z = 1`) is never created in Phase 2, and whenever Phase 1 creates `z = 1`, Phase 2 invariably places `(3, 3)` (`1^3 000`) immediately to its right: $(a, 1), (3, 3)$. On the first subsequent carry, the `000` separator forces a bounce that promotes `(3, 3)` to `(6, 2)`; on the second carry, the even block `6` sweeps across `z = 1` in state $C$ (`C0 -> 1RA`), absorbing the solitary zero into $(a+3, 3), (6, 3)$ and climbing the $+8$ ladder $6 \to 9 \to 12 \to 15 \to 14$.
* **Theorem 3 — Universal Binary-Counter Bit-Growth Law:** Proves that in the standard binary-counter alphabet $\Sigma_{\text{std}} = \{(\text{'E14'}, 3), (\text{'O15'}, 2)\}$, every bit position $j \ge 1$ from the right gains $\Delta b_j = +3 + 3 + 3 - 1 = +8$ unary $1$s per $2^{j+1}$ macro-cycles ($\Delta R = -2^{j+2}$), yielding $\Delta b_j / |\Delta R| = 1 / 2^{j-1}$.
* **Theorem 4 & Theorem 5 — Causal Shielding & Exact Modulo-16 Reservoir Recurrence:** Proves that bits $j = 1, \dots, r-1$ and $R$ are 100% causally shielded from all defects at depth $d \ge r + 1$. Consequently, the $0 \pmod 4$ reservoir sizes $\{R_0^{(n)}\}_{n \ge 1}$ (starting at Cycle 89 with $R_0^{(1)} = 60$) satisfy $R_0^{(n)} \equiv 4 \pmod 8$ and obey the exact Collatz-like recurrence:
  $$R_0^{(n+1)} = \begin{cases} \frac{3}{2} R_0^{(n)} + 6 & \text{if } R_0^{(n)} \equiv 4 \pmod{16} \quad (\text{2-era super-cycle}), \\[4pt] \frac{3}{2} R_0^{(n)} + 10 & \text{if } R_0^{(n)} \equiv 12 \pmod{16} \quad (\text{3-era super-cycle}). \end{cases}$$
* **Theorem 6 & Theorem 7 — Two-Regime Symbolic Automaton & Defect-Drain Separation:** Proves by exact symbolic model checking that **Regime 1** (the 15-Head Defect-Wave Automaton for $R \ge 20$) and **Regime 2** (the Reservoir Drain Automaton for $R \le 18 \to R_{\text{new}}$ on $\Sigma_{\text{std}}^{\ge 4}$) are 100% closed and halt-free, reducing global non-halting to the *Defect-Drain Separation Property*, verified across all $500,000$ macro-cycles ($t = 161,807,060,367$ steps; $52$ reservoir eras).

---

## 2. Theoretical Advance & Open Frontier: The Antihydra Conjecture in $BB(6)$

📄 **Document:** [`02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md`](./02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md)

### Background
Discovered in June 2024 during *The Busy Beaver Challenge* (by `mxdys` and analyzed by `Racheline`), **Antihydra** (`1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA`) is one of the most famous Cryptids in $BB(6)$. Its high-level tape evolution reduces to the coupled Collatz-like skew-product dynamical system:

$$
a_0 = 8, \quad b_0 = 0, \qquad a_{n+1} = \left\lfloor \frac{3a_n}{2} \right\rfloor = \frac{3a_n - p_n}{2}, \qquad b_{n+1} = b_n + 2 - 3p_n
$$

where $p_n = a_n \bmod 2 \in \{0, 1\}$, and the machine halts at macro-step $N$ if and only if $b_N = -1$.

### Summary of Proved Mathematical Results (Parts I–XIV)
Every theorem labeled **`[Proved]`** in the treatise is established with a complete mathematical proof (and computationally cross-checked in **Appendix B** across 8 independent test suites):

1. **Part I — Verifiable Turing Reduction & Modular Sieve:** Step-by-step proof reducing the 6-state machine from $0^\infty \mathbf{A>} 0^\infty$ (in 11 initialization steps) to canonical configurations $\mathcal{A}(b_n, a_n - 4) = 0^\infty 1^{b_n} 0 1^{a_n - 4} \mathbf{E>} 0^\infty$. Proves the temporal halting congruence $N = 3P + 1$, $O_N = 2P + 1$, $E_N = P$, and $p_{N-2} = p_{N-1} = 1$.
2. **Part II — Spin Duality & Modulo 8 Structure:** Introduces the shifted odd sequence $u_n = 2a_n - 1$ and spin $\sigma_n = 1 - 2p_n \in \{-1, +1\}$, proving the Dirichlet character law $\sigma_n = -\chi_4(u_n)$, the 2-adic involution $\mathcal{J}(a) = 1 - a$, and the exact Boolean Cubic Identity on spin triplets.
3. **Part III — Macro-Cycle Renormalization & Universal Floor Formula:** Partitions the orbit into alternating even-pumping ($r_i$) and odd-descent ($m_i$) macro-cycles, proving the Four Valuation Laws and the Universal Floor Formula expressing $d_i$ directly in terms of $d_{i+1}$.
4. **Part IV — Archimedean Domain & Certified Antihydra Constant $\alpha$:** Certifies 50 decimal places of the Antihydra constant $\alpha = 8 - \sum_{k=0}^\infty \frac{2^k}{3^{k+1}} p_k \approx 7.86417726205661897240516852968228138530742425177359\dots$ with rigorous truncation bound $(2/3)^{300} < 1.49 \times 10^{-53}$, proving strict non-integrality $R_n = a_n - \alpha(3/2)^n \in (0, 1)$ and ceiling/floor recovery $a_n = \lceil \alpha(3/2)^n \rceil$.
5. **Parts V & VI — Exact Integral Invariants & Quadratic Virial Theorem:** Establishes the history invariants $44 \cdot 3^n + \sum_{k=1}^{n-1} 3^{n-1-k} 2^k b_k = 2^n(6a_n - b_n - 4)$, the dual identities for $O_n$ and $E_n$, absolute convergence of weighted generating series, and the Quadratic Virial Theorem partitioning $\sum b_m$ across even and odd steps at any halting horizon.
6. **Parts VII–IX — Affine Algebraic Variety, Adelic Space $\mathcal{E}_S$, & Cantor Set Measure:** Eliminates the `if/else` conditional via $9a_n^2 - 12a_n a_{n+1} + 4a_{n+1}^2 - 3a_n + 2a_{n+1} = 0$, proves 2-adic injectivity of residual sets $\mathcal{R}_M$, and shows that the asymptotic 3-adic attractor has Haar measure $\mu_3(\mathcal{R}_\infty) = 0$.
7. **Parts X–XII — Time-Reversal Ternary Ceilings, Koopman-Walsh Spectrum, & Diophantine Sieve:** Proves backward recovery via $a_{n-1} = \lceil \frac{2}{3} a_n \rceil$, derives the telescopic Kirchhoff pole-conservation formula for $b_N$, constructs an explicit infinite family of rational 2-adic periodic cycles in $\mathbb{Z}_2 \cap (0, 1)$ (contrasting with their absence in $\mathbb{Z}^+$), and proves the inverse-chain quadratic autocorrelation invariant $576 + 4X^2 + 13\sum_{j=1}^{N-1} Y_j^2 - 12\sum_{j=0}^{N-1} Y_j Y_{j+1} = O_N$ along with the modular sieve $\Psi(P_K) \equiv 18 \pmod{36}$.
8. **Parts XIII & XIV — Generating Functions & Base-3 Carry Transducer:** Establishes the infinite product for $\alpha$, the base-3 left-to-right carry transducer governing digit populations $(V_n, U_n, D_n)$, and proves the **Universal Ternary Tail Theorem** ($a_{t+m+1} \bmod 3^m = \frac{3^m + 3}{2} = [11\dots 120]_3$) at the close of every odd run of length $m \ge 2$.

### ⚠️ What Remains Open to Resolve the Antihydra Conjecture
As explicitly documented in **Section 14.2** and **Appendix C.2**, this treatise **does not claim a closed proof that Antihydra never halts**. Settling the conjecture requires resolving two fundamental open problems:

1. **The Global Halting Problem for Antihydra (`[Global Open Problem]`):**
   Proving unconditionally that for no integer $P \ge 1$ (with $N = 3P + 1$) does there exist a positive integer terminal value $X = a_N \in \mathbb{Z}^+$ whose backward ternary-ceiling chain $Y_{j+1} = \lceil 2Y_j / 3 \rceil$ ($Y_0 = X$) hits the initial seed $Y_N = 8$ while satisfying the cumulative remainder sum $b_N = 2N - 3O_N = -1$ (or equivalently, proving that the finite average $\frac{1}{N}\sum_{k=0}^{N-1} R_k$ never crosses below $\frac{2}{3} - \frac{6R_0 - 1 - 6R_N}{3N}$).
2. **Unconditional Asymptotic Drift ($\lim_{n \to \infty} b_n = +\infty$) & Individual Ergodicity:**
   Under the heuristic assumption that $p_n = a_n \bmod 2$ behaves as an unbiased Bernoulli$(1/2)$ process, $b_n$ drifts upward with mean $+1/2$ per step. However, proving equidistribution of $\{\alpha (3/2)^n\} \bmod 1$ for the specific constant $\alpha$ generated by $a_0 = 8$ encounters the exact same transcendental number-theoretic barrier as **Mahler's $Z$-Numbers Problem (1968)** (which asks whether any $\xi > 0$ satisfies $0 \le \{\xi(3/2)^n\} < 1/2$ for all $n \ge 0$) and **Lagarias's $(3x+1)/2$ Conjecture**.

---

## 🧪 Running the Embedded Python Verifiers

Both documents include self-contained Python verification scripts with zero external dependencies (requiring only Python 3.8+ standard library modules):

* **TM `#1965` Exact Macro-Step, Modulo-16 Reservoir Recurrence & Two-Regime Automaton Verifier:** Located in Section 5 of [`01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md`](./01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md).
* **Antihydra 8-Test Mathematical Audit Suite:** Located in Appendix B.2 of [`02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md`](./02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md).
