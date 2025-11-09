# Kun-Sop Han LAB

[← Back to list](../README.md#university-of-sciences-pyongyang)

## PredIDR

### PredIDR Abstract
The involvement of protein intrinsic disorder in essential biological processes, it is well known in structural biology. However, experimental methods for detecting intrinsic structural disorder and directly measuring highly dynamic behavior of protein structure are limited. To address this issue, several computational methods to predict intrinsic disorder from protein sequences were developed and their performance is evaluated by the Critical Assessment of protein Intrinsic Disorder (CAID). In this paper, we describe a new computational method, PredIDR, which provides accurate prediction of intrinsically disordered regions in proteins, mimicking experimental X-ray missing residues. Indeed, missing residues in Protein Data Bank (PDB) were used as positive examples to train a deep convolutional neural network which produces two types of output for short and long regions. PredIDR took part in the second round of CAID and was as accurate as the top state-of-the-art IDR prediction methods. PredIDR can be freely used through the CAID Prediction Portal available at https://caid.idpcentral.org/portal or downloaded as a Singularity container from https://biocomputingup.it/shared/caid-predictors/.

### PredIDR Model/Method
PredIDR is a program which employs deep convolutional neural network to predict IDR. IDR chains are extracted from PDB non-homologous set by comparing primary sequences and 3D coordinates. The 8,850 IDRs of training set are divided into 3 groups according to the position of IDR in the sequence: IDR_C, IDR_M and IDR_N group. The 8,850 artificial STRs corresponding to 8,850 IDRs are also made. The input features of deep convolutional neural network are profile, secondary structure and solvent accessibility predicted from 229,752 sliding windows (L1=15 residues) from 8,850 IDRs and 8,850 artificial STRs. The predictions from the ensemble of 10 top-performing models are averaged within the second window (L2=9 or 19). The final prediction with L2=9 is PredIDR_S which is used to predict short and long IDRs (L > 4) whereas the one with L2=19 is PredIDR_L which is used to predict long IDRs (L > 10).

## PredIDR2-Seq

### PredIDR2-Seq Abstract
Intrinsically disordered proteins (IDPs) or regions (IDRs) are widespread in proteomes, and involved in several important biological processes and implicated in many diseases. Many computational methods for IDR prediction are being developed to decrease the gap between the low speed of experimental determination of annotated proteins and the rapid increase of non-annotated proteins, and their performances are blindly tested by the community-driven experiment, the Critical Assessment of protein Intrinsic Disorder (CAID). In this paper, we developed PredIDR2 series, an updated version of PredIDR tested in CAID2 in order to accurately predict intrinsically disordered regions from protein sequence. It includes four methods depending on the input features and the producing mode of the negative samples of the training set. PredIDR2 series (AUC_ROC = 0.952) perform remarkably better than our previous PredIDR (AUC_ROC = 0.933) for Disorder-PDB dataset of CAID2, which seems to be mainly attributed to the introduction of a new deep convolutional neural network and the augmentation of the training data, especially from DisProt database. PredIDR2 series outperform the state-of-the-art IDR prediction methods participated in CAID2 in terms of AUC_ROC, AUC_PR and DC_mae and belong to the seven top-performing methods in terms of MCC. PredIDR2 series can be freely used through the CAID Prediction Portal available at https://caid.idpcentral.org/portal or downloaded as a Singularity container from https://biocomputingup.it/shared/caid-predictors/.

### PredIDR2-Seq Model/Method
PredIDR2-Seq is a program for predicting IDRs in protein sequences based on convolutional neural network. The PredIDR2-Seq is faster than the PredIDR2-Prof. The sequences of PDB, DisProt release_2023_06 and CAID2 dataset are used for making a training, validation and testing data. The PredIDR2-Seq uses secondary structure, solvent accesibility and protein sequence as inputs of the neural network. The program produces outputs of two methods: PredIDR2-Seq_Art and PredIDR2-Seq_Rnd, which are different in ways of making the training data. The convolutional neural network consists of four 2D convolutional layers, four batch normalization layers and two dense layers. A sliding window of size 31 and 32-dimensional features are used, resulting in an input tensor of size (31,1,32) for convolutional neural network. In each of two methods, about 10 top-performing networks are chosen to make an ensemble and smoothing with window size 19 on the ensemble results in the final output.

## PredIDR2-Prof

### PredIDR2-Prof Abstract
see PredIDR2-Seq Abstract above

### PredIDR2-Prof Model/Method
PredIDR2-Prof is a program for predicting IDRs in protein sequences based on convolutional neural network. The PredIDR2-Prof is the updated version of PredIDR1.0 developed in 2022 and tested in CAID2.