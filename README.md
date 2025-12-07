
# **TeslaDS: Time-Series Modeling of Tesla Stock & Elon Musk Event Timeline**

Case study GitHub repository

## **Contents**

This project analyzes the relationship between **Tesla’s historical stock price movements** and **major events involving Elon Musk**, using time-series modeling, ARIMA forecasting, and event visualization. All analysis was conducted using Python, and figures were generated directly from the CSV data included in this repository.


## **Software and Platform**

This project was run using **Python** in both **Google Colab** and **Jupyter Notebook** environments.

### **Primary Packages Used**

The following Python libraries were used for data processing, statistical modeling, and visualization:

* `pandas`
* `numpy`
* `matplotlib.pyplot`
* `seaborn`
* `yfinance`
* `statsmodels` (ADF test, ARIMA modeling)
* `pmdarima`
* `matplotlib.dates` & `matplotlib.patches`

All plots and ARIMA models were generated directly from the included CSV files.
The analysis was executed on **both macOS and Windows** machines.


## **Map**

### **DATA Folder**

* **elon_musk_timeline.csv**
  Contains manually curated timestamps of Musk-related events used to overlay on Tesla stock price movements.

* **METADATA.md**
  Details the structure and origin of all datasets used in the project.
  

### **SCRIPTS Folder**

* **arima.ipynb**
  Notebook containing ARIMA and auto-ARIMA modeling for Tesla time-series data.

* **elon_tesla_modeling.ipynb**
  Notebook used to merge event timelines with price history and generate final event-aligned figures.
  
* **musk_timeseries_p2.ipynb**
  Performs preprocessing, feature preparation, and time-series forecasting visualizations for the Elon Musk event dataset.
  
* **musktimeline.ipynb**
  Notebook focused on processing, cleaning, and analyzing the Elon Musk event dataset.

### **Output Folder**

Generated visualizations, including:

* `teslastock.png` — Tesla closing price over time
* `teslastockelon.png` — Tesla stock overlaid with Elon Musk event markers
* `TSLAEvent.png` — Event-annotated timeline visualization

These plots are overwritten each time the notebooks are run.


### **LICENSE**

All financial data used in this project was obtained from Yahoo Finance. Yahoo Finance data is subject to
their Terms of Use and is provided for personal, educational, and non-commercial purposes only.
Redistribution, commercial use, or incorporation into commercial tools is prohibited without a proper
subscription (e.g., Yahoo Finance Select). This project uses Yahoo Finance data strictly for academic
analysis as part of a university course requirement. Users must comply with all applicable Yahoo Finance
terms and licensing restrictions.


## **Reproducing Results**

To reproduce all figures and analyses in the `Output/` folder, follow the steps below.

### **1. Download or Clone the Repository**

```bash
git clone https://github.com/<your-username>/TeslaDS.git
cd TeslaDS
```

### **2. Ensure Data Availability**

All required CSV files are already provided in the `Data/` folder.
No scraping or external API calls are required beyond optional use of `yfinance`.

### **3. Run the Analysis Scripts**

Begin with:

#### **Notebook 1 — elon_tesla_modeling.ipynb**

* Loads Tesla stock data
* Loads Musk event timeline
* Produces aligned time-series plots

#### **Notebook 2 — arima.ipynb**

* Performs ARIMA and auto-ARIMA forecasting
* Tests for stationarity
* Outputs forecast visualizations

#### **Notebook 3 — musktimeline.ipynb**

* Parses, cleans, and formats Musk event data
* Validates dates and event classifications

Open each notebook and run **Kernel → Restart & Run All** to regenerate all outputs.


## **Notes on Reproducibility**

* All outputs are saved automatically into the `Output/` directory.
* Relative paths are already configured, so the notebooks will run correctly as long as the repository folder structure is preserved.
* For Colab users, ensure the repository is either uploaded or cloned into `/content/`.

