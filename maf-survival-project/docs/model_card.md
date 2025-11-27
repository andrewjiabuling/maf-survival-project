# Model Card: Lasso–Cox Survival Model for MAF–Regulated Genes

## 1. Model Details
- **Model type:** Penalised Cox proportional hazards model (lasso penalty).
- **Implementation:** `sksurv.linear_model.CoxnetSurvivalAnalysis` in Python with 5-fold cross-validation.
- **Inputs:** Standardised clinical variables (Age, ISS, cytogenetic markers) and expression of BETA-defined MAF target genes.
- **Output:** Continuous risk score proportional to log-hazard of earlier progression; used to define high- vs low-risk groups.

## 2. Intended Use
- **Primary use:** Research and teaching: exploring whether MAF-regulated gene expression is associated with progression-free survival.
- **Intended users:** Researchers, students, data scientists working on cancer genomics.
- **Not intended for:** Direct clinical decision-making, individual patient counselling, or regulatory submissions.

## 3. Training Data
- Based on the CoMMpass multiple myeloma cohort (baseline samples) filtered to patients with complete PFS and expression data.
- High-dimensional gene expression restricted to genes identified as MAF targets by BETA analysis (ChIP-seq + MAF-depletion RNA-seq).

## 4. Evaluation
- **Metric:** Concordance index (C-index) on the same dataset used for training; approximate value ≈ 0.93 for TTPFS.
- **Visual evaluation:** Kaplan–Meier curves comparing high- and low-risk groups split by median risk score.
- **Limitations:** No separate test set or external validation; performance is likely optimistic.

## 5. Ethical & Safety Considerations
- Model may reflect biases present in CoMMpass (e.g. geography, treatment patterns, under-representation of certain ethnic groups).
- Overfitting and lack of external validation mean the model should not be used to make treatment decisions.
- Interpretation of gene coefficients is statistical association, not proven causality.

## 6. Limitations and Open Questions
- Assumes proportional hazards and linear effects of genes and covariates.
- Does not include important prognostic factors such as response depth or minimal residual disease.
- Future work: external validation in an independent cohort, more robust regularisation (nested CV), and mechanistic validation of candidate MAF target genes.
