# Nextstrain Hepatitis B builds

Currently a WIP

Based on Katie Kistler's work in [blab/adaptive-evolution](https://github.com/blab/adaptive-evolution)

## Ingest

You can run the ingest part of the snakemake pipeline via:

```
snakemake --cores 4 -npf ingest/results/aligned.fasta ingest/results/sequences.fasta ingest/results/metadata.tsv
```

Ingest will fetch genomes from NCBI's Entrez API and write to `./ingest/data/genbank.gb`.
As of mid 2023 there are around ~11k genomes and the full GenBank file is ~150Mb.

## Phylo

For a small ~800-tip dev tree: `snakemake --cores 4 -pf auspice/hbv_dev.json`
For the entire human-HBV tree, with 11k tips (takes ~15min on a 4-core M1 machine): `snakemake --cores 4 -pf auspice/hbv_all.json`

(If you haven't run the ingest section of the pipeline then any phylo build will run it.)

