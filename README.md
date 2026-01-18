# Ocean-Total-Alkanity-Prediction-model
This project implements learning algorithm—Random Forest (RF)—to provide high-accuracy estimates across a typical alkalinity range of 2000–2500 $\mu$mol/kg.
# Ocean Alkalinity Prediction Pipeline

## 🌊 Project Overview
This project implements a machine learning pipeline to predict **Total Alkalinity (TALK)** in ocean surface waters. By training a Random Forest Regressor on *in-situ* measurements from the **GLODAP** (Global Ocean Data Analysis Project) dataset, the model estimates alkalinity globally using satellite-derived Sea Surface Salinity (SSS) and Sea Surface Temperature (SST) data.

This tool is designed to help researchers generate high-resolution, global maps of ocean alkalinity, which is a critical parameter for understanding the ocean carbon cycle and ocean acidification.

## 🚀 Key Features
* **Automated Data Cleaning:** Filters for surface water ($depth \le 6m$) and removes physical outliers (Salinity: 32-38 PSU, Temp: -2 to 32°C).
* **Robust Machine Learning:** Utilizes a **Random Forest Regressor** (scikit-learn) optimized for non-linear oceanographic relationships.
* **Satellite Integration:** seamless mapping of satellite parameters (SSS, SST) to model features for global-scale prediction.
* **Comprehensive Validation:** Includes modules for cross-validation, feature importance analysis, and regional error assessment.
* **Visualization:** Automatically generates plots for feature importance, prediction distributions, and validation metrics (RMSE, $R^2$).


## 📊 Model Results

The Random Forest Regressor demonstrated high accuracy in estimating surface Total Alkalinity (TALK) based on the validation data split.

### 1. Model Performance Metrics
The model was evaluated on a 20% hold-out validation set from the GLODAP dataset.

| Metric | Value | Description |
| :--- | :--- | :--- |
| **R² Score** | **0.9758** | Explains ~97.6% of the variance in alkalinity data. |
| **RMSE** | **19.90** | Root Mean Square Error (µmol/kg). |
| **MAE** | **8.30** | Mean Absolute Error (µmol/kg). |
| **MSE** | **122.04** | Mean Squared Error. |

### 2. Satellite Prediction Statistics
The trained model was applied to the global satellite dataset (SSS & SST) to generate alkalinity estimates.

* **Total Predictions:** ~34.6 Million data points.
* **Mean Predicted Alkalinity:** 2,221.14 µmol/kg.
* **Prediction Range:** 721.97 — 2,621.90 µmol/kg.
* **Standard Deviation:** 212.22 µmol/kg.

### 3. Key Findings
* **High Precision:** The model achieves an $R^2 > 0.97$, indicating that Sea Surface Salinity (SSS) and Sea Surface Temperature (SST) are excellent predictors for Total Alkalinity in surface waters.
* **Robustness:** The low Mean Absolute Error (8.3 µmol/kg) suggests the model is reliable for generating global carbon budget estimates.
* **Outlier Removal:** The quality control pipeline successfully removed ~3,100 outliers (based on physical oceanography limits) before training, significantly improving model stability.

### 4. Visualizations
The pipeline generates the following plots for analysis:
* **Feature Importance:** Highlights Salinity as the dominant predictor.
* **Actual vs. Predicted:** Shows a tight correlation along the 1:1 line.
* **Residual Analysis:** Confirms errors are normally distributed and centered around zero.

 **Clone the repository:**
   ```bash
   git clone [https://github.com/yourusername/ocean-alkalinity-prediction.git](https://github.com/yourusername/ocean-alkalinity-prediction.git)
   cd ocean-alkalinity-prediction
## 🛠️ Quick Start

### Install Requirements
You need Python and these libraries:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
# Train the model and generate satellite predictions
