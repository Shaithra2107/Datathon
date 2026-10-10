# TeamName - Datathon submission (Tech-Triathlon 2026)

## What's in this folder
| Path | What |
|---|---|
| `TeamName_FinalNotebook.ipynb` | **final notebook**: labels, preprocessing, training, evaluation, all 3 tasks, and an inference demo at the end |
| `01_EDA_and_Labels.ipynb` | exploratory analysis notebook |
| `src/` | the same pipeline code as separate Python files (for deployment). The notebook has all the code inside it and does not need these |
| `models/` | saved models (`.pkl`): Task 1 regressor + classifier, Task 2A demand models |
| `submissions/` | `submission_task1.csv`, `submission_task2a.csv`, `submission_task2b.csv` |
| `docs/` | architecture diagram, data preprocessing document, Task 2B policy, AI tool disclosure |
| `data/` | organisers' data (unchanged) |
| `check_allocation.py` | organisers' Task 2B checker |

## How to run
```
pip install -r requirements.txt
jupyter notebook TeamName_FinalNotebook.ipynb     # Run All, from this folder
```
The full run takes about 7 minutes (the Task 2B optimiser takes up to 5 of those). Random seed = 42.
Check Task 2B: `python check_allocation.py submissions/submission_task2b.csv` -> `FEASIBILITY: PASSED`.

## Results (validation)
| Task | Baseline | Ours |
|---|---|---|
| Service time MAE (last 6 weeks) | dispatcher allowance 7.05 min | 3.73 min |
| Late probability AUC / log-loss | slack rule 0.880 / base rate 0.405 | 0.974 / 0.134 |
| Weekly demand WAPE (same season last year) | last year x growth 11.7% | 6.2% |
| Peak day S1 | - | 77/85 orders served, all rules passed, no outlet skipped twice |
