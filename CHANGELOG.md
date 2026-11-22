# KeepOkey Fall Alert Index — November 2026: Changelog

## Version 2.0.2 — 2026-11-21

2.0.1 — November 21, 2026: KeepOkey row updated to current product facts (10-second cancel window; fall detection included, no monthly fee). 1,121 records.

Publisher: KeepOkey · License: CC BY 4.0 · Version 2.0.2 DOI: https://doi.org/10.5281/zenodo.24417882

The comparison below is calculated from the long-form records of Versions 1 and 2 and the Version 2 wide-format table. Record counts exclude header rows. A record is a source-supported claim, not a unique product, provider or tested result.

### Coverage and record counts

| Measure | Version 1 | Version 2 |
|---|---:|---:|
| Long-form claim records | 203 | 1,121 |
| Distinct provider labels | 24 | 31 |
| Distinct measurement fields | 15 | 22 |
| Long-form columns | 12 | 14 |

The long-form record count increased by 918. The Version 2 wide comparison has 31 rows and 25 columns, comprising 27 device or service providers and 4 cellular carriers. The Version 1 provider-label count includes a benchmark entry; it should not be read as a count of device suppliers.

### Provider-list changes

Nine provider labels were added:

- ADT Health
- Aloe Care Health
- Garmin
- GetSafe
- Google
- LifeFone
- LifeStation
- Lively
- Rescue Alert

Two provider labels present in Version 1 are absent from Version 2:

- NCOA (benchmark, via KeepOkey cost guide)
- PulseMax (fitvii.com / more-pro.com)

Twenty-two provider labels are retained across both versions. These are literal label comparisons; they do not imply a market entry, closure or change in product availability. AlertLink, QMedic and One Call Alert were considered but excluded because no official page was found; they are not removals from the Version 1 provider list.

### Measurement-field changes

Version 1 contains 15 distinct fields and Version 2 contains 22. This is a net increase of 7, resulting from 8 additions and 1 removal, rather than the addition of only 7 fields.

Added fields:

- `trial_period`
- `shower_use_claim`
- `sim_provider`
- `family_contacts_count`
- `family_call_order`
- `no_answer_behavior`
- `fall_detection_accuracy_claim`
- `false_alarm_cancel_seconds`

Removed field: `total_3yr`. Version 2 preserves published prices and conditions rather than carrying forward this calculated total-cost field. Fourteen field identifiers are retained across both versions.

### Source policy and evidence structure

Version 1 includes material from sellers and review sites, including statements about other providers on a provider's comparison page. Version 2 gives priority to each provider's own product pages, terms, FAQs and manuals. Third-party material remains explicitly classified in the long format and is used in the wide comparison only where no official record exists for the same provider and field. A fallback cell is marked `[third-party source]`.

Version 2 contains 963 official-page, terms, FAQ or manual records, 141 third-party records and 17 KeepOkey product-fact records. The long format retains third-party evidence even when official evidence is selected for the corresponding wide-format cell. KeepOkey entries use its current product facts; they are not independent tests.

The long-form schema adds `durum`, `source_file`, `source_line` and `source_quote`, and removes `page_ref` and `claim_ref`. Every Version 2 record carries a documented-claim status, source URL, saved-text reference, line number and supporting quote. No record represents an observed or tested result. Capture dates in Version 2 are `2026-11-20` and `2026-11-21`.

### Review and validation

The second independent semantic review removed 34 records and corrected 12. After those semantic changes, the November 20 validation report records 1,148 input records, 0 rejected records and 75 notices. The corrected release has 1,121 accepted records after adding two KeepOkey records on November 21. The notices comprise 34 semantic removals, 12 corrections and 29 duplicates omitted from the release. These processing counts are not a measured error rate.

Missing comparison values are represented as `not stated`, not `no`. Multiple products, plans and conditions are preserved with ` / ` in the wide format. Differences between releases reflect revised coverage and source treatment as well as source content; record growth alone is not a change in provider performance or market conditions.

### Citation and identifiers

The Version 2 title is **KeepOkey Fall Alert Index — November 2026** (Version 2.0.2). The dataset page is [KeepOkey Fall Alert Index](https://keepokey.com/pages/fall-alert-index). The supplied concept DOI for the existing record is [10.5281/zenodo.24260237](https://doi.org/10.5281/zenodo.24260237); the Version 2.0.2 DOI is [10.5281/zenodo.24417882](https://doi.org/10.5281/zenodo.24417882).
