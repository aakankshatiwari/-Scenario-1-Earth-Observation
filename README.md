# Earth Observation Internship Project  
**Sustainability Lab – IIT Gandhinagar**  

**Assignment Title:** Land Use Classification & Pollution Source Mapping in Delhi-NCR  

---

## 📌 Objective

This project is part of the selection task for the internship at the Sustainability Lab, IIT Gandhinagar. The Ministry of Environment has commissioned an AI-based audit of the Delhi Airshed to analyze **land use patterns** and **potential pollution sources** using satellite imagery and geospatial data.

---

## 🛰️ Scenario Overview

The project involves building an end-to-end pipeline for land cover classification over the Delhi-NCR region using **Sentinel-2 RGB satellite images** and **ESA WorldCover 2021** labels. The tasks span across spatial gridding, data filtering, supervised labeling, model training, and performance evaluation.

---

## 📂 Directory Structure


EarthObservation/
│
├── Data/ # Raw image files, shapefiles, and raster layers
│
├── Visualizations/ # Saved confusion matrix, class plots, etc.
│ └── class_distribution.png
│
├── Dataset/ # Final dataset with labels
│ ├── image_label_map.csv
│
├── models/ # CNN model code (e.g., ResNet18)
│ └── resnet_model.py
│
├── scripts/ # Helper scripts
│ ├── grid_generator.py
│ ├── label_extractor.py
│ ├── train_model.py
│
├── Earth_Observation.ipynb 
├── requirements.txt 
├── README.md 
├── S1_Report.pdf


## ✅ Task Breakdown

### 📍 Q1: Spatial Reasoning & Data Filtering (5 Marks)
- Plotted Delhi-NCR shapefile and overlaid a 60×60 km grid.
- Displayed grid with satellite basemap using `geemap/leafmap`.
- Marked grid corners and centers.
- Filtered image patches based on coordinates within the grid.
- Counted number of images before and after filtering.

### 📍 Q2: Label Construction & Dataset Preparation (10 Marks)
- Extracted 128×128 patches from `land_cover.tif` centered on image coordinates.
- Assigned labels using **mode (most frequent)** land cover class in the patch.
- Mapped ESA class codes to **11 standardized categories**.
- Handled no-data pixels and mixed-dominance scenarios.
- Split dataset using 60/40 **train-test stratification**.
- Visualized class distribution and discussed imbalance.

### 📍 Q3: Model Training & Evaluation (10 Marks)
- Trained a **ResNet18 CNN classifier** using PyTorch.
- Evaluated using:
  - Custom F1 Score (`sklearn`)
  - TorchMetrics F1 Score
  - Confusion matrix visualization
- Plotted 5 correct and 5 incorrect predictions for qualitative analysis.

Key libraries:

geopandas, rasterio, shapely – for geospatial operations

torch, torchvision, torchmetrics – for CNN training

sklearn, seaborn, matplotlib – for metrics & plots

geemap, leafmap – for interactive mapping

📊 Key Results
Total valid image-label pairs: ✅ 3,613

Achieved F1 Score (sklearn): ✅ ~0.30

TorchMetrics F1 Score matched after correction.

Class distribution: moderately imbalanced (visualized).

Grid and overlays successfully visualized with basemaps.

📌 Author
Aakanksha Tiwari
Sustainability Lab – Internship Application
GitHub Profile

