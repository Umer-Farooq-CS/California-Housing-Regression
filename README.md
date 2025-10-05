Deep Learning for Perception — Assignment 1
=================================================

Author: Umer Farooq (Roll No: 22I-0891, Section: CS-7B)

Overview
--------
Experimental Linear Regression analysis on the California Housing dataset across five phases. No pandas used; NumPy and scikit-learn only. Target variable is `MedHouseVal` (x100k USD). Results include consistent metrics (MSE, RMSE, MAE, R2), phase-wise figures, and a formal LNCS-style report.

Repository Structure
--------------------
- `notebooks/Assignment1.ipynb`: Main experiments organized by phases.
- `data/`: Exported figures used in report and README.
- `reports/`: LaTeX LNCS project and report README.
- `memory-bank/`: Project intelligence and decisions.
 - `reports/Report.pdf`: Compiled report (also available as `reports/Report.pdf`).

Phases & Key Takeaways
----------------------
- Phase 1 — Dataset Loading (No Pandas)
  - Loaded via `sklearn.datasets.fetch_california_housing()`.
  - Displayed headers and array samples; printed target preview.

- Phase 2 — EDA
  - NumPy descriptive stats; manual skewness (standardized 3rd moment).
  - Correlations: `MedInc` strongest with `MedHouseVal`; room features correlate with each other (multicollinearity).
  - Figures: histograms/boxplots and correlation heatmap.

- Phase 3A — Single-Feature Regression
  - Chosen strongest feature by |corr| (typically `MedInc`).
  - Compared Linear Regression vs scaled SGD; metrics reported.

- Phase 3B — Multi-Feature + Polynomial Features (deg 1–3)
  - Pipelines compare LR vs scaled SGD with PolynomialFeatures.
  - In-sample metrics improve with higher degree; note overfitting risk.

- Phase 4 — Train/Test Split (80/20)
  - LR on raw features; SGD with StandardScaler.
  - Train/test metrics and residual plots; small generalization gap observed.

- Phase 5 — 5-Fold Cross-Validation
  - Pipelines with consistent folds; mean ± std for MSE, RMSE, MAE, R2.
  - LR and scaled-SGD show comparable performance; scaling critical for SGD.

Summary of Results
------------------
- Strongest single predictor: `MedInc` vs `MedHouseVal` with the highest absolute correlation (see figure in `data/Phase 3A MedInc vs MidHouseVal.png`).
- Polynomial features (degree 2–3) improve in-sample fit but risk overfitting; cross-validation stabilizes estimates.
- On 5-fold CV, Linear Regression and SGD (with StandardScaler) perform comparably in terms of RMSE and R²; scaling is essential for SGD convergence and stability.

Metrics (What is Reported)
--------------------------
- MSE, RMSE, MAE, R2 are computed consistently using NumPy-based helpers.
- For CV, results are summarized as mean ± std across folds.

Reproducing Results
-------------------
1) Environment
   - Python 3.10+
   - Install dependencies (no pandas is required or used):

```
pip install -r requirements.txt
```

2) Run the notebook
   - Open `notebooks/Assignment1.ipynb` and run all cells in order.

3) Report
   - A compiled LNCS-style PDF is available at `reports/Report.pdf`. The LaTeX source lives under `reports/lncs/`.

Figures
-------
Exported images used in README and the LaTeX report (see `data/`):
- Phase 2 EDA: `data/Phase 2 EDA.png`, `data/Phase 2 Correlation.png`
- Phase 3A: `data/Phase 3A MedInc vs MidHouseVal.png`, `data/Phase 3A Metrics.png`
- Phase 3B: `data/Phase 3B MSE.png`, `data/Phase 3B R2.png`
- Phase 4 Residuals: `data/LR Residulas Phase 4.png`, `data/SGD Residulas Phase 4.png`
- Phase 5 CV: `data/Phase 5 CV Mean Metrics.png`

Report
------
- An LNCS (Springer Lecture Notes in CS) LaTeX project is provided under `reports/lncs/` with figures included and build instructions.
 - The compiled PDF is available at `reports/Report.pdf`.

Acknowledgments
---------------
- scikit-learn California Housing dataset and APIs.
- Matplotlib/Seaborn for visualization.


