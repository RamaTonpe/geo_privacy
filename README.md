# Empirical Evaluation of Geo-Indistinguishability Under Bayesian Linkage Attack

Empirical evaluation of the planar Laplace mechanism (Andrés et al., 2013) on NYC restaurant inspection data, with single-query and multi-record Bayesian linkage attacks using PLUTO as auxiliary information.

## Setup

```bash
conda env create -f environment.yml
conda activate geo-privacy
```

## Data

Downloaded automatically via NYC Open Data API:
- [DOHMH Restaurant Inspections](https://data.cityofnewyork.us/Health/DOHMH-New-York-City-Restaurant-Inspection-Results/43nn-pn8j)
- [PLUTO](https://data.cityofnewyork.us/City-Government/Primary-Land-Use-Tax-Lot-Output-PLUTO-/64uk-42ks) — download CSV manually and set `PLUTO_PATH` in the notebook

## Key Findings

- Bayesian priors improve re-identification by up to 43%, with cuisine type as the strongest signal
- Theoretical posterior-to-prior bounds are conservative by ~10x, satisfied in 100% of records
- Record-level vulnerability is driven by noise displacement (ρ = −0.92), not record attributes
- Multi-record attacks improve re-identification with diminishing returns; the composition bound n·ε overestimates empirical degradation

## Reference

Andrés, M. E., Bordenabe, N. E., Chatzikokolakis, K., & Palamidessi, C. (2013). Geo-indistinguishability: Differential privacy for location-based systems. *CCS '13*.
