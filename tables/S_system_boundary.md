# System boundary of the NEXUS FORGE assessment (SI Table S0; v5 engines, 2026-09-05)

**Functional unit.** One proposed data-center facility in one year of steady-state operation at nameplate IT load (kW), described by the permit-application profile (Table S1). Lifetime quantities (embodied carbon of IT hardware and building shell) enter as totals in the e-waste dimension and as annualized flows (IT hardware over the server lifespan, default 4 yr; building over 30 yr) in the carbon balances.

**Spatial scope.** Local: the site parcel (land, stormwater, albedo), the property boundary (noise) and concentric population rings at 0–1, 1–5 and 5–10 km (the health dose–response uses the population-weighted mean increment over the three rings). Regional: the grid subregion supplying the facility (emission factor, renewable share, capacity), the water basin (available volume, recharge, WRI stress class) and, for the grid-attributable burden, the eGRID subregion output rates monetised with EPA benefit-per-ton values (no airshed population is required; deaths are back-calculated from the monetised burden at the VSL).

**Temporal scope.** Annual operation (8,760 h at nameplate IT load; generator hours as entered). Demand-growth projections (E15) extend to 2035 from a frozen baseline year of 2026.

## Engines and what each quantifies

| Engine | Quantity computed | Horizon | Spatial basis | Included | Excluded |
|---|---|---|---|---|---|
| Energy (R) | Facility and IT energy, Scope 1 (generators), Scope 2 (grid factor × (1 − additionally procured renewables)), CUE, grid-capacity share, equivalent homes, cost | annual | facility; grid subregion | on-site fuel combustion; purchased electricity | transmission losses; upstream fuel cycle; construction energy |
| Water (W) | Direct cooling water (WUE × IT energy), indirect thermoelectric water (EWIF derived from the eGRID resource mix × facility energy), aquifer risk (groundwater sites only), drought-vulnerability score, basin stress share of freshwater withdrawal | annual | facility; basin | evaporative consumption (zero for air- and liquid-cooled designs); freshwater withdrawal share of basin; off-site thermoelectric consumption | hydro reservoir evaporation; water quality; discharge |
| Food (F) | Production loss, agricultural revenue loss, food-supply share, irrigation displacement, farm jobs, land inflation | annual | parcel; regional demand | crop displacement; irrigation competition | indirect land-use change; price feedbacks beyond elasticity input |
| Health (H) | Generator NOx/PM2.5/SO2, population-weighted long-term Gaussian increment (Briggs rural dispersion, 0–10 km rings), log-linear premature deaths, asthma ER visits, respiratory hospitalizations, VSL-monetized cost; regional grid-attributable PM2.5/NOx/SO2, deaths and cost; noise radius; EJ score | annual | 1–10 km rings; regional airshed | primary PM2.5 from generators on top of the entered background; delivered kWh × subregion NOx/SO2/PM2.5 output rates monetised with EPA benefit-per-ton (which include secondary PM2.5 and ozone-related NOx effects) | secondary PM2.5 and ozone from the local plume; construction dust |
| Land (L) | Sequestration loss, embodied carbon, net carbon balance, added stormwater runoff, albedo change, ecosystem-service value lost, biodiversity impact score, waste heat | annual (embodied amortized over 30 yr) | parcel | land-cover conversion of the parcel | off-site habitat; supply-chain land; transmission corridors |
| Community (CM) | Net fiscal balance, capture rate, jobs per MW, ratepayer cost shift, cost–benefit ledger (tax, wages, infrastructure vs incentives, public infrastructure, health, ecosystem, agricultural, property losses); net value ex-health per MW (the quantity scored in the composite) | annual | host jurisdiction; ratepayer base | monetized cross-sector damages (tier-1 feeds) | multiplier effects beyond the local multiplier; housing; distributional effects |
| E-waste (EW) | Embodied IT and construction carbon (the default IT figure is per kW of IT capacity, so the scored intensity does not depend on the assumed servers per MW; a site-specific product carbon footprint per server overrides it), lifecycle carbon, embodied share, annualised embodied intensity (tCO₂e per MW-yr, the quantity scored), annual e-waste mass, avoided/landfilled mass, Scope 3 share | lifetime totals; annual flows | facility | hardware and shell embodied carbon; end-of-life mass | end-of-life processing emissions; export flows; toxicity |
| Heat island (UHI) | Waste heat total/to air/recovered, anthropogenic heat flux (W/m²), local ΔT from a steady-state box (cross-wind width × mixing height), albedo, impervious and vegetation terms, UHI estimate, heat-mortality relative risk, cooling-demand increase, recovery potential and revenue | annual | site footprint × near-surface mixing height | rejected waste heat; surface change | mesoscale meteorology; downwind advection |
| Grid & traffic (GR, G) | Grid-capacity share, transmission utilization, infrastructure costs, construction truck trips | annual; construction period | grid subregion; road network | capacity share; entered utilization | dispatch, reserve-margin dynamics; reliability indices unless entered |
| Supply chain (SC) | Material risk index (criticality × concentration × growth) scaled by facility energy throughput and circularity; the critical-mineral exposure of a high-renewable supply is reported separately and no longer raises the scored risk | annual | global supply chains | seven material classes with default scores | site-specific procurement; price effects |
| Nexus score (NX) | Composite Nexus Impact Score (0–1), ten normalized dimensions, five weighting presets. Scale-free raw metrics: health as damage intensity ($/MWh of facility electricity), e-waste as embodied intensity (tCO₂e per MW-yr), community as net value ex-health per MW, grid as % of utility capability | — | — | additive weighted aggregation with hard clipping to fixed ranges; weights re-normalised over the scored dimensions (coverage reported) | — |
| Compliance (CP), cumulative (CUM), climate (CR), CBA | Threshold screening; regional stacking heuristics; hazard exposure; benefit-agreement clauses | annual | as above | screening only | site-specific permitting, dispersion modelling, hazard maps |

