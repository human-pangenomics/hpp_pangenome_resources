# HPRC Pangenome Resources

This repo describes pangenomes produced by the [Human Pangenome Reference Consortium](https://humanpangenome.org/) from year 1 data. For information about data reuse and publicating with HPRC data please see the HPRC's Data Use Protocol.

Note: The pangenomes and resultant files referred to in this repo have not been fully QC'd, are not published, and may have known issues.

## Assembly Inputs

Information about the source assemblies can be found in the [HPRC Assembly GitHub repository](https://github.com/human-pangenomics/HPP_Year1_Assemblies). Of the 47 samples assembled (94 assemblies) in year 1, all but three samples were included in graph constructions (HG002, HG005 and NA19240 were excluded for evaluation purposes). GRCh38 and CHM13 were added to make the total number of haplotypes included 90.

## Minigraph

CHM13 and GRCh38 graphs are available from [minigraph](https://github.com/lh3/minigraph).

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> graph </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc.minigraph.grch38.v1.0.gfa.gz) </sub> | <sub>[graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc.minigraph.chm13.v1.0.gfa.gz) </sub> |
 <sub> bed </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc.minigraph.grch38.v1.0.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc.minigraph.grch38.v1.0.bb.bed.gz.tbi) </sub> | <sub>[bed](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc.minigraph.chm13.v1.0.bb.bed.gz) &nbsp; &nbsp; [index](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/hprc.minigraph.chm13.v1.0.bb.bed.gz.tbi) </sub> |

The CHM13 (plus Y) input sequence can be found [here](https://s3-us-west-2.amazonaws.com/human-pangenomics/pangenomes/freeze/freeze1/minigraph/CHM13v11Y.fa.gz)

## Minigraph/CACTUS

[The CACTUS pangenome pipeline's](https://github.com/ComparativeGenomicsToolkit/cactus/blob/master/doc/pangenome.md) graphs and associated files are summarized below. 

| <sub>**Description**</sub> | <sub>**GRCh38 Graph**</sub> | <sub>**CHM13 Graph**</sub> |
| :-------- | :------ | :------ |
| <sub> graph </sub> | <sub>[base graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.gfa.gz)</sub> | <sub>[base graph](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.gfa.gz)</sub> | 
| <sub> VCF </sub> | <sub>[VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.vcf.gz.tbi) </sub> | <sub> [VCF](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.GRCh38.vcf.gz) &nbsp; &nbsp; [VCF index](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.GRCh38.vcf.gz.tbi) </sub> | 
| <sub> multiple alignment </sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.hal)</sub> | <sub>[HAL](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.hal) </sub> | 
| <sub> sequences clipped out before alignment </sub> | <sub>[masking](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11-masking.tar.gz)</sub> | <sub>[masking](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11-masking.tar.gz)</sub> | 
| <sub> VG indexes </sub> | <sub>[xg](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.xg) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.snarls) &nbsp; &nbsp; [trans](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.trans.gz) </sub> | <sub>[xg](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.xg) &nbsp; &nbsp; [snarls](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.snarls) &nbsp; &nbsp; [trans](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.trans.gz) </sub> |
| <sub> Giraffe indexes </sub> | <sub>[dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.min) &nbsp; &nbsp; [gg](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.gg) &nbsp; &nbsp; [gbwt](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/GRCh38-f1g-90-mc-aug11.gbwt) </sub> | <sub>[dist](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.dist) &nbsp; &nbsp; [min](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.min) &nbsp; &nbsp; [gg](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.gg) &nbsp; &nbsp; [gbwt](https://s3-us-west-2.amazonaws.com/human-pangenomics/scratch/2021_08_11_minigraph_cactus/CHM13-f1g-90-mc-aug11.gbwt) </sub> | 


