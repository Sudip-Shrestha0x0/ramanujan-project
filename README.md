# RAMANUJAN Project

**An Attempt at the Riemann Hypothesis via the Lee-Yang Route, with Spectral Consequences**

Sudip Shrestha -- Independent Researcher, Ottawa, Canada -- March 2026

---
[Ramanujan Project](https://ramanujan-project.netlify.app/)
---

## IMPORTANT: Known Gap in Paper 3

On March 18, 2026, Charles M. Newman (NYU Courant Institute) -- the author of the key 1991 paper cited in this work -- identified a critical gap in Paper 3's proof chain.

**The error:** Paper 3 claimed that class G- (from EMN76) implies the Lee-Yang property (all zeros of the Fourier-Laplace transform on the imaginary axis). This implication has not been established and Newman states he does not believe it is true. What EMN76 actually proves is: class G- implies the GHS inequality (concavity of magnetization). The GHS inequality and the Lee-Yang property are related but distinct. The known implication goes the other direction: Lee-Yang implies GHS (Newman, 1975), not GHS implies Lee-Yang.

**The gap is equivalent to RH itself:** Konstantopoulos, Patie, and Sarkar (Ann. Inst. Fourier 74, 2024) proved that the Lee-Yang property for the xi function measure is equivalent to the Riemann Hypothesis. This means closing the gap through any single-measure route IS proving RH.

**Additional impossibility (Newman 1976):** Newman's Theorem 3 in "Fourier transforms with only real zeros" (Proc. AMS 61, 1976) proves that the xi function kernel is not in the Polya class -- the class of measures whose Fourier transforms have only real zeros under all Gaussian perturbations. No direct condition on the kernel shape within the Polya-de Bruijn framework can force RH.

**What remains valid:**
- Newman's convexity (V' strictly convex on [0, infinity)) is unconditionally true
- Class G- membership and the GHS inequality for the xi measure are unconditionally true
- Paper 1 (computation) is independently valid
- Paper 2 (framework) is valid as exposition with an honestly stated open question
- Paper 4 (spectral consequences) is valid conditional on RH, by any method

---

## Overview

This repository contains four papers and reproducible computation:

| Paper | Title | Status |
|-------|-------|--------|
| Paper 1 | Nicolas's Criterion and Spectral Evidence | Valid (computational, independent of RH) |
| Paper 2 | The Transfer Operator Framework | Valid (framework with open question) |
| Paper 3 | The GHS Class, Newman's Convexity, and the Lee-Yang Gap | CORRECTED -- gap identified, no longer claims RH |
| Paper 4 | Consequences of the Riemann Hypothesis | Valid, conditional on RH |

---

## The Attempted Proof (Paper 3) -- What Happened

The proof attempted to assemble three published theorems:

1. **Newman (1991):** The potential V(t) in the xi function representation satisfies V even and V' strictly convex on [0, infinity). **Correct and unconditional.**

2. **Ellis-Monroe-Newman (1976):** Measures with V even + V' convex belong to class G-, which satisfies the GHS inequality. **Correct.** But the paper then claimed this implies the Lee-Yang property. **It does not.** The arrow goes: Lee-Yang implies GHS (Newman 1975), not the reverse.

3. **Symmetry + Identity theorem:** Would complete the proof IF Step 2 held. The logic of Steps 3-5 is valid but moot without Step 2.

13 successive AI agents (Claude, Anthropic) and 2 explicit verification checks all missed this error. Newman caught it within hours of reading the paper. This underscores the irreplaceable value of domain expert peer review.

