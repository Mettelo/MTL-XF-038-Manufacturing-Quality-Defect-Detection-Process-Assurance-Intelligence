# MTL-XF-038 — Business context and practical use case

## Organisation and accountable decision

Confidential Steel Manufacturer is the simulated sponsor. The Head of Manufacturing Quality owns the weekly defect classification and inspection review and must decide: **Choose a seven-class defect-routing prototype and a low-confidence specialist inspection queue.**

## The operational problem

The quality manager needs consistent routing of already detected steel-plate faults to the right inspection specialist. Misclassifying two similar fault types can delay investigation, while routing every example manually consumes specialist capacity. The dataset can compare seven-class routing and low-confidence referral; it cannot establish how many normal plates pass inspection or estimate a factory-wide defect rate.

## How the finished product will be used

At weekly quality review, inspectors examine the top confusion pairs, compare confidence thresholds and choose an offline fault-routing prototype with a specialist-review queue and three process-investigation hypotheses.

**Current approach:** Route known faults inconsistently without quantified class-specific errors or confidence coverage.

**Required future approach:** Use a seven-class routing matrix, measured confusion burden and a reviewed low-confidence referral rule.

The review starts with a verified frozen population and measured baseline. The domain analyst demonstrates the specified business outputs, the operational owner challenges workload and feasibility, assurance challenges correctness, and the sponsor records accept/defer/override. Each action records a source/configuration reference, rationale, accountable role, next step and review date. Uncertain cases remain in a visible manual-review/defer route.

## Stakeholder responsibilities

| Stakeholder | Responsibility | Decision evidence |
| --- | --- | --- |
| Head of Manufacturing Quality | Approve scope, project assumptions, acceptance contract and final recommendation. | SC1–SC5 outputs; baseline/alternative trade-offs; pilot/investigation actions. |
| Manufacturing Quality Analyst | Interpret seven fault classes and produce routing instructions, three process-investigation hypotheses and required factory validation evidence. | Domain scorecard, worked cases, supported interpretation and source lineage. |
| Operational service owner | Accept workload, assignment and escalation route. | Case register, capacity/threshold comparison, due dates and overrides. |
| Data Governance Analyst | Confirm source identity, rights, exact freeze and required fields. | S1 manifest and source→field→measure→deliverable matrix. |
| Quality Model Assurance Analyst | Approve evidence quality and independently challenge the release. | Executed SC/AC/DT checks, three UAT tasks and rerun. |

## Business questions tied to outputs

1. Can the sponsor use **Fault schema and class-mix audit** to support the stated decision, with this evidence: Ordered 27 predictors/seven labels, 1,941 source examples, one-hot validity, per-class counts and duplicate/conflicting-label register.
2. Can the sponsor use **Seven-class evaluation and error review** to support the stated decision, with this evidence: Majority baseline and interpretable candidate with macro F1, balanced accuracy, seven recalls, full confusion matrix and top-three confusion pairs.
3. Can the sponsor use **Confidence-based routing policy** to support the stated decision, with this evidence: Thresholds 0.50/0.60/0.70 with auto-route coverage/accuracy and specialist review workload; ten worked routing cases.
4. Can the sponsor use **Quality routing dashboard** to support the stated decision, with this evidence: Class mix, error pairs, confidence/workload comparison and source limitations.
5. Can the sponsor use **Inspection handover and three investigation cards** to support the stated decision, with this evidence: Fault-routing instructions, ten-case handover and three non-causal process hypotheses with measurements needed from a real factory.

## Concrete outputs and required success

| Deliverable | What the team must hand over | Required contents |
| --- | --- | --- |
| D5 | Fault schema and class-mix audit | Ordered 27 predictors/seven labels, 1,941 source examples, one-hot validity, per-class counts and duplicate/conflicting-label register. |
| D6 | Seven-class evaluation and error review | Majority baseline and interpretable candidate with macro F1, balanced accuracy, seven recalls, full confusion matrix and top-three confusion pairs. |
| D7 | Confidence-based routing policy | Thresholds 0.50/0.60/0.70 with auto-route coverage/accuracy and specialist review workload; ten worked routing cases. |
| D8 | Quality routing dashboard | Class mix, error pairs, confidence/workload comparison and source limitations. |
| D11 | Inspection handover and three investigation cards | Fault-routing instructions, ten-case handover and three non-causal process hypotheses with measurements needed from a real factory. |

| Success ID | Required deliverable | Specific pass condition |
| --- | --- | --- |
| SC1 | D5 — Fault schema and class-mix audit | Exactly one active class per valid row; malformed labels quarantined; all 34 source columns mapped; no invented normal class or production denominator. |
| SC2 | D6 — Seven-class evaluation and error review | Labels excluded from predictors; duplicate feature groups kept together; all class supports reported and undefined outcomes explicit; include ten reviewed errors. |
| SC3 | D7 — Confidence-based routing policy | At 0.60, score 0.599 refers and 0.600 is eligible; every case has predicted/actual class, confidence, routing owner and review reason; no production accept/reject claim. |
| SC4 | D8 — Quality routing dashboard | Reviewer finds the largest confusion pair, shows its two class recalls and traces one low-confidence case into specialist review. |
| SC5 | D11 — Inspection handover and three investigation cards | Each hypothesis names quality/process owner and required batch/time/normal-plate evidence; no asserted root cause, defect reduction or reject-rate improvement. |

## Benefit and adoption boundary

Assessment success means the required outputs are correct, reproducible and usable in the specified review. It does not mean a model must win, a customer must buy, a fault must disappear or a security incident must be prevented. The executive pack must name the measured baseline, alternative, operating trade-off, recommendation and evidence still required for a real pilot. Do not invent commercial savings or success percentages to make the business case appear complete.

At G1 record simulated sponsor approval of the requirements and criteria. At G3 record the policy recommendation and unresolved evidence gaps. At G4 record an actual team reviewer and simulated sponsor role separately; template text is not an approval.

## Source and scope limits

All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

**Failure to prevent:** A classifier trained only on defective examples cannot demonstrate detection sensitivity against normal production or factory reject reduction.

Missing mandatory support blocks dependent acceptance until an explicit source/scope decision updates the affected deliverables and tests.

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.
