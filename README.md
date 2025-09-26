# datafun-06-eda

A small exploratory data analysis (EDA) project created for the DataFun course series.

This repository contains code, notes, and artifacts used to explore, clean, and visualize the dataset used in the course assignments. The goal is to demonstrate good EDA practices: data loading, cleaning, summary statistics, visualizations, and short write-ups of findings.

## Table of contents

- Project overview
- Getting started
- Data
- Notebooks & scripts
- Results & figures
- Reproducibility
- Contributing
- License & contact

## Project overview

This repository is intended as a lightweight EDA workspace. Typical contents you may find (or add) here:

- Jupyter notebooks with step-by-step exploration
- Python scripts to run specific analyses or generate figures
- A `requirements.txt` file listing Python dependencies
- A `data/` directory (gitignored) or instructions to download the datasets

If you are a student following along with the course, use the notebooks to reproduce the analyses and modify them to explore your own hypotheses.

### Project goal

The primary goal of this project is to analyze historical health-care spending and life expectancy trends across multiple countries. Using `healthexp.csv`, we will explore relationships between per-capita health spending (in USD) and life expectancy over time, identify patterns across countries, and create visualizations that summarize key findings.

## Getting started

Prerequisites

- Python 3.8+ recommended
- Git (to clone the repository)

Quick start (Windows PowerShell)

```powershell
# clone the repo (if you haven't already)
git clone <repo-url>
cd datafun-06-eda

# create and activate a virtual environment
python -m venv .venv; .\.venv\Scripts\Activate.ps1

# install dependencies
pip install -r requirements.txt

# open JupyterLab / Notebook
jupyter lab
```

Replace <repo-url> with your repository URL (for example the origin you cloned from).

## Data

This project does not include large raw datasets in the repository. Place data files under a `data/` directory (add this to `.gitignore`) or update the notebooks to point to your local data path. If the course provided a download link, follow the course instructions to fetch the data and put it in `data/`.

When working with sensitive or large data, avoid committing it to git. Instead, include a small sample or a data schema and the download script.

### Dataset

Included in this repository is a CSV file named [healthexp.csv](https://github.com/s-golla/datafun-06-eda/blob/main/healthexp.csv). The file contains historical records with the following columns:

- `Year` — calendar year of the observation
- `Country` — country name
- `Spending_USD` — per-capita health spending (USD)
- `Life_Expectancy` — average life expectancy (years)

You can open the file directly in a spreadsheet program or load it in Python / a notebook with pandas:

```python
import pandas as pd
df = pd.read_csv('healthexp.csv')
df.head()
```

Use this dataset as the primary source for the examples and visualizations in the notebooks.

## Notebooks & scripts

- `notebooks/` — place Jupyter notebooks here (e.g., `01-exploration.ipynb`, `02-cleaning.ipynb`).
- `src/` — reusable Python modules and analysis scripts.
- `scripts/` — convenience scripts to reproduce figures or run the pipeline.

Open the notebooks in JupyterLab and run them in order. Cells that read data assume the `data/` path is relative to the repository root.

## Results & figures

Generated figures and short write-ups can be committed to a `results/` or `figures/` directory. Use descriptive filenames and include a brief caption in the notebook or an accompanying `RESULTS.md`.

## Reproducibility

- Python version: 3.8+ (specify in your environment)
- Dependencies: see `requirements.txt`
- To ensure reproducible outputs, pin package versions in `requirements.txt` and document the random seeds used in notebooks.

