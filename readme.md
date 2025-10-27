# 30 Days of Datasets

This repository is a 30-day data challenge: each day you pick or obtain a dataset, perform exploratory data analysis and standard data-science operations, and (when appropriate) build a predictive model or produce an analysis/report. The goal is to practice end-to-end data workflows and build a small portfolio of reproducible notebooks.

## Goals

- Practice daily data handling (acquire, clean, explore, visualize).
- Learn incremental feature engineering and model building.
- Build concise, shareable notebooks that document decisions and results.

## Repository structure (convention)

- `Day 1`, `Day 2`, ... — Daily notebooks with analysis and notes.
- `sample_data/` — small example datasets used by the notebooks.

## Daily workflow (suggested checklist)

1. Choose or collect a dataset and save it under `sample_data/` or a `data/` folder.
2. Open a new notebook (e.g., `notebook.ipynb`) and write a short objective: what question will you answer?
3. Quick EDA:
	- Inspect shapes, missingness, basic statistics.
	- Visualize distributions and relationships.
4. Data cleaning and feature engineering:
	- Handle missing values, outliers, and formats.
	- Create features (dates, categories, aggregates) where useful.
5. Modeling (if relevant):
	- Define baseline.
	- Split (train/validation/test) and evaluate with appropriate metrics.
	- Iterate on features and hyperparameters.
6. Document results and next steps in the notebook (markdown cells + short summary).

## Example modeling contract (tiny)

- Input: tabular dataset (CSV) with rows = examples, columns = features + target (if supervised).
- Output: short notebook showing a baseline model, one improved model, evaluation metrics, and visualizations.
- Error modes: missing target, too-small dataset, or incompatible target type — handle with clear notes.

Edge cases to consider: missing/null values, mixed types in a column, highly imbalanced targets, time-series leakages.


## Suggested dependencies

- Python 3.8+
- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- jupyterlab or notebook
- (optional) statsmodels, xgboost


```
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyterlab
statsmodels
```

## Contribution & notes

- Keep notebooks small and focused: prefer short, reproducible analyses.
- Use relative paths for data so others can run your notebooks locally.
- If you add larger datasets, note their source and licensing in the notebook's first cell.
- Consider adding a `requirements.txt` or `environment.yml` so others can reproduce your environment.

If you'd like to contribute, open a PR with a new day notebook or an improved analysis. Keep changes focused and include a short description of the dataset and objective.