# Lithostratigraphic Well Log Correlation using Fast Dynamic Time Warping (FastDTW)

This repository contains the Python implementation of a modified well-log correlation framework developed for my thesis research. The project improves stratigraphic unit alignment by replacing traditional PCA-based similarity with **Fast Dynamic Time Warping (FastDTW)**, enhanced by a custom weighted distance function.


## 📌 Project Overview

Well-to-well correlation is a fundamental aspect of reservoir modeling and understanding subsurface geology. However, manual correlation is a challenging task due to the intrinsic heterogeneity of subsurface formations and uncertainties in geophysical logs. 

This research proposes an automated, non-linear alignment approach that accommodates variations in sedimentation rates, erosion, and compaction, which are often missed by linear or PCA-based methods.

### Key Contributions
* **FastDTW Framework:** Implemented a modified framework that allows for flexible and geologically realistic alignment of stratigraphic units.
* **Weighted Distance Function:** Introduced a custom weighted Euclidean distance function tailored to log-specific sensitivities (SGR, CGR, RHOB, DT).
* **Grid Search Optimization:** Weights were tuned using a grid search strategy to minimize prediction error across multiple observation wells.
* **Improved Accuracy:** Demonstrated a significant reduction in Mean Absolute Error (MAE) for boundary prediction compared to existing PCA-based benchmarks.

## 📊 Dataset Description

The study utilizes a real-world dataset from a **carbonate oil reservoir field in southwest Iran**.

* **Study Area:** Approximately 67 km long and 4 km wide.
* **Wells:** * **Reference Well:** Contains 6 lithologically distinct layers (L1 to L6).
  * **Observation Well 1:** Contains 6 lithologically distinct layers (L1 to L6).
  * **Observation Well 2:** Contains 2 identifiable layers (L4 and L5).
* **Geophysical Logs:**
  * **SGR (Spectral Gamma Ray):** Total radioactive count.
  * **CGR (Computed Gamma Ray):** Potassium and Thorium counts (clay/shale indicator).
  * **RHOB (Bulk Density):** Used for porosity and lithology identification.
  * **DT (Delta-T):** Sonic travel time for petrophysical estimation.
* **Resolution:** All logs were recorded at a resolution of 0.153 m.



## 🛠️ Methodology

The algorithm follows these core steps:
1. **Data Preprocessing:** Handling depth variances and normalizing log scales.
2. **Multivariate Alignment:** Treating the four log types as a multivariate time series to compute the optimal warping path between the reference and observation wells.
3. **Custom Weighting:** Applying a cost function where specific logs are weighted higher (1–10 scale) based on their reliability in identifying stratigraphic boundaries.
4. **Boundary Extraction:** Mapping known layer "tops" from the reference well to the observation wells via the FastDTW path.
