---
layout: page
title: Single-cell omics
description: single cell RNASeq data analysis with application to neurodegenerative diseases
img: /assets/img/single_cell1.png
importance: 2
category: work
---

Single-cell sequencing is a fast-growing technology in biology. It enables us to study the mechanism of biogical processes and diseases at single cell level. Single-cell RNA sequencing (scRNASeq) measures gene expression in each individual cell, allowing for identifying novel cell types; single-cell DNA sequencing can detect somatic mutations, which can be used to trace the evolution of cell lineages; single-cell ATAC-Seq can identify regulatory regions in each cell, in order to infer cell-type specific transcriptional networks. We are working on developing statistical tools to analyze single-cell sequencing data and integrate different omics to study the dynamics of cell states.  

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/fcell-06-00028-g001.jpeg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Timeline of single cell sequencing techonologies. (https://www.frontiersin.org/articles/10.3389/fcell.2018.00028/full)
</div>

A main challenge in analyzing scRNA-seq data is to reduce technical variations yet retain cell heterogeneity. Due to low mRNAs content per cell and molecule losses during the experiment (called ''dropout"), the gene expression matrix has a substantial amount of zero read counts. Some of the zeros as technical artifacts because of "dropout" and others are biological true zero as the gene is not expressed in the cell. The idea of imputation is to use the gene expression of other similar cells and co-expressed genes (e.g. in the same pathway) to identify whether the zero is true biological zero or "dropout", and impute the true gene expression for the latter case. Existing imputation methods treat either each cell or each gene as independently and identically distributed, which oversimplifies the gene correlation and cell type structure. We propose a statistical model-based approach, called SIMPLEs (SInglecell RNA-seq iMPutation and celL clustErings), which iteratively identifies correlated gene modules and cell clusters and imputes dropouts customized for individual gene module and cell type. Simultaneously, it quantifies the uncertainty of imputation and cell clustering via multiple imputations. We model the gene expression by a mixture of zero-inflated censored multivariate Gaussian distribution, where the zero component is for "dropout" event. We then model the co-expression of gene modules by a factor model. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/simples1.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Overview of SIMPLEs. SIMPLEs outputs the imputed gene expression matrix, cell clusters and gene modules.
</div>

By applying SIMPLEs to several real datasets, we could identify cell clusters and discovered gene modules that can further classify subtypes of cells. Our imputations successfully recovered the expression trends of marker genes in stem cell differentiation and can discover putative pathways regulating biological processes. 


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/simples2.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
     t-SNE visualization of imputed data by SIMPLEs for mouse immune cells.
</div>

Based on scRNASeq data, we study microglial-derived inflammation in neurodegenerative diseases and identify a subclass of microglia in mouse models of amyotrophic lateral sclerosis (ALS) which we term RIPK1-Regulated Inflammatory Microglia (RRIMs). RRIMs show significant up-regulation of classical proinflammatory pathways, and can be suppressed by inhibiting RIPK1. These findings help to elucidate a mechanism by which RIPK1 kinase inhibition has been shown to provide therapeutic benefit in mouse models of ALS and may provide an additional biomarker for analysis in ongoing phase 2 clinical trials of RIPK1 inhibitors in ALS. In the study of brain endothelial cells (EC) in Alzheimer’s Disease (AD), we find selective reduction of venous and capillary ECs in AD.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/single_cell_AD.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
     scRNA-Seq of Brain ECs Reveals a Selective Reduction of vECs and capECs in AD.
</div>

# References

* Zhirui Hu, Songpeng Zu, Jun S Liu. SIMPLEs: a single-cell RNA sequencing imputation strategy preserving gene modules and cell clusters variation. NAR Genomics and Bioinformatics, 2020, 2(4): lqaa077. <a href="https://academic.oup.com/nargab/article/2/4/lqaa077/5912574">Link</a>

* Lauren Mifflin, Zhirui Hu, Connor Dufort, Cynthia C Hession, Alec J Walker, Kongyan Niu, Hong Zhu, Nan Liu, Jun S Liu, Joshua Z Levin, Beth Stevens, Junying Yuan, and Chengyu Zou. A RIPK1-Regulated Inflammatory Microglial State in Amyotrophic Lateral Sclerosis. Proceedings of the National Academy of Sciences, 2021, 118 (13): e2025102118. <a href="https://www.pnas.org/content/118/13/e2025102118">Link</a>

* Chengyu Zou, Lauren Mifflin, Zhirui Hu, Tian Zhang, Bing Shan, Huibing Wang, Xin Xing, Hong Zhu, Xian Adiconis, Joshua Z. Levin, Fupeng Li, Chuan-Fa Liu, Jun S. Liu, Junying Yuan. Reduction of mNAT1/hNAT2 Contributes to Cerebral Endothelial Necroptosis and Aβ Accumulation in Alzheimer’s Disease. Cell Reports, 2020, 33(10): 108447.  <a href="https://www.sciencedirect.com/science/article/pii/S2211124720314364">Link</a>

* <a href="https://github.com/JunLiuLab/SIMPLEs">SIMPLEs</a>: single-cell RNA sequencing imputation and clustering. R package.

<!---
The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
```
-->