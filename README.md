# Quantitative Analysis of Single-Molecule DNA Mechanics

A reproducible Python analysis of single-molecule magnetic-tweezers data examining how cytosine methylation affects DNA mechanical properties.

### View the Analysis

**[Open the complete Jupyter notebook](codes/single_molecule_DNA_portfolio_analysis.ipynb)**

The notebook contains the complete reproducible workflow, including data-quality assessment, WLC modeling, persistence-length estimation, residual diagnostics, and exploratory classification.

This portfolio project combines **experimental molecular biophysics, data-quality assessment, polymer-physics modeling, statistical analysis, and exploratory machine learning** using representative datasets from previously published single-molecule DNA experiments.

## Scientific Question

DNA methylation is best known for its role in gene regulation, but methylation can also alter the physical properties of the DNA polymer.

This project asks:

**How does cytosine methylation affect DNA mechanical behavior, and can these differences be quantified from single-molecule force–extension measurements?**

Two representative experimental datasets are compared:

* **Control DNA (cPCR):** PCR-generated DNA containing standard dCTP
* **Methylated DNA (mPCR):** methylated PCR-generated DNA produced using 5-methyl-dCTP

## Analysis Overview

The analysis follows a physics-informed computational workflow:

1. Import processed force–extension datasets from the archived experimental project.
2. Validate data structure and historical variable definitions.
3. Assess missing values, numerical ranges, and duplicate observations.
4. Identify and remove duplicated force–extension sequences while preserving the original imported datasets.
5. Model force–extension behavior using a linearized worm-like chain (WLC) relationship.
6. Estimate DNA persistence length for control and methylated DNA.
7. Evaluate model behavior using residual diagnostics.
8. Explore whether the two experimental mechanical states can be distinguished using logistic regression.

## Key Results

The WLC-derived analysis of the two representative datasets estimated persistence lengths of:

* **Control DNA:** 61.4 nm
* **Methylated DNA:** 37.9 nm

The representative methylated dataset therefore shows an approximately **38% lower persistence length**, consistent with increased DNA flexibility.

The fitted WLC-derived models explained approximately:

* **85% of the variation** in the control dataset
* **80% of the variation** in the methylated dataset

As an exploratory computational extension, logistic regression using normalized extension and inverse-square-root force achieved:

* **Accuracy:** 0.694
* **Balanced accuracy:** 0.696
* **ROC-AUC:** 0.806
* **Majority-class baseline accuracy:** 0.529

The classification analysis demonstrates partial separation of the two mechanical states within these representative datasets. Because individual force–extension observations originate from only two representative experiments, classification performance should not be interpreted as evidence of generalization to independent molecules or experiments.

## Worm-Like Chain Analysis

DNA force–extension behavior was analyzed using the low-to-intermediate-force approximation of the worm-like chain model:

```math
\frac{Z}{L}
=
1-\sqrt{\frac{k_BT}{4A}}F^{-1/2}
```

where:

- $Z/L$ is normalized DNA extension
- $F$ is applied force
- $A$ is persistence length
- $k_BT$ is thermal energy

This formulation predicts an approximately linear relationship between normalized extension and $F^{-1/2}$. The regression slope can therefore be used to estimate persistence length:

$$
A=\frac{k_BT}{4b_1^2}
$$

where $b_1$ is the fitted regression slope.

## Data Provenance and Quality Control

The archived CSV files contain processed force–extension measurements rather than the original raw instrument measurements.

A historical column labeled `1/F` was verified against the original analysis workflow and experimental methodology to represent:

$$
F^{-1/2}=\frac{1}{\sqrt{F}}
$$

The variable is therefore renamed `inv_sqrt_force` within the analysis without modifying the archived source files.

Data-quality assessment also identified repeated consecutive sequences of exact force–extension coordinates: 12 duplicate observations in the control dataset and 11 in the methylated dataset. One copy of each duplicated coordinate was retained for modeling, while the originally imported datasets were preserved unchanged.

Final analytical dataset sizes were:

* **Control DNA:** 255 observations
* **Methylated DNA:** 228 observations

## Exploratory Classification

A standardized logistic-regression model was used as a complementary, data-driven analysis of the mechanical feature space.

Each observation was represented by:

* normalized extension
* \(F^{-1/2}\)

The model was evaluated using a stratified train/test split, a majority-class baseline, accuracy, balanced accuracy, ROC-AUC, confusion matrix, and class-specific precision and recall.

This analysis is intentionally exploratory. Individual force–extension observations are not independent biological replicates, so the classification results quantify separation within these two representative datasets rather than predictive performance on independent experiments.

## Computational Tools

* Python
* Pandas
* NumPy
* SciPy
* Matplotlib
* scikit-learn
* Jupyter Notebook

## Repository Contents

* `codes/` — current analysis notebook and historical computational materials
* `archive/` — archived processed datasets and earlier project materials
* `basic_data.xlsx` — historical Excel workbook associated with the original data-processing workflow
* `README.md` — project overview and documentation

## Scientific Context

This portfolio analysis uses representative data from experimental work reported in:

**Zaichuk T, Marko JF.** Single-molecule micromanipulation studies of methylated DNA. *Biophysical Journal*. 2021;120(11):2148–2155.

The published study analyzed multiple independent experiments per condition. The present repository uses two representative processed datasets to demonstrate a transparent and reproducible Python analysis workflow. Consequently, numerical estimates in this notebook are not intended to reproduce the publication-level aggregate statistics.

## Skills Demonstrated

* Scientific data provenance and quality assessment
* Reproducible Python data analysis
* Single-molecule experimental data interpretation
* Physics-informed quantitative modeling
* Linear regression and model diagnostics
* Persistence-length estimation
* Scientific visualization
* Exploratory machine-learning classification
* Recognition of experimental-design and generalization limitations
* Translation of experimental research into a documented computational workflow

## Author

**Tetiana Zaichuk, PhD**

Molecular biology | Genomics | Chromatin biology | Liquid biopsy | Quantitative biophysics | Scientific data analysis

