# Reproducible Analysis for ReADI vs NA-ADI (JAMA Netw Open 2025)

This repository contains the **fully reproducible analysis pipeline** for:

> **Estimation of Mortality via the Neighborhood Atlas and Reproducible Area Deprivation Indices**\
> Nicole Gladish, PhD; Robert L. Phillips, MD, MSPH; David H. Rehkopf, ScD, MPH\
> *JAMA Network Open.* 2025;8(12):e2546800.\
> <doi:10.1001/jamanetworkopen.2025.46800>


To view the fully rendered analysis code click [here](<https://ngladish.github.io/Publications/Gladish_2025_ReADI_Creation/Analysis.html>)

The code in this folder reproduces all analyses reported in the paper:

-   construction of analysis datasets,
-   comparison of ReADI and NA-ADI at census block group, tract, and county levels,
-   agreement and discrepancy analyses,
-   life expectancy models using USALEEP tract estimates, and
-   all figures and tables included in the manuscript.

All data used here are **publicly available** from external sources.

------------------------------------------------------------------------

## 1. How to reproduce the analysis

### 1.1 R and system requirements

-   This analysis was developed and tested under **R 4.4.1**.
-   Please use R 4.4.1 (or another R 4.4.x release) if possible.

This project uses spatial packages (`sf`, `s2`) that sometimes need extra system tools on a fresh machine. If `renv::restore()` fails with errors about compiling `s2`, `cmake`, or `abseil`:

**On macOS:**

1.  Open the Terminal app.
2.  Run:
    ``` bash
    xcode-select --install 
    brew install cmake
    ```
(If you do not have Homebrew, see <https://brew.sh> to install it.)
3.  Then restart R and continue with the R commands in section 1.2 below.

**On Windows**

1.  Install the current version of **R** and the matching **Rtools** for your R version from CRAN (<https://cran.r-project.org>).
2.  During the Rtools install, allow it to add itself to the system PATH.
3.  Restart R and continue with the R commands in section 1.2 below.

**On Ubuntu / Debian Linux**

1.  Open a terminal and run:
    ``` bash
    sudo apt-get update
    sudo apt-get install -y build-essential cmake \
        libudunits2-dev libgdal-dev libgeos-dev libproj-dev
    ```
2.  Then restart R and continue with the R commands in section 1.2 below.

### 1.2 Clone the repository

From a terminal:

``` bash
git clone https://github.com/ngladish/Publications.git
cd Publications/Gladish_2025_ReADI_Creation
```

You should now see `Analysis.Rmd` and the subdirectories described below.

### 1.3 Restore the R environment (same on macOS, Windows, and Linux)

In R, with the working directory set to `Gladish_2025_ReADI_Creation`, run:

``` R
install.packages("renv")      # if not already installed
renv::restore()               # installs the project-specific package versions
```

If you prefer that `renv` avoid compiling from source when a binary is available, you can run:

``` R
Sys.setenv(RENV_CONFIG_INSTALL_FROM_SOURCE = "never")
renv::restore()
```

(This does not remove the need for system tools if no binary exists for your platform, but it avoids unnecessary compilation.)

### 1.4 Run the full pipeline (same on all systems)

Once `renv::restore()` has completed successfully, run:

``` R
rmarkdown::render("Analysis.Rmd")
```

This will:

-   download and/or load all required public datasets into `data_raw/` (if not already present),
-   construct intermediate and derived analysis datasets,
-   fit all models and perform all diagnostics, and
-   write output figures and tables used in the manuscript.

------------------------------------------------------------------------

## 2. How to cite

If you use this code or the ReADI index in your work, please cite:

- The manuscript: *Estimation of Mortality via the Neighborhood Atlas and Reproducible Area Deprivation Indices* (JAMA Network Open, 2025; add full citation once available).

- This analysis repository:  
  Gladish N. **ReADI vs NA-ADI reproducible analysis code**.  
  GitHub: https://github.com/ngladish/Publications  
  Subdirectory: `Gladish_2025_ReADI_Creation`.
