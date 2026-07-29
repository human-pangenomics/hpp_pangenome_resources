# HPRC Pangenome Resources

This repo describes pangenomes produced by the [Human Pangenome Reference Consortium](https://humanpangenome.org/) from year 2 data. For information about data reuse and publishing with HPRC data please see the HPRC's [Data Use Protocol](https://humanpangenome.org/data-use/).

Note: The pangenomes and resultant files referred to in this repo have not been fully QC'd, are not published, and may have known issues.

## Background Information

### Previous Version

For HPRC v1, click [here](README-v1.md).

### Preprint

[HPRC2: A human pangenome reference with near-complete coverage of common genetic variation](https://doi.org/10.64898/2026.07.21.739710)

### Graph Creation Strategies

Graphs are available from three different strategies summarized in the table (and relevant sections) below:

| <sub>	</sub> | <sub>[**Minigraph**](#minigraph)</sub> | <sub>[**Minigraph-Cactus**](#minigraph-cactus)</sub> | <sub>[**IMPG/PGGB**](#impgpggb)</sub> |
| :-------- | :-------- | :------ | :------ |
| <sub> sequence comparison </sub> | <sub> reference-based, progressive </sub> | <sub> reference-based, progressive </sub> | <sub> symmetric, all-vs-all </sub> |
| <sub> resolution </sub> | <sub> SV only </sub> | <sub> base-level (via abPOA) </sub> | <sub> base-level (via seqwish/POA) </sub> |
| <sub> scope </sub> | <sub> full assemblies </sub> | <sub> Non-centromeric </sub> | <sub> full assemblies </sub> |
| <sub> cyclic paths </sub> | <sub> no </sub> | <sub> non-reference </sub> | <sub> all </sub> |
| <sub> short read mapping </sub> | <sub> untested </sub> | <sub> yes (fast) </sub> | <sub> untested </sub> |
| <sub> long read mapping </sub> | <sub> yes (fastest) </sub> | <sub> yes </sub> | <sub> yes (slowest) </sub> |
| <sub> Assembly mapping </sub> | <sub> yes (direct) </sub> | <sub> untested </sub> | <sub> yes (via injection) </sub> |

Index files listing file locations for download with the AWS CLI can be found in the indexes folder of this repository. Alternatively, tables are listed below in each graph creation strategy's section. Note that the index files list the file locations with s3:// uris -- as opposed to http:// urls as found in the tables.

### Assembly Inputs

Information about the source assemblies can be found in the [HPRC Assembly GitHub repository](https://github.com/human-pangenomics/hprc_intermediate_assembly).  Of the 232 samples assembled (464 assemblies) in year 2, all but one were included in graph construction (HG00272 was held out due to an apparent large-scale misassembly in chrX). GRCh38 and CHM13 were added to make the total number of haplotypes included 464.


## Graphs
### Minigraph

[Minigraph](https://github.com/lh3/minigraph) ([cite](https://doi.org/10.1186/s13059-020-02168-z)) is a generalization of minimap2 (very fast) which builds the graph with iterative construction. Minigraph aligns with approximate locations and can be used to call structural variants (>50nt). Graphs were built with GRCh38, CHM13v2.0, and GRCh37 used as reference sequences. Note, these results were produced as part of Minigraph-Cactus (see below). 

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> | <sub>**GRCh37 Graph**</sub> |
| :-------- | :------ | :------ | :------ |
| <sub> Graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.sv.gfa.gz) </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.sv.gfa.gz) </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.sv.gfa.gz) </sub> |
 

### Minigraph-Cactus

[Minigraph-Cactus](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/pangenome.md) ([cite](https://doi.org/10.1038/s41587-023-01793-w)) adds base-level alignment to `minigraph` graphs.

The graphs below are **v2.1**. An earlier **v2.0** version (built before the mitochondria-alignment and per-chromosome minigraph-ordering improvements) is documented [here](hprc-v2.0-mc.md).

All steps to reproduce the graphs can be found [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/README)


| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> | <sub>**GRCh37 Graph**</sub> |
| :-------- | :------ | :------ | :------ |
| <sub> Graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.gbz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.gbz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.gbz)</sub> |
| <sub> Full (Unclipped) Graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.full.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.full.gbz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.full.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.full.gbz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.full.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.full.gbz)</sub> |
| <sub> Chromosome Graphs </sub> | <sub>[chroms](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.chroms)</sub> | <sub>[chroms](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.chroms)</sub> | <sub>[chroms](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.chroms)</sub> |
| <sub> Multiple Alignment </sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.full.hal)</sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.full.hal)</sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.full.hal)</sub> |
| <sub> vcfwaved VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.wave.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.wave.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.wave.vcf.gz.tbi)</sub> |
| <sub> VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.vcf.gz.tbi)</sub> |
| <sub> Raw VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.raw.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.raw.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.raw.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.raw.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.raw.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.raw.vcf.gz.tbi)</sub> |
| <sub> PanGenie VCFs </sub> | <sub>[biallelic](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.pgbi.vcf.gz) &nbsp; &nbsp; [biallelic index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.pgbi.vcf.gz.tbi) &nbsp; &nbsp; [input](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.pgin.vcf.gz) &nbsp; &nbsp; [input index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.pgin.vcf.gz.tbi)</sub> | <sub>[biallelic](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.pgbi.vcf.gz) &nbsp; &nbsp; [biallelic index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.pgbi.vcf.gz.tbi) &nbsp; &nbsp; [input](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.pgin.vcf.gz) &nbsp; &nbsp; [input index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.pgin.vcf.gz.tbi)</sub> | <sub> N/A </sub> |
| <sub> VG Indexes </sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.gbz) &nbsp; &nbsp; [hapl](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.hapl) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.snarls)</sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.gbz) &nbsp; &nbsp; [hapl](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.hapl) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.snarls)</sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.gbz) &nbsp; &nbsp; [hapl](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.hapl) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.snarls)</sub> |
| <sub> AF-Filtered VG Indexes </sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.d46.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.d46.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.d46.shortread.withzip.min) &nbsp; &nbsp; [zipcodes](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.d46.shortread.zipcodes) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.d46.snarls)</sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.d46.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.d46.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.d46.shortread.withzip.min) &nbsp; &nbsp; [zipcodes](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.d46.shortread.zipcodes) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.d46.snarls)</sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.d46.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.d46.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.d46.shortread.withzip.min) &nbsp; &nbsp; [zipcodes](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.d46.shortread.zipcodes) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.d46.snarls)</sub> |
| <sub> Reference Gaps </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.refgaps.bed)</sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.refgaps.bed)</sub> | <sub> N/A </sub> |
| <sub> Excluded Regions </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.missing.tar.gz) &nbsp; &nbsp; [full bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.full.missing.tar.gz) &nbsp; &nbsp; [af bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38/hprc-v2.1-mc-grch38.d46.missing.tar.gz)</sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.missing.tar.gz) &nbsp; &nbsp; [full bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.full.missing.tar.gz) &nbsp; &nbsp; [af bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13/hprc-v2.1-mc-chm13.d46.missing.tar.gz)</sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.missing.tar.gz) &nbsp; &nbsp; [full bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.full.missing.tar.gz) &nbsp; &nbsp; [af bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37/hprc-v2.1-mc-grch37.d46.missing.tar.gz)</sub> |
| <sub> All Files </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch38) </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-chm13) </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.1/hprc-v2.1-mc-grch37) </sub> |

