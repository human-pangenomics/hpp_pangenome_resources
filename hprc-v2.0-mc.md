# HPRC v2.0 Minigraph-Cactus Graphs

**Note:** This page documents the **v2.0** Minigraph-Cactus graphs. The current release is **[v2.1](README.md#minigraph-cactus)**, which improves on v2.0 in two main ways:

1. Mitochondrial start positions in the input assemblies were corrected so that the mitochondria align.
2. Minigraph construction order is determined on a chromosome-by-chromosome basis (v2.0 used the default, whole-genome ordering).

The input assemblies are otherwise nearly the same, so unless you need to reproduce v2.0 results specifically, please consider using v2.1.

[Minigraph-Cactus](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/pangenome.md) ([cite](https://doi.org/10.1038/s41587-023-01793-w)) adds base-level alignment to `minigraph` graphs.

All steps to reproduce the graphs can be found [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/README).

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> Graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.gbz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.gbz)</sub> |
| <sub> Full (Unclipped) Graph </sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.full.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.full.gbz)</sub> | <sub>[gfa](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.full.gfa.gz) &nbsp; &nbsp; [gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.full.gbz)</sub> |
| <sub> Chromosome Graphs </sub> | <sub>[chroms](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.chroms)</sub> | <sub>[chroms](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.chroms)</sub> |
| <sub> Multiple Alignment </sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.full.hal) &nbsp; &nbsp; [TAF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.full.taf.gz) &nbsp; &nbsp; [TAF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.full.taf.gz.tai)</sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.full.hal) &nbsp; &nbsp; [TAF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.full.taf.gz) &nbsp; &nbsp; [TAF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.full.taf.gz.tai)</sub> |
| <sub> vcfwaved VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.wave.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.wave.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.wave.vcf.gz.tbi)</sub> |
| <sub> VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.vcf.gz.tbi)</sub> |
| <sub> Raw VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.raw.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.raw.vcf.gz.tbi)</sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.raw.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.raw.vcf.gz.tbi)</sub> |
| <sub> PanGenie VCFs </sub> | <sub>[biallelic](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.pgbi.vcf.gz) &nbsp; &nbsp; [biallelic index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.pgbi.vcf.gz.tbi) &nbsp; &nbsp; [input](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.pgin.vcf.gz) &nbsp; &nbsp; [input index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.pgin.vcf.gz.tbi)</sub> | <sub>[biallelic](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.pgbi.vcf.gz) &nbsp; &nbsp; [biallelic index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.pgbi.vcf.gz.tbi) &nbsp; &nbsp; [input](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.pgin.vcf.gz) &nbsp; &nbsp; [input index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.pgin.vcf.gz.tbi)</sub> |
| <sub> VG Indexes </sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.gbz) &nbsp; &nbsp; [hapl](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.hapl) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.snarls)</sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.gbz) &nbsp; &nbsp; [hapl](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.hapl) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.snarls)</sub> |
| <sub> AF-Filtered VG Indexes </sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.d46.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.d46.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.d46.min) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.d46.snarls)</sub> | <sub>[gbz](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.d46.gbz) &nbsp; &nbsp; [dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.d46.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.d46.min) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.d46.snarls)</sub> |
| <sub> Reference Gaps </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38/hprc-v2.0-mc-grch38.refgaps.bed)</sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13/hprc-v2.0-mc-chm13.refgaps.bed)</sub> |
| <sub> All Files </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-grch38) </sub> | <sub> [files](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.0/hprc-v2.0-mc-chm13) </sub> |

The graphs are available in gfa format alongside other graph and index files. Information about the associated file formats can be found:
* [mc output overview](https://github.com/ComparativeGenomicsToolkit/cactus/blob/v2.9.7/doc/pangenome.md#output)
* [vg wiki](https://github.com/vgteam/vg/wiki/Index-Types)
* [gbz format](https://github.com/jltsiren/gbwtgraph/blob/master/SERIALIZATION.md) ([cite](https://doi.org/10.1093/bioinformatics/btac656))
* [hapl format](https://github.com/vgteam/vg/wiki/Haplotype-Sampling): allows `vg giraffe` to infer a personalized pangenome as alternative to AF-filtering.

#### VCF Decomposition
Three VCFs are provided for each graph, from least to most processed:

* **Raw VCF** (`.raw.vcf.gz`): a site for each bubble in the graph. Nested bubbles result in overlapping sites, with the nesting relationships denoted by the `PS` (parent snarl), `LV` (level) and `AT` (allele traversal) tags, which need to be taken into account when interpreting the VCF.
* **VCF** (`.vcf.gz`): nested bubbles have been "popped" with [vcfbub](https://github.com/pangenome/vcfbub) (removing alleles larger than 100kb), but the alt alleles have not been realigned.
* **vcfwaved VCF** (`.wave.vcf.gz`): as above, with each alt allele additionally realigned to the reference using [vcfwave](https://github.com/vcflib/vcflib/blob/master/doc/vcfwave.md) plus further normalization.

Unlike the v1.1 graphs (which used vcfbub and vcfwave only), the v2.0 decomposition applies additional normalization, built into Minigraph-Cactus via the `--vcfwave` option:

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

#### PanGenie VCFs
The **PanGenie VCFs** were normalized using [PanGenie's pipeline](https://github.com/eblerjana/genotyping-pipelines/tree/master/prepare-vcf-MC) for use with [PanGenie](https://github.com/eblerjana/pangenie):

* The `.pgbi.vcf.gz` (biallelic) files are an alternative to the `.wave.vcf.gz` files above. Rather than realigning large bubbles, this approach uses the paths in the graph to split them up.
* The `.pgin.vcf.gz` (input) files are the PanGenie input VCFs and can be used to genotype other samples with PanGenie.

#### Evaluation Graphs
Versions of the CHM13 and GRCh38-based graphs are [available here](https://s3-us-west-2.amazonaws.com/human-pangenomics/index.html?prefix=pangenomes/freeze/release2/minigraph-cactus/v2.0/benchmark-graphs/) with `HG002`, `HG005`, and `NA19240` excluded. Use these if, for example, you are running Genome-In-A-Bottle benchmarks.

#### Reference Assemblies
Slightly different reference assemblies were used in the two graphs in order to handle the fact that `CHM13v2.0` has `chrY` from `HG002`, and that `GRCh38` unplaced contigs aren't wanted except when `GRCh38` is the reference.

* `hprc-v2.0-mc-chm13` : `CHM13v2.0`, `GRCh38` (chromosomes only)
* `hprc-v2.0-mc-grch38` : `CHM13v2.0` (without `chrY`), `GRCh38`

(GRCh37-based v2.0 graphs are not available; see the [v2.1 graphs](README.md#minigraph-cactus) for a GRCh37 graph.)

#### Filtered Graphs
The "AF-Filtered VG indexes" above were created by dropping nodes and edges supported by fewer than 10% of haplotypes, and give the best performance for Giraffe. Note that `giraffe` requires only the `.gbz`, `.dist` and `.min` indexes.

#### Reference Gaps
Regions unaligned in the reference (predominantly satellite sequences) are provided in the refgaps BED file.
