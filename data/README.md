# MTL-XF-038 — Data acquisition and engineering

## Approved S1

[Steel Plates Faults](https://archive.ics.uci.edu/dataset/198); required files: **Faults.NNA and Faults27x7_var**. Expected source population: 1,941 faulty-plate examples.

Exact official download:

https://archive.ics.uci.edu/static/public/198/steel+plates+faults.zip

No paid API or temporary dashboard export is required. [Source register](SOURCE_REGISTER.md) records checked byte references and rights.

## Frozen cohort and schema

All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

**Grain:** One labelled fault example; not an entire production batch or a population of all manufactured plates.

**Required fields:** 27 numeric process/geometry/steel predictors followed by seven fault indicator columns; verify exact order from Faults27x7_var.

## Acquisition and freeze procedure

1. Retrieve original bytes and required documentation into approved durable storage outside Git. Record retrieval UTC, requested/resolved URLs and HTTP result.
2. Verify archive/member integrity, actual sizes and SHA-256 against the checked reference. A mismatch stops processing for publisher-change/corruption review.
3. Inspect schema, encoding, separator, headers/sheets, count, label coding, dates and coverage. Faults.NNA has no header. Apply all 34 ordered names from Faults27x7_var; first 27 are predictors and last seven fault indicators.
4. Complete source→actual field→KPI→deliverable support matrix for K1–K7 and D1–D12. Missing mandatory fields block dependent work; do not invent substitutes.
5. Approve an immutable S1-v1 byte manifest and exact cohort with retention owner, reviewer access, analyst/reviewer identities and date. Master source verification does not replace team G1 approval.
6. Transform reproducibly into separate curated outputs. Account for every raw row once as retained, excluded or quarantined; preserve lineage and treatment reason.

## Evaluation

Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors.

## Interpretation and quality

No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

Profile every actual column. Dictionary includes spelling, type, unit, valid values, sentinel/null policy, meaning and feature/target/ID role plus availability time. Investigate duplicates/label conflicts; no silent deduplication or denominator invention. Validate key uniqueness and joins at the declared grain.

Keep [raw](raw/README.md), [references](reference/README.md) and [metadata](metadata/README.md) separate. Derived outputs belong in team data/curated/ or an approved location. Raw data are not uploaded by this update. Refresh creates a new snapshot while the accepted core stays reproducible.
