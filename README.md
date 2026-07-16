# README: In Silico Analysis of CA9 gene Methylation: Insights into its Role in Regulating CA IX Expression and its Clinical Associations

This repository contains a Jupyter Notebook implementing a complete Python pipeline for the full analysis of CA9 methylation used in this manuscript. All datasets were obtained from the Xena database (GDC Hub; https://xenabrowser.net/datapages/), precise links are bellow.

The notebook is fully self-contained and, after adjusting the file paths for the cancer type of interest, can be executed end-to-end to do the whole data aquisition and analysis done in the manuscript. Each step is documented with inline comments. Required packages are automatically checked and installed upon execution.

# Contents
  - merging datasets from Xena
  - location of methylation sites
  - correlation between expression and methylation data
  - CA9 methylation and clinicopathological associations
  - CA9 methylation and associated gene expression patterns
  - DNA methylation and treatment sensitivity
  - survival analysis

# Requirements
  - Python 3.12.7 or higher (tested with Python 3.12.7). Jupyter Notebook 7.4.5 or higher.

The following packages are required and will be automatically checked and installed upon execution:

  - pandas
  - numpy
  - scipy
  - matplotlib
  - requests

# Used databases and access to them

-	cohort: GDC TCGA Breast Cancer (BRCA): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Breast%20Cancer%20(BRCA)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A
-	cohort: GDC TCGA Colon Cancer (COAD): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Colon%20Cancer%20(COAD)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A
-	cohort: GDC TCGA Esophageal Cancer (ESCA): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Esophageal%20Cancer%20(ESCA)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A 
-	cohort: GDC TCGA Head and Neck Cancer (HNSC): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Head%20and%20Neck%20Cancer%20(HNSC)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A 
-	cohort: GDC TCGA Kidney Clear Cell Carcinoma (KIRC): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Kidney%20Clear%20Cell%20Carcinoma%20(KIRC)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A 
-	cohort: GDC TCGA Lung Adenocarcinoma (LUAD): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Lung%20Adenocarcinoma%20(LUAD)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A 
-	cohort: GDC TCGA Prostate Cancer (PRAD): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Prostate%20Cancer%20(PRAD)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A 
-	cohort: GDC TCGA Endometrioid Cancer (UCEC): https://xenabrowser.net/datapages/?cohort=GDC%20TCGA%20Endometrioid%20Cancer%20(UCEC)&removeHub=http%3A%2F%2F127.0.0.1%3A7222&removeHub=https%3A%2F%2Fucscpublic.xenahubs.net&removeHub=https%3A%2F%2Ftcga.xenahubs.net&removeHub=https%3A%2F%2Fpancanatlas.xenahubs.net&removeHub=https%3A%2F%2Ficgc.xenahubs.net&removeHub=https%3A%2F%2Fpcawg.xenahubs.net&removeHub=https%3A%2F%2Ftoil.xenahubs.net&removeHub=https%3A%2F%2Fxena.treehouse.gi.ucsc.edu%3A443&removeHub=https%3A%2F%2Fatacseq.xenahubs.net&removeHub=https%3A%2F%2Fkidsfirst.xenahubs.net&removeHub=https%3A%2F%2Fpreviewsinglecell.xenahubs.net&removeHub=notebook%3A 

For all cancer types we downloaded specifically: Illumina Human Methylation 450 GDC Hub, STAR - TPM GDC Hub, Phenotype GDC Hub, and survival data GDC Hub (all downloaded 10/05/2024). 
