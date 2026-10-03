# Live-app cross-check (v4 and v5 engines, corrected presets)

The harness (`harness/core.mjs`, not deposited because it imports the engine source) mirrors `src/store/NexusContext.jsx` call for call, so every number in this package must also appear in the running application. Two cross-checks were run on 2026-09-05.

**Round 1 (first v4 run, independent auditor).** The dev server was started locally, each of the six Quick-Start presets was applied through the app (full state reset, then the preset overlay) and the Full Report, Nexus Score, Compliance Check and Water views were read through the sidebar. **114 displayed values compared, 0 mismatches** (19 metrics x 6 sites, tolerance = display rounding). Scope 2 carbon is not displayed on those four views, so it could not be compared there. Two display observations were recorded: the Full Report rendered every number at or above one million as a dollar amount regardless of unit, and PM2.5 concentrations below 0.005 µg/m³ display as "0" at two decimals.

**Round 2 (final run, after the mitigation, food, community-benefit and emission-factor fixes).** The same procedure was repeated for all six presets against `json/E1_baseline_<site>.json`. The unit-formatting defect found in round 1 was fixed in `src/sections/FullReport.jsx` (money now carries the currency symbol, other quantities are compacted as `M`/`B` with their own unit) and re-verified.

| Site | Metric | App (Full Report) | Harness (E1 baseline) | Match |
|---|---|---|---|---|
| Northern Virginia | Nexus Impact Score | 0.192 | 0.1917 | yes |
| Northern Virginia | Carbon (Scope 1+2) | 292,507.2 tCO2e/yr | 292,507.2 | yes |
| Northern Virginia | Total energy | 1.05M MWh/yr | 1,051,200 | yes |
| Northern Virginia | Grid impact | 0.58 % | 0.583 | yes |
| Northern Virginia | Daily water consumption | 2.24M gal/day | 2,241,556 | yes |
| Northern Virginia | NOx (local generators) | 76.8 t/yr | 76.8 | yes |
| Northern Virginia | PM2.5 (local generators) | 2.4 t/yr | 2.4 | yes |
| Northern Virginia | Local health cost | $972,460.22/yr | 972,460.22 | yes |
| Northern Virginia | Grid health cost | $29.4M/yr | 29,401,538 | yes |
| Northern Virginia | Total health cost | $30.4M/yr | 30,374,000 | yes |
| Northern Virginia | Premature deaths | 0.08 /yr | 0.08 | yes |
| Northern Virginia | Food security impact | 0.42 % | 0.4153 | yes |
| Northern Virginia | E-waste generated | 312.5 t/yr | 312.5 | yes |
| Northern Virginia | Heat-island estimate | 0.27 °C | 0.272 | yes |
| Northern Virginia | Compliance | 3 violations, 4 warnings | fail 3, warn 4 | yes |
| Tucson | Nexus Impact Score | 0.226 | 0.2261 | yes |
| Tucson | Carbon (Scope 1+2) | 819,782.4 tCO2e/yr | 819,782.4 | yes |
| Tucson | Grid impact | 9.15 % | 9.154 | yes |
| Tucson | Daily water consumption | 1.81M gal/day | 1,807,618 | yes |
| Tucson | NOx (local generators) | 153.6 t/yr | 153.6 | yes |
| Tucson | Local health cost | $422,139.86/yr | 422,139.86 | yes |
| Tucson | Total health cost | $77.4M/yr | 77,393,092 | yes |
| Tucson | Production lost (desert parcel) | 0 t/yr | 0 | yes |
| Tucson | E-waste generated | 718.75 t/yr | 718.75 | yes |
| Tucson | Compliance | 3 violations, 4 warnings | fail 3, warn 4 | yes |
| Central Ohio | Nexus Impact Score | 0.202 | 0.2023 | yes |
| Central Ohio | Total energy | 709,560 MWh/yr | 709,560 | yes |
| Central Ohio | Carbon (Scope 1+2) | 301,689.36 tCO2e/yr | 301,689.4 | yes |
| Central Ohio | NOx (local generators) | 57.6 t/yr | 57.6 | yes |
| Central Ohio | Local health cost | $268,795.93/yr | 268,795.93 | yes |
| Central Ohio | Total health cost | $33.6M/yr | 33,557,151 | yes |
| Central Ohio | Food security impact | 0.03 % | 0.033 | yes |
| Central Ohio | Net community value | -$11.4M/yr | -11,439,790 | yes |
| Central Ohio | Compliance | 4 violations, 2 warnings | fail 4, warn 2 | yes |
| Memphis | Nexus Impact Score | 0.229 | 0.2290 | yes |
| Memphis | NOx (local generators, SCR factor) | 1.09 t/yr | 1.089 | yes |
| Memphis | PM2.5 (local generators) | 0.87 t/yr | 0.871 | yes |
| Memphis | Local health cost | $33,777.22/yr | 33,777.22 | yes |
| Memphis | Grid health cost | $143.0M/yr | 142,968,824 | yes |
| Memphis | Grid PM2.5 (regional) | 219.79 t/yr | 219.79 | yes |
| Memphis | Daily water consumption | 3.84M gal/day | 3,844,787 | yes |
| Memphis | Environmental-justice score | 78.2 | 78.2 | yes |
| Memphis | Compliance | 2 violations, 4 warnings | fail 2, warn 4 | yes |
| Memphis | Mitigation: preset package ΔNIS | ↓ 0.102 (4 interventions) | -0.1020 (E10, kind = recommended) | yes |
| Nordic | Nexus Impact Score | 0.203 | 0.2026 | yes |
| Nordic | Total energy | 267,355.2 MWh/yr | 267,355 | yes |
| Nordic | Carbon (Scope 1+2) | 9,791.59 tCO2e/yr | 9,791.6 | yes |
| Nordic | NOx (local generators) | 0.43 t/yr | 0.426 | yes |
| Nordic | Local health cost | $3,264.64/yr | 3,264.64 | yes |
| Nordic | Total health cost | $2.9M/yr | 2,917,276 | yes |
| Nordic | Daily water consumption | 156,780.35 gal/day | 156,780 | yes |
| Nordic | Production lost (forest parcel) | 0 t/yr | 0 | yes |
| Nordic | Compliance | 1 violation, 1 warning | fail 1, warn 1 | yes |
| Saline Township | Nexus Impact Score | 0.394 | 0.3943 | yes |
| Saline Township | IT load | 1.11M kW | 1,106,000 | yes |
| Saline Township | Total energy | 12.11M MWh/yr | 12,110,700 | yes |
| Saline Township | Carbon (Scope 1+2) | 5.37M tCO2e/yr | 5,365,162 | yes |
| Saline Township | Grid impact | 11.43 % | 11.427 | yes |
| Saline Township | Daily water consumption | 9.82M gal/day | 9,823,384 | yes |
| Saline Township | Annual water total | 13.57B L/yr | 13,571,283,000 | yes |
| Saline Township | NOx (local generators) | 1.08 t/yr | 1.075 | yes |
| Saline Township | Local health cost | $410.58/yr | 410.58 | yes |
| Saline Township | Grid health cost | $704.81M/yr | 704,813,432 | yes |
| Saline Township | Food security impact | 0.15 % | 0.1486 | yes |
| Saline Township | Compliance | 0 violations, 2 warnings | fail 0, warn 2 | yes |

