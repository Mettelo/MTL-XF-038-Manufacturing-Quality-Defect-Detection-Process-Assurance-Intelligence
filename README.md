# MTL-XF-038 — Manufacturing Quality Defect Detection Process Assurance Intelligence

**Track:** Cross-Functional · **Use case:** Commercial / private sector · **Team:** 6–8 · **Duration:** 8 weeks

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Business commission

**Client:** Confidential Steel Manufacturer. **Decision owner:** Head of Manufacturing Quality. **Cadence:** weekly defect classification and inspection review.

Quality inspectors need consistent fault routing and a clearer view of difficult-to-classify defect patterns. The dataset contains seven fault classes and no good plates, so it can support defect classification and specialist review routing but cannot measure production defect incidence or automatic accept/reject performance.

**Decision:** Choose a seven-class defect-routing prototype and a low-confidence specialist inspection queue.

## End-to-end delivery

Deliver business requirements, governed source acquisition, engineering and data quality, seven defined metrics, baseline/alternative policy comparison, decision dashboard, assurance/UAT, executive recommendation and operational handover. A model alone is insufficient.

Baseline majority-class classifier; alternative regularised multinomial/logistic or tree classifier with validation-selected tuning. Route low-confidence cases (max probability<0.60, simulation threshold) for specialist review and compare 0.50/0.70 alternatives; classify known faults only.

## Core dataset and frozen cohort

**S1:** [Steel Plates Faults](https://archive.ics.uci.edu/dataset/198). **Input:** Faults.NNA and Faults27x7_var. **Source population:** 1,941 faulty-plate examples.

All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

Exact official download:

https://archive.ics.uci.edu/static/public/198/steel+plates+faults.zip

No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

No raw data are uploaded by this update. Teams preserve original bytes outside Git in an approved durable snapshot, with checksums, source metadata and reviewer access. The source register records verification evidence and acquisition rules.

## Pack navigation

- [Project brief](project/PROJECT_BRIEF.md) — scope, roles and milestones.
- [Business context](project/BUSINESS_CONTEXT.md) — stakeholders and decisions.
- [Deliverables](project/DELIVERABLES.md) — D1–D12 and K1–K7.
- [Acceptance criteria](project/ACCEPTANCE_CRITERIA.md) — AC1–AC12 and DT1–DT10.
- [Governance](project/GOVERNANCE.md) — gates, assumptions and changes.
- [Data guidance](data/README.md) and [source register](data/SOURCE_REGISTER.md).
- [Submission pack](submission/README.md) — team repository and final evidence.

## Evaluation and policy boundary

Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors.

**Primary risk:** A classifier trained only on defective examples cannot demonstrate detection sensitivity against normal production or factory reject reduction.

At G1 (week 2), approve requirements, source rights, actual schema and frozen bytes. At G2 (week 4), approve row accounting, all seven metrics and evaluation design. At G3 (week 6), review baseline/alternative and uncertainty. At G4 (week 8), require all twelve deliverables, ten executed domain tests, three UAT tasks, five reconciliations and a distinct-member clean rerun.

Assign named authors and review partners. Unsupported mandatory outputs remain blocked until an approved source/scope change resolves them. Record actual results in a separate Mettelo team repository; this master defines the work.
