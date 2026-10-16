# MTL-XF-038 — Manufacturing Quality Defect Detection Process Assurance Intelligence

**Track:** Cross-Functional · **Sector:** Private-sector commercial operations · **Team:** 3–5 · **Duration:** 8 weeks

## The business problem

The quality manager needs consistent routing of already detected steel-plate faults to the right inspection specialist. Misclassifying two similar fault types can delay investigation, while routing every example manually consumes specialist capacity. The dataset can compare seven-class routing and low-confidence referral; it cannot establish how many normal plates pass inspection or estimate a factory-wide defect rate.

**Simulated organisation:** Confidential Steel Manufacturer. **Accountable decision owner:** Head of Manufacturing Quality.

## Practical use case

At weekly quality review, inspectors examine the top confusion pairs, compare confidence thresholds and choose an offline fault-routing prototype with a specialist-review queue and three process-investigation hypotheses.

**Decision the project must enable:** Choose a seven-class defect-routing prototype and a low-confidence specialist inspection queue.

**Current approach:** Route known faults inconsistently without quantified class-specific errors or confidence coverage.

**Required future approach:** Use a seven-class routing matrix, measured confusion burden and a reviewed low-confidence referral rule.

## Specific deliverables

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Fault schema and class-mix audit | Ordered 27 predictors/seven labels, 1,941 source examples, one-hot validity, per-class counts and duplicate/conflicting-label register. |
| D6 | Seven-class evaluation and error review | Majority baseline and interpretable candidate with macro F1, balanced accuracy, seven recalls, full confusion matrix and top-three confusion pairs. |
| D7 | Confidence-based routing policy | Thresholds 0.50/0.60/0.70 with auto-route coverage/accuracy and specialist review workload; ten worked routing cases. |
| D8 | Quality routing dashboard | Class mix, error pairs, confidence/workload comparison and source limitations. |
| D11 | Inspection handover and three investigation cards | Fault-routing instructions, ten-case handover and three non-causal process hypotheses with measurements needed from a real factory. |

These five business outputs sit inside the full D1–D12 engagement. The team also delivers requirements/process mapping, source governance, engineering and quality evidence, independent UAT, handover and contribution records. [Detailed deliverable specifications](project/DELIVERABLES.md) define owners, artefact paths, fields, calculations and review evidence.

## Required success criteria

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Fault schema and class-mix audit | Exactly one active class per valid row; malformed labels quarantined; all 34 source columns mapped; no invented normal class or production denominator. |
| SC2 | D6 — Seven-class evaluation and error review | Labels excluded from predictors; duplicate feature groups kept together; all class supports reported and undefined outcomes explicit; include ten reviewed errors. |
| SC3 | D7 — Confidence-based routing policy | At 0.60, score 0.599 refers and 0.600 is eligible; every case has predicted/actual class, confidence, routing owner and review reason; no production accept/reject claim. |
| SC4 | D8 — Quality routing dashboard | Reviewer finds the largest confusion pair, shows its two class recalls and traces one low-confidence case into specialist review. |
| SC5 | D11 — Inspection handover and three investigation cards | Each hypothesis names quality/process owner and required batch/time/normal-plate evidence; no asserted root cause, defect reduction or reject-rate improvement. |

These are assessment requirements, not claims that results have already been achieved. At G1 the team records simulated stakeholder approval of scope, policy assumptions and criteria; later changes require a decision log. Financial benefit, causal uplift, production safety and operational adoption need separate pilot evidence. [Acceptance and worked tests](project/ACCEPTANCE_CRITERIA.md) control pass/fail.

## Data and fixed analytical boundary

**Official source:** [Steel Plates Faults](https://archive.ics.uci.edu/dataset/198). **Required input:** Faults.NNA and Faults27x7_var. **Expected source population:** 1,941 faulty-plate examples.

All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

**Download:** https://archive.ics.uci.edu/static/public/198/steel+plates+faults.zip

No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

The [source register](data/SOURCE_REGISTER.md) records checked hashes, exact acquisition and snapshot rules. No raw data are uploaded; teams retain immutable originals outside Git with a manifest and reviewer access.

## Analysis and decision rules

Stratified 60/20/20 seed 38; keep identical 27-feature groups in one partition and quarantine conflicting labels for review. Validate exactly one of seven class indicators. Train-only scaling/feature selection; remove seven target columns from predictors.

Baseline majority-class classifier; alternative regularised multinomial/logistic or tree classifier with validation-selected tuning. Route low-confidence cases (max probability<0.60, simulation threshold) for specialist review and compare 0.50/0.70 alternatives; classify known faults only.

Report measured baselines and alternatives, sample sizes, uncertainty and failure cases. A weaker model does not justify disguising results: the final recommendation must say whether to retain the baseline, improve the prototype or run a controlled pilot, and cite the evidence.

## Who does what

- Business Analyst / Delivery Lead: eight testable user requirements, process map and decision-to-evidence traceability.
- Data Governance Analyst: source rights, frozen cohort, field support and seven-KPI lineage.
- Data Engineer: reproducible model/pipeline, exact row accounting and key/join checks.
- Manufacturing Quality Analyst: Interpret seven fault classes and produce routing instructions, three process-investigation hypotheses and required factory validation evidence.
- Data Scientist / Decision Modelling Analyst: baseline/alternative, feature timing, validation and sensitivity.
- BI / Decision Product Developer: the specified decision views, filter reconciliation and static export.
- Quality Model Assurance Analyst: independent checks, three stakeholder walkthroughs and clean rerun.

Assign named authors and distinct reviewers; combining roles cannot remove independent review.

## Delivery and review

| Gate | Due | Evidence and accountable reviewers |
| --- | --- | --- |
| G1 scope/source | Week 2 | Head of Manufacturing Quality, BA and Governance approve eight requirements, S1 rights/manifest, actual fields and frozen cohort. Unsupported mandatory outputs block dependent work. |
| G2 engineering/metrics | Week 4 | Engineer, Manufacturing Quality Analyst and distinct reviewer approve row accounting, keys/joins, K1–K7, five reconciliations and evaluation manifest. |
| G3 policy | Week 6 | Head of Manufacturing Quality reviews baseline/alternative, sensitivity, workload, assumptions and one insufficient-evidence/manual-review case. |
| G4 release | Week 8 | Simulated Mettelo panel and Quality Model Assurance Analyst accept D1–D12, AC1–AC12, ten executed tests, three UAT tasks and clean rerun with zero critical/high defects. |

## Full master pack

[Project brief](project/PROJECT_BRIEF.md) · [Business context](project/BUSINESS_CONTEXT.md) · [Deliverables](project/DELIVERABLES.md) · [Success criteria and tests](project/ACCEPTANCE_CRITERIA.md) · [Governance](project/GOVERNANCE.md) · [Data guidance](data/README.md) · [Submission](submission/README.md).

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
