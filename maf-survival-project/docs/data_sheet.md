# Datasheet for MAF–Regulated Gene Survival Dataset

## 1. Motivation
- **Purpose:** Study whether MAF-regulated genes are associated with time to progression in multiple myeloma.
- **Tasks:** Survival prediction (time-to-event), biomarker discovery.
- **Creators:** [Qizhen], using publicly available data from the MMRF CoMMpass study and BETA analysis of MAF targets.

## 2. Composition
- **Instances:** ~263 patients with baseline clinical and RNA-seq data. Myeloma MM1S Myeloma cell line group (MAF depleted, control) with CHIP-seq and RNA-seq data 
- **Features:**
  - Clinical: age, sex, ISS stage, LDH, major cytogenetic lesions (MAF, MAFA, MAFB, NSD2, 1q21, 17p13, 1p22).
  - Molecular: expression of BETA-defined MAF target genes (Ensembl IDs).
- **Labels:**
  - `ttpfs`: time to progression-free survival in days.
  - `censpfs`: event indicator (1 = progression/death, 0 = censored).
- **Population:** Newly diagnosed multiple myeloma patients enrolled in CoMMpass; may not be representative of all global populations.

## 3. Collection Process
- Clinical and genomic data were generated and curated by the MMRF and collaborators.
- RNA-seq was processed by the CoMMpass consortium; BETA target genes were defined from separate ChIP-seq and MAF-depletion RNA-seq experiments.
- This project uses a processed subset exported as `survival_gene.tsv` plus a gene list `BETA_MAF_combined_genes_EnsemblIDs.tsv`.

## 4. Pre-processing
- Samples with missing `ttpfs` or `censpfs` were removed.
- Only genes present in both the CoMMpass expression matrix and the BETA target list were kept.
- Continuous variables were standardised in the modelling pipeline.
- No batch correction was applied within this project; we rely on CoMMpass preprocessing.

## 5. Uses
- Appropriate for: exploratory survival modelling, feature selection, and educational purposes.
- Not appropriate for: making individual treatment decisions, clinical risk stratification without further validation, or inference about populations very different from CoMMpass.

## 6. Distribution
- Raw CoMMpass data are distributed by MMRF under controlled access.
- This repository provides only small derived tables and code; users must obtain original data separately.

## 7. Maintenance
- Maintainer: [Qizhen, qj22@ic.ac.uk].

