# Company Communications Data Contract

Store quarterly company communications here before ingestion. The original
download and the reviewed canonical copy are both retained so the source can be
audited later.

```text
data/company_communications/
  raw/<TICKER>/
  curated/<TICKER>/
```

- Put downloaded files in `raw/<TICKER>/` unchanged. For Applied Materials,
  use `raw/AMAT/` and download from
  `https://ir.appliedmaterials.com/financial-information/quarterly-results`.
- After review, copy each file to `curated/<TICKER>/` using the canonical name
  below. Do not delete the raw download.
- `curated/` is a renamed source file, not cleaned or extracted text. Future
  ingestion creates the separate cleaned representation required by the domain
  model.

## Canonical File Name

```text
<TICKER>__<FISCAL_PERIOD>__<PUBLISHED_AT>__<SOURCE>__<DOCUMENT_TYPE>.<extension>
```

Example:

```text
AMAT__FY2025-Q3__2025-08-14__investor_relations__earnings_call_prepared_remarks.pdf
```

- `TICKER`: approved registry ticker, for example `AMAT`.
- `FISCAL_PERIOD`: the issuer's reported period, for example `FY2025-Q3`; do
  not infer it from the calendar date.
- `PUBLISHED_AT`: official transcript or call publication date in ISO format:
  `YYYY-MM-DD`.
- `SOURCE`: `investor_relations` for this Applied Materials page.
- `DOCUMENT_TYPE`: use `earnings_call_transcript` only for a complete call
  transcript. The current Applied Materials PDFs are
  `earnings_call_prepared_remarks`.
- `extension`: preserve the source format, such as `pdf`, `html`, or `txt`.

After files are reviewed, record their canonical filename, original filename,
source URL, publication date, fiscal period, and SHA-256 checksum in a
company-specific manifest before ingestion.
