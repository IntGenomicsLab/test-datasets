# HMF report resources (lrsomatic)

Defaults of [IntGenomicsLab/lrsomatic](https://github.com/IntGenomicsLab/lrsomatic)'s optional HMF
(Hartwig Medical Foundation) driver annotation in the per-sample report: the subset of the
oncoanalyser resource bundle the report reads, one tarball per genome, fetched and MD5-checked by
the pipeline (`conf/igenomes.config`: `hmf_bundle_url`, `hmf_bundle_md5`).

| File | Contents |
| --- | --- |
| `v2.2.0/hmf_report.GRCh38.tar.gz` | `hmf_pipeline_resources.38_v2.2.0--3`: driver panel, known fusions, hotspots, actionable coding panel, Ensembl cache (canonical transcripts only); `REFERENCE` = `hg38` |
| `v2.2.0/hmf_report.CHM13.tar.gz` | the same, lifted to T2T-CHM13v2.0 by lrsomatic's `bin/hmf_liftover.py` with the T2T consortium's `grch38-chm13v2.chain`; `REFERENCE` = `t2t` |

Each tarball unpacks to one directory in the oncoanalyser layout (`common/`, `dna/sv/`,
`dna/variants/`) with a `README.md` giving its provenance and, for CHM13, `hmf_liftover_report.tsv`.
`*.md5` hold their checksums. The tarballs are built reproducibly (sorted entries, fixed mtime and
owner, `gzip -n`).

Do not modify these files in place: the pipeline pins their MD5s. A new bundle version goes in a
new folder (`v<version>/`).
