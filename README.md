# binny_database

CheckM-like marker gene database used by [binny](https://github.com/a-h-b/binny) for metagenome-assembled genome (MAG) quality assessment. Used by [ChloroScan](https://github.com/Andyargueasae/ChloroScan) v0.1.7+.

> **Note:** This is a data repository. No software packages are developed here.

## Repository structure

```
data/
├── hmms/
│   ├── checkm_pf/          # Protein family HMM profiles (CheckM-filtered)
│   │   └── checkm_filtered_pf.hmm
│   └── checkm_tf/          # Transcription factor HMM profiles (CheckM-filtered)
│       └── checkm_filtered_tf.hmm
└── marker_sets/            # Marker gene set definitions
```

## Contents

- **`data/hmms/checkm_pf/`** — Hidden Markov Model (HMM) profiles for CheckM-filtered protein families, used as marker genes for binning quality estimation.
- **`data/hmms/checkm_tf/`** — HMM profiles for CheckM-filtered transcription factors.
- **`data/marker_sets/`** — Marker gene set definitions that map HMM profiles to taxonomic lineages.

## Usage

This database is consumed by [binny](https://github.com/a-h-b/binny) during the binning step of [ChloroScan](https://github.com/Andyargueasae/ChloroScan). Point your binny configuration to the relevant HMM file, for example:

```yaml
# config.yaml (binny)
database:
  hmm: /path/to/binny_database/data/hmms/checkm_pf/checkm_filtered_pf.hmm
```

## Data sources

The HMM profiles are derived from the [CheckM](https://github.com/Ecogenomics/CheckM) marker gene database and have been filtered for use with the binny workflow.

