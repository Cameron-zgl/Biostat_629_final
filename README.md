# MSK-CHORD Final Project Reproducibility

This repository contains the reproducible R Markdown file for the final project.

## Project Overview

This project analyzes the MSK-CHORD 2024 cohort by integrating multiple genomic data modalities, including somatic mutations, copy-number alterations (CNA), structural variants (SV), and clinical sample information.

The main goal is to identify unsupervised genomic abnormality patterns and evaluate whether these clusters are associated with clinical variables such as cancer type, metastatic site, tumor mutational burden (TMB), and microsatellite instability (MSI).

## Repository Structure

```text
.
├── project.Rmd
├── outputs/
│   ├── figures/
│   └── tables/
└── msk_chord_2024/
```

## Main Reproducible File

The main analysis file is:

```text
project.Rmd
```

Open this file in RStudio and click **Knit** to reproduce the analysis and output.

## Data Source

The required MSK-CHORD data files are read directly from the cBioPortal DataHub GitHub repository:

```text
https://github.com/cBioPortal/datahub/tree/master/public/msk_chord_2024
```

The R Markdown file reads the necessary files directly from the online GitHub raw URLs, including:

```text
data_clinical_patient.txt
data_clinical_sample.txt
data_mutations.txt
data_cna.txt
data_sv.txt
```

The local `msk_chord_2024/` folder is not required to run the reproducible analysis if the online data links are available.

## How to Run

1. Clone or download this repository.
2. Open `project.Rmd` in RStudio.
3. Click **Knit**.
4. The analysis should run from the online MSK-CHORD data files and generate the same output.

## Outputs

The R Markdown file generates output files under:

```text
outputs/
```

This folder contains generated figures and tables used in the final report.

## Reproducibility Notes

- A random seed is set at the beginning of the R Markdown file using `set.seed()`.
- All required MSK-CHORD data files are read directly from the cBioPortal DataHub GitHub repository.
- Non-random numerical results are calculated directly in the R Markdown file.
- Random steps such as k-means clustering are controlled using the seed for reproducibility.
- The analysis was checked by rerunning the R Markdown file and confirming that the main outputs remained consistent.

## Main Packages Used

The analysis uses standard R packages, including:

```text
tidyverse
dplyr
ggplot2
readr
janitor
knitr
```

Additional packages may be loaded in the R Markdown file for data cleaning, plotting, or clustering diagnostics.

## Notes

If the R Markdown file takes longer than expected to run, this is likely due to downloading and processing the full MSK-CHORD genomic files from GitHub. The generated outputs are saved in the `outputs/` folder after running the analysis.
