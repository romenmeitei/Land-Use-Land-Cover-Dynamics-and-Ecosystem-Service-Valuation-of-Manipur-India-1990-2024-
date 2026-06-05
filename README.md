# Land Use/Land Cover Dynamics and Ecosystem Service Valuation of Manipur, India (1990–2024)

## Overview

This repository contains the complete Google Colab workflow, datasets, and analytical outputs used in the study:

**"Land Use/Land Cover Dynamics and Ecosystem Service Value Changes Across Nine Districts of Manipur, Northeast India (1990–2024): A Geospatial Assessment Using Random Forest Classification and Ecosystem Service Valuation."**

The project integrates satellite remote sensing, machine learning, ecosystem service valuation (ESV), land-cover transition analysis, hotspot identification, and sensitivity analysis to quantify long-term environmental changes across Manipur, India.

---

## Study Area

The analysis covers nine districts of Manipur, Northeast India:

* Bishnupur
* Chandel
* Churachandpur
* East Imphal
* West Imphal
* Senapati
* Tamenglong
* Thoubal
* Ukhrul

The study region lies within the Indo-Burma Biodiversity Hotspot and comprises a central valley surrounded by extensive hill ecosystems.

---

## Objectives

The study aimed to:

1. Generate multi-temporal land-use and land-cover (LULC) maps for 1990, 2000, 2010, 2020, and 2024.
2. Quantify district-level land-cover dynamics.
3. Estimate ecosystem service values (ESVs) associated with different land-cover classes.
4. Identify major land-cover transitions.
5. Determine ecosystem service hotspots.
6. Evaluate uncertainty using sensitivity analysis.

---

## Methodological Workflow

### Phase 1: Land Use/Land Cover Mapping

Historical Landsat imagery was processed using Google Earth Engine.

| Year | Dataset                       |
| ---- | ----------------------------- |
| 1990 | Landsat 5 TM                  |
| 2000 | Landsat 5 TM / Landsat 7 ETM+ |
| 2010 | Landsat 5 TM / Landsat 7 ETM+ |
| 2020 | ESA WorldCover                |
| 2024 | Dynamic World                 |

Random Forest classification was applied to historical imagery.

---

### Phase 2: LULC Harmonization

All datasets were reclassified into six ecosystem-relevant categories:

* Forestland
* Cropland
* Grassland/Shrubland
* Open/Barren/Built-up
* Water Bodies
* Wetland

---

### Phase 3: Ecosystem Service Valuation

Ecosystem Service Values (ESVs) were estimated using the benefit-transfer approach:

[
ESV = \sum (A_i \times VC_i)
]

Where:

* (A_i) = area of land-cover class (i)
* (VC_i) = ecosystem service value coefficient

Outputs were calculated at:

* District level
* State level

Units:

* USD ha⁻¹ yr⁻¹
* Million USD yr⁻¹

---

### Phase 4: Transition Analysis

Land-cover transition matrices were generated to quantify:

* Forest gains
* Forest losses
* Cropland expansion
* Shrubland dynamics
* Major ecosystem conversions

---

### Phase 5: Hotspot Analysis

Districts were ranked according to mean ecosystem service value.

Hotspot classes:

* Very High
* High
* Moderate
* Low
* Very Low

---

### Phase 6: Sensitivity Analysis

Sensitivity analysis was conducted using the coefficient of sensitivity (CS):

[
CS =
\frac{(ESV_j - ESV_i)/ESV_i}
{(VC_j - VC_i)/VC_i}
]

A 50% increase in ecosystem service value coefficients was applied individually to evaluate robustness.

---

## Repository Structure

```text
├── notebooks/
│   ├── District_Level_Ecosystem_Service_Valuation.ipynb
│
├── data/
│   ├── Table_LULC_Area_OptionB.csv
│   ├── Table_Total_ESV.csv
│   ├── Table_ESV_Contribution.csv
│   ├── Table_ESV_Hotspot_Ranking.csv
│   ├── Table_Major_LULC_Transitions.csv
│   ├── Table_Sensitivity_Summary.csv
│
├── figures/
│   ├── Fig1_District_ESV_Trends.png
│   ├── Fig2_LULC_Composition_2024.png
│   ├── Fig3_ESV_Hotspot_Ranking.png
│   ├── Fig4_ESV_Contribution_2024.png
│   ├── Fig5_Major_Transitions_1990_2024.png
│   ├── Fig6_Coefficient_Sensitivity.png
│   ├── Fig7_Total_Manipur_ESV.png
│   ├── Fig8_Forest_Area_Trends.png
│   ├── Fig9_Cropland_Area_Trends.png
│   ├── Fig10_ESV_Contribution_Heatmap_2024.png
│
├── manuscript/
│   ├── Paper.docx
│
└── README.md
```

---

## Software Requirements

### Google Earth Engine

Used for:

* Satellite image acquisition
* Cloud masking
* Image compositing
* Random Forest classification
* Area extraction

### Google Colab

Used for:

* Data processing
* Ecosystem service valuation
* Transition analysis
* Sensitivity analysis
* Statistical summaries
* Figure generation

### Python Libraries

```python
pandas
numpy
matplotlib
seaborn
geopandas
rasterio
scikit-learn
```

---

## Key Findings

* Total ecosystem service value increased from approximately **USD 2.00 billion yr⁻¹ (1990)** to **USD 3.38 billion yr⁻¹ (2024)**.
* Forestland represented the dominant contributor to ecosystem service provision.
* Churachandpur and Tamenglong emerged as the highest ecosystem service hotspots.
* Grassland/Shrubland → Forestland was the largest land-cover transition.
* Sensitivity analysis demonstrated robust valuation estimates with CS values below one.

---

## Reproducibility

All analyses are fully reproducible using the provided Google Colab notebooks and input datasets.

Researchers are encouraged to:

* Reuse the workflow.
* Adapt the methodology to other regions.
* Compare ecosystem service dynamics across landscapes.

---

## Citation

If you use this repository, please cite:

**Lourembam RM, et al.** Land Use/Land Cover Dynamics and Ecosystem Service Value Changes Across Nine Districts of Manipur, Northeast India (1990–2024): A Geospatial Assessment Using Random Forest Classification and Ecosystem Service Valuation. [Manuscript under review].

---

## Contact

**Dr. Romen Meitei Lourembam**
BRIC – Institute of Bioresources and Sustainable Development (IBSD)
Imphal, Manipur, India

Email: [romenmeitei.lourembam@aus.ac.in](mailto:romenmeitei.lourembam@aus.ac.in)

---

## License

This repository is released under the MIT License.

Users are free to use, modify, and distribute the code with appropriate citation.
