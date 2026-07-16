# README: In Silico Analysis of CA9 gene Methylation: Insights into its Role in Regulating CA IX Expression and its Clinical Associations

This repository contains a Jupyter Notebook implementing a complete Python pipeline for identifying methylation sites of the CA9 gene and their genomic locations, as well as merging publicly available datasets used in this manuscript. All datasets were obtained from the Xena database (GDC Hub; https://xenabrowser.net/datapages/).

The notebook is fully self-contained and, after adjusting the file paths for the cancer type of interest, can be executed end-to-end to identify methylation sites, their genomic locations, and generate the CSV files used in the manuscript. Required packages are automatically checked and installed upon execution.

Code for statistical analysis is available upon request.

# Requirements
Python 3.12.7 or higher (tested with Python 3.12.7). Jupyter Notebook 7.4.5 or higher.

The following packages are required and will be automatically checked and installed upon execution:

  - pandas
  - numpy
  - scipy
  - matplotlib
  - requests
