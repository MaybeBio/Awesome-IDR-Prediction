# Lucia Beatriz Chemes Lab

[← Back to list](../README.md#iibio-conicet-unsam)

## LINKER-Pred (LINKER-Pred / LINKER-Pred-Lite / LINKER-Pred2)

### LINKER-Pred Abstract
Disordered Flexible Linkers (DFLs) are unstructured regions that play critical roles in interdomain communication and multivalent protein interactions. Despite their biological
significance, the accurate identification of DFLs remains challenging due to limited
experimental annotations and sparsity of dedicated prediction tools. Here we introduce
LINKER-Pred, a publicly available web server featuring two convolutional neural networkbased predictors trained on a novel large-scale dataset of linkers connecting folded domains
(DLD dataset) and DisProt linkers. LINKER-Pred2 combines ProtTrans and MSA-Transformer
embeddings within an ensemble CNN framework, achieving state-of-the-art performance on
CAID2 and CAID3 benchmarks. LINKER-Pred-Lite excludes MSA-based features, improving
speed while maintaining competitive predictive accuracy. LINKER-Pred predictors offer robust
residue-level DFL predictions directly from sequence, providing a scalable solution for DFL
annotation across proteomes. The LINKER-Pred web server and associated resources are
freely available at https://pcrgwd.ucd.ie/linker_pred/, offering the research community an
accessible tool for studying protein disorder and modularity.

### LINKER-Pred Model/Method
- LINKER-Pred: LINKER-Pred is a Linker only predictor trained on our DLD linker dataset and Disprot Linker dataset. Please check https://github.com/deemeng/punch_linker for more information.

    LINKER-Pred project belongs to a series of LINKER-Pred-Suite projects which focus on the Structure and Function prediction of Disordered Flexible Linkers (DFLs). Currently we have LINKER-Pred for fast DFL prediction and LINKER-Pred for more accurate DFL prediction. LINKER-Pred is trained on more than 2000 DFL linker dataset from our DLD dataset and Disprot, its performance is better than TOP predictors on the CAID2 Linker dataset. 
- LINKER-Pred-Lite: A fast Linker predictor. Do not need Multiple Sequence Alignment. Generate one prediction in seconds.
- LINKER-Pred2: Linker predictor. An updated version of LINKER-Pred.