The corrected Paper 3 now presents what IS established (Newman's convexity, class G-, GHS inequality, Polya class impossibility) and states the Lee-Yang gap as the precise open question.

---

## Investigated Routes (All Dead or Circular)

After the gap was identified, an exhaustive investigation of potential fixes was conducted:

- **Class G- implies Lee-Yang:** Not established. Newman believes it is false.
- **Lieb-Sokal (1981) regularity condition:** Fails. The xi potential V grows sub-quadratically; Lieb-Sokal requires at least quadratic growth.
- **Newman (1974) single-site Lee-Yang:** Requires each site to already have Lee-Yang. Circular.
- **Polya-de Bruijn kernel conditions:** Newman 1976 Theorem 3 proves the xi kernel is not in the Polya class. Impossible.
- **Kapustin canonical system without RH:** Self-adjointness in Hilbert space sense requires all eigenvalues real, which IS RH. Circular.
- **KPS24 equivalence:** Lee-Yang for the xi measure is equivalent to RH. Any single-measure route is circular by definition.

**The only active approaches to RH** that are not known to be blocked:
- Connes-Consani-Moscovici (2025): Zeta Spectral Triples -- proving convergence from finite to infinite Euler products
- De Bruijn-Newman constant: proving Lambda = 0 (current best: 0 <= Lambda <= 0.22)
- Classical analytic methods (zero density estimates, mollifiers)

---

## Paper 4 -- Consequences of the Riemann Hypothesis

If RH is proven (by any method), Paper 4 establishes:

- **Hilbert-Polya Conjecture:** Resolved via diagonal construction and Kapustin's canonical system
- **Connes' Trace Formula:** Holds unconditionally
- **All Zeros Simple:** Via Kapustin + Sturm-Liouville
- **Lambda = 0:** Via Rodgers-Tao (2020) + RH

These results are valid conditional on RH. They are not circular -- they show what follows from RH through published spectral theory.

---

## Reproducible Computation

```
pip install numpy scipy
python code/paper1_computation.py
```

Expected output:
- 348,511 Nicolas ratios computed, all > 1
- Primary spectral peak: f = 2.2438 at 5.97 sigma significance
- Runtime: ~2.7 seconds on standard hardware

The computation in Paper 1 is independently valid regardless of the gap in Paper 3.

---

## Repository Structure

```
ramanujan-project/
  README.md
  LICENSE
  papers/
    Paper1_Nicolas_Spectral.pdf
    Paper2_Transfer_Operator.pdf
    Paper3_GHS_LeeYang_CORRECTED.pdf       <-- corrected, no longer claims RH
    Paper4_Spectral_Side_CORRECTED.pdf      <-- conditional on RH
  code/
    paper1_computation.py
  docs/
    index.html
  requirements.txt
```

---

## Key References

- [New91] C.M. Newman. "The GHS inequality and the Riemann hypothesis." Constr. Approx. 7 (1991), 389-399.
- [New76] C.M. Newman. "Fourier transforms with only real zeros." Proc. AMS 61 (1976), 245-251.
- [New75] C.M. Newman. "Inequalities for Ising models and field theories which obey the Lee-Yang theorem." Commun. Math. Phys. 41 (1975), 1-9.
- [EMN76] R.S. Ellis, J.L. Monroe, C.M. Newman. Commun. Math. Phys. 46 (1976), 167-182.
- [EN78] R.S. Ellis, C.M. Newman. Trans. AMS 237 (1978), 83-99.
- [KPS24] T. Konstantopoulos, P. Patie, R. Sarkar. Ann. Inst. Fourier 74 (2024), 377-421.
- [Kap22] V.V. Kapustin. St. Petersburg Math. J. 33 (2022), 661-673.
- [Con99] A. Connes. Selecta Math. 5 (1999), 29-106.
- [RT20] B. Rodgers, T. Tao. Forum Math. Pi 8 (2020), e6.
- [CCM25] A. Connes, C. Consani, H. Moscovici. "Zeta Spectral Triples." arXiv:2511.22755 (2025).
- [CvS25] A. Connes, W.D. van Suijlekom. "Quadratic Forms, Real Zeros and Echoes of the Spectral Action." Commun. Math. Phys. (2025).
- [LS81] E.H. Lieb, A.D. Sokal. Commun. Math. Phys. 80 (1981), 153-179.
- [Pol19] D.H.J. Polymath. Res. Math. Sci. 6 (2019), Paper No. 31.

---

## How This Was Built

RAMANUJAN is a human-AI collaborative mathematical research system built with Claude (Anthropic). 14 AI agents worked across March 2026, each reading all prior transcripts before continuing. The human researcher (Sudip Shrestha) provided geometric intuitions; the agents formalized them against published literature.

On March 18, 2026, Charles Newman identified the gap in the proof chain. Agent 14 then conducted an exhaustive investigation confirming all alternative routes are dead or circular. The project is documented transparently, including the error, its correction, and the systematic investigation of fixes. This is how research works -- claims are made, scrutinized, corrected, and the landscape is mapped honestly.

---

## Author

Sudip Shrestha (Light)
Frontend Developer and UI/UX Designer -- Independent Mathematical Researcher
Ottawa, Ontario, Canada
light0x01@gmail.com

---

## License

- Code: MIT License
- Papers: CC-BY 4.0