# MTL-XF-038 — Source register

## S1 — Steel Plates Faults

| Field | Approved definition |
| --- | --- |
| Provider | UCI Machine Learning Repository; preserve original creator attribution |
| Documentation | https://archive.ics.uci.edu/dataset/198 |
| Exact download | https://archive.ics.uci.edu/static/public/198/steel+plates+faults.zip |
| Required inputs | Faults.NNA and Faults27x7_var |
| Source population | 1,941 faulty-plate examples |
| Decision owner | Head of Manufacturing Quality |
| Status | Official archive/feed retrieved and inspected; team freeze/sign-off and analysis remain to be completed. No raw data uploaded. |

Persistent citation: https://doi.org/10.24432/C5J88N

## Checked byte reference

Official archive retrieved and inspected on **2026-10-16**. Archive size **100890 bytes**; SHA-256 **cb8eb9859198b63f053e443513036b401746fa517ef58bd17c846c6741c93919**.

| Archive member | Bytes | SHA-256 |
| --- | --- | --- |
| Faults.NNA | 299482 | 08994f5b0185a8e6cc22afe9910fd36834990fb1ca30852ed79012a832fbff55 |
| Faults27x7_var | 497 | 887dbfa140b48877b706865ef277550dc0203699243c600e24bfe8b090a9a953 |

Member names and byte hashes were inspected; CSV record counts were checked where present. Actual cohort transformations and business analysis remain team delivery work.

Faults.NNA has no header. Apply all 34 ordered names from Faults27x7_var; first 27 are predictors and last seven fault indicators.

## Cohort and field support

All 1,941 rows of Faults.NNA using the ordered 27-feature and seven-label names in Faults27x7_var. Preserve publisher spelling in raw schema; map display names separately.

**Grain:** One labelled fault example; not an entire production batch or a population of all manufactured plates.

**Required mapping:** 27 numeric process/geometry/steel predictors followed by seven fault indicator columns; verify exact order from Faults27x7_var.

**Interpretation limits:** No normal class, production denominator, batch/time key, defect cost or confirmed root cause. Do not call class mix a production defect rate or feature associations a causal process diagnosis.

## Rights and attribution

Publisher page declares [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Cite original creators, UCI and [dataset DOI](https://doi.org/10.24432/C5J88N); preserve notices and state transformations.

## Team acquisition record required at G1

Record source/freeze ID, requested/resolved URL, retrieval UTC, release/feed timestamp, archive/member filename, actual bytes/checksum, encoding/delimiter/worksheet/schema, row count, date bounds, included/excluded scope, licence/citation evidence, storage/access and retention owner, verification checks, analyst and reviewer approval/date. Unknown or unexecuted fields remain explicitly pending.

## Raw-data durability

Preserve original archive, required members and documentation in a read-only S1-v1 snapshot in approved durable storage outside Git with a second recoverable copy. Record reviewer access and restore instructions without credentials. Provider/DOI URLs locate the source; retained checksum-addressed bytes define reproducibility. Stable URLs do not guarantee immutable contents or perpetual availability.

No raw data are committed by this master update. Restore verified retained bytes if the provider becomes unavailable. If no approved copy exists, block G1; do not substitute an unofficial mirror, another variant or guessed schema. A new official version requires rights/schema/scope review, new freeze ID and rerun of affected tests.

## Refresh and supplementary inputs

Do not stack overlapping UCI samples/variants. Required publisher codebooks remain source references. Business costs, capacities and pilot outcomes absent from S1 are synthetic assumptions, not measured facts.

Every added reference/supplement needs ID, official source/version/URL, rights, grain/coverage, purpose, join key/cardinality, effect on K/D/AC/DT and reviewer approval. Optional extensions cannot replace core requirements silently.
