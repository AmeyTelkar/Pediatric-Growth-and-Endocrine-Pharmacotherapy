# Pediatric Growth and Endocrine Pharmacotherapy — FAERS ML Framework

## Overview
This repository contains the dataset, LaTeX paper, and verified reference list for the study:

**"Machine Learning-Based Outcome Severity Classification in Pediatric Growth and Endocrine Pharmacotherapy: A FAERS Cohort Study (2021–2025)"**

**Authors:** Atherv D. Telkar, Amey D. Telkar, Aarav Javalgikar, Nachiket Madanwale, Deepak Ruikar, Pramod Baligar

---

## Repository Contents

### `Growth and Endocrine Model/`
- `EndocrineAll_Drugs_Pediatric_14Columns_Imputed.xlsx` — 14-column leakage-aware model dataset (N=44,431)
- `EndocrineAll_Drugs_Pediatric_15Columns_Imputed.xlsx` — 15-column sanity-check model dataset
- `Endocrine_Counts_2021_2025.xlsx` — Quarter-wise cohort counts per drug class (2021Q1–2025Q4)
- `ML_Multiclass_Model_Comparison_Results.xlsx` — XGBoost and Random Forest performance metrics

### `Growth and Endocrine Model/Journal References/`
- `VERIFIED_REFERENCES.md` — All 24 paper citations with confirmed DOIs and access links

### `Research paper latex/`
- `EndocrineDrugs.tex` — Full Q1-journal-quality LaTeX paper

---

## Key Results
| Model | Columns | Accuracy | Macro-F1 |
|---|---|---|---|
| XGBoost | 14 (leakage-aware) | **87.28%** | **0.4903** |
| Random Forest | 14 (leakage-aware) | 86.99% | 0.4889 |
| XGBoost | 15 (sanity-check) | 97.47% | 0.9704 |

**Cohort:** N = 44,431 pediatric cases (0–17 years) | 5 drug classes | 20 quarters (2021Q1–2025Q4)

---

## Drug Classes Covered
- Somatropin (rhGH): n = 31,948
- Levothyroxine: n = 6,523
- Hydrocortisone: n = 5,035
- Leuprolide (GnRH agonist): n = 1,970
- Methimazole: n = 283

---

## Citation
If you use this dataset or framework, please cite:
Telkar A, Telkar A, et al. *Machine learning-based outcome severity classification in pediatric growth and endocrine pharmacotherapy: a FAERS cohort study (2021–2025)*. [Preprint, 2026].

---

## License / Copyright
All datasets, code, pipeline, and paper are original works by the named copyright owners.
MIT Vishwaprayag University holds no intellectual property rights over this work.
Copyright vests exclusively with the named individuals under Section 17, Indian Copyright Act, 1957.
