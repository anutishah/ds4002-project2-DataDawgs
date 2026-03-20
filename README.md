# ds4002-project2-DataDawgs

## Repository Contents
This repository contains all data, code, and outputs used to analyze and forecast monthly precipitation trends in Charlottesville, Virginia.

### Folder Structure
- **DATA/**  
  Contains all datasets used in this project.
  
- **OUTPUT/**  
  Contains all generated figures, model outputs, and evaluation metrics.

- **SCRIPTS/**  
  Contains the main Jupyter Notebook used for data cleaning, analysis, modeling, and forecasting.

- **LICENSE.md**  
  Describes how this repository can be used and cited.

---

## Software and Platform

### Software Used
- Python 3 (Jupyter Notebook / Google Colab)

### Add-on Packages Used
- pandas  
- numpy  
- matplotlib  
- statsmodels  
- scikit-learn  

### Platform Used
- macOS / Windows (compatible with both)
- Developed using Jupyter Notebook (can also be run in Google Colab)

---

## Documentation Map

### DATA (folder) contains:
- `charlottesville_precip_cleaned.csv` (cleaned dataset with precipitation and temperature data)
- 'Project 2 Data Appendix (1).pdf' (Data Appendix)
- 'precipdata_initial.csv' (initial dataset)

### OUTPUT (folder) contains:
- Time series plots of monthly precipitation  
- Regression Results 

### SCRIPTS (folder) contains:
- 'Project2EDA.ipynb' (Exploratory Data Analysis)
- `Project_2_Code.ipynb`  
  - Data cleaning and preprocessing  
  - Time series aggregation (monthly precipitation)  
  - Visualization of trends  
  - Linear regression trend analysis  
  - SARIMA model training and forecasting  
  - Model evaluation (RMSE, AIC, residual diagnostics)  

---

## Instructions for Reproducing Results

Follow these steps to reproduce the results of this project:

### Step 1: Download Files
- From the GitHub repository:
  - Download the **SCRIPTS/Project_2_Code.ipynb**
  - Download the **DATA/charlottesville_precip_cleaned.csv**

---

### Step 2: Open Notebook
- Open the notebook in:
  - Jupyter Notebook **OR**
  - Upload it to **Google Colab**

---

### Step 3: Upload Dataset
- In your notebook environment:
  - Upload `charlottesville_precip_cleaned.csv` to the working directory (same location as the notebook)

---

### Step 4: Run the Notebook
- Run all cells **from top to bottom**

---

### Step 5: What the Code Does

The notebook performs the following steps:

#### Data Cleaning
- Removes unnecessary columns (`Snow`, `Average Temperature`)
- Drops rows with missing values in:
  - Precipitation
  - Maximum temperature
  - Minimum temperature
- Converts the `Date` column to datetime format

---

#### Data Aggregation
- Aggregates daily data into **monthly precipitation totals**
- Creates a time variable (`YearMonth`) for time series analysis

---

#### Visualization
- Plots monthly precipitation over time (2007–2026)
- Displays long-term seasonal and trend patterns

---

#### Trend Analysis
- Creates a numeric time index
- Fits a **linear regression model** using `statsmodels`
- Outputs regression summary statistics

---

#### Train-Test Split
- Training data: 2007–2023  
- Testing data: 2024–2026  

---

#### SARIMA Modeling
- Fits a **SARIMA model** with parameters:
  - Order: (0,0,1)
  - Seasonal Order: (1,1,1,12)
- Generates forecasts for the test period

---

#### Forecast Evaluation
- Compares forecasted vs actual precipitation
- Calculates **RMSE (Root Mean Squared Error)**

---

#### Baseline Comparison
- Implements a **seasonal naïve model**
- Compares its RMSE against the SARIMA model

---

#### Model Diagnostics
- Evaluates model quality using:
  - AIC (model fit metric)
  - Residual analysis
  - Ljung-Box test (checks autocorrelation)

---

### Step 6: Verify Results

You should confirm your results by checking:

- Time series plot of precipitation  
- Forecast vs actual plot  
- Printed RMSE values:
  - SARIMA RMSE (~2.56 inches)  
  - Seasonal naïve RMSE (~3.39 inches)  
- Model summary output (from statsmodels)  
- Residual diagnostics (no significant autocorrelation)  
