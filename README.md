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

[Minigraph](https://github.com/lh3/minigraph) is a generalization of minimap2 (very fast) which builds the graph with iterative construction. Minigraph aligns with approximate locations and can be used to call structural variants (>50nt). Graphs were built with both GRCh38 and CHM13+Y (found [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/CHM13v11Y.fa.gz)) used as reference sequences.

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> graph </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.gfa.gz) </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.gfa.gz) </sub> |
 <sub> bed </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-grch38.bb.bed.gz.tbi) </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc-v1.0-minigraph-chm13.bb.bed.gz.tbi) </sub> |


### Minigraph/CACTUS

[The CACTUS pangenome pipeline](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/pangenome.md) adds base-level alignments to the minigraph graphs above (so both GRCh38- and CHM13-based graphs are available). 

Graphs and associated files are summarized below. 

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.gfa.gz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.gfa.gz)</sub> | 
| <sub> Decomposed VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc.grch38.vcfbub.a100k.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.vcf.gz.tbi) </sub> | <sub>  </sub> |
| <sub> Pangenie-ready VCF </sub> | <sub>[VCF](https://zenodo.org/record/6797328/files/cactus_filtered_ids.vcf.gz) &nbsp; &nbsp; [VCF index](https://zenodo.org/record/6797328/files/cactus_filtered_ids.vcf.gz.tbi) </sub> | <sub>  </sub> |
| <sub> Raw VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.vcf.gz.tbi) </sub> | <sub> [VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.grch38.vcf.gz) &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.grch38.vcf.gz.tbi) &nbsp; [VCF(CHM13)](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.vcf.gz) &nbsp; [VCF(CHM13) index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.vcf.gz.tbi) </sub> | 
| <sub> multiple alignment </sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.hal)</sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.hal) </sub> | 
| <sub> sequences clipped out before alignment </sub> | <sub>[masking](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.masking.tar.gz)</sub> | <sub>[masking](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.masking.tar.gz)</sub> | 
| <sub> VG indexes </sub> | <sub>[xg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.xg) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.snarls) &nbsp; &nbsp; [trans](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.trans.gz) </sub> | <sub>[xg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.xg) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.snarls) &nbsp; &nbsp; [trans](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.trans.gz) </sub> |
| <sub> Giraffe indexes </sub> | <sub>[dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.dist2) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.min2) &nbsp; &nbsp; [gg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.gg) &nbsp; &nbsp; [gbwt](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.gbwt) &nbsp; &nbsp; [dist(vg<1.44.0)](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.dist)  &nbsp; &nbsp; [min(vg<1.44.0)](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.min)</sub> | <sub>[dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.dist2) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.min2) &nbsp; &nbsp; [gg](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.gg) &nbsp; &nbsp; [gbwt](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.gbwt) &nbsp; &nbsp; [dist(vg<1.44.0)](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.dist) &nbsp; &nbsp; [min(vg<1.44.0)](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.min)</sub> |


The graphs are available in gfa format alongside other graph and index files. Information about the associated file formats can be found:
* graph formats: [xg/gg](https://github.com/vgteam/vg/wiki/Index-Types)
* index formats: [gbwt/dist/min](https://github.com/vgteam/vg/wiki/Index-Types)
* snarls format: [snarls](https://github.com/vgteam/vg/wiki/Index-Construction)

#### VCF Decomposition
The Raw VCF files contain a site for each bubble in the graph. Nested bubbles will result in overlapping sites. The nesting relationships are denoted with the `PS` (parent snarl), `LV` (level) and `AT` (allele traversal) tags and need to be taken into account when interpreting the VCF.  Alternatively, you can use the "Decomposed VCFs" which have been normalized by using [vcfbub](https://github.com/pangenome/vcfbub) to "pop" bubbles with alleles larger than 100k and [vcfwave](https://github.com/vcflib/vcflib/blob/master/doc/vcfwave.md) to realign each alt allele to the reference ([script](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/wave.mc.grch38.a100k.sh)). The "Pangenie-ready VCF" was created using a different decomposition that does not use re-alignment ([description](https://zenodo.org/record/6797328/files/README-HPRC-PanGenie.txt), [intermediate files](https://zenodo.org/record/6797328)), with the aim of optimizing genotyping performance with [Pangenie](https://github.com/eblerjana/pangenie).

#### Filtered Graphs
The [Giraffe](https://www.biorxiv.org/content/10.1101/2020.12.04.412486v2.abstract) short read mapper relies on the graph's snarl decomposition.  The versions of the Cactus/Minigraph graphs released here contain some spurious large deletion edges that make this decomposition less efficient, which impacts Giraffe *runtime*. Furthermore, we have found that for calling small variants with the Giraffe-[DeepVariant](https://doi.org/10.1038/nbt.4235) pipeline, *accuracy* is improved if all alleles with frequency < 10% are removed from the graph before indexing.  Two filtered versions of each of the two Minigraph/Cactus graphs are available [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/freeze1/minigraph-cactus/filtered/).  The graphs with `maxdel.10mb` in the name (recommended to speed up general mapping experiments) were created by removing edges that imply deletions > 10mb, and the graphs with `minaf.0.1` in the name (recommended when using with DeepVariant) were created by removing, in addition to the deletions, nodes that are covered by fewer than 9 haplotypes. When using `vg` version `1.44.0` or later, use the `.dist2` and `.min2` indexes for `vg giraffe` as they are in the new formats. 

#### Masked Sequence
Highly repetitive sequence such as found in centromeres was excluded from the Minigraph/Cactus graphs using the following process. [dna-brnn](https://github.com/lh3/dna-nn) was first run with its default parameters and model to identify alpha satellite and hsat 2/3 regions >100kb, which were clipped out of the input fasta files. Gaps >100kb between minigraph mappings were likewise removed. Any remaining contigs or contig fragments that could not be assigned to a reference chromosome were excluded. Finally, gaps >10kb left unaligned after Cactus were removed. Each removed interval, as well as the step it was removed by, are available:
* regions removed from GRCh38-based graph: [hprc-v1.0-mc-grch38.clipped-intervals.bed.gz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-grch38.clipped-intervals.bed.gz)
* regions removed from CHM13-based graph: [hprc-v1.0-mc-chm13.clipped-intervals.bed.gz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph-cactus/hprc-v1.0-mc-chm13.clipped-intervals.bed.gz)

### PGGB

The Pangenome Graph Builder pipeline ([PGGB](https://github.com/pangenome/pggb)) creates and all-vs-all graph with base-level alignments and no clipping of mitochondrial or centromeric regions.

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
