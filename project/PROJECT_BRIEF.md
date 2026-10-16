# MTL-XF-038 — Project brief

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

**Client:** Confidential Steel Manufacturer · **Sponsor:** Head of Manufacturing Quality · **Team:** 3–5 · **Duration:** 8 weeks · **Cycle:** weekly defect classification and inspection review

## Problem and commission

The quality manager needs consistent routing of already detected steel-plate faults to the right inspection specialist. Misclassifying two similar fault types can delay investigation, while routing every example manually consumes specialist capacity. The dataset can compare seven-class routing and low-confidence referral; it cannot establish how many normal plates pass inspection or estimate a factory-wide defect rate.

> Choose a seven-class defect-routing prototype and a low-confidence specialist inspection queue.

## Practical use case and business outputs

At weekly quality review, inspectors examine the top confusion pairs, compare confidence thresholds and choose an offline fault-routing prototype with a specialist-review queue and three process-investigation hypotheses.

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Fault schema and class-mix audit | Ordered 27 predictors/seven labels, 1,941 source examples, one-hot validity, per-class counts and duplicate/conflicting-label register. |
| D6 | Seven-class evaluation and error review | Majority baseline and interpretable candidate with macro F1, balanced accuracy, seven recalls, full confusion matrix and top-three confusion pairs. |
| D7 | Confidence-based routing policy | Thresholds 0.50/0.60/0.70 with auto-route coverage/accuracy and specialist review workload; ten worked routing cases. |
| D8 | Quality routing dashboard | Class mix, error pairs, confidence/workload comparison and source limitations. |
| D11 | Inspection handover and three investigation cards | Fault-routing instructions, ten-case handover and three non-causal process hypotheses with measurements needed from a real factory. |

## Required success contract

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Fault schema and class-mix audit | Exactly one active class per valid row; malformed labels quarantined; all 34 source columns mapped; no invented normal class or production denominator. |
| SC2 | D6 — Seven-class evaluation and error review | Labels excluded from predictors; duplicate feature groups kept together; all class supports reported and undefined outcomes explicit; include ten reviewed errors. |
| SC3 | D7 — Confidence-based routing policy | At 0.60, score 0.599 refers and 0.600 is eligible; every case has predicted/actual class, confidence, routing owner and review reason; no production accept/reject claim. |
| SC4 | D8 — Quality routing dashboard | Reviewer finds the largest confusion pair, shows its two class recalls and traces one low-confidence case into specialist review. |
| SC5 | D11 — Inspection handover and three investigation cards | Each hypothesis names quality/process owner and required batch/time/normal-plate evidence; no asserted root cause, defect reduction or reject-rate improvement. |

[Detailed acceptance](ACCEPTANCE_CRITERIA.md) defines executed evidence; [deliverables](DELIVERABLES.md) defines exact artefacts and ownership. G1 records simulated sponsor approval, not invented real-client agreement.

## Core scope

All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

Required source: Faults.NNA and Faults27x7_var. Model grain: One labelled fault example; not an entire production batch or a population of all manufactured plates.

No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

Additional datasets, live integrations, operational deployment and claims of achieved benefits are outside core. Scope/source changes need approval and updated tests.

## Cross-functional roles

| Role | Required evidence |
| --- | --- |
| Business Analyst / Delivery Lead | Eight numbered prioritised requirements for Choose a seven-class defect-routing prototype and a low-confidence specialist inspection queue. As-is/to-be workflow, stakeholder map and requirement→D→AC→DT traceability. |
| Data Governance Analyst | S1 rights, byte manifest, field support, approved cohort and lineage for all seven KPIs; review A classifier trained only on defective examples cannot demonstrate detection sensitivity against normal production or factory reject reduction. |
| Data Engineer | Reproducible ingestion, curated model, source-row ledger and key/join controls at grain: One labelled fault example; not an entire production batch or a population of all manufactured plates. |
| Manufacturing Quality Analyst | Interpret seven fault classes and produce routing instructions, three process-investigation hypotheses and required factory validation evidence. |
| Data Scientist / Decision Modelling Analyst | Baseline/alternative implementation, evaluation manifest, uncertainty and sensitivity. Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors. |
| BI / Decision Product Developer | Four views for the weekly defect classification and inspection review: overview, diagnostics, action/policy comparison, quality/limitations. Five independent KPI reconciliations and static export. |
| Quality Model Assurance Analyst | Execute DT1–DT10, three UAT tasks and a distinct-member clean rerun; record expected/actual evidence, defects and retests. |

Assign named owners and review partners at kickoff. Combine roles only when a distinct member reviews critical calculations and performs final clean rerun. Sponsor labels describe simulated roles, separate from actual team identities.

## Evaluation contract

Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors.

Record predictor allowlist, target mapping, timing assumptions, partition/resample IDs and train-only transforms. Report partition/class counts and uncertainty. Negative model results can support a manual/baseline recommendation; invented performance cannot.

## Decision contract

Baseline majority-class classifier; alternative regularised multinomial/logistic or tree classifier with validation-selected tuning. Route low-confidence cases (max probability<0.60, simulation threshold) for specialist review and compare 0.50/0.70 alternatives; classify known faults only.

## Objectives and gates

Deliver D1–D12, K1–K7, AC1–AC12, ten executed domain tests, three UAT tasks, five reconciliations and an independent rerun. The sponsor must trace one action to source and explain why uncertain cases are deferred.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Manufacturing Quality, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Manufacturing Quality Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Manufacturing Quality reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Quality Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

[Deliverables](DELIVERABLES.md), [acceptance](ACCEPTANCE_CRITERIA.md), [data register](../data/SOURCE_REGISTER.md).

## Team organisation

The recommended team size is **3–5 people**. Delivery roles describe responsibilities, not separate positions: members can combine complementary business analysis, governance, engineering, analysis/modelling, BI and domain responsibilities. Assign a named owner to each deliverable and use a different team member to review critical calculations and perform the final clean rerun.
