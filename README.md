# NHS/NHSII/HPFS/PHS GWAS Studies

## Introduction

The Nurses' Health Study (NHS), Nurses' Health Study II (NHSII), Health Professionals Follow Up Study (HPFS) and the Physicians Health Study (PHS) have collected detailed longitudinal data on multiple exposures and traits for approximately 310,000 study participants over the last 40 years. Over 160,000 study participants across the cohorts have donated a DNA sample and to date, over 47,000 subjects have been genotyped as part of genome-wide association studies (GWAS) of seventeen primary outcomes. However, these studies utilized different GWAS arrays making it difficult to conduct analyses of secondary phenotypes or share controls across studies. To allow for secondary analyses of these data, we have created five datasets merged by platform family ([Table 1](https://docs.google.com/spreadsheets/d/1i8Tl8p1VM2HMXRtavLaLsO1wxT_JeWH-vtNW7aKhnpw/edit?usp=sharing "Table 1. Numbers of GWAS samples in NHS/NHSII/HPFS/PHS cohorts")). The previous version of three datasets were presented in [^1].

We performed imputation using common reference panels, the 1,000 Genomes Phase III release, Haplotype Reference Consortium (HRC) release I, and Trans-Omics for Precision Medicine (TOPMed) release II. The pooled resource can be used to maximize power in GWAS of phenotypes collected across the cohorts and for studying gene-environment interactions as well as rare phenotypes and genotypes.  

## GWAS studies and genotyping 

Since 2007, seventeen separate GWAS have been conducted within these four cohorts ([Table 2](https://docs.google.com/spreadsheets/d/1PLOWKqM6Lb15C3e7IIM1VwsAT7H0VJ1QWsVNZSgGitw/edit?usp=sharing "Table 2. GWAS datasets in NHS/NHSII/HPFS/PHS cohorts")). The primary traits are breast cancer, colon cancer, coronary heart disease, endometrial cancer, endometriosis, glaucoma, gout, kidney stone, mammographic density, melanoma, ovarian cancer, pancreatic cancer, post-traumatic stress disorder, prostate cancer, squamous cell carcinoma, type 2 diabetes and Venous thromboembolism. These studies were genotyped on five different arrays. Standard quality control filters for call rate, Hardy-Weinberg equilibrium, and other measures were applied to the genotyped variants or/and samples in the individual studies. In total, these GWAS data sets comprise 47,579 participants including 19,559 from NHS, 13,298 subjects from NHSII, 12,415 subjects from HPFS and 2,307 subjects from PHS.

## Dataset merging and QC

Successfully merging genotype data for different individuals requires complete overlap in variants. We previously looked at the overlap of variants in three different genotyping platform families of the Illumina HumanHap, Illumina OmniExpress and Affymetrix 6.0 arrays. There were high degree of overlap within each platform families, but low overlap across the three platform families ([Figure 1](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5354293/figure/pone.0173997.g001/ "Figure 1. The intersections of three platform families")). The intersection among five platform families was fewer. To achieve the largest GWAS datasets as possible without losing variant information, we created five GWAS datasets by platform families - the Affymetrix 6.0, Illumina HumanHap, Illumina OmniExpress, HumanCore Exome and Illumina OncoArray.

In the merging process, we removed variants with call rate<5%. We ran pairwise identity by descent (IBD) analyses within and across the combined datasets to detect duplicate and related individuals. Some of the duplicates flagged were expected, having been genotyped in multiple datasets and hence having the same cohort identifiers. In this case, the sample with lower call rate in each pair was removed from the dataset. In instances where pairs showed pairwise genotype concordance rate>0.999 but were not expected duplicates, both individuals were removed. Related individuals (full siblings, half siblings/avunculates) were not removed from the final datasets. Across the five datasets, we identified 2,997 duplicate pairs (2,828 expected) and thus additional 3,166 duplicate individuals should be removed from analysis across all five platform families ([Table 1](https://docs.google.com/spreadsheets/d/1i8Tl8p1VM2HMXRtavLaLsO1wxT_JeWH-vtNW7aKhnpw/edit?usp=sharing "Table 1. Numbers of GWAS samples in NHS/NHSII/HPFS/PHS cohorts")).

After removing duplicate samples, we used EIGENSTRAT [^2] to run principal component analysis (PCA) on each dataset. For Affymetrix and Illumina HumanHap, we used approximately 12,000 SNPs from Yu et al [^3] that were filtered to ensure low pairwise linkage disequilibrium (LD). For the OmniExpress, HumanCore Exome and Illumina OncoArray datasets we used approximately 33,000 SNPs that were similarly filtered. The top principal components were manually checked for outliers.

To identify any variants that created spurious associations, we ran several logistic regression analyses among subjects that were selected as controls in the initial GWAS (i.e. excluding all case subjects). For each regression, we used cohort-specific controls from one original GWAS as cases and the rest of the controls in that dataset as controls. For example, in the OmniExpress dataset, we considered NHS controls from the gout GWAS as “cases” while treating controls from the gout (HPFS), endometrial cancer (NHS), colon cancer (NHS, HPFS and PHS), and mammographic density (NHS) as “controls”. We repeated this, treating each cohort-specific “controls set” as “cases” and all other controls as “controls”. For each analysis, we excluded genome-wide significant variants (p< $10^{-8}$) and examined QQ plot. 

## Imputation

Before imputation, we performed alleles, strand, and allele frequency comparison with those in reference panels. Variants that were not in reference panel and variants with different alleles, allele frequency difference > 0.2, A/T and C/G variants with minor allele frequency > 0.4 were removed from each dataset. The five datasets were separately imputed. We used three reference panels - the 1,000 Genomes Phase III release, Haplotype Reference Consortium (HRC) release I, and Trans-Omics for Precision Medicine (TOPMed) release II. Our datasets were submitted to Michigan Imputation Server[^4] for the 1000 genomes and HRC imputation, and TOPMed Imputation Server[^4][^5] for the TOPMed imputation. Eagle[^6] and Minimac[^7] were used for genotype phasing and imputation by the Michigan and TOPMed imputation servers. The quality of imputation was estimated by [Rsq and EmpRsq](https://genome.sph.umich.edu/wiki/Minimac3_Info_File) in Minimac info files. [Table 3](https://docs.google.com/spreadsheets/d/1ZvKsZV6QUEOUaDbSpbEz1DAIyOmCzqQewoc9nMYz55I/edit?usp=sharing "Table 3. Rsq and EmpRsq summary for 5 datasets and 3 imputation reference panels") provides a summary of Rsq and EmpRsq for each of the five datasets based on each of the three imputation reference panels.

## Data access statement

The Nurses' Health Study (NHS), Nurses' Health Study II (NHSII), Health Professionals Follow Up Study (HPFS) welcome new collaborations and strive to make establishing them as simple and transparent as possible. Limits are not placed on scientific questions or methods, and there is no requirement for co-authorship. Investigators interested in collaborations are invited to fill out a simple form for [internal investigators](https://docs.google.com/forms/d/e/1FAIpQLSfCkvXpW59_sDFOEzyM0m0c3Z0Iqv1o-0WB6UdkpWZRfc3Pqg/viewform?c=0&w=1 "Collaboration request form for internal investigators") and [external investigators](https://docs.google.com/forms/d/e/1FAIpQLScAPV23ZIBpkk9CyEJ1OcFJjMol9elKEpLYnPu7g3PgBL57XA/viewform "Collaboration request form for external investigators") that asks about the details of the collaboration. Every two weeks, new collaboration requests are reviewed based on feasibility; the vast majority of requests are approved.

With collaboration approval, [standard operating procedure](https://docs.google.com/document/d/1h_R-4eCrtlEWQWCJEF5JPGe8nv2MGXQ44iLeYrmFDE8/edit?usp=sharing "standard operating procedure") for data analysis is available upon request.


## References
[^1]: Lindström S, Loomis S, Turman C, Huang H, Huang J, Aschard H, et al. A comprehensive survey of 
genetic variation in 20,691 subjects from four large cohorts.
[PLoS ONE.(2017); PMID: 28301549](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5354293/)

[^2]: Price AL, Patterson NJ, Plenge RM, Weinblatt ME, Shadick NA, Reich D. Principal components analysis corrects for stratification in genome-wide association studies. [Nature genetics. 2006;38(8):904–9. 10.1038/ng1847](https://pubmed.ncbi.nlm.nih.gov/16862161/)

[^3]: Yu K, Wang Z, Li Q, Wacholder S, Hunter DJ, Hoover RN, et al. Population substructure and control selection in genome-wide association studies. [PloS one. 2008;3(7):e2551 PubMed Central PMCID: PMC2432498. 10.1371/journal.pone.0002551](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2432498/)

[^4]: Das S, Forer L, Schönherr S, Sidore C, Locke AE, Kwong A, Vrieze S, Chew EY, Levy S, McGue M, Schlessinger D, Stambolian D, Loh PR, Iacono WG, Swaroop A, Scott LJ, Cucca F, Kronenberg F, Boehnke M, Abecasis GR, Fuchsberger C. Next-generation genotype imputation service and methods. [Nat Genet 48, 1284–1287 (2016).](https://www.ncbi.nlm.nih.gov/pubmed/27571263)

[^5]: Taliun, D. et al. (2019) Sequencing of 53,831 diverse genomes from the NHLBI TOPMed Program. [Biorxiv, doi:10.1101/563866](https://www.biorxiv.org/content/10.1101/563866v1) 

[^6]: Loh, P.-R., Danecek, P., Palamara, P. F., Fuchsberger, C., A Reshef, Y., K Finucane, H., Schoenherr, S., Forer, L., McCarthy, S., Abecasis, G. R., Durbin, R., & L Price, A. (2016). Reference-based phasing using the Haplotype Reference Consortium panel. [Nature Genetics, 48(11), 1443–1448](http://dx.doi.org/10.1038/ng.3679) 

[^7]: Fuchsberger, C., Abecasis, G. R., & Hinds, D. A. (2014). minimac2: faster genotype imputation. [Bioinformatics, 31(5), 782–784](https://doi.org/10.1093/bioinformatics/btu704) 


