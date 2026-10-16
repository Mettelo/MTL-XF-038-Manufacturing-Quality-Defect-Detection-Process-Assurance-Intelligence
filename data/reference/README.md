# MTL-XF-038 — References and mappings

Retain source documentation, licence/citation notices and required codebooks for Steel Plates Faults. Faults.NNA has no header. Apply all 34 ordered names from Faults27x7_var; first 27 are predictors and last seven fault indicators.

Version each reference with ID, official URL, retrieval date/version, content checksum, rights, raw→display mapping, rationale, owner and reviewer. Unknown categories remain visible; validate mapping completeness/uniqueness and all many-to-many joins.

**Interpretation rule:** No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

**Project policy assumptions:** Baseline majority-class classifier; alternative regularised multinomial/logistic or tree classifier with validation-selected tuning. Route low-confidence cases (max probability<0.60, simulation threshold) for specialist review and compare 0.50/0.70 alternatives; classify known faults only.

Keep choices separate from publisher facts. Register categorical/segment/class labels, unit conversions and any financial or capacity assumptions. Do not invent operational history absent from S1.

A reference explains the source; it cannot supply an unmeasured outcome. Register supplements and scope changes in [SOURCE_REGISTER.md](../SOURCE_REGISTER.md) before dependent work.
