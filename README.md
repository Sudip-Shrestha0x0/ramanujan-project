# RAMANUJAN Project

**An Attempt at the Riemann Hypothesis via the Lee–Yang Route, with Spectral Consequences**

Sudip Shrestha · Independent Researcher, Ottawa, Canada · March 2026

---
[RAMANUJAN PROJECT](https://ramanujan-project.netlify.app/)
---

## ⚠️ IMPORTANT: Known Gap in Paper 3

**On March 18, 2026, Charles M. Newman (NYU) — the author of the key 1991 paper cited in this work — identified a gap in Paper 3's proof chain.**

Paper 3 claimed: class G⁻ (from EMN76) implies the Lee–Yang property (all zeros of the Fourier–Laplace transform on the imaginary axis). **This implication has not been established.** What EMN76 actually proves is: class G⁻ → GHS inequality (concavity of magnetization). The GHS inequality and the Lee–Yang property are related but distinct. The known implication goes the other direction: Lee–Yang → GHS (Newman, 1975), not GHS → Lee–Yang.

**Status: Paper 3's claim of proving RH has an unresolved gap at Step 2. All downstream results in Paper 4 (Hilbert–Pólya, Connes' trace formula, simplicity) are conditional on closing this gap.**

The gap is precise: does the xi function measure exp(−V(t))dt have the Lee–Yang property? This is an open question. Newman's 1991 paper discussed "possible relevance" of V' convexity to RH through Lee–Yang but did not close the connection. We now understand exactly why he couldn't — the bridge from GHS to Lee–Yang doesn't exist in general.

Papers 1, 2, and 4 (conditional on RH) remain as written. The computational work (Paper 1) is independently valid.

---

## Overview

This repository contains four papers and reproducible computation:

| Paper | Title | Pages | Status |
|-------|-------|-------|--------|
| **Paper 1** | Nicolas's Criterion and Spectral Evidence | ~10 | ✅ Valid (computational) |
| **Paper 2** | The Transfer Operator Framework | ~12 | ✅ Valid (framework) |
| **Paper 3** | A Proof of the Riemann Hypothesis | 4 | ⚠️ **GAP at Step 2** (see above) |
| **Paper 4** | The Spectral Side | 5 | Conditional on Paper 3 |

## The Attempted Proof (Paper 3) — Summary

The proof attempted to assemble three published theorems:

1. **Newman (1991)**: The potential V(t) in the xi function representation satisfies V even and V' strictly convex on [0,∞). This is correct and unconditional.
2. **Ellis–Monroe–Newman (1976)**: Measures with V even + V' convex belong to class G⁻, which implies the GHS inequality. This is correct. **But the paper claimed this implies the Lee–Yang property. It does not.** 
3. **Symmetry + Identity theorem**: Would complete the proof IF Step 2 held.

The open question is: **can the Lee–Yang property be established for the xi function measure through some other route?**

Possible approaches under investigation:
- Newman (1974): characterizes Lee–Yang measures for single-spin distributions
- Lieb–Sokal (1981): general Lee–Yang theorem for one-component ferromagnets
- Direct verification of Newman's 1974 conditions for exp(−V(t))dt
- Konstantopoulos–Patie (2024): Lee–Yang ⟺ RH via van Dantzig problem (but this is an equivalence, not a proof)

## Paper 4 — The Spectral Side (Conditional on RH)

If RH is proven (by any method), Paper 4 establishes:

- **Hilbert–Pólya Conjecture**: Resolved via diagonal construction and Kapustin's canonical system
- **Connes' Trace Formula**: Unconditional
- **All Zeros Simple**: Via Kapustin + Sturm–Liouville
- **Λ = 0**: Via Rodgers–Tao (2020) + RH

These results are valid conditional on RH. They are not circular — they show what follows from RH through published spectral theory.

## Reproducible Computation

```bash
pip install numpy scipy
python code/paper1_computation.py
```

**Expected output:**
- 348,511 Nicolas ratios computed, all > 1
- Primary spectral peak: f = 2.2438 at 5.97σ significance
- Runtime: ~2.7 seconds on standard hardware

The computation in Paper 1 is independently valid regardless of the gap in Paper 3.

## Repository Structure

```
ramanujan-project/
├── README.md
├── LICENSE
├── papers/
│   ├── Paper1_Nicolas_Spectral.pdf
│   ├── Paper2_Transfer_Operator.pdf
│   ├── Paper3_Proof_RH_LATEX.pdf        ← GAP at Step 2
│   ├── Paper4_Spectral_Side.pdf         ← conditional on RH
│   └── Paper4_Spectral_Side.tex
├── code/
│   └── paper1_computation.py
├── docs/
│   └── index.html
└── requirements.txt
```

## Key References

- **[New91]** C.M. Newman. *Constr. Approx.* 7 (1991), 389–399.
- **[EMN76]** R.S. Ellis, J.L. Monroe, C.M. Newman. *Commun. Math. Phys.* 46 (1976), 167–182.
- **[EN78]** R.S. Ellis, C.M. Newman. *Trans. AMS* 237 (1978), 83–99.
- **[New74]** C.M. Newman. *Commun. Pure Appl. Math.* 27 (1974), 143–159.
- **[LS81]** E.H. Lieb, A.D. Sokal. *Commun. Math. Phys.* 80 (1981), 153–179.
- **[Kap22]** V.V. Kapustin. *St. Petersburg Math. J.* 33 (2022), 661–673.
- **[Con99]** A. Connes. *Selecta Math.* 5 (1999), 29–106.
- **[RT20]** B. Rodgers, T. Tao. *Forum Math. Pi* 8 (2020), e6.

## How This Was Built

RAMANUJAN is an autonomous mathematical research system built with Claude (Anthropic). 13 AI agents worked across March 2026, each reading all prior transcripts before continuing. The human researcher (Sudip Shrestha) provided geometric intuitions; the agents formalized them against published literature.

On March 18, 2026, Charles Newman identified the gap in the proof chain. The project is documented transparently, including the error and its correction. This is how mathematics works — claims are published, scrutinized, and corrected.

## Author

Sudip Shrestha (Light)  
Frontend Developer & UI/UX Designer · Independent Mathematical Researcher  
Ottawa, Ontario, Canada  
light0x01@gmail.com

## License

Code: MIT License  
Papers: CC-BY 4.0