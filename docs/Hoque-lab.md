# Md Tamjidul Hoque Lab

[← Back to list](../README.md#university-of-new-orleans)

## DisPredict2

### DisPredict2 Abstract
A set of features computed from the primary amino acid sequence of proteins, is crucial in the process of inducing a machine learning model that is capable of accurately predicting three-dimensional protein structures. Solutions for existing protein structure prediction problems are in need of features that can capture the complexity of molecular level interactions. With a view to this, we propose a novel approach to estimate position specific estimated energy (PSEE) of a residue using contact energy and predicted relative solvent accessibility (RSA). Furthermore, we demonstrate PSEE can be reasonably estimated based on sequence information alone. PSEE is useful in identifying the structured as well as unstructured or, intrinsically disordered region of a protein by computing favorable and unfavorable energy respectively, characterized by appropriate threshold. The most intriguing finding, verified empirically, is the indication that the PSEE feature can effectively classify disorder versus ordered residues and can segregate different secondary structure type residues by computing the constituent energies. PSEE values for each amino acid strongly correlate with the hydrophobicity value of the corresponding amino acid. Further, PSEE can be used to detect the existence of critical binding regions that essentially undergo disorder-to-order transitions to perform crucial biological functions. Towards an application of disorder prediction using the PSEE feature, we have rigorously tested and found that a support vector machine model informed by a set of features including PSEE consistently outperforms a model with an identical set of features with PSEE removed. In addition, the new disorder predictor, DisPredict2, shows competitive performance in predicting protein disorder when compared with six existing disordered protein predictors.


### DisPredict2 Model/Method
N/A

## DisPredict3.0

### DisPredict3.0 Abstract
Intrinsically disordered proteins (IDPs) or protein regions (IDRs) do not have a stable three-dimensional structure, even though they exhibit important biological functions. They are structurally and functionally very different from ordered proteins and can cause many critical diseases. Accurate identification of disordered proteins/regions significantly impacts fields such as drug design, protein engineering, protein design, and related research. However, experimental identification of IDRs is complex and time-consuming, necessitating the development of an accurate and efficient computational method. The recent development of deep learning methods for protein language models shows the ability to learn evolutionary information from billions of protein sequences. This motivates us to develop a computational method, named DisPredict3.0, to predict proteins’ disordered regions (IDRs) using evolutionary information from a protein language model. Compared to the state-of-the-art method in the CAID (2018) assessment, DisPredict3.0 has an improvement of 2.51 %, 16.13 %, 17.98 %, and 11.94 % in terms of AUC, F1-score, MCC, and kappa, respectively. In addition, in the CAID-2 assessment (2022), DisPredict3.0 shows promising results and is ranked first for disorder residue prediction on the Disorder-NOX dataset. The DisPredict3.0 webserver is available at https://bmll.cs.uno.edu.

### DisPredict3.0 Model/Method
We develop a computational method named Dispredict3.0 to predict proteins’ disordered regions (IDRs) using evolutionary information from a protein language model. Dispredict3.0 is developed based on the representation of a protein language model and the features extracted from the flDPnn method. We further transformed the high-dimensional protein representation into a lower dimension with Principal Component Analysis (PCA) and trained an optimized Light gradient boosting Machine model.

## ESMDisPred (1 / 2 / 2PDB / DNN)

### ESMDisPred Abstract
N/A

### ESMDisPred Model/Method
ESMDisPred: Enhanced Prediction of Disordered Regions Utilizing Representations from a Large Protein Language Model.
- ESMDisPred-1: Utilizes sequence-based features from DisPredict3.0 and ESM-1 embeddings.
- ESMDisPred-2: Extends ESMDisPred-1 by incorporating ESM-2 embeddings, providing richer contextual protein representations.
- ESMDisPred-2PDB: Builds upon ESMDisPred-2 by integrating structural-related features derived from PDB data, enhancing structural context awareness.
- ESMDisPred-DNN: A comprehensive CNN–Transformer hybrid model trained using all feature types from DisPredict3.0, ESM-1, ESM-2, and PDB-derived structural descriptors.This variant captures both local residue patterns (via CNNs) and long-range dependencies (via Transformers), resulting in superior predictive performance.