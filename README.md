# Epilepsy-Gene-Expression-ML-Project
Machine learning + SHAP-based interpretability on epilepsy transcriptomics

📄 Abstract
Epilepsy is a complex neurological disorder that affects over 50 million people worldwide. Despite advancements in neuroimaging and clinical diagnostics, accessible molecular biomarkers for diagnosis, subtype differentiation, and treatment response prediction remain limited. This project investigates whether blood-derived gene expression signatures can support machine learning models in classifying:
(1) Epilepsy vs Control,
(2) Epilepsy subtypes, and
(3) Drug responders vs non-responders.
Using Illumina microarray gene expression data, three machine learning pipelines (Logistic Regression, Random Forest, SVC) were developed and evaluated using stratified cross-validation. Feature selection (ANOVA-F), differential expression analysis, PCA, and SHAP explainability were used to identify biologically meaningful gene signatures. The results demonstrate that blood transcriptomics contains measurable predictive signal, with Model 1 achieving strong separability via ROC analysis and interpretable gene-level contributions. This repository provides a complete, reproducible workflow for transcriptomic ML modelling and biomarker exploration.
🧬 Project Overview
Blood-based gene expression was analysed to address three predictive tasks:
1. Epilepsy vs Control
Binary classification leveraging ~20k probes reduced by ANOVA feature selection.
2. Epilepsy Subtype Classification
Multiclass task. ROC not performed due to incompatibility, but confusion matrices and SHAP plots were used to interpret subtype-specific signatures.
3. Drug Response Prediction
Binary classification identifying responders vs non-responders.
A consistent ML pipeline was used across tasks, allowing fair comparison.

🧪 Methodology
1. Preprocessing
Quality control and missing value checks
Variance filtering
Data scaling using StandardScaler
Feature selection using SelectKBest (ANOVA F-test)
Label balancing checks via countplots
2. Differential Gene Expression (DGE)
Epilepsy vs Control volcano plot
Identification of significantly up/down-regulated probes
Fold-change visualisation and interpretation
3. Machine Learning Pipeline
StandardScaler → SelectKBest → Classifier (LR / RF / SVC)

Implemented using Scikit-Learn Pipelines
GridSearchCV used for hyperparameter optimisation
Stratified k-fold (k=10) for fairness
4. Model Evaluation
Accuracy, Precision, Recall, F1
Confusion matrices
ROC & AUC (for binary models)
PCA for visual class separability
5. Model Explainability (XAI)
SHAP summary plots for top 20 genes
Gene-level effect interpretation
Comparison with differential expression results

📊 Key Results
✓ Model 1 – Epilepsy vs Control
Strong separation in PCA
AUC-ROC: High performance
SHAP reveals biologically relevant gene markers involved in neuronal pathways, inflammation, and synaptic signalling
Volcano plot shows clear DEGs supporting ML findings
✓ Model 2 – Subtype Classification
Multiclass, moderate accuracy (expected due to small sample sizes)
SHAP indicates subtype-specific transcriptional fingerprints
PCA shows partial but interpretable grouping
✓ Model 3 – Drug Response Prediction
Logistic Regression and Random Forest show consistent performance
SHAP highlights potential predictive markers for treatment sensitivity
Useful insight for personalised medicine direction

📈 Visual Outputs
Repository includes high-quality figures ready for publication:
PCA plots (2D/3D)
ROC Curves (Model 1 and Model 3)
SHAP Summary Plots (all models, top 20 genes)
Volcano Plot (Epilepsy vs Control)
Confusion Matrices
Age & Sex Distribution Plots
Drug Frequency Charts
Expression QC Boxplots

💬 Interpretation & Biological Insight
Explainable AI (XAI) reveals consistent gene signatures across:
Differential expression
Feature selection
SHAP model contributions
These converging patterns support the feasibility of blood-based biomarkers for epilepsy research.
While not clinically validated, results demonstrate methodological potential and avenues for further investigation (larger datasets, RNA-seq, deep learning, longitudinal sampling).

🛠 Technologies Used
Python 3.10
Pandas, NumPy
Scikit-Learn
SHAP
SciPy
Seaborn, Matplotlib
Jupyter Notebook

📚 Academic Value
This project demonstrates:
Competency in computational transcriptomics
Reproducible ML pipeline design
Hyperparameter tuning
XAI-driven biomarker discovery
Integration of clinical metadata with gene expression
Clear documentation and scientific communication
This GitHub repo can be referenced in your dissertation appendix as evidence of code transparency and reproducibility.
