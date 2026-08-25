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
repository contains their outputs. The default root is the current working
directory for local tooling compatibility; use the environment variable when
working with this repository.

## Reproducibility

Keep source URLs, publication dates, source identifiers, retrieval dates, and
SHA-256 checksums in manifests. Do not store API keys, credentials, private
documents, or generated secrets here. This snapshot is development input and
must not be used as the final held-out evaluation corpus without an explicit
research decision.
