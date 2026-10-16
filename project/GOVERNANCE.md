# MTL-XF-038 — Governance

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Accountability and gates

Head of Manufacturing Quality owns business scope, assumptions and action approval. Governance owns source/rights/freeze; Engineer owns transformations; Manufacturing Quality Analyst owns interpretation; Quality Model Assurance Analyst independently reviews. The simulated Mettelo panel owns programme acceptance. Record actual team members separately from simulated stakeholder roles.

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Manufacturing Quality, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Manufacturing Quality Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Manufacturing Quality reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Quality Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Domain controls

No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

**Primary risk:** A classifier trained only on defective examples cannot demonstrate detection sensitivity against normal production or factory reject reduction.

Baseline majority-class classifier; alternative regularised multinomial/logistic or tree classifier with validation-selected tuning. Route low-confidence cases (max probability<0.60, simulation threshold) for specialist review and compare 0.50/0.70 alternatives; classify known faults only.

All capacity, threshold, financial and review/remediation targets are project assumptions unless explicitly attributed. Human deferrals/overrides record reason, evidence, owner and next review. No production action is authorised by this pack.

## Source and evaluation control

All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

Follow [S1 register](../data/SOURCE_REGISTER.md); preserve original bytes outside Git, immutable snapshot, manifest and reviewer access. Checksum mismatch stops processing until investigated. Never silently replace a variant/feed. No raw data uploaded by this update.

Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors.

Lock target mapping, predictors, timing and policy configuration before test evaluation. Descriptive projects retain resample/sensitivity evidence. Record unsupported metrics and negative findings.

## Change and exception control

Record change ID, requester/date/reason, original/revised source/cohort/requirement, rights/field evidence, affected K/D/AC/DT, time/risk impact, owner, reviewer and decision. New inputs get new freeze IDs and affected checks rerun. Missing mandatory support blocks dependent work.

Each operational exception needs case, rationale, evidence, accountable owner, approval, compensating/manual control, expiry and next review; expired exceptions return to review.

Use only approved public data and fictional operational assumptions. Avoid unnecessary customer identifiers and unsupported protected-characteristic inference.

## Publication and release

Keep attribution, snapshot and limitations in every portfolio/dashboard/slide export. No secrets or private correspondence. Release after all AC/DT/UAT and rerun evidence passes with zero critical/high defects. Record final commit/tag and rollback to approved snapshot/configuration.

## Business acceptance and approval record

The specific use case is: At weekly quality review, inspectors examine the top confusion pairs, compare confidence thresholds and choose an offline fault-routing prototype with a specialist-review queue and three process-investigation hypotheses.

SC1–SC5 in [acceptance](ACCEPTANCE_CRITERIA.md) govern the five concrete business outputs. G1 records criterion, version, actual team approver, simulated sponsor role, date and assumptions. G3 records measured baseline/alternative, decision and trade-off. G4 records executed pass evidence for each SC; a document's existence is insufficient. Never describe simulated sign-off or unmeasured benefits as real-client agreement or adoption.
