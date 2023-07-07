# HPRC Pangenome Resources

This repo describes pangenomes produced by the [Human Pangenome Reference Consortium](https://humanpangenome.org/) from year 1 data. For information about data reuse and publicating with HPRC data please see the HPRC's Data Use Protocol.

Note: The pangenomes and resultant files referred to in this repo have not been fully QC'd, are not published, and may have known issues.

## Background Information

### Preprint

[A Draft Human Pangenome Reference](https://www.biorxiv.org/content/10.1101/2022.07.09.499321v1)

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

Index files listing file locations for download with the AWS CLI can be found in the indexes folder of this repository. Alternatively, tables are listed below in each graph creation strategy's section. Note that the index files list the file locations with s3:// uris -- as opposed to http:// urls as found in the tables.

### Assembly Inputs

Information about the source assemblies can be found in the [HPRC Assembly GitHub repository](https://github.com/human-pangenomics/HPP_Year1_Assemblies). Of the 47 samples assembled (94 assemblies) in year 1, all but three samples were included in graph constructions (HG002, HG005 and NA19240 were excluded for evaluation purposes). GRCh38 and CHM13 were added to make the total number of haplotypes included 90.


## Graphs
### Minigraph

[Minigraph](https://github.com/lh3/minigraph) ([cite](https://doi.org/10.1186/s13059-020-02168-z)) is a generalization of minimap2 (very fast) which builds the graph with iterative construction. Minigraph aligns with approximate locations and can be used to call structural variants (>50nt). Graphs were built with both GRCh38 and CHM13+Y (found [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/CHM13v11Y.fa.gz)) used as reference sequences.

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> graph </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.gfa.gz) </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.gfa.gz) </sub> |
 <sub> bed </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.bb.bed.gz.tbi) </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.bb.bed.gz.tbi) </sub> |


### Minigraph-Cactus

[Minigraph-Cactus](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/pangenome.md) ([cite](https://doi.org/10.1038/s41587-023-01793-w)) adds base-level alignment to `minigraph` graphs.

**Note:** The links below have been updated to point to [version 1.1](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/mc-pangenomes/hprc-v1.1-mc.md) of the graphs which contain numerous bug fixes and updated file formats.  The original version 1.0 graph that was described in [the HPRC paper](https://doi.org/10.1038/s41586-023-05896-x), has been moved [here](hprc-v1.0-mc.md). The input assemblies are the same for both versions, so unless you are trying to exactly reproduce results from the paper, please consider using the updated version.  

Graphs and associated files are summarized below. 

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> Graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.gbz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.gbz)</sub> |
| <sub> Full (Unclipped) Graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.full.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.full.gbz) &nbsp; &nbsp; [odgi](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.full.og) </sub> | <sub> [gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.full.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.full.gbz) &nbsp; &nbsp; [odgi](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.full.og)</sub> |
| <sub> Chromosome Graphs </sub> | <sub>[chroms](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.chroms) </sub> | <sub>[chroms](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.chroms) </sub> |
| <sub> Decomposed VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.vcfbub.a100k.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.vcfbub.a100k.wave.vcf.gz.tbi) </sub> | <sub> [VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.vcfbub.a100k.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.vcfbub.a100k.wave.vcf.gz.tbi) &nbsp; &nbsp; [GRCh38-VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.GRCh38.vcfbub.a100k.wave.vcf.gz) &nbsp; &nbsp; [GRCh38-VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.GRCh38.vcfbub.a100k.wave.vcf.gz.tbi) </sub> |
| <sub> Raw VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.raw.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.raw.vcf.gz.tbi) </sub> | <sub> [VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.raw.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.raw.vcf.gz.tbi) &nbsp; &nbsp; [GRCh38-VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.GRCh38.raw.vcf.gz) &nbsp; &nbsp; [GRCh38-VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.GRCh38.raw.vcf.gz.tbi) </sub> |
| <sub> Multiple Alignment </sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.full.hal)</sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.full.hal) </sub> | 
| <sub> VG Indexes </sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.min) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.snarls)  </sub> | <sub> [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.min) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.snarls)  </sub> |
| <sub> AF-Filtered VG Indexes </sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.d9.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.d9.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.d9.min) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.d9.snarls)  </sub> | <sub> [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.d9.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.d9.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.d9.min) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.d9.snarls)  </sub> |
| <sub> Excluded Regions </sub> | <sub> [full graph bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.full.cut.bed) &nbsp; &nbsp; [clipped graph bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.cut.bed)</sub> | <sub> [full graph bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38/hprc-v1.1-mc-grch38.full.cut.bed) &nbsp; &nbsp; [clipped graph bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13/hprc-v1.1-mc-chm13.cut.bed)</sub> |
| <sub> All Files </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-grch38) </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.1-mc-chm13)</sub> |

