# Reproducible Analysis for ReADI vs NA-ADI (JAMA Netw Open 2025)

This repository contains the **fully reproducible analysis pipeline** for:

> **Estimation of Mortality via the Neighborhood Atlas and Reproducible Area Deprivation Indices**  
> Nicole Gladish, PhD; Robert L. Phillips, MD, MSPH; David H. Rehkopf, ScD, MPH  
> *JAMA Network Open.* 2025;8(12):e2546800.  
> doi:10.1001/jamanetworkopen.2025.46800

The code in this folder reproduces all analyses reported in the paper:

- construction of analysis datasets,
- comparison of ReADI and NA-ADI at census block group, tract, and county levels,
- agreement and discrepancy analyses,
- life expectancy models using USALEEP tract estimates, and
- all figures and tables included in the manuscript.

All data used here are **publicly available** from external sources.

---

## 1. How to reproduce the analysis

### 1.1 Requirements

- R version: a modern R 4.x release.  
  The original analysis was conducted under an R 4.4.1 environment; the exact version and platform are recorded in the `sessionInfo()` output at the end of the rendered report.
- Internet connection for the first run (to download required data into `data_raw/`).
- Roughly 15–20 minutes of runtime on a standard laptop.

This project uses [`renv`](https://rstudio.github.io/renv/) to freeze package versions and ensure reproducibility.

### 1.2 Clone the repository

From a terminal:

```bash
git clone https://github.com/ngladish/Publications.git
cd Publications/Gladish_2025_ReADI_Creation