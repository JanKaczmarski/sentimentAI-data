# SentimentAI Research Data

Local research inputs for the `sentimentAI` application repository.

This repository stores downloaded source snapshots and derived acquisition
metadata separately from the application code. It is not the final thesis
corpus or evaluation split.

## Layout

- `cik_map.csv`: SEC ticker-to-CIK mapping used by acquisition tools.
- `data/company_communications/`: raw and curated investor-relations files.
- `data/market_prices/`: local market-price snapshot.
- `data/sec/`: SEC submissions, filing text, and acquisition manifests.

## Use With The Application

Set the application data-repository root before running acquisition tools:

```bash
export SENTIMENT_DATA_ROOT=/Users/jan/private/sentimentAI-data
```

The application repository contains the acquisition scripts and the data
repository contains their outputs. `SENTIMENT_DATA_ROOT` is required by the
application acquisition tools; set it explicitly whenever running them.

## Functional Six-Company Snapshot

The previous-calendar-quarter SEC earnings-release manifest includes a bounded
functional snapshot for `AAPL`, `MSFT`, `NVDA`, `JPM`, `XOM`, and `JNJ`. Each of
these records has a raw-content checksum and a corresponding cached source file.
This snapshot is for local application verification, not the final five-year
thesis corpus or held-out evaluation set.

## Reproducibility

Keep source URLs, publication dates, source identifiers, retrieval dates, and
SHA-256 checksums in manifests. Do not store API keys, credentials, private
documents, or generated secrets here. This snapshot is development input and
must not be used as the final held-out evaluation corpus without an explicit
research decision.
