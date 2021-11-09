# HPRC Pangenome Resources

This repo describes pangenomes produced by the [Human Pangenome Reference Consortium](https://humanpangenome.org/) from year 1 data. For information about data reuse and publicating with HPRC data please see the HPRC's Data Use Protocol.

Note: The pangenomes and resultant files referred to in this repo have not been fully QC'd, are not published, and may have known issues.

## Background Information
### Graph Creation Strategies

Graphs are available from three different strategies summarized in the table (and relevant sections) below:

| <sub>	</sub> | <sub>**Minigraph**</sub> | <sub>**Minigraph-Cactus**</sub> | <sub>**PGGB**</sub> |
| :-------- | :-------- | :------ | :------ |
| <sub> sequence comparison </sub> | <sub> reference-based, progressive </sub> | <sub> reference-based, progressive </sub> | <sub> symmetric, all-vs-all </sub> |
| <sub> resolution </sub> | <sub> SV only </sub> | <sub> base-level (via abPOA) </sub> | <sub> base-level (via abPOA) </sub> |
| <sub> scope </sub> | <sub> full assemblies </sub> | <sub> Non-centromeric </sub> | <sub> full assemblies </sub> |
| <sub> cyclic paths </sub> | <sub> no </sub> | <sub> non-reference </sub> | <sub> all </sub> |
| <sub> short read mapping </sub> | <sub> untested </sub> | <sub> yes (fast) </sub> | <sub> untested </sub> |
| <sub> long read mapping </sub> | <sub> yes (fastest) </sub> | <sub> yes </sub> | <sub> yes (slowest) </sub> |
| <sub> Assembly mapping </sub> | <sub> yes (direct) </sub> | <sub> untested </sub> | <sub> yes (via injection) </sub> |


### Assembly Inputs

Information about the source assemblies can be found in the [HPRC Assembly GitHub repository](https://github.com/human-pangenomics/HPP_Year1_Assemblies). Of the 47 samples assembled (94 assemblies) in year 1, all but three samples were included in graph constructions (HG002, HG005 and NA19240 were excluded for evaluation purposes). GRCh38 and CHM13 were added to make the total number of haplotypes included 90.


## Graphs
### Minigraph

[Minigraph](https://github.com/lh3/minigraph) is a generalization of minimap2 (very fast) which builds the graph with iterative construction. Minigraph aligns with approximate locations and can be used to call structural variants (>50nt). Graphs were built with both GRCh38 and CHM13+Y (found [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/CHM13v11Y.fa.gz)) used as reference sequences.

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> graph </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.gfa.gz) </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.gfa.gz) </sub> |
 <sub> bed </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.bb.bed.gz.tbi) </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.bb.bed.gz.tbi) </sub> |


### Minigraph/CACTUS

[The CACTUS pangenome pipeline](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/pangenome.md) adds base-level alignments to the minigraph graphs above (so both GRCh38- and CHM13-based graphs are available). Centromeric regions are removed during  Minigraph/CACTUS graph creation.

Graphs and associated files are summarized below. 

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> graph </sub> | <sub>[base graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.gfa.gz)</sub> | <sub>[base graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.gfa.gz)</sub> | 
| <sub> VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.vcf.gz.tbi) </sub> | <sub> [VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.grch38.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.grch38.vcf.gz.tbi) </sub> | 
| <sub> multiple alignment </sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.hal)</sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.hal) </sub> | 
| <sub> sequences clipped out before alignment </sub> | <sub>[masking](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.masking.tar.gz)</sub> | <sub>[masking](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.masking.tar.gz)</sub> | 
| <sub> VG indexes </sub> | <sub>[xg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.xg) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.snarls) &nbsp; &nbsp; [trans](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.trans.gz) </sub> | <sub>[xg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.xg) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.snarls) &nbsp; &nbsp; [trans](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.trans.gz) </sub> |
| <sub> Giraffe indexes </sub> | <sub>[dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.min) &nbsp; &nbsp; [gg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.gg) &nbsp; &nbsp; [gbwt](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.gbwt) </sub> | <sub>[dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.min) &nbsp; &nbsp; [gg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.gg) &nbsp; &nbsp; [gbwt](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.gbwt) </sub> | 

### PGGB

Coming soon
