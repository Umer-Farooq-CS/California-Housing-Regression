# Progress

- Phase 1: Loaded dataset via sklearn (no pandas), printed arrays and table preview.
- Phase 2: NumPy stats, skewness per feature, hist/box plots, corr matrix & heatmap, corr with target.
- Phase 3A: Single-feature LR & SGD, metrics; polynomial degrees 2 & 3 compared.
- Phase 3B: Multi-feature LR & SGD on original and engineered (deg 2, 3) features.
- Phase 4: 80/20 split, StandardScaler for SGD, metrics train/test, residual plots.
- Phase 5: 5-fold CV for LR & SGD (scaled); reported mean±std for MSE, RMSE, MAE, R2.

Current status: All phases complete; figures exported; README finalized; LNCS LaTeX compiled to `reports/Report.pdf`.

- Added enhanced visualizations: scatter+fit, metrics bars (3A/3B/4), CV boxplots and mean bars (5).
