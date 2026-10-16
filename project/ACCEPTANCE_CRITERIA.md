# MTL-XF-038 — Acceptance and domain tests

Acceptance requires executed evidence, not headings. Quality Model Assurance Analyst records state, actual result, evidence/commit, date, author, reviewer and defect/retest reference. Templates start NOT RUN.

## AC1–AC12

| Criterion | Output | Measurable pass condition |
| --- | --- | --- |
| AC1 | D1 | All eight link source support, D/AC/DT and Head of Manufacturing Quality approval. |
| AC2 | D2 | Every required file/field is verified and approved; unsupported requirements explicitly block G1. |
| AC3 | D3 | Input=retained+excluded+quarantined exactly; no unexplained join multiplication; clean-run instructions exist. |
| AC4 | D4 | Every treatment has affected count, reason, owner and reviewer; no silent row loss or coercion. |
| AC5 | D5 / SC1 | Exactly one active class per valid row; malformed labels quarantined; all 34 source columns mapped; no invented normal class or production denominator. |
| AC6 | D6 / SC2 | Labels excluded from predictors; duplicate feature groups kept together; all class supports reported and undefined outcomes explicit; include ten reviewed errors. |
| AC7 | D7 / SC3 | At 0.60, score 0.599 refers and 0.600 is eligible; every case has predicted/actual class, confidence, routing owner and review reason; no production accept/reject claim. |
| AC8 | D8 / SC4 | Reviewer finds the largest confusion pair, shows its two class recalls and traces one low-confidence case into specialist review. |
| AC9 | D9 | All ten tests and three tasks pass; zero unresolved critical/high defects. |
| AC10 | D10 | Second member reproduces all seven KPIs and policy queue from approved bytes; environment, elapsed time and discrepancies recorded. |
| AC11 | D11 / SC5 | Each hypothesis names quality/process owner and required batch/time/normal-plate evidence; no asserted root cause, defect reduction or reject-rate improvement. |
| AC12 | D12 | All D/AC/DT evidence links resolve at final commit/tag; individual contribution is demonstrated beyond bulk upload or commit count. |

## SC1–SC5 — Business output success contracts

These requirements supplement AC1–AC12 and are mandatory. Record approval at G1, then execute against final outputs. All five require PASS with traceable evidence, or a formally approved scope revision; an unmet model-performance target must be reported as unmet and reflected in the recommendation.

### SC1 / D5 — Fault schema and class-mix audit

**Accountable delivery role:** Manufacturing Quality Analyst. **Business reviewer:** Head of Manufacturing Quality. **Independent assurance:** Quality Model Assurance Analyst.

**Required artefact:** data/curated/fault-schema-and-class-mix-audit.csv and docs/05-kpi-catalogue/fault-schema-and-class-mix-audit.md.

**Content:** Ordered 27 predictors/seven labels, 1,941 source examples, one-hot validity, per-class counts and duplicate/conflicting-label register.

**Pass condition:** Exactly one active class per valid row; malformed labels quarantined; all 34 source columns mapped; no invented normal class or production denominator.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC2 / D6 — Seven-class evaluation and error review

**Accountable delivery role:** Data Scientist / Decision Modelling Analyst. **Business reviewer:** Head of Manufacturing Quality. **Independent assurance:** Quality Model Assurance Analyst.

**Required artefact:** docs/06-analysis/seven-class-evaluation-and-error-review.md plus machine-readable evaluation_results.csv.

**Content:** Majority baseline and interpretable candidate with macro F1, balanced accuracy, seven recalls, full confusion matrix and top-three confusion pairs.

**Pass condition:** Labels excluded from predictors; duplicate feature groups kept together; all class supports reported and undefined outcomes explicit; include ten reviewed errors.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC3 / D7 — Confidence-based routing policy

**Accountable delivery role:** Manufacturing Quality Analyst. **Business reviewer:** Head of Manufacturing Quality. **Independent assurance:** Quality Model Assurance Analyst.

**Required artefact:** docs/07-decision-framework/confidence-based-routing-policy.csv plus policy.md.

**Content:** Thresholds 0.50/0.60/0.70 with auto-route coverage/accuracy and specialist review workload; ten worked routing cases.

