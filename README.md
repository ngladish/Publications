
# Publications

Analysis code for selected published manuscripts.

**Disclaimer.** Code here is written to reproduce specific analyses as
they were performed for each paper. It depends on the R versions and
package stacks used at the time of publication and is **not** a
general-purpose, actively maintained software library. If you adapt it
for new data or newer R/package versions you will likely need to make
modifications.

------------------------------------------------------------------------

## Contents

-   [ReADI (JAMA Network Open
    2025)](1-estimation-of-mortality-via-the-neighborhood-atlas-and-reproducible-area-deprivation-indices-readi)
-   [GUTS sperm DNA methylation (Translational Psychiatry
    2018)](#2-exposure-to-childhood-abuse-is-associated-with-human-sperm-dna-methylation)
-   [General notes](#general-notes-on-using-this-repository)

------------------------------------------------------------------------

## Repository structure

-   `Gladish_2025_ReADI_Creation/`\ Reproducible analysis for the Reproducible Area Deprivation Index (ReADI) vs Neighborhood Atlas ADI mortality paper (JAMA Network Open 2025).

-   `Roberts_2018_ChildhoodAbuse_DNAm/`\ Analysis code for the GUTS sperm DNA methylation / childhood abuse paper (Translational Psychiatry 2018).

Each subdirectory contains its own README with more detailed
instructions, including R / package versions and how to run the
corresponding analysis.

------------------------------------------------------------------------

## Manuscripts

### 1. Estimation of Mortality via the Neighborhood Atlas and Reproducible Area Deprivation Indices (ReADI)

<br>

#### Citation

Gladish N, Phillips RL, Rehkopf DH.\
**Estimation of Mortality via the Neighborhood Atlas and Reproducible
Area Deprivation Indices.** *JAMA Network Open.* 2025;8(12):e2546800.\
<doi:10.1001/jamanetworkopen.2025.46800>

<br>

#### Overview

This paper introduces the **Reproducible Area Deprivation Index
(ReADI)** and compares it with the widely used **Neighborhood Atlas ADI
(NA-ADI)** for predicting mortality in the United States. Analyses are
performed at the census block group, tract, and county levels and
include:

-   construction of ReADI and NA-ADI measures on common public data
    inputs,
-   cross-walks between geographies,
-   agreement, discrepancy, and rank-change analyses, and
-   mortality and life-expectancy models comparing the predictive
    performance of ReADI vs NA-ADI.

The paper is designed to be fully reproducible from public inputs only;
all intermediate data products used in the manuscript can be re-created
with this code and publicly available datasets.

<br>

#### Code and documentation

-   **Directory:**\ `Gladish_2025_ReADI_Creation/`

-   **Primary analysis notebook:**\ `Gladish_2025_ReADI_Creation/Analysis.Rmd`\ Runs the full pipeline from raw public data to all manuscript figures, tables, and key summary statistics.

-   **Rendered HTML report (complete analysis):**\ If you are viewing this on GitHub with Pages enabled:
    -   [View the full reproducible HTML report](https://ngladish.github.io/Publications/Gladish_2025_ReADI_Creation/Analysis.html)
<br>
    Otherwise (or for local use):
    -   Download or open `Gladish_2025_ReADI_Creation/Analysis.html` in a web browser.
<br>
-   **Reproducibility / environment:**\
    The subdirectory uses [`renv`](https://rstudio.github.io/renv/) to
    freeze the R package environment (developed under **R 4.4.1**). See
    `Gladish_2025_ReADI_Creation/README.md` for:

    -   system requirements (macOS / Windows / Linux),
    -   instructions for running `renv::restore()`, and
    -   how to render the full report via
        `rmarkdown::render("Analysis.Rmd")`.

------------------------------------------------------------------------

### 2. Exposure to childhood abuse is associated with human sperm DNA methylation (GUTS)

<br>

#### Citation

Roberts AL, Gladish N, Gatev E, et al.\
**Exposure to childhood abuse is associated with human sperm DNA
methylation.**\
*Translational Psychiatry.* 2018;8:194.\
<doi:10.1038/s41398-018-0252-1>

[Access Here](https://www.nature.com/articles/s41398-018-0252-1)

(Open access under a Creative Commons Attribution 4.0 license.)

<br>

#### Overview

Using data from the **Growing Up Today Study (GUTS)**, this paper
examines whether men’s self-reported exposure to childhood abuse is
associated with DNA methylation in sperm. Key features:

-   46 sperm samples from 34 men, with oversampling of men reporting
    high levels of childhood abuse.
-   Genome-wide methylation profiling using Illumina HumanMethylation450
    BeadChips and stringent QC / normalization.
-   Multiple analytic approaches:
    -   principal component analysis of whole-genome methylation,
    -   identification of differentially methylated regions (DMRs) by
        abuse exposure (DMRcate),
    -   pyrosequencing confirmation of selected loci,
    -   elastic-net machine learning to derive a parsimonious
        methylation signature predictive of high vs. no abuse.
-   Identification of DMRs in genes involved in neuronal function (e.g.
    *MAPT*, *CLU*), adipose regulation (*PRDM16*), and immune function
    (*SDK1*).

<br>

#### Code and documentation

-   **Directory:** `Roberts_2018_ChildhoodAbuse_DNAm/`

-   **Contents:**

    -   preprocessing and QC of 450K methylation data,
    -   PCA and association of principal components with abuse exposure,
    -   DMR identification (DMRcate),
    -   pyrosequencing confirmation analyses,
    -   elastic-net model fitting and performance evaluation,

- **Available Code**:
    - [Pre-processing of DNAm data](https://github.com/ngladish/Publications/blob/main/Roberts_2018_ChildhoodAbuse_DNAm/Pre-Processing%20and%20Normalization%20GUTS.Rmd)
    - [Analysis code](https://github.com/ngladish/Publications/blob/main/Roberts_2018_ChildhoodAbuse_DNAm/GUTS_Abuse_Analysis.Rmd)

-   **Usage:**\ See the README within the `Roberts_2018_ChildhoodAbuse_DNAm/` subdirectory for further details.

------------------------------------------------------------------------

## General notes on using this repository

<br>

-   **Project-specific environments.**\ Each manuscript subdirectory was developed under its own R / package
    environment. Always start by reading the sub-README and restoring
    the project environment (typically via `renv::restore()`) before
    running any code.

-   **Data access.** All data used for the ReADI JAMA paper are public
    and are downloaded directly from external sources at run time or via
    documented URLs. For the GUTS project, the underlying sperm DNA
    methylation data are restricted and subject to data-use agreements.
    The GUTS code in this repo therefore focuses on the **preprocessing
    and normalization steps only** and is provided for transparency
    rather than as a fully self-contained, rerunnable pipeline.

-   **Code maturity and intended use.** The ReADI materials are designed
    as a fully reproducible analysis, with an environment that can be
    restored and rerun using only public inputs. The GUTS materials
    document key analytic steps for a project conducted on restricted
    data and are intended primarily for methodological transparency and
    reference. Across both projects, the code is meant to show how the
    published results were generated and to support careful review or
    extension by other researchers. It is not optimized or guaranteed
    for arbitrary new datasets, clinical decision-making, or production
    software use.

-   **Questions/issues.**\ If you encounter problems reproducing an analysis or have questions
    about specific steps, please open an issue on the GitHub repository
    or contact the corresponding author of the relevant paper.
