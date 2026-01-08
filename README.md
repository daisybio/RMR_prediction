# Predicting Resting Metabolic Rate in healthy adults: A Comparative Analysis Using the enable cohort

This is the GitHub repository accompanying the manuscript [_Predicting Resting Metabolic Rate in healthy adults: A Comparative Analysis Using the enable cohort_ doi.org/10.1152/ajpendo.00375.2025](https://doi.org/10.1152/ajpendo.00375.2025).

## Reproduce Analysis

All analyses are done in [publication.Rmd](./publication.Rmd) using `R version 4.2.1`.
To ensure maximum reproducibility of the models and figures from the publication, the project environment [`renv`](https://rstudio.github.io/renv/) is used.
All packages should be installed after running `renv::restore()`.

The data folder is deposited on [zenodo](https://zenodo.org/records/17735477) and has to be downloaded before running the analysis.

## Overview

In short, the analysis consists of the following steps:

1. **Load and clean data**
   Imports Enable and Kiel datasets; standardizes names, fixes formatting issues, merges all sources.
2. **Define predictor sets**
   Creates groups of clinical, microbial (family level), diversity, and established-model variables; defines response (RMR).
3. **Prepare data for modeling**
   Removes missing responses, splits into training/test by site.
4. **Specify and fit models**
   Builds multiple tidymodels workflows (including established equations), tunes them, and stores fitted objects.
5. **Bootstrap model performance**
   Estimates R² and other metrics via resampling for all models.
6. **Compare and summarize models**
   Aggregates metrics, prepares comparison tables, generates visual summaries of model performance.
7. **Predict on test sets**
   Computes predictions for Freising and Nürnberg, evaluates accuracy.
8. **Plot results**
   Produces summary figures for performance, model comparison, and selected model diagnostics.
