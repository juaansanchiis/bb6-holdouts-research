# Busy Beaver $BB(6)$ Holdouts Research: Formal Proofs & Algebraic-Adelic Theory

This repository contains two comprehensive mathematical monographs investigating 6-state, 2-symbol Turing machines ($BB(6)$) from [**The Busy Beaver Challenge**](https://bbchallenge.org/):

1. **A Complete, Self-Contained Formal Non-Halting Proof** for Holdout Turing Machine **`#1965`** (`1RB1RC_0LC1RE_1RA0LD_1LB0RD_0RF---_0RA0RF`) via a Parity-Aware Closed Tape Language (CTL) and a 29-state Deterministic Finite Automaton (DFA).
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
| [`01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md`](./01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md) | **TM `#1965`**<br>`1RB1RC_0LC1RE_1RA0LD_1LB0RD_0RF---_0RA0RF` | ✅ **Resolved**<br>*(Proved Non-Halting)* | Complete, human- and machine-verifiable inductive closure proof ($t = \infty$) with embedded Python CTL/DFA verifier. |
| [`02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md`](./02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md) | **Antihydra**<br>`1RB1RA_0LC1LE_1LD1LC_1LA0LB_1LF1RE_---0RA` | 🔬 **Theoretical Advance**<br>*(Halting Conjecture Open)* | 14-part mathematical treatise proving exact algebraic, $p$-adic, Archimedian, and Diophantine invariants + 8-test Python verification suite. |

---

## 1. Complete Mathematical Solution: Turing Machine `#1965`

📄 **Document:** [`01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md`](./01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md)

### Problem Statement & Difficulty
Within $BB(6)$, machines classified under *"Tape invariants, block structure"* exhibit complex bouncer and fractal counter dynamics where runs of `1`s separated by variable-width zero delimiters (`000`, `00`, and `0`) expand and merge across the tape. Standard fixed-width block deciders fail on Machine `#1965` because phase shifts introduce a solitary `0` separator whose survival or annihilation depends on the exact modulo-$2$ parity of adjacent blocks of `1`s.

### Main Result (Proved)
> **Theorem:** Started on a blank tape $0^\infty [A] 0^\infty$, Turing Machine `#1965` (`1RB1RC_0LC1RE_1RA0LD_1LB0RD_0RF---_0RA0RF`) never halts ($t = \infty$).

### Key Components of the Proof
* **Exact Halting Characterization (Lemma 11):** Proves that the undefined transition `E1 -> ---` can only be triggered if a left-moving `C`-sweep encounters a solitary `0` immediately preceded by an **odd** run of `1`s ($1^{2k+1} 0 [C] 0$).
* **System of 10 Block Macro-Transitions (Lemmas 1–10):** Derives exact symbolic multi-step rules governing left-sweeps in state $C$, boundary bounces, and right-sweeps in state $A$.
* **Parity-Aware Closed Tape Language $\mathcal{I}_A$ (Section 3):** Defines an explicit regular language partitioned into five disjoint subtypes ($\mathcal{I}_A = \mathcal{I}_A^{(\text{I})} \cup \mathcal{I}_A^{(\text{II})} \cup \mathcal{I}_A^{(\text{III})} \cup \mathcal{I}_A^{(\text{IV})} \cup \mathcal{I}_A^{(\text{V})}$), formalized both as a pure Regular Expression and as an explicit **29-state Deterministic Finite Automaton (DFA)** over the left tape.
* **Uniqueness & Parity Protection of the Solitary `0` (Lemmas 12 & 13):** Proves that at most one solitary `0` separator exists on the tape at any cut-point and that it is invariably shielded to its left by an **even** block $1^{2m}$ ($m \ge 1$), preventing the halting condition from ever occurring.
* **Exhaustive Inductive Closure (Section 4) & Standalone Verifier (Section 5):** Enters $\mathcal{I}_A$ at step $t_0 = 10$ ($0^\infty 100010 [A] 0^\infty \in \mathcal{I}_A^{(\text{I})}$) and proves closure ($\mathcal{I}_A \to \mathcal{I}_A$) across all five subtypes, accompanied by an automated Python verification script validating the DFA, regexes, and execution trace up to $t = 710$.

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

* **TM `#1965` CTL & 29-State DFA Verifier:** Located in Section 5 of [`01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md`](./01-tm-1965-ctl-proof/formal_non_halting_proof_tm_1965.md).
* **Antihydra 8-Test Mathematical Audit Suite:** Located in Appendix B.2 of [`02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md`](./02-antihydra-adelic-theory/complete_treatise_antihydra_bb6.md).
