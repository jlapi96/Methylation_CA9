# README: In Silico Analysis of CA9 gene Methylation: Insights into its Role in Regulating CA IX Expression and its Clinical Associations

This repository contains a Jupyter Notebook implementing a complete Python pipeline for the full analysis of CA9 methylation used in this manuscript. All datasets were obtained from the Xena database (GDC Hub; https://xenabrowser.net/datapages/).

The notebook is fully self-contained and, after adjusting the file paths for the cancer type of interest, can be executed end-to-end to do the whole data aquisition and analysis in the manuscript. Required packages are automatically checked and installed upon execution.

# Contents
  - merging datasets from Xena
  - location of methylation sites
  - correlation between expression and methylation
  - CA9 methylation and clinicopathological associations
  - CA9 methylation and associated gene expression patterns
  - DNA methylation and treatment sensitivity
  - survival analysis

# Requirements
Python 3.12.7 or higher (tested with Python 3.12.7). Jupyter Notebook 7.4.5 or higher.

The following packages are required and will be automatically checked and installed upon execution:

  - pandas
  - numpy
  - scipy
  - matplotlib
  - requests

