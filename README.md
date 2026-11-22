# 25280049 — Assignment 3 (AI651: Deep Learning for Space, Time and Graphs)

Syed Obaidullah Hassan Chishti — 25280049

## File arrangement

```
25280049_Assignment3_DL4STG/
├── 25280049_Question1.ipynb     # Message passing: what a sum remembers
├── 25280049_Question2.ipynb     # Ring road: direction of a moving slowdown
├── 25280049_Question3.ipynb     # Dataset prep + graph construction (LargeST San Diego)
├── 25280049_Question4.ipynb     # STGNN + temporal-only baseline
├── 25280049_Question5.ipynb     # Fixed / adaptive / hybrid adjacency
├── 25280049_Question6.ipynb     # Comparison table + graph analysis
├── 25280049_Question7.ipynb     # Reproducibility summary (reads results_q6.csv + figures)
├── results_q6.csv               # Final comparison table, written by Question 6
├── figures/                     # All figures used by the notebooks and the report
└── README.md
```

Questions 1–2 are self-contained (NumPy only). Questions 3–7 use the LargeST dataset.

## Requirements

```bash
pip install numpy pandas matplotlib torch h5py tables kagglehub
```

The LargeST data is downloaded from Kaggle (`liuxu77/largest`). Place a Kaggle API token at
`~/.kaggle/kaggle.json`. The notebooks call `kagglehub.dataset_download("liuxu77/largest")`, which
downloads the files once to the kagglehub cache (`~/.cache/kagglehub/...`) and returns that path on
later runs — nothing is copied into the project.

## How to run

Open each notebook in Jupyter and run all cells, in order:

1. `25280049_Question1.ipynb`
2. `25280049_Question2.ipynb`
3. `25280049_Question3.ipynb`
4. `25280049_Question4.ipynb`
5. `25280049_Question5.ipynb`
6. `25280049_Question6.ipynb` — writes `results_q6.csv` and the comparison figures
7. `25280049_Question7.ipynb`

Run Q3–Q6 before Q7, because Q7 reads `results_q6.csv` and displays the figures the earlier
notebooks save into `figures/`.

Reproducibility: fixed seed (2023), z-score normalization from the training split only, missing
values handled identically everywhere, and forecasting windows never cross split boundaries.
