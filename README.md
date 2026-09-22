# Comparative Evaluation of Machine Learning Models Under Class Imbalance

This repository contains the initialization and dataset-audit stage for a reproducible
study of model evaluation under class imbalance. The research experiments are
intentionally not included in this stage.

## Scope

- Preserve the official UCI downloads in `data/raw/`.
- Inspect the downloaded files and record verified structure, dimensions, labels,
  missing-value indicators, and checksums.
- Keep source data separate from derived audit reports and future experiment outputs.

## Repository layout

```text
data/
  raw/                 Original UCI archives and extracted source files
  interim/             Future intermediate data products
  processed/           Future experiment-ready data products
reports/
  dataset_audit.md     Generated audit summary
  dataset_audit.json   Generated machine-readable audit
scripts/
  audit_datasets.py    Deterministic dataset inspection
```

The extracted files under `data/raw/` are derived from the unchanged archives in the
same directory. Do not edit or overwrite either original archive.

## Environment

Python 3.10 or newer is recommended. Install the pinned minimum dependencies with:

```powershell
python -m pip install -r requirements.txt
```

## Run the audit

```powershell
python scripts/audit_datasets.py
```

The command writes `reports/dataset_audit.md` and `reports/dataset_audit.json`.
It does not train models, resample data, impute values, or otherwise transform the
datasets.

## Data sources

The datasets are downloaded from their authoritative UCI Machine Learning Repository
dataset pages:

- [Dataset 350: Default of Credit Card Clients](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)
- [Dataset 222: Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank+marketing)

The audit records the retrieval URLs and SHA-256 checksums so that the raw files can
be verified independently.
