**Software and Platforms Used**

### **Primary Software**

This project was implemented entirely in **Python**, using both **Jupyter Notebook** and **Google Colab** environments for development, analysis, and visualization.

### **Required Python Packages**

The following libraries were used for data manipulation, time-series modeling, visualization, and pulling historical stock prices:

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import adfuller
from statsmodels.tsa.arima.model import ARIMA
from pmdarima import auto_arima
from matplotlib.dates import DateFormatter
from matplotlib.patches import Patch
import yfinance as yf
```

### **Operating Systems**

Analysis was conducted on both:

* **Windows 11**
* **macOS (Sonoma)**
  to ensure cross-platform reproducibility.


# **Project Structure**

```
TeslaDS/
│
├── Data/
│   ├── METADATA.md
│   ├── elon_musk_timeline.csv
│
├── Scripts/
│   ├── arima.ipynb
│   ├── elon_tesla_modeling.ipynb
│   ├── musktimeline.ipynb
│   └── elon_tesla_modeling.ipynb
│
├── Output/
│   ├── TSLAEvent.png
│   ├── teslastockelon.png
│   ├── teslastock.png
│
├── LICENSE.md
├── README.md
└── MIP2.pdf
```

# **License**

All financial data used in this project was obtained from Yahoo Finance. Yahoo Finance data is subject to
their Terms of Use and is provided for personal, educational, and non-commercial purposes only.
Redistribution, commercial use, or incorporation into commercial tools is prohibited without a proper
subscription (e.g., Yahoo Finance Select). This project uses Yahoo Finance data strictly for academic
analysis as part of a university course requirement. Users must comply with all applicable Yahoo Finance
terms and licensing restrictions.

#  **Instructions for Reproducing the Results**

Follow these steps to regenerate the figures saved in the `Output/` directory using the data in `Data/` and the notebooks in `Scripts/`.


## **0) Prerequisites**

You will need:

* **Python 3.9+**
* **Git**
* (Optional) A clean **virtual environment**
* No web scraping is required — all needed files are already in `Data/`.


## **1) Clone the Repository**

```bash
git clone https://github.com/<your-username>/TeslaDS.git
cd TeslaDS
```

---

## **2) Create & Activate a Virtual Environment**

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows (PowerShell):**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```


## **3) Install Dependencies**

If the repo contains a `requirements.txt`:

```bash
pip install -r requirements.txt
```

Otherwise, install the minimum required packages:

```bash
pip install pandas matplotlib seaborn beautifulsoup4 lxml requests jupyter
```


## **4) Verify Project Structure**

Your working directory should contain:

```
Data/   Scripts/   Output/   LICENSE.md   README.md
```

Ensure that `Data/elon_musk_timeline.csv` exists.


## **5) Run the Analysis Notebook**

### **Option A — Jupyter Notebook (local, interactive)**

```bash
jupyter notebook
```

Then open:

`Scripts/elon_tesla_modeling.ipynb`
→ Select **Kernel → Restart & Run All**

All figures will automatically be written to `Output/`.

---

### **Option B — Command Line (non-interactive, reproducible)**

```bash
jupyter nbconvert --execute \
  --to notebook \
  --output Output/elon_tesla_modeling.ipynb \
  Scripts/arima.ipynb
```

This runs the notebook headlessly and saves an executed copy in `Output/`.

---

### **Option C — Google Colab**

1. Open the repo in Colab (Upload or "Open from GitHub").
2. Ensure the working directory includes the `Data/` folder.
3. Run all cells normally.


## **6) Expected Outputs**

If the analysis runs successfully, `Output/` will contain:

* `teslastock.png`
* `teslastockelon.png`
* `TSLAEvent.png`
* (plus the executed notebook if using nbconvert)

Existing files will be overwritten.


## **7) Re-Running From a Clean Slate (optional)**

**macOS / Linux:**

```bash
rm -f Output/*.png Output/elon_tesla_modeling.ipynb
```

**Windows (PowerShell):**

```powershell
Remove-Item Output\*.png, Output\elon_tesla_modeling.ipynb -ErrorAction Ignore
```


## **8) Troubleshooting Guide**

| Issue                           | Fix                                                         |
| ------------------------------- | ----------------------------------------------------------- |
| **FileNotFoundError (CSV)**     | Verify you're in the repo root and `Data/` exists.          |
| **Missing package ImportError** | Re-run dependency installation (Step 3).                    |
| **Plots not saving**            | Ensure "Restart & Run All" was executed; verify save paths. |
| **Colab path errors**           | Clone repo into `/content` or mount Google Drive.           |
| **Matplotlib not displaying**   | Add `%matplotlib inline` near the top of the notebook.      |


