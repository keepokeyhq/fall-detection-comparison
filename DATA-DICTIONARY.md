# KeepOkey Fall Alert Index — November 2026: Data Dictionary

Version 2.0 · Publisher: KeepOkey · Capture date: 2026-11-20 · License: CC BY 4.0

## Structure and missing information

Both formats are UTF-8, comma-delimited tables with a header row. Quoted CSV cells may contain commas or quotation marks; read them with a CSV parser. Long-form values are text, including monetary amounts, durations and categorical codes. A record is a documented source claim, not a test result.

The long format contains 1,121 records and 14 columns. A record identifies one provider, product, field and source-supported value. There can be several records for the same provider and field. It is not a complete provider-by-field grid.

The wide format contains 31 provider rows and 25 columns: 2 provider identifiers, the 22 measurement fields below, and a source list. It combines products and plans at provider level; use the long format for individual conditions and citations.

`not stated` is the wide-format missing-information marker: no accepted record for the provider and field in this collection. It is not a negative answer or a zero. The long format omits unrecorded fields rather than generating missing-value rows. A blank `unit` or `condition_note` means that metadata is unspecified, not that the claim itself is missing.

`[third-party source]` marks a wide-format cell supported only by third-party records because no official record was available for that provider and field. In the long format, third-party records are identified by `source_kind`. They remain in that format even when an official record is selected for the wide comparison.

## Long-form columns

Legacy machine-readable column names and code tokens are preserved exactly; their English meanings are given below.

| Column | Definition | Value format |
|---|---|---|
| `row_id` | Record identifier within this release; not an evidence-quality label or a cross-version matching key. | Non-empty text; treat as opaque. |
| `provider` | Name of the company or organization whose product, service or carrier plan is described. | Non-empty text. |
| `product` | Product or service named by the source. | Text; `(all)` indicates provider-wide or general material. |
| `field` | Attribute being documented. | Exactly one of the 22 field identifiers below. |
| `value` | Published wording or a categorical code supported by the source quote. | Non-empty text; code lists below apply to categorical fields. Other values are source-quote substrings under the check's text normalization. |
| `unit` | Unit annotation when supplied; it does not turn a text value into a numeric variable. | `USD`, `days`, `months`, `hours`, `seconds`, `people`, or blank. |
| `condition_note` | Scope or qualification, such as product plan, promotion, billing frequency, intended behavior or test status. | English text or blank. `jsonld` identifies structured page data. Accuracy claims use `study cited: yes` or `study cited: no` to indicate whether the page cites a study or test source. |
| `source_kind` | Source category, not an independent quality assessment. | One of the source-category codes below. |
| `durum` | Evidence status: documented claim. | Constant legacy code `belge`; every record has this status. It does not mean observed or tested. |
| `source_url` | Public address associated with the cited source or product facts. | Absolute HTTP or HTTPS URL. |
| `source_file` | Reference to the saved source text used for the audit. | Text reference; not a public download URL. |
| `source_line` | Position of the quote in the saved source text, including any saved headers. | Positive integer encoded as text; line numbering starts at 1. It is not a browser or PDF page number. The automated check permits a flagged match within two neighboring lines. |
| `source_quote` | Continuous source excerpt supporting the value or code. | Non-empty text; checked against saved text with whitespace, case, quotation-mark and dash normalization. |
| `captured_on` | Source capture or incorporation date assigned to the record. | ISO date `YYYY-MM-DD`; all records in this release use `2026-11-20`. |

## Source-category codes

| `source_kind` code | English meaning | Records in this release |
|---|---|---:|
| `resmi_sayfa` | Official product or provider page; only statements about the provider's own products count as official evidence. | 577 |
| `sartlar` | Official terms, policies or contractual material. | 192 |
| `sss` | Official FAQ. | 142 |
| `kilavuz` | Official manual or support guide. | 52 |
| `ucuncu_taraf` | Third-party seller, review or other external source; not the provider's own claim. | 141 |
| `gercekler` | KeepOkey's own product facts associated with its published product page; documented company claims. | 15 |

## Measurement fields

Unless a code list is specified, `value` is published text rather than a standardized number. Units shown here describe the subject; the actual `unit` annotation may be blank. “No fee” or “included” wording is retained when explicitly stated. None of these fields implies independent verification.

