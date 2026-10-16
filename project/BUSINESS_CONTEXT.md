# MTL-XF-038 — Business context

This is a simulated confidential-client engagement using public/open data. Stakeholders and commercial/security scenarios are fictional. Do not claim real-client employment, endorsement, operational deployment or realised benefits. This master pack specifies work to be completed; it does not claim the team has executed it.

## Organisation and problem

Confidential Steel Manufacturer is the fictional organisation. Quality inspectors need consistent fault routing and a clearer view of difficult-to-classify defect patterns. The dataset contains seven fault classes and no good plates, so it can support defect classification and specialist review routing but cannot measure production defect incidence or automatic accept/reject performance.

The Head of Manufacturing Quality needs a weekly defect classification and inspection review supporting **Choose a seven-class defect-routing prototype and a low-confidence specialist inspection queue.**

## Stakeholders

| Stakeholder | Decision | Required evidence |
| --- | --- | --- |
| Head of Manufacturing Quality | Approve scope, policy assumptions and next investigation/pilot. | D7 policy comparison, D11 recommendations, workload/risk and limitations. |
| Manufacturing Quality Analyst | Interpret observations and own action proposals. | K1–K7, source-supported dimensions, sensitivity and case lineage. |
| Data Governance Analyst | Approve source, freeze and interpretation rights. | S1 manifest, licence, actual schema and source-to-output support. |
| Operations / service owner | Accept workload and review/escalation responsibilities. | Action register, eligibility, owners, review dates and override reasons. |
| Quality Model Assurance Analyst | Challenge correctness and release readiness. | DT1–DT10, UAT, reconciliations and clean rerun. |

## Workflow to improve

Current simulated process: separate extracts/headline totals → informal prioritisation → manual review with limited lineage. This is a teaching scenario, not an observed real client process.

Proposed process: acquire approved bytes → validate/freeze → curate at declared grain → calculate K1–K7 → compare policies → inspect uncertainty/exclusions → sponsor approves investigation/pilot → record disposition and review date. No score bypasses human approval.

## Questions to answer

1. What is the baseline fault-class mix, and what defines its denominator?
2. Which supported groups/cases account for macro f1, and with what sample support?
3. Which cases change between the baseline and alternative, and why?
4. How do the specified transformation, threshold, cost or capacity alternatives alter the decision?
5. Which recommendations remain unsupported and what evidence must be collected next?

## Decision and action evidence

Baseline majority-class classifier; alternative regularised multinomial/logistic or tree classifier with validation-selected tuning. Route low-confidence cases (max probability<0.60, simulation threshold) for specialist review and compare 0.50/0.70 alternatives; classify known faults only.

Every action record contains case/group key, snapshot, observed measure, eligibility, baseline and alternative rank/policy, evidence link, uncertainty, proposed next step, accountable owner, due/review date, disposition and override rationale. Use source-row IDs; do not invent real customer identities.

## Value and limits

Delivery success is evidence-backed acceptance of D1–D12, not guaranteed model superiority. Benefits remain hypotheses until an approved pilot specifies population, comparator, outcome window and guardrails. D11 includes three next actions and a case where the evidence does not justify action.

No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

**Risk to prevent:** A classifier trained only on defective examples cannot demonstrate detection sensitivity against normal production or factory reject reduction.

**Source boundary:** All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

Missing mandatory support blocks G1 or a dependent output until a governed scope/source decision is recorded.
