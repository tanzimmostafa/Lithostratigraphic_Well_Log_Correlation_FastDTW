# Lithostratigraphic Well Log Correlation using Fast Dynamic Time Warping (FastDTW)

This repository contains the Python implementation of a well-log correlation framework developed for my Master's thesis research. It uses the **Fast Dynamic Time Warping (FastDTW)** algorithm with a weighted distance function tuned using grid search. This approach achieved a significant reduction in Mean Absolute Error (MAE) for boundary prediction compared to an existing PCA-based benchmark on the same dataset. More information can be found in Chapter 4 of my Master's thesis: https://www.proquest.com/docview/3240874881

## 📌 Project Overview

Well-to-well correlation is a fundamental aspect of reservoir modeling and understanding subsurface geology. However, it is a challenging task due to the intrinsic heterogeneity of subsurface formations and uncertainties in geophysical logs. We employ the FastDTW algorithm, which is widely used for aligning time series of different lengths, to align the log curves of the reference well with each of the observation wells.

## 📊 Dataset Description

The study utilizes a real-world dataset from a **carbonate oil reservoir field in southwest Iran**.

* **Wells:**
  * **Reference Well:** Contains 6 lithologically distinct layers (L1 to L6).
  * **Observation Well 1:** Contains 6 lithologically distinct layers (L1 to L6).
  * **Observation Well 2:** Contains 2 identifiable layers (L4 and L5).
* **Geophysical Logs:**
  * **SGR (Spectral Gamma Ray):** Measures total gamma ray radioactivity from potassium, thorium, and uranium.
  * **CGR (Computed Gamma Ray):** Measures potassium and thorium while excluding uranium. More representative of clay/shale content.
  * **RHOB (Bulk Density):** Measures formation density. Useful for estimating porosity, lithology, and identifying hydrocarbon zones.
  * **DT (Sonic Log):** Measures the travel time of sound waves. Used to estimate porosity and other petrophysical properties.
* **Resolution:** All logs were recorded at a resolution of 0.153 m.