| `field` | Definition | Value format and interpretation |
|---|---|---|
| `device_price` | Published equipment or hardware charge. | Price or charge text, including explicitly free equipment; monetary values may carry `USD`. Preserve product and offer conditions. |
| `monthly_fee` | Published recurring service or monitoring fee. | Price or fee text, including an explicit no-fee statement; may carry `USD`. Read billing and carrier-plan qualifications. |
| `fall_detection_addon_monthly` | Published additional monthly charge for fall detection, or a statement that it is included. | Price or inclusion text; may carry `USD`. It is separate from the base service fee. |
| `activation_fee` | Published activation or setup charge. | Price or explicit fee-waiver text; may carry `USD`. A statement that activation is unnecessary is not itself a fee amount. |
| `contract_required` | Whether the source explicitly states that a contract is required. | Code: `yes` or `no`; duration and conditions belong in `condition_note`. |
| `cancellation_terms` | Published rules for ending a service or agreement. | Terms text, including restrictions, notice or refund conditions. |
| `trial_period` | Published trial or money-back-guarantee period, or an explicit statement that no trial is offered. | Duration or policy text; may carry `days` or `months`. A trial is not automatically the same as a return window. |
| `return_window` | Published period during which a return is permitted. | Duration or return-policy text; may carry `days` or `months`; preserve starting event and conditions when recorded. |
| `restocking_fee` | Published restocking charge or deduction, including an explicit no-fee statement. | Fee or policy text; may carry `USD`. Preserve rental or equipment conditions. |
| `return_shipping_payer` | Published allocation of return-shipping responsibility. | Text specifying the company, customer or another stated arrangement. |
| `warranty` | Published warranty coverage, duration or optional warranty offer. | Warranty text; may carry `days` or `months`. Optional paid coverage must not be read as included coverage. |
| `battery_life_published` | Published battery operating-life claim or an explicit statement that measured life is still being tested. | Duration or claim text; may carry `hours`, `days` or `months`. Preserve operating-mode conditions; an unmeasured claim is not a measured runtime. |
| `shower_use_claim` | Published water-use permission, restriction or water-resistance specification. | Claim text, including an IP rating when present. A resistance rating alone does not establish permission to shower. |
| `carrier_network` | Published carrier, network technology or supported cellular-band statement. | Network or band text. Stated bands do not establish activation or calling compatibility on a particular carrier. |
| `sim_provider` | Who supplies the SIM, or whether no SIM is needed. | Code: `provider_supplies`, `customer_supplies` or `no_sim_needed`; meanings below. |
| `smartphone_required` | Whether the described product or function explicitly requires a smartphone. | Code: `yes` or `no`; product, setup and connection conditions remain in the note. |
| `who_is_called_after_fall` | Published call destination or selectable destination for the described alert workflow. | Code: `monitoring_center`, `911`, `family`, `selectable` or `mixed`; meanings below. Read notes for manual-button-only workflows. |
| `family_contacts_count` | Published number or limit of configured family or personal contacts. | Number or count phrase; `people` when annotated. Contact capacity does not prove every contact is called. |
| `family_call_order` | Published order or mode of reaching family or personal contacts. | Code: `sequential`, `simultaneous` or `notification_only`; meanings below. |
| `no_answer_behavior` | Published action when a contact does not answer or the monitoring center cannot reach someone. | Behavior text. Preserve retry limits, escalation conditions and “designed to” qualifications. |
| `fall_detection_accuracy_claim` | Published detection-accuracy statement or limitation, including statements that not all falls are detected. | Claim text; `condition_note` indicates `study cited: yes` or `study cited: no`. Citation presence is not validation of a study or claim. |
| `false_alarm_cancel_seconds` | Published time allowed to cancel the described false-alarm or pre-call countdown. | Source duration text with `seconds` when annotated. Read the note for the triggering event; it is not a response-time measurement. |

## Categorical code lists

These are the permitted extraction codes. A permitted code need not occur in this release; `mixed`, for example, has no long-form records. Missing evidence is never recoded as `no`.

| Field | Code | Meaning |
|---|---|---|
| `contract_required` | `yes` | A contract requirement is explicitly stated. |
| `contract_required` | `no` | The source explicitly states no contract requirement for the described offer. |
| `sim_provider` | `provider_supplies` | The device or service provider supplies the SIM. |
| `sim_provider` | `customer_supplies` | The customer supplies or obtains the SIM or SIM plan. |
| `sim_provider` | `no_sim_needed` | The source explicitly states that no SIM is needed. |
| `smartphone_required` | `yes` | A smartphone is explicitly required for the described product or function. |
| `smartphone_required` | `no` | The source explicitly says the described product or function can operate without a smartphone. |
| `who_is_called_after_fall` | `monitoring_center` | The call connects to a monitoring center. |
| `who_is_called_after_fall` | `911` | The call goes to emergency services; the code is a destination category, not a promise that the same number applies in every country. |
| `who_is_called_after_fall` | `family` | The call goes to configured family or personal contacts. |
| `who_is_called_after_fall` | `selectable` | The source explicitly describes a choice of call destination. |
| `who_is_called_after_fall` | `mixed` | The described workflow explicitly combines destination categories. |
| `family_call_order` | `sequential` | Contacts are called in a stated sequence. |
| `family_call_order` | `simultaneous` | Contacts are called simultaneously. |
| `family_call_order` | `notification_only` | Family receives a message or application notification rather than a family voice call. |

## Wide-format columns and construction

| Column or column group | Definition and format |
|---|---|
| `provider` | Provider name; one row per provider. |
| `provider_type` | `device_or_service` for a device or alert-service provider; `carrier` for a cellular carrier. There are 27 and 4 rows respectively. |
| All 22 measurement columns | Exactly the field identifiers in the measurement table, in that order. Each cell contains selected values or `not stated`. |
| `sources` | Distinct source URLs retained for that provider, separated by ` ; `. This is a provider-level list, not a cell-by-cell evidence map. |

For each measurement cell, official records take priority over third-party records for that provider and field; KeepOkey product facts count as the company's own claims. If only third-party records exist, their values are used with `[third-party source]` appended to the cell. The long format retains both categories.

Distinct display values are joined with ` / `. A condition note is added in parentheses when not already part of the value; a product name is added in square brackets unless it is `(all)`. A unit is appended when the source value is numeric-only and a unit annotation is available. These display additions are not part of the verbatim long-form value. Product brackets are distinct from the `[third-party source]` marker. The separator does not imply equivalence, a range or a single plan; do not split on every slash without checking the long-form records.