The graphs are available in gfa format alongside other graph and index files. Information about the associated file formats can be found:
* [mc output overview](https://github.com/ComparativeGenomicsToolkit/cactus/blob/v2.6.4/doc/pangenome.md#output)
* [vg wiki](https://github.com/vgteam/vg/wiki/Index-Types)
* [gbz format](https://github.com/jltsiren/gbwtgraph/blob/master/SERIALIZATION.md) ([cite](https://doi.org/10.1093/bioinformatics/btac656))

#### VCF Decomposition
The Raw VCF files contain a site for each bubble in the graph. Nested bubbles will result in overlapping sites. The nesting relationships are denoted with the `PS` (parent snarl), `LV` (level) and `AT` (allele traversal) tags and need to be taken into account when interpreting the VCF.  Alternatively, you can use the "Decomposed VCFs" which have been normalized by using [vcfbub](https://github.com/pangenome/vcfbub) to "pop" bubbles with alleles larger than 100k and [vcfwave](https://github.com/vcflib/vcflib/blob/master/doc/vcfwave.md) to realign each alt allele to the reference ([script](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/wave.mc.grch38.a100k.sh)). Note that in order to reproduce the PanGenie analyses from the papers, you should instead use the [PanGenie HPRC Workflow](https://bitbucket.org/jana_ebler/hprc-experiments/src/master/genotyping-experiments/). This workflow has a [CHM13 branch](https://bitbucket.org/jana_ebler/hprc-experiments/branch/chm13-based-pipeline) to use when working with that reference.

The exact tools and commands used to produce the VCFs are given [here](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/mc-pangenomes/hprc-v1.1-mc.md).


#### Filtered Graphs
The "AF-Filtered VG indexes" above were created by dropping nodes and edges supported by fewer than 10% of haplotypes, and give the best performance for Giraffe and are what have been used in the various papers to date. Note that `giraffe` requires only the `.gbz`, `.dist` and `.min` indexes.  


#### Excluded Sequence
Some input contigs could not be assigned to a reference chromosome and were dropped.  See the "full graph bed" files above for a listing of these.  Contig fragments >10kb that did not map anywhere were likewise excluded (these regions are predominantly centromeric).  See the "clipped graph bed" files above for these regions (this file includes the unassigned contigs). `dna-brnn` was not used to make these graphs.

### PGGB

The Pangenome Graph Builder pipeline ([PGGB](https://github.com/pangenome/pggb)) ([cite](https://doi.org/10.1101/2023.04.05.535718)) creates and all-vs-all graph with base-level alignments and no clipping of mitochondrial or centromeric regions.

Graphs and associated files are summarized below. 

| <sub>**Description**</sub> | <sub>**Location**</sub> |
| :-------- | :------ |
| <sub> graph </sub> | <sub> [gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/hprc-v1.0-pggb.gfa.gz) </sub> |
| <sub> untangle </sub> | <sub> [delta](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/untangle/hprc-v1.0-pggb.all.vs.grch38.untangle-m10000-s0-j0.delta.gz) &nbsp; &nbsp; [paf](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/untangle/hprc-v1.0-pggb.all.vs.grch38.untangle-m10000-s0-j0.paf.gz) </sub> |
| <sub> Decomposed VCFs </sub> | <sub> [GRCh38 VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/hprc-v1.0-pggb.grch38.vcfbub.a100k.wave.vcf.gz) &nbsp; &nbsp; [GRCh38 VCF Index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/hprc-v1.0-pggb.grch38.vcfbub.a100k.wave.vcf.gz.tbi) </sub> |
| <sub> Raw VCFs </sub> | <sub> [chm13.1-22+X](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/hprc-v1.0-pggb.chm13.1-22%2BX.vcf.gz) &nbsp; &nbsp; [chm13.M](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/hprc-v1.0-pggb.chm13.M.vcf.gz) &nbsp; &nbsp; [grch38.1-22+X](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/hprc-v1.0-pggb.grch38.1-22%2BX.vcf.gz) &nbsp; &nbsp; [grch38.M](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/hprc-v1.0-pggb.grch38.M.vcf.gz) &nbsp; &nbsp; [grch38.Y](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/hprc-v1.0-pggb.grch38.Y.vcf.gz) </sub> |


Graph chromosome files and images can be found [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/freeze1/pggb/chroms/) and [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/freeze1/pggb/images/).

See [above](#vcf-decomposition) for more information of VCF decomposition ([script](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/pggb/vcfs/wave.pggb.grch38.a100k.sh)). 

### Change Log

```
* Dec 03, 2021: updated minigraph-cactus VCFs to fix headers (thanks to Wen-Wei)
```
