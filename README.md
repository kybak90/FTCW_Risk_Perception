
<!-- README.md is generated from README.Rmd. Please edit that file -->

## Overview

This repository contains the code used for the analysis in the paper:

**“Role of government and information trust in public perception of
environmental risk: a case study of treated contaminated water discharge
in Fukushima.”**

The primary goal of this repository is to ensure **transparency and
reproducibility** of the empirical results presented in the study. All
scripts included here are designed to replicate the main statistical
analyses, figures, and tables reported in the manuscript.

The study investigates how **trust in government and information
sources** shapes public perception of environmental risk, focusing on
the case of treated contaminated water discharge from Fukushima. Using
survey data, we examine the relationship between trust, risk perception,
and related covariates through a series of statistical models.

------------------------------------------------------------------------

## Contact

For questions related to the analysis or code in this repository, please
contact:

Kwan-Young Bak, Professor  
Sungshin Women’s University  
Email: <kybak@sungshin.ac.kr>  
ORCID: <https://orcid.org/0000-0002-4541-160X>

As a co-author of the paper, I am happy to provide clarification on the
analysis workflow, variable construction, and implementation details
where needed.

------------------------------------------------------------------------

## Contents

This repository includes:

- Data preprocessing scripts  
- Statistical analysis code  
- Code for generating tables and figures in the manuscript  
- Figures and tables presented in the manuscript

Due to data sharing restrictions, the raw dataset is not publicly
available. However, we provide a detailed mapping table that links (i)
variable names in the raw data, (ii) variable names used in the analysis
code, and (iii) variable names reported in the manuscript. In addition,
this repository includes all code required to reproduce the figures and
tables presented in the paper.

Through this setup, readers can transparently trace the full data
analysis workflow, from variable construction to final results. While
the original data cannot be shared, the structure of the analysis and
the logic underlying each step are fully documented and reproducible.

Below, we outline the complete analysis pipeline and provide the
corresponding code. For detailed methodological descriptions and formal
model specifications, please refer to the manuscript.

------------------------------------------------------------------------

## Notes

- The code was developed for research purposes and may require
  adaptation for use in other contexts.  
- Please refer to the manuscript for detailed methodological
  explanations and interpretation of results.

------------------------------------------------------------------------

## Repository Structure

The repository is organized to reflect the full analysis workflow,
including code and outputs corresponding to the manuscript. The dataset
used here is not publicly available.

``` bash
📁 FTCW_Risk_Perception/
├── Analysis Workflow.Rmd       # Main analysis script (reproduces all results)
├── Analysis-Workflow.html      # Rendered HTML of the main analysis
├── Variable Codebook.Rmd       # Variable mapping and data processing details
├── Variable-Codebook.html      # Rendered HTML of the variable codebook
│
├── 📁 data/
│   └── 23_08.xlsx              # Raw survey data (not publicly distributable)
│
├── 📁 figure/
│   ├── rel_imp.pdf             # ✓ Figure 2 (Manuscript)
│   ├── interaction_plot.pdf    # ✓ Figure 3 (Manuscript)
│   ├── missing_pattern.pdf     # ✓ Figure S1 (Appendix A)
│   ├── traceplot.pdf           # ✓ Figure S2 (Appendix A)
│   ├── modelplot_mice.pdf      # Internal diagnostic plot (not in manuscript)
│   └── mosaicplot.pdf          # ✓ Figure S3 (Appendix C)
│
└── 📁 latex_table/
    ├── table_1.txt             # ✓ Table 1 (Manuscript)
    ├── table_s2.txt            # ✓ Table S1 (Appendix A)
    ├── table_s3.txt            # ✓ Table S2 (Appendix B)
    ├── rp-mice.txt             # ✓ Table S3 (Appendix D)
    ├── rp-interaction.txt      # ✓ Table S4 (Appendix E)
    ├── rp-sensitivity-cog.txt  # ✓ Table S5 (Appendix F)
    └── rp-sensitivity-aff.txt  # ✓ Table S6 (Appendix F)
```

### Description

- **Analysis Workflow.Rmd:** A single, integrated R Markdown file that
  contains the complete analysis pipeline, from data preprocessing to
  final model estimation and output generation. See
  **Analysis-Workflow.html** for the rendered output.

- **Variable Codebook.Rmd:** An R Markdown file that generates
  **Variable-Codebook.html**, which documents the detailed mapping of
  variables used in the analysis, along with key preprocessing steps.

