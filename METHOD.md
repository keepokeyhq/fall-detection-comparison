---
kanal: dataset
kaynak: data/KIYAS-TABLOSU.csv, data/kiyas-uzun.csv
baslik: Method and limits of the November 2026 comparison
baglanti: none
fiyat: hayir
urun_olgusu: none
---

# Method and limits of the November 2026 comparison

This release documents published statements about charges, commitments, returns, connectivity, and alert destinations. The compilation was frozen on November 14, 2026. External-source records carry November 13, 2026 capture dates; seller-facts and cost-guide records carry November 14, 2026 dates. Capture dates describe this snapshot rather than the date a policy first took effect.

## Scope and units

`data/KIYAS-TABLOSU.csv` presents 39 provider/product contexts, 18 columns, and 158 nonempty value cells. `data/kiyas-uzun.csv` contains 203 supporting records in 12 columns. A context can describe a device, service, policy, carrier check, or benchmark. Several contexts can belong to the same provider, and several evidence records can support one cell. Neither row count nor evidence count is a count of distinct tested products.

The release consists of these CSVs and their documentation. Definitions and exact cell examples are in [DATA-DICTIONARY.md](DATA-DICTIONARY.md).

## Source classes

These are the literal `source_kind` values in the evidence ledger. They classify saved source material, not its reliability or independence.

| Value | Recorded source material | Interpretation |
|---|---|---|
| `gercekler` | KeepOkey's seller-facts file. | Seller statements remain separate from competitor-source records; inclusion does not independently verify them. |
| `rakip_kopya` | Saved external page extracts, including provider pages, pricing, FAQs, policies, and third-party comparisons. | Preserve the named publisher and whether it reports another provider's claims. This class does not mean every source is a provider's own publication. |
| `olgular` | Saved fact notes attributing seller-site or advertisement statements; these ledger entries have no source URL. | Retain the seller/ad attribution and missing address; do not turn the notes into a direct provider-page citation. |
| `kaynak_sayfa` | Frozen KeepOkey cost-guide extract, used for the already recorded three-year scenarios. | These are scenarios published in the guide, not fresh calculations or new competitor quotations. |

The public ledger retains `source_url`, `source_kind`, `captured_on`, `page_ref`, and `claim_ref`. A blank URL means not stated. Matching to saved source text took place during compilation; local capture paths and line numbers are omitted from the public export.

## Transcription and coding

Recorded amounts and substantive wording are kept as written in the saved evidence. Qualifications remain in `condition_note` and in the wide cell. Do not strip billing periods, purchase-versus-lease scope, exclusions, or statements that publications differ.

The fields for commitment, phone dependency, and alert destination also use compiler categories. Examples are `yes`, `no`, `family`, `911`, and `monitoring_center`; these category labels are not verbatim provider quotations. Their accompanying source wording explains the coding. A source-class label likewise describes the compilation rather than a provider claim.

The wide file groups ledger entries by provider, product, and field, retaining alternate statements and attribution. No averaging resolves disagreements. Repeated statements can come from related publications and should not be counted as independent checks.

An empty cell is reported as **not stated**. It does not establish a zero charge, a missing feature, or permission to cancel without cost.

## KeepOkey's position

KeepOkey is the institutional compiler and a seller included in the comparison. Its row uses `gercekler` evidence from the separate seller-facts file. Competitor entries use the other recorded source classes. This separation identifies the origin of statements; it does not remove the compiler's commercial interest or establish equivalent evidence quality across rows.

## Three-year scenarios

The `total_3yr` values are restricted to expressions and scenarios already present in the frozen CSVs. The guide scenarios assume **listed rates held constant** and continued use of the original device. Taxes, shipping, replacements, and unconfirmed charges are excluded. A carrier-charge example and a monitoring-only benchmark retain those narrower scopes.

The KeepOkey cell is a hardware-price-plus-carrier-plan expression; the compilation supplies neither a carrier quote nor a calculated ownership total for that row. No new total, difference, percentage, or projection is calculated in this documentation.

## Exclusions and known limits

This is one documentary snapshot, with prices and policies subject to change. Its scoped rows are not an exhaustive market sample or a uniform product matrix. Missing fields and differently scoped policy rows prevent an unqualified comparison of every provider.

Published specifications and seller claims are not device trials. The records do not establish detection accuracy, missed-fall frequency, emergency response time, actual operating duration, carrier activation success, or clinical outcomes. Network references and compatibility instructions do not demonstrate activation of an untested watch.

The package provides recorded facts, source addresses where present, dates, and reference identifiers. It does not redistribute the saved source texts. Source matching supports transcription checks; it does not settle whether each underlying statement remains current or is correct in practice.

AI citation and study tables: not included in this version.
