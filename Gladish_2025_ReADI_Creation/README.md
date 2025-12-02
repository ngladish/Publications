# Estimation of Mortality via the Neighborhood Atlas and Reproducible Area Deprivation Indices

**Manuscript:** Estimation of Mortality via the Neighborhood Atlas and Reproducible Area Deprivation Indices  
**Journal:** *JAMA Network Open* (Original Investigation)  
**Status:** Accepted; embargoed until **December 24, 2025**  
**Authors:** Nicole Gladish, PhD; Robert L Phillips, MD, MSPH; David H Rehkopf, ScD, MPH

> **Embargo note:**  
> This repository is private until the manuscript embargo lifts. After publication, this README and code will be made public. Do **not** redistribute files from this repo prior to the official publication date.

---
## 1. Repository purpose

This repository contains the **analysis code, minimal data derivatives, and documentation** used to reproduce the results for:

> **Gladish N, et al.** *Estimation of Mortality via the Neighborhood Atlas and Reproducible Area Deprivation Indices.* JAMA Network Open. 2025;X(X):eXXXXX.

This repo **does _not_ contain full deprivation index construction code**. Each index (ReADI, NA-ADI, SDI, SVI, NSS7, FDEP) is maintained in its own dedicated repository. Here we:

- Import pre-computed deprivation indices from those repos/datasets
- Merge them with mortality and contextual data
- Run the statistical analyses and generate tables/figures for the paper

The goal is that anyone with access to the underlying indices and input data can **fully reproduce all published results**.

---

## 2. Background (short)

The Neighborhood Atlas Area Deprivation Index (NA-ADI) is widely used in health policy research and incorporated into Medicare payment models such as the Accountable Care Organization Realizing Equity, Access, and Community Health (ACO REACH) Model. However, multiple independent groups have identified calculation errors in the NA-ADI that distort deprivation estimates and risk inequitable funding allocation and outcome adjustment.

In this study, we:

- Compare mortality estimation using the NA-ADI against a **Reproducible Area Deprivation Index (ReADI)** and other deprivation measures
- Quantify how index choice and specification affect mortality risk estimation and potential policy implications

---

## 3. Deprivation indices used in this repository

This repo **consumes** the following indices; it does not build them from raw data.

Update the links below once your index repos are live.

| Index                         | Year(s)| Notes                                                                 |
|------------------------------|---------|-----------------------------------------------------------------------|
| [Reproducible ADI (ReADI)](https://github.com/ngladish/ReADI/tree/main/2011-2015)     | 2015    | Fully reproducible ADI; code and tract-level outputs maintained there |
| [Reproducible ADI (ReADI)](https://github.com/ngladish/ReADI/tree/main/2018-2022)     | 2022    | Updated ReADI for 2022                                                |
| [Neighborhood Atlas ADI (NA-ADI)](https://www.neighborhoodatlas.medicine.wisc.edu/) | 2022 | NA-ADI as recovered from the Neighborhood Atlas website    |
| [Neighborhood Atlas ADI (NA-ADI)](https://www.neighborhoodatlas.medicine.wisc.edu/) | 2015 | NA-ADI version provided directly by the Neighborhood Atlas team       |
| Social Deprivation Index (SDI)  | 2022 | SDI 2022, constructed by Gladish; updated annually                |
| [Social Vulnerability Index (SVI)](https://www.atsdr.cdc.gov/place-health/php/svi/svi-data-documentation-download.html) | 2022 |CDC SVI, downloaded from official website; processed in that repo     |
| NSS7 (Neighborhood SES index)   | 2022 |Seven-component neighborhood SES index; constructed by Gladish        |
| French Deprivation Index (FDEP) | 2022 | FDEP adaptation; constructed by Gladish                               |
| Other indices (future updates)  | various | Central repo aggregating other deprivation indices and updates        |

> **Important:**  
> - This analysis repo assumes the above indices already exist as tract-/ZCTA-level datasets (e.g., `.rds` or `.csv` files).  
> - Users must clone or otherwise obtain those repos/data and adjust file paths accordingly.

---