**Pass condition:** At 0.60, score 0.599 refers and 0.600 is eligible; every case has predicted/actual class, confidence, routing owner and review reason; no production accept/reject claim.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC4 / D8 — Quality routing dashboard

**Accountable delivery role:** BI / Decision Product Developer. **Business reviewer:** Head of Manufacturing Quality. **Independent assurance:** Quality Model Assurance Analyst.

**Required artefact:** dashboard/README.md, runnable dashboard/prototype and static review export.

**Content:** Class mix, error pairs, confidence/workload comparison and source limitations.

**Pass condition:** Reviewer finds the largest confusion pair, shows its two class recalls and traces one low-confidence case into specialist review.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.

### SC5 / D11 — Inspection handover and three investigation cards

**Accountable delivery role:** Business Analyst / Delivery Lead with domain specialist. **Business reviewer:** Head of Manufacturing Quality. **Independent assurance:** Quality Model Assurance Analyst.

**Required artefact:** deliverables/inspection-handover-and-three-investigation-cards.pdf plus editable slides and supporting cards/runbook.

**Content:** Fault-routing instructions, ten-case handover and three non-causal process hypotheses with measurements needed from a real factory.

**Pass condition:** Each hypothesis names quality/process owner and required batch/time/normal-plate evidence; no asserted root cause, defect reduction or reject-rate improvement.

**Evidence to retain:** actual output at final commit, source/configuration lineage, executed expected-versus-actual checks, reviewer identity/date and PASS/FAIL/BLOCKED. Do not mark complete from document presence alone.


## DT1–DT10

| Test | Case | Expected result |
| --- | --- | --- |
| DT1 | One-hot validity | A row with zero or two active class flags is quarantined, not forced into a class. |
| DT2 | Normal class absent | A normal-versus-faulty accuracy claim fails because no normal examples exist. |
| DT3 | Target isolation | Any of the seven fault indicator columns appearing as predictors fails. |
| DT4 | Rare class | Every test class has its count and recall reported; absent classes are explicitly undefined. |
| DT5 | Confidence boundary | At threshold 0.60, score 0.599 routes to review; 0.600 is eligible for automated routing in simulation. |
| DT6 | Root-cause restraint | A feature importance chart alone cannot establish the cause of a manufacturing fault. |
| DT7 | Source row accounting | One malformed fixture row is quarantined with source ID/reason; retained+excluded+quarantined equals input with no overlap. |
| DT8 | Missing versus zero | A 0/0 rate is unavailable with reason. Missing source evidence never becomes a measured zero or a fabricated result. |
| DT9 | BI reconciliation | K1–K5 match independent calculations on full cohort and one filtered slice. Counts exact; arithmetic unrounded or tolerance at most 0.01 displayed unit. |
| DT10 | Independent rerun | Distinct member reproduces cohort IDs, K1–K7 and policy selections from frozen bytes/configuration. Any stochastic tolerance is declared before running and discrepancies resolved. |

Use small synthetic fixtures for edge cases and frozen-source checks where relevant. Clearly distinguish fixture results from measured source outputs. Retain expected/actual evidence in docs/08-assurance-uat/; automate deterministic calculations where practical and document UI/interpretation reviews.

## Three project-specific UAT tasks

1. **Business review:** At weekly quality review, inspectors examine the top confusion pairs, compare confidence thresholds and choose an offline fault-routing prototype with a specialist-review queue and three process-investigation hypotheses. The participant must explain the observed baseline, population and decision limitation without assistance from the author; record actual completion and any defect.
2. **Policy challenge:** use the D7 artefact to compare a baseline and alternative case, then record accept/defer/override with evidence and accountable owner. The domain reviewer must independently reproduce the case outcome.
3. **Operational walkthrough:** Reviewer finds the largest confusion pair, shows its two class recalls and traces one low-confidence case into specialist review. Retain the task recording/screenshots, expected/actual values and reviewer outcome.

All three must pass after defect retest. Static exports may support review if interactive access is unavailable. The independent reviewer also checks every SC output against its declared artefact and source/configuration lineage.

## Release

All twelve ACs, ten DTs, UAT and independent rerun require evidence with zero unresolved critical/high defects. Underperformance can justify a baseline/manual policy; wrong labels/units, leakage, unregistered data or unsupported operational claims block acceptance. A scope revision updates affected requirements/tests; it cannot mark an unexecuted check passed.
