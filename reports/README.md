Place report.pdf here when ready. Include any exported figures if needed.
Reports
=======

This directory contains the LNCS-style LaTeX report for Assignment 1.

Structure
---------
- `lncs/main.tex`: LNCS document using class `llncs` (compile on Overleaf or with the Springer LNCS style installed).
- `lncs/references.bib`: Bibliography entries.
- Figures: referenced directly from `../../data/*.png` so images stay centralized.

Build
-----
On Overleaf, select the Springer LNCS template and replace `main.tex` and `references.bib` with these files. Locally, ensure `llncs.cls` and `splncs04.bst` are available.

Commands (from `reports/lncs/`):

```
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Notes
-----
- Keep dataset figures in `data/`. The LaTeX uses relative paths `../../data/...`.
- Do not use pandas in the analysis; all results stem from NumPy + scikit-learn.