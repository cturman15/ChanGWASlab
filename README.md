# NHS/NHSII/HPFS/PHS GWAS Studies

## Introduction

The Nurses' Health Study (NHS), Nurses' Health Study II (NHSII), Health Professionals Follow Up Study (HPFS) and the Physicians Health Study (PHS) have collected detailed longitudinal data on multiple exposures and traits for approximately 310,000 study participants over the last 40 years. Over 160,000 study participants across the cohorts have donated a DNA sample and to date, over 47,000 subjects have been genotyped as part of genome-wide association studies (GWAS) of seventeen primary outcomes. However, these studies utilized different GWAS arrays making it difficult to conduct analyses of secondary phenotypes or share controls across studies. To allow for secondary analyses of these data, we have created five datasets merged by platform family ([Table 1](https://docs.google.com/spreadsheets/d/1i8Tl8p1VM2HMXRtavLaLsO1wxT_JeWH-vtNW7aKhnpw/edit?usp=sharing "Table 1. Numbers of GWAS samples in NHS/NHSII/HPFS/PHS cohorts")). The previous version of three datasets were presented in [[1](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5354293/ "Lindström S, Loomis S, Turman C, Huang H, Huang J, Aschard H, et al. A comprehensive survey of genetic variation in 20,691 subjects from four large cohorts. PLoS ONE.(2017);PMID: 28301549")].

We performed imputation using common reference panels, 1,000 Genomes Phase III release, Haplotype Reference Consortium (HRC) release I, and Trans-Omics for Precision Medicine (TOPMed) release II. The pooled resource can be used to maximize power in GWAS of phenotypes collected across the cohorts and for studying gene-environment interactions as well as rare phenotypes and genotypes.  

## GWAS studies and genotyping 

Since 2007, seventeen separate GWAS have been conducted within these four cohorts ([Table 2](https://docs.google.com/spreadsheets/d/1PLOWKqM6Lb15C3e7IIM1VwsAT7H0VJ1QWsVNZSgGitw/edit?usp=sharing "Table 2. GWAS datasets in NHS/NHSII/HPFS/PHS cohorts")). The primary traits are breast cancer, colon cancer, coronary heart disease, endometrial cancer, endometriosis, glaucoma, gout, kidney stone, mammographic density, melanoma, ovarian cancer, pancreatic cancer, post-traumatic stress disorder, prostate cancer, squamous cell carcinoma, type 2 diabetes and Venous thromboembolism. These studies were genotyped on five different arrays. Standard quality control filters for call rate, Hardy-Weinberg equilibrium, and other measures were applied to the genotyped variants or/and samples in the individual studies. In total, these GWAS data sets comprise 47,579 participants including 19,559 from NHS, 13,298 subjects from NHSII, 12,415 subjects from HPFS and 2,307 subjects from PHS.

## Dataset merging and QC

Successfully merging genotype data for different individuals requires complete overlap in variants. We previously looked at the overlap of variants in three different genotyping platform families of the Illumina HumanHap, Illumina OmniExpress and Affymetrix 6.0 arrays. There were high degree of overlap within each platform families, but low overlap across the three platform families ([Figure 1](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5354293/figure/pone.0173997.g001/ "Figure 1. The intersections of three platform families")). The intersection among five platform families was fewer. To achieve the largest GWAS datasets as possible without losing variant information, we crerated five GWAS datasets by platform families - Affymetrix 6.0, Illumina HumanHap, Illumina OmniExpress, HumanCore Exome and Illumina OncoArray.

In the merging process, we removed variants with call rate<5%. We ran a pairwise identity by descent (IBD) analysis within and across the combined dataset to detect duplicate and related individuals. Some of the duplicates flagged were expected, having been genotyped in multiple datasets and hence having the same cohort identifiers. In this case, the sample with lower call rate in each pair was removed from the dataset. In instances where pairs showed pairwise genotype concordance rate>0.999 but were not expected duplicates, both individuals were removed. Related individuals (full siblings, half siblings/avunculars) were not removed from the final datasets. Across the five datasets, we identified 3,166 duplicate pairs (2,828 expected) and thus additional 3,166 dupliate individuals should be removed from analysis across all five platform families ([Table 1](https://docs.google.com/spreadsheets/d/1i8Tl8p1VM2HMXRtavLaLsO1wxT_JeWH-vtNW7aKhnpw/edit?usp=sharing "Table 1. Numbers of GWAS samples in NHS/NHSII/HPFS/PHS cohorts")).

After removing duplicate samples, we used EIGENSTRAT [ac](##-References) to run principal component analysis (PCA) on each dataset

## Imputation

## References
1. Lindström S, Loomis S, Turman C, Huang H, Huang J, Aschard H, et al. A comprehensive survey of 
genetic variation in 20,691 subjects from four large cohorts.
[PLoS ONE.(2017); PMID: 28301549](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5354293/)