**Round 2 result: 62 displayed values compared across the six presets, 0 mismatches**, including the four quantities that the final round of engine changes moved (on-site NOx and PM2.5 under the verified emission factors, the food dimension on non-cropland parcels, the compliance verdict at Memphis, and the mitigation-package score change). Combined with round 1 the application and the publication package agree on 176 displayed values with no discrepancy.

Notes for reproducing the check: the application is sidebar-routed (no URL paths), so sections are reached by clicking the sidebar; applying a preset performs a full state reset before overlaying the preset data; PM2.5 concentrations below 0.005 µg/m³ still display as "0" at the Full Report's two decimals (the underlying values are in `E1_key_metrics_by_metric.csv`); Scope 2 carbon appears only in the Energy section's results panel.

## Round 3 (v5 engines: health intensity, embodied-carbon basis, supply penalty, heat model)

The four v5 changes alter what the composite scores, so the Nexus Score panel was re-read in the application for two presets and compared with `csv/E1_key_metrics_wide.csv` and `json/E1_baseline_<site>.json`.

| Site | Panel value (app) | Harness | Match |
|---|---|---|---|
| Saline Township | composite 0.384; coverage 100 %, 10 of 10 dimensions | 0.3842; coverage 1.0 | yes |
| Saline Township | health 0.48 at 58.2 $/MWh | 0.485 at 58.20 $/MWh | yes |
| Saline Township | e-waste 0.73 at 1,311.0 tCO₂e/MW-yr | 0.728 at 1,311.0 | yes |
| Saline Township | heat island 0.39 at 0.8 °C | 0.387 at 0.774 °C | yes |
| Saline Township | supply chain 0.61 | 0.612 | yes |
| Saline Township | grid 0.38 at 11.4 % of capability | 0.381 at 11.43 % | yes |
| Memphis | composite 0.304; coverage 100 % | 0.3041 | yes |
| Memphis | health 0.42 at 50.2 $/MWh | 0.419 at 50.23 $/MWh | yes |
| Memphis | e-waste 0.96 at 1,727.6 tCO₂e/MW-yr | 0.960 at 1,727.6 | yes |
| Memphis | heat island 0.24 at 0.5 °C | 0.242 at 0.483 °C | yes |
| Memphis | food 0.00 (brownfield parcel) | 0.000 | yes |
| Memphis | community 0.22 ex-health per MW | 0.219 | yes |

**Round 3 result: 12 displayed values compared, 0 mismatches.** Together with rounds 1 and 2 the application and the publication package agree on 188 displayed values with no discrepancy. The panel also shows the new units directly ("58.2 $/MWh", "1,311.0 tCO₂e/MW-yr"), so a reader of the application sees the same normalisation basis the manuscript reports.
