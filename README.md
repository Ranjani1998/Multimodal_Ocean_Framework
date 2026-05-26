# Multimodal Ocean Intelligence Framework for Indian Ocean Risk Analysis

This repository contains the reproducibility package for a PhD research project on multimodal ocean-state analysis and climate-risk modelling over the Bay of Bengal and Arabian Sea. The workflow integrates open-source oceanographic, atmospheric, cyclone, bathymetry, wave, and remote-sensing datasets to support physically informed ocean intelligence, cross-modal learning, and domain-adaptive prediction.

## Project Scope

The study domain is fixed to the Indian Ocean sector covering the Bay of Bengal and Arabian Sea. The project uses daily temporal alignment over the period from 01 January 2020 to 31 December 2024, with depth-aware analysis from the surface to 1000 m where profile data are available.

| Component | Specification |
|---|---|
| Study period | 01 January 2020 to 31 December 2024 |
| Bay of Bengal boundary | 5°N–22°N, 80°E–98°E |
| Arabian Sea boundary | 5°N–22°N, 60°E–75°E |
| Temporal resolution | Daily |
| Depth range | 0–1000 m |
| Standard depth levels | 0, 10, 20, 30, 50, 75, 100, 150, 200, 300, 500, 700, 1000 m |

## Research Objective

The objective of this repository is to provide a clean and reproducible implementation for multimodal ocean data preparation, dataset auditing, transfer learning, and physics-aware cross-modal domain adaptation. The framework is designed to support SCI/SCIE journal submission by enabling transparent dataset provenance, reproducible processing, and reviewer-friendly code organization.

## Dataset Sources

The project uses the following open-source datasets:

| Dataset | Main Role in the Project |
|---|---|
| Argo Profile Dataset | Temperature, salinity, pressure, depth, and quality-controlled vertical ocean profiles |
| NOAA OISST | Sea surface temperature and thermal anomaly detection |
| NASA MODIS-Aqua Ocean Color | Chlorophyll-a concentration, biological productivity, and harmful algal bloom indicators |
| Copernicus Marine Global Ocean Physics Reanalysis | Currents, sea-level anomaly, mixed-layer depth, temperature, and salinity fields |
| Copernicus Marine Global Ocean Waves Reanalysis | Significant wave height, wave period, wave direction, and derived wave energy |
| ERA5 Atmospheric Dataset | Wind speed, wind direction, mean sea-level pressure, and surface pressure |
| NOAA IBTrACS | Cyclone event tracks, cyclone labels, storm intensity, and cyclone distance features |
| GEBCO Bathymetry | Seafloor depth, bathymetric context, and ocean-zone classification |
| INCOIS / OMNI-RAMA / Wave Buoy / HF Radar | Optional Indian Ocean in-situ validation data where access is available |

## Repository Structure

```text
Multimodal_Ocean_PhD_Framework/
│
├── README.md
├── requirements.txt
├── config.yaml
├── run_reproducibility.sh
│
├── notebooks/
│   ├── 01_argo_profile_dataset.ipynb
│   ├── 02_noaa_oisst_dataset.ipynb
│   ├── 03_nasa_modis_aqua_chlorophyll.ipynb
│   ├── 04_1_copernicus_marine_physics.ipynb
│   ├── 04_2_copernicus_marine_waves.ipynb
│   ├── 05_era5_atmospheric_dataset.ipynb
│   ├── 06_noaa_ibtracs_cyclone_dataset.ipynb
│   ├── 07_gebco_bathymetry_dataset.ipynb
│   ├── 08_incois_omni_rama_validation.ipynb
│   ├── dataset_analysis_report.ipynb
│   ├── phase_0_multimodal_ocean_deep_audit.ipynb
│   ├── phase_1_multimodal_ocean_transfer_learning.ipynb
│   └── phase_2_physics_crossmodal_domain_adaptive_framework.ipynb
│
├── src/
│   ├── data_download.py
│   ├── preprocessing.py
│   ├── feature_engineering.py
│   ├── model.py
│   ├── train.py
│   ├── evaluate.py
│   ├── metrics.py
│   ├── plots.py
│   └── utils.py
│
├── data/
│   ├── raw/
│   ├── interim/
│   ├── processed/
│   └── external/
│
├── results/
│   ├── figures/
│   ├── tables/
│   ├── metrics/
│   └── logs/
│
└── docs/
    ├── DATA_AVAILABILITY.md
    ├── CODE_AVAILABILITY.md
    ├── REPRODUCIBILITY_GUIDE.md
    └── DATASET_PROVENANCE.md
```

## Workflow Overview

The framework follows three major phases.

**Initialization Phase:** This phase performs dataset inventory, spatial-temporal boundary verification, missing-data audit, variable standardization, and metadata preparation. It ensures that all datasets are aligned to the Indian Ocean study domain before model development.

**Primary Processing Phase:** This phase prepares multimodal ocean, atmospheric, remote-sensing, cyclone, and bathymetric features for learning. It supports transfer learning and feature fusion across gridded, profile-based, and event-based datasets.

**Advanced Optimization Phase:** This phase applies physics-aware cross-modal and domain-adaptive modelling to improve generalization across the Bay of Bengal and Arabian Sea. It supports climate-risk interpretation, cyclone-induced disturbance analysis, and explainable ocean-state classification.

## Installation

Create a fresh Python environment and install the required packages.

```bash
python -m venv venv
source venv/bin/activate      # Linux/Mac
venv\Scripts\activate         # Windows

pip install -r requirements.txt
```

## Reproducibility

After installing dependencies and preparing dataset access credentials where required, run:

```bash
bash run_reproducibility.sh
```

The script is intended to execute the major steps in sequence: dataset preparation, preprocessing, model training, evaluation, and generation of publication-ready outputs.

## Expected Outputs

The repository is designed to generate:

- Cleaned and harmonized multimodal ocean datasets
- Dataset audit summaries
- Training and validation metrics
- Climate-risk classification outputs
- Cyclone-induced disturbance features
- Publication-ready figures and tables
- Reproducibility logs for reviewer verification

## Notes for SCI/SCIE Submission

For journal submission, upload the complete GitHub repository with source code, cleaned scripts, configuration files, and reproducibility instructions. Do not upload raw large datasets directly to GitHub. Instead, provide dataset source links, access instructions, and processed sample files if the journal permits. Large model files, processed datasets, and supplementary outputs should be placed in Zenodo, Figshare, OSF, institutional repositories, or journal supplementary material, depending on the journal policy.

## Citation and Dataset Acknowledgement

Users of this repository should cite the original dataset providers and comply with the access policies of Argo, NOAA, NASA, Copernicus Marine, ECMWF/Copernicus Climate Data Store, GEBCO, IBTrACS, and INCOIS/OMNI-RAMA where applicable.

## Repository Status

This repository is prepared as a research reproducibility package for manuscript submission and reviewer verification. The implementation should be executed with project-specific data paths and valid dataset credentials where required.
