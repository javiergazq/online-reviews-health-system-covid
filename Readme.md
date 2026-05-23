# Public Perception of Health Care Before, During, and After COVID-19: A Longitudinal Analysis of Online Reviews

This repository contains the analytical notebook supporting the manuscript:

**Public Perception of Health Care Before, During, and After COVID-19: A Longitudinal Analysis of Online Reviews**

**Authors:** Javier Gazquez-Garcia, Carlos Luis Sánchez-Bocanegra, Carlos Fernández-Llatas

## Overview

This study examines longitudinal changes in citizen-generated online reviews of publicly funded health care facilities in Andalusia, Spain, with particular attention to differences between primary care and hospital services before, during, and after the COVID-19 pandemic.

The repository provides the Python notebook used to perform the analyses reported in the manuscript. It is a paper-specific extraction of the original working notebook and includes only the analytical procedures directly supporting the reported results.

## Repository Contents

- `JMIR_paper_covid_analysis.ipynb` — main analysis notebook.
- `LICENSE` — license governing reuse of the source code.

The public notebook has been shared without stored cell outputs in order to avoid inadvertent disclosure of review-level textual content.

## Analytical Workflow

The notebook is organized around the following analytical steps:

0. **Environment setup**  
   Import of the Python libraries required for data processing, statistical analysis, change-point detection, and visualization.

1. **Data loading and initial preprocessing**  
   Loading of the raw review-level dataset, variable normalization, date processing, and creation of the star-rating-based sentiment classification.

2. **Validation of star-rating-based sentiment classification**  
   Manual annotation of a stratified sample of reviews and estimation of agreement between manual labels and star-rating-derived sentiment categories using linearly weighted Cohen's kappa.

3. **Construction of the analytical textual corpus**  
   Exclusion of reviews without sufficient textual content and application of the preprocessing steps required for the final analytical dataset.

4. **Structural exploratory data analysis**  
   Descriptive characterization of the data, including the annual volume of raw reviews retrieved before application of the final analytical inclusion criteria.

5. **Change-point detection**  
   Identification of structural breaks in the monthly proportion of negative reviews using the Pruned Exact Linear Time (PELT) algorithm with a radial basis function (RBF) cost function.

6. **Global logistic regression models**  
   Estimation of nested logistic regression models assessing associations between level of care, temporal trend, and the probability of a negative review, with robust standard errors clustered at the facility level.

7. **Pandemic-period analysis**  
   Comparison of pre-pandemic, pandemic, and post-pandemic phases; estimation of interactions between level of care and pandemic period; visualization of temporal trajectories by level of care; and likelihood ratio testing of the period-based model.

## Study Periods

For the pandemic-period analyses, the study period was operationalized as follows:

- **Pre-pandemic:** 2016–2019  
- **Pandemic:** 2020–2022  
- **Post-pandemic:** 2023–2025  

## Input Data

The notebook is designed to read the source dataset from a local file:

```text
Merged.csv
```

The validation procedure also relies on a local manual-annotation file used by the authors during the study.

These input files are not included in the public repository.

## Data Availability

The underlying review-level dataset is not redistributed in this repository because it contains user-generated review text retrieved from Google Maps. Public redistribution of the raw scraped corpus is restricted in accordance with the Google Maps Platform Terms of Service, and verbatim review-level content may also raise privacy considerations.

The manual annotation file used for validation is also not publicly distributed because it contains review-level textual content.

The manuscript reports the aggregated findings derived from the analytical dataset, while this repository provides the source code used for data preprocessing, sentiment classification validation, change-point detection, statistical modeling, and figure generation.

## Software Environment

The analyses were conducted in Python and make use of libraries including:

- `pandas` and `numpy` for data manipulation;
- `matplotlib` and `seaborn` for visualization;
- `statsmodels` and `scipy` for statistical analysis;
- `scikit-learn` for agreement metrics;
- `ruptures` for change-point detection;
- `nltk` and `spaCy` for text preprocessing procedures.

## Reproducibility Notes

The notebook was prepared for public sharing with all stored outputs cleared. To reproduce the analyses, users must provide the required local input files and execute the notebook sequentially.

The annual raw-review volume figure is descriptive of the retrieved review dataset before application of the final analytical text inclusion criteria. The main longitudinal, change-point, and regression analyses are based on the analytical corpus described in the manuscript.

## Citation

Please cite the associated manuscript when using or adapting this code:

> Gazquez-Garcia J, Sánchez-Bocanegra CL, Fernández-Llatas C. *Public Perception of Health Care Before, During, and After COVID-19: A Longitudinal Analysis of Online Reviews*. Manuscript submitted for publication.

The citation details should be updated once the final publication record and DOI are available.
