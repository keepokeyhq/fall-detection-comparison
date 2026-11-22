KeepOkey offers a 4G fall detection watch that calls family. This dataset uses only providers' own published pages; the data file and method are linked below.

# KeepOkey Fall Alert Index — November 2026

Version 2.0.2 · Publisher: KeepOkey · Capture dates: 2026-11-20 to 2026-11-21 · License: CC BY 4.0

Data downloads and method: [KeepOkey Fall Alert Index](https://keepokey.com/pages/fall-alert-index).

Official sources take priority. The long-form release also retains 141 explicitly labelled third-party records; the wide-format comparison uses them only when no official record is available for the same provider and field. These exceptions qualify the opening disclosure.

## What the dataset records

The index records published claims about prices, contractual terms, device specifications and alert handling. It contains 1,121 long-form records across 22 fields and 31 provider entries: 27 device or service providers and 4 cellular carriers. Each long-form record represents one provider–product–field claim from a source. Multiple records may describe the same field under different plans, products, conditions or sources.

Every populated comparison value is traceable to a source quote and a source-text line. All records are documented claims, not observations or product tests. The index does not measure fall-detection performance, response reliability, clinical outcomes or carrier compatibility. It does not assign scores or rank providers. A published limitation or absence of automatic fall detection is retained with its context.

## Scope and selection

Device and service providers were included when an official product or support page was found in the source collection. Cellular carriers are included separately as context for connectivity and plan charges; their entries are not fall-detection devices. The collection is a defined comparison set, not a census of the market.

- AlertLink — excluded: no official page found.
- QMedic — excluded: no official page found.
- One Call Alert — excluded: no official page found.

The Lively terms page, ADT FAQ and Rescue Alert myActive page could not be opened and were not used as evidence. Other available pages for those providers remain eligible. Missing or inaccessible evidence does not establish that a feature or term is absent.

## Sources and collection

Primary source types are official product pages, terms, FAQs and manuals. Only a provider's statements about its own products are treated as official evidence; statements about competitors on a provider's comparison page are not official evidence for those competitors. Third-party review or seller material is separately labelled and is a fallback for a provider–field combination without official evidence in the collection.

Pages were collected on 2026-11-20; KeepOkey product facts were updated on 2026-11-21. Collection was by plain HTTP request with a non-browser user agent honoring robots.txt; pages blocked to plain requests were saved manually from a regular browser session. Pages that remained unavailable were omitted. Source text includes visible page text and, where present, structured page data; claims taken from JSON-LD are identified in the condition note.

The long-form release retains all accepted source categories, including third-party records that are not selected for the wide comparison. Of its 1,121 records, 963 are from official product pages, terms, FAQs or manuals; 141 are third-party records; and 17 are KeepOkey product-fact records. A capture date records when the source was collected or incorporated, not when a price or claim first took effect.

## Extraction and checks

Extraction was model-assisted. Each accepted long-form record carries a source URL, source-text reference, line number and verbatim quote. Non-coded values preserve source wording; categorical values use the documented code lists. Product, plan, promotion, billing and study-related qualifiers are retained in the condition note rather than inferred or reconciled.

An automated verbatim check compared quotes with the saved source text and checked that non-coded values occur within their quotes. The check normalizes whitespace, case, quotation marks and dash variants; it is not a byte-for-byte comparison. A match within two lines of the recorded line is flagged rather than silently treated as an exact line match. Code validation checks permitted values; semantic support requires review.

A second, independent semantic review removed 34 records and corrected 12 records. The November 20 validation report lists 1,148 records entering validation and 0 rejected records after those semantic changes. The corrected release has 1,121 accepted records, including two KeepOkey records added on November 21. Its 75 notices comprise the 34 removals, 12 corrections and 29 duplicate records omitted from the release. These are processing counts, not an estimated accuracy rate, and do not establish that the remaining records are error-free.

## Building the wide comparison

The wide format has one row per provider. For each provider and field, accepted official records are selected if available; otherwise accepted third-party records are selected and the cell ends with `[third-party source]`. KeepOkey product facts are treated as the company's own claims. Third-party records remain identifiable in the long format even when an official record takes precedence in the wide format.

Distinct retained values are joined with ` / `. Conditions appear in parentheses and product names in square brackets. This preserves plan and product differences; it does not choose a single offer or reconcile conflicting statements. The provider-level source list includes all retained source URLs, including those not selected for a particular wide-format cell. Use the long format to identify the evidence for an individual claim.

`not stated` means no accepted record for that provider and field in this collection. It does not mean `no`, zero cost, no feature, no contract or a verified absence. Unknown fields have no placeholder record in the long format.

## KeepOkey disclosure

KeepOkey publishes this index and offers a fall detection watch. Its 17 records are limited to the company's product facts associated with its published product page; they are not independent evidence. KeepOkey values use the current product facts published on its product page. These records are documentary claims, not independent product tests.

## Limits and reuse

Prices may change after capture. Promotional prices, billing schedules, equipment charges and plan differences must be read with their conditions; values joined with ` / ` are not interchangeable prices for one offer. Monetary and duration values preserve published wording rather than being converted into a common total cost. Manual SOS calling, automatic fall detection and notifications must also be distinguished using the product and condition notes.

Published specifications and provider claims have not been independently tested for this dataset. An accuracy claim or a cited study is recorded as a statement on the source page, not validated as a result. Source availability and field coverage vary across providers. Changes from the previous release reflect changes in coverage and method as well as source content; they do not by themselves establish market trends.

The compilation is offered under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Quoted source material remains attributable to its respective rights holders; this license does not relicense third-party source pages.

## How to cite

> KeepOkey. (2026). KeepOkey Fall Alert Index — November 2026 (Version 2.0.2) [Data set]. https://doi.org/10.5281/zenodo.24417882
>
> Free to use with attribution (CC BY 4.0).

Concept DOI supplied for the existing record: [10.5281/zenodo.24260237](https://doi.org/10.5281/zenodo.24260237). Version 2.0.2 DOI: [10.5281/zenodo.24417882](https://doi.org/10.5281/zenodo.24417882).
