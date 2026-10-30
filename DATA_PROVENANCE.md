# Data provenance, transformation, legal use, and limitations

## Actual data (not generated)
The separate `pakistan_roman_urdu_real_2000.csv` contains 2,000 unique source-derived comment/review records from the **Roman Urdu Data Set**, UCI Machine Learning Repository, credited to **Zareen Sharf (2017)**. UCI reports original corpus of approximately 20,000 Roman Urdu records with Positive / Neutral / Negative labels, donated 2018. UCI canonical DOI: https://doi.org/10.24432/C58325 . UCI page: https://archive.ics.uci.edu/dataset/458/roman+urdu+data+set . GitHub source mirror: https://github.com/Smat26/Roman-Urdu-Dataset/blob/master/Dataset/Roman%20Urdu%20DataSet.csv (original blob SHA 108c5df4c89a1bfefa4cfd7c258c3d6b3bfbd721). Accessed 30 October 2026.

## Redistribution/license
UCI states the dataset is licensed under **Creative Commons Attribution 4.0 International**. It permits sharing/adaptation with attribution. License: https://creativecommons.org/licenses/by/4.0/ . This extract modifies the original by de-duplicating, omitting malformed/unlabeled/short and very long records, masking typical email/URL/handle/phone patterns, and selecting a fixed random sample. It adds derived source-record IDs, screening cohorts and provenance fields. UCI author retains original credit; the derived segmentation and notebook are not endorsed by the author. Privacy review is advised before any public report.

## Extraction methodology
Read source `Roman Urdu DataSet.csv` as text and CSV-parse quoted fields. Preserve original record number. Retain `Positive`, `Neutral` and `Negative` labels and texts of 12 to 850 characters after basic whitespace normalization/privacy masking. Case-insensitive near-exact normalization is used for deduplication. Derive the `apparel_keyword_candidate` flag from a clothing-related keyword regex (shirt, suit, dress, jeans, kurti, kapra, trouser, etc.). From 18,551 accepted unique records, take all 161 regex apparel matches and seeded randomly selected 1,839 other real records; shuffle reproducibly. Seed `20261030` and record rows in `source_row_number`; there were 20,229 raw parsed entries. **This is intentionally stratified/oversampled, not a representative random sample**. The keyword flag is not manually verified and contains false positives. CSV contains 2,000 source-derived records, 6 columns, and no fabricated engagement metrics. The notebook validates 1,997 after excluding 3 very short post-trim entries; it preserves all original 2,000 in the downloaded CSV.

## Data fields
`record_id`: derived source row ID; `comment_text`: real source comment/review with basic masking; `sentiment`: original source label; `segment`: apparel-keyword candidate or broad/general group, machine-derived; `source_row_number`: original corpus record number for lineage; `source_dataset`: UCI citation identifier.

## Limitations relevant to the uploaded Big Data lecture wizard
The lecture describes a **Pakistani clothing brand on Instagram** with marketing engagement data. The licensed corpus is a **language/sentiment proxy** and cannot substantiate findings about Pakistani Instagram platform reach, best posting time, city, brand mentions, likes, comments per post, paid campaigns, cost, conversion, ROAS or period trend; no such columns are present. Roman Urdu does not guarantee a Pakistani resident. This educational dataset supports defensible introductory cleaning, EDA, keyword-screened consumer-language themes, sentiment classification, and a workload scaling experiment only.

## File fingerprint
CSV SHA256: `92ae8e6b62cbe8c8d71506f8fb974d58e20bab68d9ffbeb22d21e7e195ff7e74`