- **data/** Contains the original survey dataset used in the study. Due
  to data sharing restrictions, this file is not publicly accessible.

- **figure/** Includes all figures generated in the analysis. Each file
  is directly mapped to the corresponding figure in the manuscript or
  appendix.

- **latex_table/** Contains text files of LaTeX-formatted tables used in
  the manuscript and appendices, allowing direct integration into the
  paper.

------------------------------------------------------------------------

## R Session Information

All analyses and code in this repository were implemented in **R**. The
computational environment used for the analysis is provided below to
ensure reproducibility.

``` r
sessionInfo()
#> R version 4.4.1 (2024-06-14)
#> Platform: aarch64-apple-darwin20
#> Running under: macOS 26.2
#> 
#> Matrix products: default
#> BLAS:   /Library/Frameworks/R.framework/Versions/4.4-arm64/Resources/lib/libRblas.0.dylib 
#> LAPACK: /Library/Frameworks/R.framework/Versions/4.4-arm64/Resources/lib/libRlapack.dylib;  LAPACK version 3.12.0
#> 
#> locale:
#> [1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8
#> 
#> time zone: Asia/Seoul
#> tzcode source: internal
#> 
#> attached base packages:
#> [1] grid      stats     graphics  grDevices utils     datasets  methods  
#> [8] base     
#> 
#> other attached packages:
#>  [1] kableExtra_1.4.0   knitr_1.49         mice_3.19.0        vcd_1.4-13        
#>  [5] relaimpo_2.2-7     mitools_2.4        survey_4.4-2       survival_3.7-0    
#>  [9] Matrix_1.7-1       boot_1.3-31        MASS_7.3-61        naniar_1.1.0      
#> [13] pals_1.9           xtable_1.8-4       broom_1.0.7        ggeffects_1.7.2   
#> [17] modelsummary_2.2.0 corrplot_0.95      lubridate_1.9.3    forcats_1.0.0     
#> [21] stringr_1.5.1      dplyr_1.1.4        purrr_1.0.4        readr_2.1.5       
#> [25] tidyr_1.3.1        tibble_3.2.1       tidyverse_2.0.0    ggpubr_0.6.0      
#> [29] ggmosaic_0.3.3     ggplot2_3.5.2      gridExtra_2.3      readxl_1.4.3      
#> 
#> loaded via a namespace (and not attached):
#>  [1] DBI_1.2.3         rlang_1.1.5       magrittr_2.0.3    compiler_4.4.1   
#>  [5] systemfonts_1.1.0 vctrs_0.6.5       maps_3.4.2        pkgconfig_2.0.3  
#>  [9] shape_1.4.6.1     fastmap_1.2.0     backports_1.5.0   rmarkdown_2.29   
#> [13] tzdb_0.4.0        nloptr_2.1.1      visdat_0.6.0      xfun_0.49        
#> [17] glmnet_4.1-8      jomo_2.7-6        jsonlite_1.8.9    pan_1.9          
#> [21] R6_2.6.1          tables_0.9.31     stringi_1.8.7     rpart_4.1.23     
#> [25] car_3.1-3         lmtest_0.9-40     cellranger_1.1.0  Rcpp_1.1.0       
#> [29] iterators_1.0.14  zoo_1.8-15        splines_4.4.1     nnet_7.3-19      
#> [33] timechange_0.3.0  tidyselect_1.2.1  rstudioapi_0.17.1 dichromat_2.0-0.1
#> [37] abind_1.4-8       yaml_2.3.10       codetools_0.2-20  lattice_0.22-6   
#> [41] withr_3.0.2       evaluate_1.0.1    xml2_1.3.8        pillar_1.10.2    
#> [45] carData_3.0-5     foreach_1.5.2     insight_0.20.5    plotly_4.10.4    
#> [49] generics_0.1.3    hms_1.1.3         munsell_0.5.1     scales_1.3.0     
#> [53] minqa_1.2.8       glue_1.8.0        mapproj_1.2.11    lazyeval_0.2.2   
#> [57] tools_4.4.1       data.table_1.16.2 lme4_1.1-35.5     ggsignif_0.6.4   
#> [61] colorspace_2.1-1  nlme_3.1-166      Formula_1.2-5     cli_3.6.4        
#> [65] viridisLite_0.4.2 svglite_2.1.3     corpcor_1.6.10    gtable_0.3.6     
#> [69] rstatix_0.7.2     digest_0.6.37     ggrepel_0.9.6     htmlwidgets_1.6.4
#> [73] htmltools_0.5.8.1 lifecycle_1.0.4   httr_1.4.7        mitml_0.4-5
```
