# Stroke Lesion Analysis & Segmentation Pipeline

[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity)

This repository contains a comprehensive, 20-module automated pipeline for the **external validation, clinical correlation, and systematic error characterization** of deep learning-based stroke lesion segmentation models. 

It is designed to go beyond simple overlap metrics (Dice) by integrating spatial topology, voxel-based lesion-symptom mapping (VLSM), connectomics, and publication-ready statistical reporting.


---
>  **CODE EMBARGO NOTICE** 
> 
> The full source code and analysis scripts associated with this repository are temporarily withheld. This project is currently undergoing peer review for an upcoming international medical imaging conference and subsequent journal publication.
> 
> To comply with strict anonymity requirements and academic embargo policies, the complete codebase will be made fully open-source and publicly available in this repository immediately upon the official acceptance of the manuscript.
> 
> In the meantime, you can read the preprint of our external validation and systematic error characterization on Zenodo:
>  **[Preprint: DOI 10.5281/zenodo.18802086](https://zenodo.org/records/18802086)**
--- 
## Features

The pipeline is structured into 4 main analytical phases:

### Phase 1: Morphological & Topological Analysis
* **Volumetric & Hemispheric Profiling:** Calculates precise lesion volumes (mL), center of mass (MNI coordinates), and laterality indices.
* **Connectomics (Atlas-Based):** Maps lesions to the Juelich histological atlas to identify the frequency of specific regional damage (e.g., Insular Cortex, Motor Tracts).
* **Vascular Territories:** Determines the dominant affected vascular supply (MCA, ACA, PCA).

### Phase 2: Clinical Integration & Statistics
* **Voxel-Based Lesion-Symptom Mapping (VLSM):** Generates statistical T-maps identifying critical brain regions correlated with severe clinical deficits (NIHSS).
* **Clinical Correlation:** Computes Spearman correlations between spatial features (e.g., Motor Damage) and functional outcomes (mRS).
* **Predictive Modeling:** Cross-validated logistic regression (AUC) comparing Volume-Only vs. Volume+Topology models for stroke severity prediction.

### Phase 3: AI Segmentation Validation
* **Advanced Metrics:** Computes DSC, Precision, Recall, and 95th percentile Hausdorff Distance (HD95).
* **Subgroup & Domain Shift Analysis:** Stratifies performance by lesion size (<5 mL, 5-20 mL, >20 mL) and evaluates registration impact (Native vs. MNI space).
* **Failure Case Characterization:** Automatically extracts the best, average, and worst-performing cases, outputting visual overlays to identify systematic biases (e.g., leukoaraiosis misclassification).
* **Calibration & Bias:** Evaluates size-dependent bias using Bland-Altman plots and Reliability Diagrams (Brier Score).

### Phase 4: Publication-Ready Outputs
* Automatically generates formatted `.csv` tables for Demographics, Segmentation Performance, Subgroup Analysis, and Clinical Correlations.


