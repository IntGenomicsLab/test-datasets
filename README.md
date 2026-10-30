This repository contains test datasets and reference files that are used as minimal input files for testing of nextflow pipelines.
## lrsinglecell

Test data for [IntGenomicsLab/lrsinglecell](https://github.com/IntGenomicsLab/lrsinglecell), used by its `test*` profiles.

| File | Used by profile |
| --- | --- |
| `lrsinglecell/samplesheet/samplesheet_test.csv` | `test`, `test_lrkallisto` |
| `lrsinglecell/samplesheet/samplesheet_test_dna.csv` | `test_dna` |
| `lrsinglecell/samplesheet/samplesheet_test_mixed.csv` | `test_mixed` |
| `lrsinglecell/samplesheet/samplesheet_full.csv` | `test_full` (points to the full ENA runs) |
| `lrsinglecell/fastq/sub_ERR9958133.fastq.gz`, `sub_ERR9958134.fastq.gz` | `test`, `test_lrkallisto` |
| `lrsinglecell/fastq/sub_RPMI8402_DNA.fastq.gz` | `test_dna`, `test_mixed` |
| `lrsinglecell/fastq/sub_RPMI8402_cDNA.fastq.gz` | `test_mixed` |
| `lrsinglecell/reference/chr21.fa`, `chr21.gtf` | all small profiles |

Provenance:

- `sub_ERR9958133/4.fastq.gz`: ~5000 reads subsampled (`seqtk sample -s123`) from ERR9958133/ERR9958134 of You _et al._ (2023), Identification of cell barcodes from long-read single-cell RNA-seq with BLAZE, _Genome Biology_ 24:66, doi:[10.1186/s13059-023-02907-y](https://doi.org/10.1186/s13059-023-02907-y).
- `sub_RPMI8402_{DNA,cDNA}.fastq.gz`: subsampled in-house 10x Multiome ONT data of the RPMI-8402 cell line.
- `chr21.fa` / `chr21.gtf`: GENCODE GRCh38 v40, filtered to chr21.
- `samplesheet_full.csv`: from [U-BDS/test-datasets@8ca6f50](https://github.com/U-BDS/test-datasets/tree/8ca6f50d1f48335457c392a843864c6a5b2dddbf).

Attribution: the data files were copied unchanged (byte-identical, see `lrsinglecell/SHA256SUMS`) from [nf-core/test-datasets](https://github.com/nf-core/test-datasets), branch `scnanoseq`, commit `3fc8e5a` (MIT License, Copyright (c) 2018 nf-core; see `lrsinglecell/LICENSE-nf-core-test-datasets`). The `samplesheet_test*.csv` files were changed only to point their FASTQ URLs at this repository.

The pipeline's nf-test snapshots depend on these exact bytes: do not modify files in place (add new files instead), and do not track them with git LFS, since raw URLs of LFS files return pointers.
