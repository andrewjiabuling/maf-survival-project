📁 Data Instructions
The raw and processed MMRF CoMMpass data used in this project are too large to store on GitHub (>25 MB) and are subject to licensing restrictions.
To reproduce the analysis, please download the required datasets manually and place them in:
maf-survival-project/data/
🔹 1. CoMMpass RNA-seq + Clinical Survival Data
This file contains:
RNA-seq expression matrix
Clinical metadata
TTPFS (time-to-progression–free survival)
Censoring indicator
Cytogenetic annotations (e.g., MAF, NSD2, del17p, gain1q21)
📥 Download link:
https://drive.google.com/uc?export=download&id=177yYarB0SRviTWb6OkxFLEXnkxAbzipv
After downloading, rename the file:
data/survival_gene.tsv
🔹 2. BETA MAF-Related Genes List
This file contains the curated list of genes identified from:
MAF ChIP-seq binding peaks
RNA-seq differential expression after MAF depletion
Combined regulatory targets
📥 Download link:
https://drive.google.com/uc?export=download&id=1AcoJgqAiijg-RjoYxvBaRbvI655t1Jul
Save as:
data/BETA_MAF_combined_genes_EnsemblIDs.tsv
📘 Notes
Original raw CoMMpass data can be accessed (with registration) at:
https://research.themmrf.org
This repository only includes small processed gene lists and analysis code, not sensitive or large datasets.
Users must obtain the necessary data independently before running the analysis.
