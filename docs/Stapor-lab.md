# Katarzyna Stapor LAB

[← Back to list](../README.md#silesian-university-of-technology)

## DisorderUnetLM

### DisorderUnetLM Abstract
The prediction of intrinsic disorder regions has significant implications for understanding protein functions and dynamics. It can help to discover novel protein-protein interactions essential for designing new drugs and enzymes. Recently, a new generation of predictors based on protein language models (pLMs) is emerging. These algorithms reach state-of-the-art accuracy without calculating time-consuming multiple sequence alignments (MSAs). This article introduces the new DisorderUnetLM disorder predictor, which builds upon the idea of ProteinUnet. It uses the Attention U-Net convolutional network and incorporates features from the ProtTrans pLM. DisorderUnetLM achieves top results in the direct comparison with recent predictors exploiting MSAs and pLMs. Moreover, among 43 predictors on the latest CAID-2 benchmark, it ranks 1st for the NOX subset in terms of the ROC-AUC metric (0.844) and 2nd for the AP metric (0.596). For the CAID-2 PDB subset, it ranks in the top 10 (ROC-AUC of 0.924 and AP of 0.862). The code and model are publicly available and fully reproducible at doi.org/10.24433/CO.7350682.v1.


### DisorderUnetLM Model/Method
Deep learning-based protein intrinsic disorder predictor based on the ensemble of 10 Attention U-Net convolutional neural networks and features from protein language model ProtTrans-T5-XL-U50.
