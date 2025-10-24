# Fahd Rehman Master Thesis Code Repository

## Project Description
This repository contains code for the Master's thesis "Hybrid Model For Early Anomaly Detection In Wind Turbine Operations" at the Technical University of Munich. It develops a hybrid wake-aware physics-integrated machine learning (HWPIML) model using the CARE dataset from Fraunhofer. Folders include 01_Layout_Finalization, 02_Status_Reassignment, 03_Light GBM&Smoothing, and 04_CARE_Score. Additional folders are Autoencoder Replica and Component Identification. Excel sheets for Wind Farm Events support CARE score calculation.

The methodology follows this sequence:
1. **Layout Finalization (01_Layout_Finalization)**: Determines wind farm layout based on wake effects, classifying turbines into rows.
2. **Status Reassignment (02_Status_Reassignment)**: Assigns codes per row for wake effect adjustment; 2 codes for Wind Farms A and B, 3 for Wind Farm C (see thesis for details).
3. **LightGBM & Smoothing (03_Light GBM&Smoothing)**: Trains LightGBM with three farm-specific smoothing parameters. Table below summarizes (representative settings; see thesis for full variations):

| Wind Farm | Confidence Threshold | Maximum Weight | Weight per Match |
|-----------|-----------------------|----------------|------------------|
| A         | 0.9997                | 0.84           | 0.21             |
| B         | 0.9996                | 0.75           | 0.15             |
| C         | 0.9999                | 0.75           | 0.15             |

4. **CARE Score Calculation (04_CARE_Score)**: Computes Coverage, Accuracy, Reliability, Earliness, and overall CARE score with results.

- **Autoencoder Replica**: Replicates Fraunhofer’s baseline architecture.
- **Component Identification**: Introduces a novelty via normal behavior distribution.
- **Wind Farm Events**: Excel sheets are key for CARE scoring.

**Data Sources**:
- Project datasets: https://syncandshare.lrz.de/getlink/fiziHotizHcDBvy17CiaC/DATA (contains two datasets: 1) Status Reassignment Dataset, obtained after running `02_Status_Reassignment/*.ipynb` code; 2) Final Processed Dataset, obtained after running `03_Light GBM&Smoothing/Light_GBM&Smoothing_Code.ipynb`).
- CARE dataset: https://zenodo.org/records/14006163

## Getting Started
### Installation
Requires Python 3.10+, LightGBM, NumPy, Pandas etc.

Run `.ipynb` files in Jupyter Notebook (e.g., open terminal, type `jupyter notebook`).

### Usage
1. Execute `01_Layout_Finalization/Windfarm_[A/B/C]_Layout.ipynb` to set layouts.
2. Run `02_Status_Reassignment/Wind Farm [A/B/C]/*.ipynb` for status codes (details in thesis).
3. Use `03_Light GBM&Smoothing/Light_GBM&Smoothing_Code.ipynb` with farm-specific params (table above is representative; full settings in thesis).
4. Apply `04_CARE_Score/*.ipynb` for CARE scores.

## Collaborate with Your Team
Invite team members via GitLab.

## Authors and Acknowledgment
- Author: Fahd Rehman
- Thanks to Annika Schneider for supervision and Cyriana Roelofs (Fraunhofer) for dataset support.

## Project Status
Complete for thesis. Open to contributions.