## Cross-engine feed ledger (13 feeds) and the sequential-review counterfactual

| Feed | Tier | Kept in sequential review? | From → to | What flows |
|---|---|---|---|---|
| R>W | 0 | yes | energy → water | IT × PUE × 8,760 (facility and IT energy) |
| R>G | 0 | yes | energy → grid reliability | facility MW |
| R>GR | 0 | yes | energy → grid & traffic | facility MW ÷ regional capacity |
| R>SM | 0 | yes | energy → scenarios | facility energy |
| W>F | 1 | no | water → food | direct withdrawal as irrigation competition |
| R>L | 1 | no | energy → land | operational carbon in the site carbon balance |
| H>CM | 1 | no | health → community | monetized local health damages in the cost–benefit ledger (the composite scores the ledger ex-health, so this feed no longer reaches the score) |
| L>CM | 1 | no | land → community | ecosystem-service loss in the ledger |
| F>CM | 1 | no | food → community | agricultural revenue loss in the ledger |
| R>EW | 1 | no | energy → e-waste | operational carbon in lifecycle carbon |
| L>UHI | 1 | no | land → heat | impervious fraction in the warming term |
| R>H | 2 | no | energy → health | grid-attributable regional PM2.5/NOx/SO2 burden (scope boundary of a local air-quality review) |
| R>SC | 3 | no (fallback to server count) | energy → supply chain | energy throughput as the scale proxy (severing it substitutes another application field) |

**Counting glossary (used consistently in the manuscript).** 14 pathways are described in the platform registry (E7); 13 of them are computed cross-engine feeds in code, of which 4 are tier-0 identity arithmetic (always kept) and 9 are severable; 8 of the 9 are severed in the manuscript definition of sequential review (tiers 1 and 2; the tier-3 scale proxy R>SC is kept and reported separately); 2 feeds carry more than 95 % of the coupling gap (R>H at the fossil-heavy sites, R>SC at Northern Virginia and the Nordic site; E5c); 5 severable feeds (W>F, R>L, H>CM, R>EW, L>UHI) are numerically inert for the composite score in v4 because the quantities they carry are not scored (H>CM: the community dimension is ex-health) or enter dimensions whose inputs are fixed.

Tier 0 feeds are identity arithmetic on application fields that every reviewer performs; they are never severed. The manuscript's "sequential single-sector review" is defined as severing tiers 1 and 2 (E5b `tier1_2`); the legacy all-nine definition (E5) and the exact Shapley attribution of the gap to each feed (E5c) are reported for transparency.

## Explicitly outside the boundary

Construction-phase emissions and traffic beyond truck-trip counts; transmission and distribution losses; upstream fuel-cycle emissions; secondary aerosol formation from the local plume; hydro reservoir evaporation in the off-site water term; end-of-life processing of hardware; housing and labor-market effects; cumulative effects beyond the heuristic multipliers of the cumulative engine.
