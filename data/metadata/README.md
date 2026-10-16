# MTL-XF-038 — Metadata and audit records

Required team evidence:

| Record | Minimum contents | Owner/gate |
| --- | --- | --- |
| source_manifest.csv | S1/freeze ID, requested/resolved URL, retrieval UTC, release, archive/member bytes and SHA-256, storage/access owner, rights/citation and approval. | Governance / G1 |
| data_dictionary.csv | Actual field/type/unit, valid values, null/sentinel policy, meaning, target/feature/ID role, availability time and curated mapping. | Governance + Engineer / G1–G2 |
| source_to_output.csv | Requirement, S1 field, transformation, K/D/AC/DT link, supported/blocked state and reason. | BA + Governance / G1 |
| cohort_ledger.csv | Raw file/sheet/row ID, mutually exclusive retain/exclude/quarantine state, reason and freeze. | Engineer / G2 |
| metric_lineage.csv | K1–K7 raw fields, formula/code/output, population, denominator/unit/grain, missing policy and test/reviewer. | Domain specialist / G2 |
| evaluation_manifest.csv | Split/group/resample IDs, seed/order, predictor allowlist, target mapping, timing audit and policy lock version. | Modelling analyst / G2–G3 |
| quality_and_decisions.csv | Issue/change, affected count/outputs/tests, treatment, rationale, reviewer/date and state. | Delivery Lead / all gates |

**Grain:** One labelled fault example; not an entire production batch or a population of all manufactured plates.

**Fields:** 27 numeric process/geometry/steel predictors followed by seven fault indicator columns; verify exact order from Faults27x7_var.

**Evaluation:** Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors.

Use UTF-8 metadata, ISO dates and UTC retrieval times. Keep sensitive/raw contents and credentials out of logs; use IDs/hashes, and defanged security examples. Exact row accounting and seven-KPI lineage are mandatory. Team approval remains pending until executed; checked source references do not establish completed team analysis.
