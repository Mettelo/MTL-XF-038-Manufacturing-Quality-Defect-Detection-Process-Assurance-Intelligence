# MTL-XF-038 — Deliverables and metric contracts

**Decision:** Choose a seven-class defect-routing prototype and a low-confidence specialist inspection queue.

Required team outputs follow; this master does not claim they are complete. Each item needs a named author, distinct reviewer, version, evidence link and status.

## D1 — Discovery and requirements

**Due:** Week 2 · **Owner:** Business Analyst / Delivery Lead · **Team location:** docs/01-discovery/

Eight user requirements, prioritised by decision value, each with owner and measurable test; stakeholder map and as-is/to-be workflow for weekly defect classification and inspection review.

**Pass evidence:** All eight link source support, D/AC/DT and Head of Manufacturing Quality approval.

## D2 — Governed source and freeze

**Due:** Week 2 · **Owner:** Data Governance Analyst · **Team location:** docs/02-data-governance/

S1 provenance, rights, dictionary, storage/restore path and immutable byte manifest. All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

**Pass evidence:** Every required file/field is verified and approved; unsupported requirements explicitly block G1.

## D3 — Engineering pipeline and model

**Due:** Week 4 · **Owner:** Data Engineer · **Team location:** src/ and docs/03-data-model/

Versioned ingestion/transformation and curated model. Grain: One labelled fault example; not an entire production batch or a population of all manufactured plates. Preserve file/sheet/row lineage and all exclusion reasons.

**Pass evidence:** Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist.

## D4 — Quality and exceptions

**Due:** Week 4 · **Owner:** Data Engineer + independent reviewer · **Team location:** docs/04-data-quality/

Profile types, nulls, duplicates, sentinels, labels, units and source support. Address A classifier trained only on defective examples cannot demonstrate detection sensitivity against normal production or factory reject reduction.

**Pass evidence:** Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion.

## D5 — Fault schema and class-mix audit

**Due:** Week 4 · **Owner:** Manufacturing Quality Analyst · **Business reviewer:** Head of Manufacturing Quality · **Independent reviewer:** Quality Model Assurance Analyst

**Required artefact:** data/curated/fault-schema-and-class-mix-audit.csv and docs/05-kpi-catalogue/fault-schema-and-class-mix-audit.md.

Ordered 27 predictors/seven labels, 1,941 source examples, one-hot validity, per-class counts and duplicate/conflicting-label register.

**Mandatory pass condition (SC1):** Exactly one active class per valid row; malformed labels quarantined; all 34 source columns mapped; no invented normal class or production denominator.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D6 — Seven-class evaluation and error review

**Due:** Week 6 · **Owner:** Data Scientist / Decision Modelling Analyst · **Business reviewer:** Head of Manufacturing Quality · **Independent reviewer:** Quality Model Assurance Analyst

**Required artefact:** docs/06-analysis/seven-class-evaluation-and-error-review.md plus machine-readable evaluation_results.csv.

Majority baseline and interpretable candidate with macro F1, balanced accuracy, seven recalls, full confusion matrix and top-three confusion pairs.

**Mandatory pass condition (SC2):** Labels excluded from predictors; duplicate feature groups kept together; all class supports reported and undefined outcomes explicit; include ten reviewed errors.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D7 — Confidence-based routing policy

**Due:** Week 6 · **Owner:** Manufacturing Quality Analyst · **Business reviewer:** Head of Manufacturing Quality · **Independent reviewer:** Quality Model Assurance Analyst

**Required artefact:** docs/07-decision-framework/confidence-based-routing-policy.csv plus policy.md.

Thresholds 0.50/0.60/0.70 with auto-route coverage/accuracy and specialist review workload; ten worked routing cases.

**Mandatory pass condition (SC3):** At 0.60, score 0.599 refers and 0.600 is eligible; every case has predicted/actual class, confidence, routing owner and review reason; no production accept/reject claim.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D8 — Quality routing dashboard

