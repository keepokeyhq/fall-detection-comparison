# KeepOkey Fall Alert Index — November 2026

Published by KeepOkey, which offers a 4G fall detection watch that calls family. This repository holds Version 2.0.2 of a comparison of published fall detection watch and medical alert terms in the United States: who is called after a fall, and what each service says it costs.

Version 2.0.2 · Capture dates 2026-11-20 to 2026-11-21 · Publisher: KeepOkey

## What this dataset answers
Who a US fall detection watch or medical alert service calls after a fall (monitoring center, family or 911), how many family contacts it takes and in what order, what happens when nobody answers, and the published device price, monthly fee, contract, trial, return and battery terms.

## How it was compiled
Every value is a documented claim from a provider's own published page, terms, FAQ or manual; third-party records are labelled. Each record carries a source URL, a saved-text reference, a line number and the verbatim supporting quote. Capture dates: 2026-11-20 to 2026-11-21. No record is a product test or an observed result.

## Files
- `data/keepokey-fall-alert-index-2026-11-wide.csv`: 31 rows: 27 device or service providers and 4 cellular carriers, one row per provider. `not stated` means no accepted record, not "no".
- `data/keepokey-fall-alert-index-2026-11-long.csv`: 1,121 records, one provider–product–field claim each, with `source_url`, `source_quote` and `captured_on`.
- `METHOD.md`, `DATA-DICTIONARY.md`, `CHANGELOG.md` (Version 1 to 2), `CITATION.cff`, `LICENSE.md`

## Limits
Prices and terms change; use the capture date. A missing value means no accepted source record. Record counts are not a count of products. The KeepOkey rows describe its current product facts and are not independent tests.

## How to cite
KeepOkey. (2026). KeepOkey Fall Alert Index — November 2026 (Version 2.0.2) [Data set]. https://doi.org/10.5281/zenodo.24417882

Dataset page: https://keepokey.com/pages/fall-alert-index?utm_source=github&utm_medium=dataset&utm_campaign=dagitim-2026-11
Concept DOI (all versions): https://doi.org/10.5281/zenodo.24260237
License: CC BY 4.0

## Earlier version
Version 1.0.0 stays available at https://doi.org/10.5281/zenodo.24260238 (tag `v1.0.0`). This release is tagged `v2.0.2`.
