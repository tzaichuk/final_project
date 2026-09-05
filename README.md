# Quantitative Analysis of Single-Molecule DNA Mechanics

## Overview

This project applies Python-based quantitative analysis to experimental magnetic-tweezers measurements of individual DNA molecules. The analysis examines the mechanical behavior of methylated and control DNA and explores computational approaches for estimating DNA persistence length from force-extension measurements.

The project was developed as part of the Northwestern University Data Science and Visualization Boot Camp using experimental single-molecule datasets.

## Scientific Question

DNA methylation can influence the physical properties of DNA in addition to its established role in gene regulation. This project examines whether quantitative analysis of single-molecule magnetic-tweezers measurements can characterize differences in the mechanical behavior of methylated and control DNA.

## Data

The analysis uses digitized measurements obtained from magnetic-tweezers experiments on individual DNA molecules.

Experimental measurements include:

* magnet position and applied force
* DNA extension
* magnet rotation
* methylated and control DNA conditions
* repeated measurements across experimental conditions

## Analysis Workflow

1. Import and clean experimental data from CSV/Excel files.
2. Transform magnet-position measurements into force-related variables.
3. Normalize DNA extension relative to maximum measured length.
4. Calculate mean and standard deviation of normalized DNA extension across force and rotation conditions.
5. Transform force measurements for quantitative modeling.
6. Apply linear regression to experimental measurements to estimate DNA persistence length.
7. Combine measurements from multiple experiments for comparative analysis.
8. Compare conventional linear-regression results with exploratory machine-learning regression approaches.
9. Visualize and compare results for methylated and control DNA.

## Computational Methods

The project uses Python-based tools for data processing, numerical analysis, visualization, statistical modeling, and exploratory machine learning.

**Tools and libraries:**

* Python
* Pandas
* NumPy
* SciPy
* Matplotlib
* scikit-learn
* Jupyter Notebook

Modeling approaches explored include:

* linear regression
* support-vector regression
* random-forest regression
* training/test data splitting for model evaluation

## Scientific Context

The computational analysis complements experimental studies of how DNA methylation affects DNA mechanics and structural behavior. It demonstrates the integration of experimental molecular-biophysics data with quantitative and computational analysis.

## Repository Contents

* `codes/` — analysis notebooks and computational workflows
* `basic_data.xlsx` — experimental dataset used for analysis
* `archive/` — earlier project materials

## Skills Demonstrated

* Processing and quality assessment of experimental scientific data
* Quantitative analysis of instrument-derived measurements
* Python-based scientific computing
* Statistical and regression analysis
* Data visualization
* Exploratory machine-learning analysis
* Integration of computational analysis with a biological research question

## Author

**Tetiana Zaichuk, PhD**

Molecular biology, genomics, chromatin biology, quantitative biophysics, and translational research.
