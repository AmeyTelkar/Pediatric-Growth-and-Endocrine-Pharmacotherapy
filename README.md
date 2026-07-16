 > **Copyright © 2026 Atherv D. Telkar & Amey D. Telkar. All Rights Reserved.**
> 
> All datasets, the 13-step FAERS preprocessing pipeline, the two-stage clinical imputation scheme, ML training framework, and associated works are **original intellectual creations** of the named copyright owners, created entirely using personal computing resources.
> 
> Protected under: Section 17, **Indian Copyright Act, 1957** · **Berne Convention** (181 member countries)
> 
> **MIT Vishwaprayag University holds NO intellectual property rights over any part of this work.**
> 
> Reproduction, modification, redistribution, or commercial use without **explicit written permission from both copyright owners** is strictly prohibited.
> 
> Contact: athervtelkar08@gmail.com (Atherv D. Telkar) · ameytelkar08@gmail.com (Amey D. Telkar)

---

# Pediatric Growth and Endocrine Pharmacotherapy — FAERS ML Framework

## Overview
This repository contains the dataset and verified reference list for the study:

**"Machine Learning-Based Outcome Severity Classification in Pediatric Growth and Endocrine Pharmacotherapy: A FAERS Cohort Study (2021–2025)"**

**Authors:** Atherv D. Telkar, Amey D. Telkar, Aarav Javalgikar, Nachiket Madanwale, Deepak Ruikar, Pramod Baligar

---

## Repository Contents

### `Growth and Endocrine Model/`

> **Note:** GitHub cannot preview `.xlsx` files. Use the **CSV files** below to view data directly in GitHub. Download the `.xlsx` files for full Excel access.

| File | Format | Description |
|---|---|---|
| `EndocrineAll_14Columns_Preview.csv` | CSV ✅ GitHub preview | First 500 rows of the 14-column leakage-aware dataset |
| `EndocrineAll_Drugs_Pediatric_14Columns_Imputed.xlsx` | Excel (download) | Full 14-column leakage-aware model dataset (N=44,431) |
| `EndocrineAll_Drugs_Pediatric_15Columns_Imputed.xlsx` | Excel (download) | Full 15-column sanity-check model dataset (N=44,431) |
| `Endocrine_Counts_2021_2025.csv` | CSV ✅ GitHub preview | Quarter-wise cohort counts per drug class (2021Q1–2025Q4) |
| `Endocrine_Counts_2021_2025.xlsx` | Excel (download) | Same — Excel version |
| `ML_Model_Results.csv` | CSV ✅ GitHub preview | XGBoost and Random Forest performance metrics |
| `ML_Multiclass_Model_Comparison_Results.xlsx` | Excel (download) | Same — Excel version |

### `Growth and Endocrine Model/Journal References/`
- `VERIFIED_REFERENCES.md` — All 24 paper citations with confirmed DOIs and PMC free-download links

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
- **Somatropin (rhGH):** n = 31,948
- **Levothyroxine:** n = 6,523
- **Hydrocortisone:** n = 5,035
- **Leuprolide (GnRH agonist):** n = 1,970
- **Methimazole:** n = 283

---

## 13-Step FAERS Preprocessing Pipeline — Copyright Protected

The deterministic 13-step FAERS preprocessing pipeline is an **original intellectual contribution** of the named copyright owners, developed entirely using personal computing resources.

| Step | Description |
|---|---|
| **Step 0** | Raw FAERS file ingestion (header-based automatic file-type detection across all 20 quarters) |
| **Step 1** | High-sparsity column removal (>90% null threshold) — removes ~1.4M null cells per quarter |
| **Step 2** | Four-level case deduplication: caseversion → i_f_code (F preferred) → fda_dt → primaryid |
| **Step 3** | Age normalisation — 6 unit variants (years, months, weeks, days, hours, decades) → decimal years |
| **Step 4** | ICH E11(R1) age-band assignment: neonate, infant, toddler, child, pre-adolescent, adolescent (0–17 y) |
| **Step 5** | Weight unit harmonisation (lbs → kg via 0.453592 factor) |
| **Step 6** | Configurable age filter — restricted to 0–17 years for endocrine cohort |
| **Step 7** | Null-safe date standardisation (event and FDA receipt dates) |
| **Step 8** | Primary-ID pre-join filtering before DEMO/DRUG/REAC table merge |
| **Step 9** | val_vbm = 2 invalid weight record removal |
| **Step 10** | Drug name normalisation: RxNorm API (94% match) + RapidFuzz fuzzy match (6% fallback) |
| **Step 11** | Seven-level outcome severity scale encoding: RI < DS < CA < LT < DE < HO < OT |
| **Step 12** | Indication text cleaning (handles 49.16% missingness) |
| **Step 13** | Human Approve/Reject quality gate with full deterministic audit trail |

> The **i_f_code** follow-up/initial tie-break at Step 2 and the **two-stage clinical imputation** scheme (AE-specific mode imputation → clinical-indicator hierarchical fallback) are original contributions not documented in any reviewed pharmacovigilance publication.

---

## Citation
If referencing this work or pipeline, please cite:

> Telkar A, Telkar A, Javalgikar A, Madanwale N, Ruikar D, Baligar P.
> *Machine learning-based outcome severity classification in pediatric growth and endocrine pharmacotherapy: a FAERS cohort study (2021–2025)*. [Preprint, 2026].