**Due:** Week 7 · **Owner:** BI / Decision Product Developer · **Business reviewer:** Head of Manufacturing Quality · **Independent reviewer:** Quality Model Assurance Analyst

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

Class mix, error pairs, confidence/workload comparison and source limitations.

**Mandatory pass condition (SC4):** Reviewer finds the largest confusion pair, shows its two class recalls and traces one low-confidence case into specialist review.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D9 — Independent assurance and UAT

**Due:** Week 7 · **Owner:** Quality Model Assurance Analyst · **Team location:** docs/08-assurance-uat/

Execute DT1–DT10 and three stakeholder tasks; record actual results and defects/retests.

**Pass evidence:** All ten tests and three tasks pass; zero unresolved critical/high defects.

## D10 — Technical/operational handover

**Due:** Week 8 · **Owner:** Engineer + Delivery Lead · **Team location:** docs/09-technical-handover/

One documented run entry point, dependency versions, manifest, output checksums/tolerances, refresh, rollback and operational owner.

**Pass evidence:** Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded.

## D11 — Inspection handover and three investigation cards

**Due:** Week 8 · **Owner:** Business Analyst / Delivery Lead with domain specialist · **Business reviewer:** Head of Manufacturing Quality · **Independent reviewer:** Quality Model Assurance Analyst

**Required artefact:** deliverables/inspection-handover-and-three-investigation-cards.pdf plus editable slides and supporting cards/runbook.

Fault-routing instructions, ten-case handover and three non-causal process hypotheses with measurements needed from a real factory.

**Mandatory pass condition (SC5):** Each hypothesis names quality/process owner and required batch/time/normal-plate evidence; no asserted root cause, defect reduction or reject-rate improvement.

**Review evidence:** retain the actual output, source-to-field/code/configuration lineage, expected/actual verification, reviewer and date. A heading, screenshot or unsupported claim alone cannot satisfy this deliverable.


## D12 — Contribution and final submission

**Due:** Weekly; final week 8 · **Owner:** Delivery Lead · **Team location:** CONTRIBUTIONS.md and submission/FINAL_SUBMISSION.md

Named D owners/reviewers, authored work, issues/PRs/commits, substantive reviews and demo/handover contribution for each member.

**Pass evidence:** All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count.

## K1–K7 — Authoritative contracts

| ID | Metric | Definition and population | Grain |
| --- | --- | --- | --- |
| K1 | Fault-class mix | examples of class / valid fault examples; not factory incidence. | seven classes |
| K2 | Macro F1 | unweighted mean of per-class F1; explicit zero/undefined policy. | test |
| K3 | Per-class recall | correctly classified class examples / actual class examples. | each class |
| K4 | Balanced accuracy | mean of seven class recalls. | test |
| K5 | Specialist review share | cases below locked confidence threshold / test cases. | test |
| K6 | Auto-route accuracy | correct predictions / cases meeting confidence threshold; report coverage alongside. | test |
| K7 | Confusion burden | counts for every actual×predicted class pair and top three error pairs. | test |

Extend each contract with actual S1 raw fields and curated columns, code lineage, population/exclusions, numerator/denominator, units/grain, aggregation, missing/zero/undefined policy, owner/reviewer, freeze ID and tests. Manufacturing Quality Analyst owns interpretation; Engineer implements; Quality Model Assurance Analyst reviews.

Zero denominators produce unavailable values with reasons. Do not average subgroup rates when compatible summed numerators/denominators are required. Show class/segment counts beside rates and uncertainty. Counts reconcile exactly; arithmetic reconciles unrounded or to a documented tolerance no wider than 0.01 displayed unit. No source field can silently be replaced by an assumption.

## Evaluation and decision policy

Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors.

Baseline majority-class classifier; alternative regularised multinomial/logistic or tree classifier with validation-selected tuning. Route low-confidence cases (max probability<0.60, simulation threshold) for specialist review and compare 0.50/0.70 alternatives; classify known faults only.

**Interpretation boundary:** No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

See [acceptance](ACCEPTANCE_CRITERIA.md) for tests and [governance](GOVERNANCE.md) for release decisions.
