# NEXUS FORGE publication data package

Data and records for the article **"Sector-by-sector permitting omits the off-site electricity and water burdens that dominate data-center impacts"**
by Zainab Ashkanani, Raúl Sánchez, Reem Abdulrahman, Rashed Albatayneh and Rabi Mohtar (Resources, Conservation and Recycling, submitted).
The article assesses six proposed data centers in the United States and Sweden with the NEXUS FORGE platform, which is free to use online
at https://nexusforgetool.com; its source code is not distributed. Every result in the article can be reproduced in the online tool by loading
the corresponding regional preset (Northern Virginia, Tucson, Central Ohio, Memphis, Nordic, Saline Township) or by entering the site inputs
listed in `reference/site_pedigree.csv`.

## Contents

| Folder | Content |
|---|---|
| `csv/`, `json/` | Outputs of experiments E0 to E28: site inputs with provenance tags, baseline coupled results, weighting presets, coupled versus sequential review and Shapley attribution, compliance screening, sensitivity analyses (one-at-a-time, Monte Carlo, Sobol, weight robustness, normalization and aggregation variants, plume dispersion, valuation), alternative configurations, mitigation interventions, cumulative and climate screening, and the registries of dimensions, rules and interventions. `json/manifest.json` records the random seeds, the sample sizes and the SHA-256 hash of every engine file used in the run. |
| `mc/` | The 10,000 Monte Carlo draws per site (inputs and outputs), for replay of the uncertainty analysis. |
| `figures/` | The 21 figures of the article and its supplement (PNG and PDF), with their captions in `figures_manifest.csv`; the numbering is given below. |
| `tables/` | Equations registry (Supplementary Table S3), methods-sources ledger (Supplementary Table S4), site pedigree, system boundary and feed ledger, the live-application cross-check record, and a workbook containing every table. |
| `reference/` | Source ledgers: every constant with its citation (`methods_sources.csv`), every site input with its tag and citation (`site_pedigree.csv`), the verified constants of the engine revision, field definitions, and the bibliographic manifest of the literature consulted. |

## Figure numbering in the article

| Article | File in `figures/` | Article | File in `figures/` |
|---|---|---|---|
| Fig. 1 | `fig00_system_boundary` | Fig. S8 | `fig19_sobol` |
| Fig. 2 | `fig04_coupled_vs_siloed` | Fig. S9 | `fig20_compliance_variants` |
| Fig. 3 | `fig09_grid_vs_onsite` | Fig. S10 | `fig13_cumulative` |
| Fig. 4 | `fig05_compliance_matrix` | Fig. S11 | `fig14_climate_risk` |
| Fig. S1 | `fig01_pathway_network` | Fig. S12 | `fig15_plume_sensitivity` |
| Fig. S2 | `fig06_sensitivity_tornado` | Fig. S13 | `fig02_dimension_profiles` |
| Fig. S3 | `fig10_cascade` | Fig. S14 | `fig03_nis_presets` |
| Fig. S4 | `fig10b_cascade_dimensions` | Fig. S15 | `fig07_monte_carlo` |
| Fig. S5 | `fig11_normalization_robustness` | Fig. S16 | `fig12_weight_robustness` |
| Fig. S6 | `fig16_tiered_definitions` | Fig. S17 | `fig08_mitigation` |
| Fig. S7 | `fig18_dimension_correlation` | | |

## Reproducing a result

The relations and constants applied by the platform are listed in full in `tables/S_equations_registry.md` and
`tables/S_methods_sources.md`, so any reported value can be recomputed from the inputs in `reference/site_pedigree.csv`
independently of the implementation. For an interactive check, load a preset at https://nexusforgetool.com; the
application and the deposited outputs agree on 188 displayed values (`tables/live_app_crosscheck.md`).

## Citation

See `CITATION.cff`. Correspondence: Zainab Ashkanani, ashkanani@tamu.edu; ashkanani@saaah.co.

## License

The data, figures and tables are released under the Creative Commons Attribution 4.0 International license (CC BY 4.0); see `LICENSE`.
