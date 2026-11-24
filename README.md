# Minimum Wage Increases and Short-Term Job Stability: Testing for Gendered Effects in the US Labor Market
Author: Camilla Santopietro  
University: Bocconi University  
Degree: BSc International Politics and Government  
Year: 2025  
Project: Undergraduate Thesis  
Research Areas: Labor Economics, Gender Inequality, Applied Econometrics
## Overview

This repository contains the paper and supporting Python notebooks for an empirical investigation of the relationship between minimum-wage policies and short-term employment stability in the United States.

The research examines whether increases in the minimum wage are associated with changes in workers' probability of remaining employed and whether these relationships differ between women and men.

The analysis is grounded in a monopsonistic model of the labor market, under which moderate increases in minimum wages may improve employment outcomes by limiting employers' wage-setting power.

## Research Questions

1. How do minimum-wage increases relate to short-term employment stability?
2. Are there systematic gender differences in employment stability?
3. Do minimum-wage increases affect women's employment stability differently from men's?

## Data

The research focuses on prime-age workers (25–54) and uses three principal data sources:

**1. CPS Basic Monthly — IPUMS**

Individual-level employment and demographic information used to construct longitudinal employment-stability measures.

Source: https://cps.ipums.org/

**2. CPS Outgoing Rotation Group — CEPR**

Wage and demographic information used for descriptive analysis and the construction of state-level median wages.

Source: https://ceprdata.org/cps-uniform-data-extracts/

**3. Historical State and Sub-state Minimum Wages**

Minimum-wage policy data compiled by Vaghul and Zipperer, used to identify policy variation and construct measures of minimum-wage bindingness.

The Kaitz index is defined as:

Kaitz Index = Minimum Wage / Median Wage

### Data availability

The original microdata and large intermediate datasets are not distributed through this repository.

Researchers should obtain the relevant datasets from their original providers, comply with the applicable terms of use, and place them in the directories described in `README_SETUP.md`.

## Empirical Methodology

The thesis employs three complementary approaches:

- **Fixed-effects linear probability models:** Estimate the association between minimum-wage bindingness and employment stability, including interactions with gender.
- **Difference-in-Differences (DiD):** Examine employment-stability changes surrounding the January 2015 minimum-wage increases in selected US states.
- **Triple-Differences (DDD):** Investigate whether the estimated policy effects differ between women and men.

Robustness analyses consider nonlinear relationships with minimum-wage bindingness and longer employment-stability windows.

## Repository Structure

| Directory | Contents |
|---|---|
| `notebooks/` | Data preparation, longitudinal matching, estimation, and robustness notebooks |
| `src/` | Reusable Python utilities |
| `scripts/` | Input preparation and validation scripts |
| `config/` | Project configuration |
| `docs/` | Supporting documentation and dataset metadata |
| `data/` | Locally stored datasets, excluded from version control |

## Notebook Execution Order

| Notebook | Purpose |
|---|---|
| `00_project_setup.ipynb` | Initialize project directories and dependencies |
| `00_support_setup.ipynb` | Configure support utilities |
| `01_cps_basic_matching.ipynb` | CPS longitudinal matching and employment-stability construction |
| `02_org_wages.ipynb` | ORG wage preparation and weighted medians |
| `03_minimum_wage_kaitz.ipynb` | Minimum-wage policies and Kaitz index |
| `04_build_analysis_panels.ipynb` | Construct OLS and DiD analysis datasets |
| `05_fixed_effects_ols.ipynb` | Fixed-effects regressions and nonlinear specifications |
| `06_did_ddd_robustness.ipynb` | DiD, candidate DDD, and three-month robustness analysis |

## Installation

Clone the repository and install the Python dependencies:

```bash
git clone https://github.com/YOUR-USERNAME/minimum-wage-gender-job-stability.git
cd minimum-wage-gender-job-stability
python -m pip install -r requirements.txt
```

Obtain the source datasets separately and follow `README_SETUP.md` for directory setup, extraction, and preparation instructions.

Run Jupyter from the project root:

```bash
jupyter notebook
```

## Reproducibility Status

The Python notebooks contain source-based translations, data-processing procedures, and diagnostic checks related to the thesis.

**They should not currently be interpreted as a fully verified reproduction of the thesis's published estimates.**

Outstanding validation work includes longitudinal matching, geographic code harmonization, policy definitions, weighting, fixed-effects specifications, and reconciliation of regression results.

The original datasets are preserved without modification.

## Thesis

The full academic thesis is available in [`thesis.pdf`](thesis.pdf).

## Data Citations

This research uses three datasets:

**1. IPUMS CPS Basic Monthly**

Flood, S., King, M., Rodgers, R., Ruggles, S., Warren, J. R., Backman, D., Breton, E., Cooper, G., Rivera Drew, J. A., Richards, S., Van Riper, D., & Williams, K. C. W. (2025). *IPUMS CPS: Version 13.0* [dataset]. IPUMS. https://doi.org/10.18128/D030.V13.0

**2. CEPR CPS Outgoing Rotation Group (ORG)**

Center for Economic and Policy Research (CEPR). (n.d.). *CPS ORG Uniform Extracts* (Version 2.5) [dataset]. https://ceprdata.org/cps-uniform-data-extracts/

**3. Historical State and Sub-state Minimum Wages**

Vaghul, K., & Zipperer, B. (2022). *Historical State and Sub-state Minimum Wages* [dataset]. https://github.com/benzipperer/historicalminwage

The datasets are provided by their respective institutions and authors. Original microdata are not redistributed through this repository.

## License

The original Python code in this repository is licensed under the **Apache License, Version 2.0**. See the [LICENSE](LICENSE) file for details.

The academic thesis PDF remains subject to the author's copyright and is not licensed under Apache 2.0.

Third-party datasets, including IPUMS CPS, CEPR CPS ORG, and minimum-wage policy data, remain subject to their respective providers' licensing and usage conditions.

The Apache 2.0 license does not grant redistribution rights over third-party data or documentation.
