# Breast Cancer Subtype Discovery: Gene Data Analysis

## Introduction
This repository contains the full statistical analysis conducted for the *Statistical Foundations for Data Science* course during my master's degree.

The project applies dimensionality reduction (PCA) and unsupervised classification (K-means) to the METABRIC breast cancer gene expression dataset. The goal is to identify distinct molecular subtypes of tumors and evaluate their relationship with the [Nottingham score](https://en.wikipedia.org/wiki/Nottingham_Prognostic_Index).

## Setup and Dependencies
### Software Prerequisites
To execute and read this project you must have the following installed:
* **R** (version 4.0 or higher) [download here](https://cran.rstudio.com/)
* **RStudio** for viewing the .Rmd file [download here](https://posit.co/download/rstudio-desktop/)

### Required R Packages
The following packages must be installed in your R environment. 
You can install them using the command: *install.packages("package_name")*.

* **tidyverse** &rarr; Data manipulation, cleaning and reading
* **FactoMineR** &rarr; PCA function
* **factoextra** &rarr; Visualization functions
* **cluster** &rarr; clustering functions

## Repository Structure
``` bash
.
├── breast_cancer_analysis.pdf      (The final rendered output document)
├── breast_cancer_analysis.Rmd      (The complete R Markdown source code)
├── data
│   └── METABRIC_RNA_Mutation.csv   (The raw gene expression and mutation data)
├── README.md
└── sujet.pdf                       (The project subject in french)
``` 
## Summary of the Methodology
1. **Feature Selection**: reducing the number of variables to 100 based on their correlation with the Nottingham score.
2. **PCA**: running a normalized PCA on the 100 genes (the top 34 components are retained based on the 80.1% cumulative variance).
3. **Clustering**: first I used the Elbow method to determine the optimal number of clusters. K-mean is then applied with the chosen number of clusters to assign patients to a final tumor subtype.
4. **Validation**: The Chi2 test is performed to see if the resulting K-means clusters are statistically associated with categorical medical variables.
5. **Prediction**: A linear regression model is constructed to predict the continuous Nottingham score.

## Author


**Justine Andreolli**  _alias_ [@jandreolli](https://github.com/jandreolli)
