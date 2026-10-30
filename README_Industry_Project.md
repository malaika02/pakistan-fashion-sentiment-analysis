# Pakistan Fashion Consumer Voice Intelligence | Colab Project

This project is built against the user-provided **Big Data Analytics — Project 1 Lecture Wizard**. It includes a **separate real-data CSV** and a reproducible Google Colab notebook.

## Quick start
1. Download `Pakistan_Fashion_Real_Data_Industry_Project_Colab.ipynb` and `pakistan_roman_urdu_real_2000.csv`.
2. Open Google Colab; upload the `.ipynb` using File → Upload notebook.
3. Runtime → Run all. The notebook requests the CSV upload if it is missing.
4. Run optional Spark comparison only if required (`RUN_SPARK=True`), after installing PySpark.
5. Read generated `EXECUTIVE_SUMMARY.md`, pictures, classification report, and benchmarks in its output folder.

## Included
- 2,000 genuine source-derived public Roman Urdu comments/reviews in CSV with citation, lineage and screening flag.
- Python notebook with validation, EDA, statistical description, 5 chart outputs, consumer-language themes, TF-IDF logistic regression + baseline, held-out test, inference, 2k/20k/200k repeated-workload benchmark and optional Spark.
- `DATA_PROVENANCE.md` documenting source, CC BY 4.0 license, extraction and sampling, missing metrics and application boundaries.
- Demonstration run output ZIP, produced by executing all notebook code cells locally (excluding Colab package-install magic and optional Spark).

## Non-negotiable caveat
This is **not** a dataset of Pakistani fashion-brand Instagram posts. About 161 of the 2,000 real Roman Urdu records match clothing-apparel keywords; other records provide a general-purpose language classification sample. Screened candidates require human verification. There are **no real engagements/Instagram metrics** in the corpus, so the project does not claim platform trends or sales uplift. To meet an Instagram-specific marketing-outcome requirement in full, obtain permissioned first-party Instagram Insights data with engagement and caption fields.

## Verified model run (local, 2026-10-30)
Source-data CSV: 2,000 rows, no missing values, 0 duplicate source IDs. After stricter text-length check, 1,997 records train/evaluate. Holdout: 400; TF-IDF + Logistic Regression macro-F1 **0.592**, majority dummy macro-F1 **0.193**. Scores are **on original mixed-domain source text**, not external validated Pakistani-fashion accuracy. The 2k-to-200k experiment repeats rows **for performance testing only**, not to manufacture more Pakistani observations.
