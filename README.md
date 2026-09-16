# When the wild type hits the ceiling

Companion code for the manuscript:
*When the wild type hits the ceiling: identifiability of mutation–lineage interactions in pharmacogenomic panels*

## Contents

- **r0_r5_check.py** — the executable version of the R0–R5 rules (the methodological checklist)
- **analysis scripts 55–83** — simulations, census, and figure generation

| Script | Purpose |
|---|---|
| 63 | 2D grid (censoring rate × cell count), separates geometry from small-n effects |
| 64–65 | A1b census + n-threshold sensitivity |
| 67–68 | hotspot sub-analysis + GDSC1 external replication |
| 69–70 | positive controls + negative-control FPR calibration |
| 71c–72 | sign-reversal (homoscedastic) + rank-test failure DGP |
| 73 | CONSORT-style three-level bottleneck count |
| 74 | Monte-Carlo SE for σ̂ ratios |
| 75, 83 | figures |
| 76–79 | δ_W grid, E6, sharp interval, Tobit m_l grid |

## Data

- GDSC1/GDSC2 fitted dose-response: Genomics of Drug Sensitivity in Cancer (release 27 Oct 2023), https://www.cancerrxgene.org
- CCLE/DepMap: `CCLE_mutations.csv`, `sample_info.csv`, https://depmap.org

## Environment

Python 3.11 with numpy, scipy, pandas, statsmodels.

## Reproducing the analysis

Run scripts 55–79 for the simulations and census; scripts 75 and 83 regenerate the figures. The R0–R5 checklist is importable from `r0_r5_check.py`:

    from r0_r5_check import check_interaction
    check_interaction(n_mut_A, n_wt_A, n_mut_B, n_wt_B, wt_censoring_rate)