The graphs are available in gfa format alongside other graph and index files. Information about the associated file formats can be found:
* [mc output overview](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/pangenome.md#output)
* [vg wiki](https://github.com/vgteam/vg/wiki/Index-Types)
* [gbz format](https://github.com/jltsiren/gbwtgraph/blob/master/SERIALIZATION.md) ([cite](https://doi.org/10.1093/bioinformatics/btac656))
* [hapl format](https://github.com/vgteam/vg/wiki/Haplotype-Sampling): allows `vg giraffe` to infer a personalized pangenome as alternative to AF-filtering.

#### VCF Decomposition
Three VCFs are provided for each graph, from least to most processed:

* **Raw VCF** (`.raw.vcf.gz`): a site for each bubble in the graph. Nested bubbles result in overlapping sites, with the nesting relationships denoted by the `PS` (parent snarl), `LV` (level) and `AT` (allele traversal) tags, which need to be taken into account when interpreting the VCF.
* **VCF** (`.vcf.gz`): nested bubbles have been "popped" with [vcfbub](https://github.com/pangenome/vcfbub) (removing alleles larger than 100kb), but the alt alleles have not been realigned.
* **vcfwaved VCF** (`.wave.vcf.gz`): as above, with each alt allele additionally realigned to the reference using [vcfwave](https://github.com/vcflib/vcflib/blob/master/doc/vcfwave.md) plus further normalization.

Unlike the v1.1 graphs (which used vcfbub and vcfwave only), the v2.1 decomposition applies additional normalization, built into Minigraph-Cactus via the `--vcfwave` option:

```
vcfbub -l 0 -a 100000
bcftools annotate -x INFO/AT
bcftools norm -m -any
vcfwave -I 1000
bcftools norm -f <ref.fa>
sort -k1,1d -k2,2n -s
merge_duplicates.py   # https://github.com/Han-Cao/collapse-bubble
bcftools norm -m +any
vcffixup
```

These extra steps (relative to v1.1) 1) pass biallelic input to vcfwave, which has had issues with multiallelic sites, 2) left-shift variants after vcfwave, and 3) merge the left-shifted variants back into multiallelic sites.

These steps are also described in the [Minigraph-Cactus VCF documentation](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/mc-pangenomes/hprc-v1.1-mc.md#vcf-postprocessing).

#### Evaluation Graphs

Versions of the CHM13 and GRCh38-based graphs are [available here](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.1/benchmark-graphs/) with `HG002`, `HG005`, and `NA19240` excluded.  Use these if, for example, you are running Genome-In-A-Bottle benchmarks.

#### Reference Assemblies

Slightly different reference assemblies were used in different graphs in order to handle the fact that `CHM13v2.0` has `chrY` from `HG002`, and that `GRCh38` unplaced contigs aren't wanted except when `GRCh38` is the reference.

* `hprc-v2.1-mc-chm13` : `CHM13v2.0`, `GRCh38` (chromosomes only)
* `hprc-v2.1-mc-grch38` : `CHM13v2.0` (without `chrY`), `GRCh38`
* `hprc-v2.1-mc-grch37` : `CHM13v2.0` (without `chrY`), `GRCh38` (chromosomes only), `hs37d5`
* `hprc-v2.1-mc-chm13-eval` : `CHM13v2.0` (but with `chrY` from `HG03017` instead of `HG002`), `GRCh38` (chromosomes only)
* `hprc-v2.1-mc-grch38-eval` : `CHM13v2.0` (without `chrY`), `GRCh38`


#### Filtered Graphs
The "AF-Filtered VG indexes" above were created by dropping nodes and edges supported by fewer than 10% of haplotypes, and give the best performance for Giraffe and are what have been used in the various papers to date. Note that `giraffe` requires only the `.gbz`, `.dist` and `.min` indexes.  


#### PanGenie VCFs
The **PanGenie VCFs** (GRCh38 and CHM13 only) were normalized using [PanGenie's pipeline](https://github.com/eblerjana/genotyping-pipelines/tree/master/prepare-vcf-MC) for use with [PanGenie](https://github.com/eblerjana/pangenie):

* The `.pgbi.vcf.gz` (biallelic) files are an alternative to the `.wave.vcf.gz` files above. Rather than realigning large bubbles, this approach uses the paths in the graph to split them up.
* The `.pgin.vcf.gz` (input) files are the PanGenie input VCFs and can be used to genotype other samples with PanGenie.


#### Reference Gaps 
Regions unaligned in the reference (predominantly satellite sequences) are provided in the refgaps BED file.  

#### Excluded Regions
The Minigraph-Cactus pipeline clips out contigs (or pieces of contigs) that don't align confidently into the graph. Per-sample BED files of these removed intervals are bundled in the `.missing.tar.gz` archives, one archive per graph variant: the default graph (`.missing.tar.gz`), the full graph (`.full.missing.tar.gz`, which still excludes contigs that couldn't be confidently assigned to a reference chromosome), and the AF-filtered graph (`.d46.missing.tar.gz`).  

### IMPG/PGGB

[PGGB](https://github.com/pangenome/pggb) (the PanGenome Graph Builder) constructs a graph from an all-vs-all alignment of the input assemblies, giving base-level resolution with no reference bias. In this release, that same all-vs-all alignment is also provided through [IMPG](https://github.com/pangenome/impg) (implicit pangenome), which represents the pangenome as a set of assembly-vs-assembly alignments that can be projected and queried on the fly. The IMPG alignments, the PGGB graphs, and VCFs called from those graphs are provided below.

#### Graphs (PGGB)

Graphs were built with pggb `-p 98 -k 311` and are provided as whole-genome, per-chromosome, and per-partition (community) GFAs. All files are [zstd](https://github.com/facebook/zstd)-compressed (`.zst`).

| <sub>**Description**</sub> | <sub>**Location**</sub> |
| :-------- | :------ |
| <sub> Whole-genome graph </sub> | <sub> [gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/pggb/gfas/whole-genome/20250930_hprc25272.p98-k311.tmp.fix.gfa.zst) </sub> |
| <sub> Per-chromosome graphs </sub> | <sub> [gfas](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/pggb/gfas/by-chromosome/) </sub> |
| <sub> Partition graphs </sub> | <sub> [gfas](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/pggb/gfas/whole-genome/20250823_hprc25272.p98-k311_partitions/) </sub> |
| <sub> All Files </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/pggb/gfas/) </sub> |

#### VCFs (PGGB)

Variants decomposed from the PGGB graphs, relative to GRCh38. These are bgzipped VCFs with no tabix (`.tbi`) index.

| <sub>**Description**</sub> | <sub>**Location**</sub> |
| :-------- | :------ |
| <sub> Whole-genome VCF </sub> | <sub> [vcf](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/pggb/vcfs/whole-genome/20250930_hprc25272.GRCh38.p98-k311.laced.vcf.gz) </sub> |
| <sub> Per-chromosome VCF </sub> | <sub> [vcf](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/pggb/vcfs/by-chromosome/20251014_hprc25272.GRCh38.p98-k311.laced.concatenated.vcf.gz) </sub> |


#### Alignments (IMPG)

Alignments are provided in PAF format and in IMPG's TPA format (one file per haplotype, 466 total).

| <sub>**Description**</sub> | <sub>**Location**</sub> |
| :-------- | :------ |
| <sub> All-vs-all alignment </sub> | <sub> [paf](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/impg/pafs/hprc25272.aln.paf.gz) </sub> |
| <sub> All haplotypes vs GRCh38 </sub> | <sub> [paf](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/impg/pafs/hprc465vsgrch38.aln.paf.gz) </sub> |
| <sub> All haplotypes vs CHM13 </sub> | <sub> [paf](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/impg/pafs/hprc465vschm13.aln.paf.gz) </sub> |
| <sub> Per-target alignments (all-vs-1) </sub> | <sub> [pafs](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/impg/pafs/all-vs-1/) </sub> |
| <sub> Per-haplotype alignments (TPA) </sub> | <sub> [tpas](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/impg/tpas/) </sub> |
