
# datafun-06-eda

A compact, reproducible exploratory data analysis (EDA) project focused on historical health-care spending and life expectancy across countries. The analysis is implemented as a Jupyter notebook (`sgolla_eda.ipynb`) and uses the dataset `healthexp.csv` included in the repository.

This README explains how to set up the environment, run the notebook, and reproduce the figures and analyses.

## Contents

- `healthexp.csv` — dataset used for the analyses (per-capita spending and life expectancy by year and country)
- `sgolla_eda.ipynb` — the main EDA notebook (data loading, diagnostics, visualizations, regression)
- `requirements.txt` — Python dependencies (install into a virtual environment)

## Project summary

Goal: explore the relationship between per-capita health spending (`Spending_USD`) and average life expectancy (`Life_Expectancy`) over time and across countries. The notebook contains both static (Matplotlib/Seaborn) and interactive (Plotly) visualizations and a basic OLS regression analysis.

## Quick start (Windows PowerShell)

1. Clone the repository (if needed) and change into the project directory:

```powershell
git clone <repo-url>
cd datafun-06-eda
```

2. Create and activate a virtual environment named `.venv` (PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

3. Install required packages:

```powershell
pip install -r requirements.txt
```

4. Start JupyterLab / Notebook and open `sgolla_eda.ipynb`:

```powershell
jupyter lab
```

Notes:
- If you encounter permission issues when activating the virtual environment on Windows, run `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force` in an elevated PowerShell (follow your local IT/security rules).
- If `requirements.txt` is missing or incomplete, install `pandas numpy matplotlib seaborn plotly statsmodels`.

## Data

The repository includes `healthexp.csv` with these columns:

- `Year` — calendar year
- `Country` — country name
- `Spending_USD` — per-capita health spending (USD)
- `Life_Expectancy` — average life expectancy (years)

Load the data in Python as follows:

```python
import pandas as pd
df = pd.read_csv('healthexp.csv')
df.head()
```

## Notebook sections (what's in `sgolla_eda.ipynb`)

1. Imports and settings — sets plotting defaults and imports libraries.
2. Load the dataset — reads `healthexp.csv` into `df` and shows head/dtypes/summary.
3. Quick checks — missing values, unique countries, year range, and sample pivots.
4. Static visualizations — Matplotlib/Seaborn plots (time series, scatter, heatmap).
5. Interactive visualizations — Plotly line and scatter charts for exploration.
6. Regression analysis — OLS model (Life_Expectancy ~ Spending_USD) with diagnostics.

