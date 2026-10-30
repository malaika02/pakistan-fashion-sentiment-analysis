# Project 1 — Evidence-based executive readout

**Data source:** UCI Roman Urdu Data Set, 2,000 source-derived unique Roman Urdu comment/review records, NOT a verified Pakistani fashion Instagram feed.

**Observation 1:** Source labels across the complete pilot: {'Positive': 630, 'Neutral': 811, 'Negative': 556}. The cohort is intentionally mixed-source, so these percentages are sample descriptions only.

**Observation 2:** Among 161 *keyword-screened apparel candidates*, 51 carried the source Negative label (31.7%) and 54 the Positive label (33.5%). These are not manually confirmed brand reviews.

**Observation 3:** The most frequent apparel-topic screen is **Quality / material** (75/161 candidate texts). Regex rules overlap and can misclassify.

**Proposed business test:** Have a native Roman Urdu reader verify an audited random sample of the apparel candidates, identify which quality/fit/price/delivery concerns genuinely recur, and run a controlled Instagram or social-listening experiment with the brand's authorized post-level analytics. Compare posts by per-post median outcomes and, only if supplied, engagement per impression/reach. Keep platform/account/format/time consistent where possible.

**Not supported:** best posting days, which platform works best, city rankings, follower-normalized engagement, ad ROAS, causal effects, Pakistan-wide market prevalence.

**Scale decision:** Benchmarking above uses repeated real records as a computational load test only, not extra unique observations. For this 2k-row task Pandas is appropriate; evaluate Spark when requirements exceed available single-machine compute/storage or there is a distributed processing need.

**Model:** Held-out TF-IDF macro-F1=0.592; majority macro-F1=0.193. This is source-domain validation, not verified fashion deployment accuracy.
