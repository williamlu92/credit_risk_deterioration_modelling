# Credit Risk Early Warning System

This project uses LendingClub loan data to estimate default risk, compare model approaches, and identify loans whose risk may rise over time. It combines a fully executed analysis notebook with a polished technical report.

## What is included

- `notebook/CreditRisk_fixed.ipynb` — the complete analysis with concise, result-focused notes.
- `report/credit_risk_report.pdf` — the finished report for quick reading.
- `report/credit_risk_report.tex` — the editable report source.
- `report/figures/` — chart files used by the report.

## Main findings

- The baseline logistic model has useful ranking power on resolved 2015 loans, with ROC-AUC of 0.729 and average precision of 0.406.
- Observed default rises from 5.5% in the lowest-risk group to 42.3% in the highest-risk group.
- Higher-risk loans default more often than the models predict, so probability calibration remains important.
- 60-month loans are materially riskier than 36-month loans, although unresolved outcomes make the lifetime comparison selective.
- A 12/24/36-month framework helps distinguish immediate risk from slower deterioration.
- The economic watchlist is illustrative and depends on assumptions that should be approved before operational use.

## Running the notebook

The raw LendingClub dataset is not included. The notebook expects `accepted_2007_to_2018Q4.csv.gz`. Place it in a local `data/` directory or set the `CREDIT_RISK_DATA` environment variable to its location before running.

Create an environment and install the Python packages with `pip install -r requirements.txt`. Then run the notebook from top to bottom with a Python 3 kernel. It processes more than two million loan records, so execution may take several minutes and requires adequate memory.

## Important limitation

This is a research prototype, not a production underwriting, pricing, capital, or accounting model. Default timing is approximated with the last payment date, and the economic assumptions are scenarios rather than validated business inputs.
