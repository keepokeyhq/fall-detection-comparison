---
kanal: dataset
kaynak: data/KIYAS-TABLOSU.csv, data/kiyas-uzun.csv
baslik: Fall detection comparison data dictionary
baglanti: none
fiyat: evet
urun_olgusu: none; CSV examples only
---

# Fall detection comparison data dictionary

The wide CSV describes provider-and-product contexts; the long CSV keeps the evidence behind individual fields. Version 1.0.0 is frozen on November 14, 2026. Its 39 wide rows contain 158 filled value cells backed by 203 evidence records. Counts do not describe distinct companies or independent confirmations.

All CSV cells are stored as text. Types below describe how to interpret them, not automatic numeric conversions. An empty cell means **not stated** in the recorded evidence, never zero, false, free, or not applicable. Examples reproduce complete CSV cell values, including attribution and qualifications where present. Each example illustrates its own row; examples across columns do not form a single record.

## data/KIYAS-TABLOSU.csv

The public wide CSV has 18 columns.

`provider` and `product` identify a row's scope. A provider may have several rows covering devices, policies, or carrier information. Value fields can combine more than one evidence entry; keep their conditions and attributions together. The `sources` column collects recorded web addresses.

| Column | Interpreted type | Meaning | Exact example | Empty cell |
|---|---|---|---|---|
| `provider` | Text | Organization or attributed source context; not a unique company identifier. | `AT&T` | not stated |
| `product` | Text | Named device, service, plan, policy, or carrier context. | `Halo` | not stated |
| `device_price` | Attributed text | Equipment charge, with recorded qualifications; not a normalized number. | `$479 [livindi.com, 2026-11-13]` | not stated |
| `monthly_fee` | Attributed text | Recurring charge or statement about it; preserve billing and plan conditions. | `$19 [livindi.com, 2026-11-13]` | not stated |
| `fall_detection_addon_monthly` | Attributed text | Separately described fall-detection charge, including the identity of the reporting publisher. | `$10 per month (Medical Guardian blog states: Medical Guardian third-party description) [medicalguardian.com, 2026-11-13]` | not stated |
| `activation_fee` | Attributed text | Initial activation or connection charge, with any plan restrictions. | `$35 device connection charge due at sale. [t-mobile.com, 2026-11-13]` | not stated |
| `contract_required` | Classified text | Compiler label followed by evidence about commitment; conditions can differ by plan. | `no: MobileHelp does not require a contract. [mobilehelp.com, 2026-11-13]` | not stated |
| `cancellation_terms` | Attributed text | Stated steps or conditions for ending service; a short statement may leave fees unresolved. | `Device return required [bayalarmmedical.com, 2026-11-13]` | not stated |
| `who_is_called_after_fall` | Classified text | Recorded alert destination and supporting wording; the label is compiler coding. | `911: Guardian Alert 911 Plus will automatically call Emergency Services. [logicmark.com, 2026-11-13]` | not stated |
| `smartphone_required` | Classified text | Recorded phone dependency; preserve whether it concerns setup or use. | `no: the wearer does not need a phone. [aevaalert.com, 2026-11-13]` | not stated |
| `total_3yr` | Scenario text | Existing cost-guide scenario or seller cost expression, with its scope retained; not a new calculation. | `$159.90 + your carrier plan (KeepOkey facts: operator price and a calculated ownership total are not stated) [KeepOkey]` | not stated |
| `return_window` | Attributed text | Published return-period statement; any eligibility conditions remain part of the evidence. | `30 Day Money Back Guarantee [logicmark.com, 2026-11-13]` | not stated |
| `restocking_fee` | Attributed text | Published return deduction or restocking statement. | `up to $50 (restocking charge) [aevaalert.com, 2026-11-13]` | not stated |
| `return_shipping_payer` | Attributed text | Return-label or shipping-cost responsibility, including deductions and conditions. | `return shipping label if requested and paid for by MCA. (deducted from refund; shipping costs incurred by MCA also deductible) [medicalcarealert.com, 2026-11-13]` | not stated |
| `warranty` | Attributed text | Coverage wording as recorded, with any limits in the cell; not an inferred entitlement. | `A Limited Lifetime Consumer Warranty applies to the physical Equipment [unaliwear.com, 2026-11-13]` | not stated |
| `battery_life_published` | Attributed text | Published duration claim or capacity-only statement; not a device-test result. | `up to 24 hours [aevaalert.com, 2026-11-13]` | not stated |
| `carrier_network` | Attributed text | Stated network, connectivity requirement, or compatibility context; not proof of activation. | `4G LTE [logicmark.com, 2026-11-13]` | not stated |
| `sources` | URL-list text | Recorded source URLs, separated by ` ; ` when several are present; seller/ad and internal evidence can lack a URL. | `https://www.aevaalert.com/` | not stated |

## data/kiyas-uzun.csv

The public evidence CSV has 12 columns.

Each row records one value in a specified provider/product/field context. Multiple records can feed the same wide cell, including differently scoped or conflicting statements. Use the identifiers, source URLs, and capture dates to distinguish them; repetition is not independent corroboration.

Local capture locators (file path and line) were removed from the public export; each entry keeps `source_url`, `source_kind`, `captured_on`, `page_ref` and `claim_ref`.

| Column | Interpreted type | Meaning | Exact example | Empty cell |
|---|---|---|---|---|
| `row_id` | Text identifier | Identifier for an evidence entry within this frozen release. | `B1a-0012` | not stated |
| `provider` | Text | Organization or attributed source context corresponding to the wide row. | `Apple` | not stated |
| `product` | Text | Device, plan, policy, or other scoped context corresponding to the wide row. | `Apple Watch (supported models)` | not stated |
| `field` | Field-name text | Wide value column documented by this entry. | `who_is_called_after_fall` | not stated |
| `value` | Text | Transcribed value or compiler category; read with `condition_note`, source attribution, and date. | `911` | not stated |
| `unit` | Unit-label text | Unit recorded separately where supplied; do not infer a unit from an empty entry. | `USD/month` | not stated |
| `condition_note` | Text | Scope, qualifications, source wording supporting category coding, and disagreement notes. | `No smartphones are required for the basic plan.` | not stated |
| `source_kind` | Enumerated text | Internal source class: `gercekler`, `rakip_kopya`, `olgular`, or `kaynak_sayfa`; see METHOD.md. | `rakip_kopya` | not stated |
| `source_url` | URL text | Recorded public address, when supplied; an address is not a saved web archive. | `https://support.apple.com/en-euro/guide/watch/apd34c409704/watchos` | not stated |
| `captured_on` | Date text, YYYY-MM-DD | Capture date assigned to this evidence record, not a guaranteed price-validity period. | `2026-11-13` | not stated |
| `page_ref` | Reference text | Internal page-context identifier associated with the entry. | `P01` | not stated |
| `claim_ref` | Reference text | Internal claim identifier where one was supplied; not a clinical or certification code. | `I011` | not stated |

## Reading and reuse

In the wide file, prefixes such as `family:`, `911:`, `monitoring_center:`, `yes:`, and `no:` identify compiler categories. They are separate from the source wording. Monetary strings must retain their currency and billing context. Return terms must retain their eligibility conditions. The same rule applies to other qualifications stored in either CSV.

See [METHOD.md](METHOD.md) for source classes and limitations, and [CITATION.cff](CITATION.cff) for release attribution.

AI citation and study tables: not included in this version.
