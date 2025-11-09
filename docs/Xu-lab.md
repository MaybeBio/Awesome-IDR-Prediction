# Jinbo Xu Lab

[← Back to list](../README.md#toyota-technological-institute-at-chicago)

## AUCpreD

### AUCpreD Abstract
Protein intrinsically disordered regions (IDRs) play an important role in many biological processes. Two key properties of IDRs are (i) the occurrence is proteome-wide and (ii) the ratio of disordered residues is about 6%, which makes it challenging to accurately predict IDRs. Most IDR prediction methods use sequence profile to improve accuracy, which prevents its application to proteome-wide prediction since it is time-consuming to generate sequence profiles. On the other hand, the methods without using sequence profile fare much worse than using sequence profile.

Our experimental results show that our IDR prediction method AUCpreD outperforms existing popular disorder predictors. More importantly, AUCpreD works very well even without sequence profile, comparing favorably to or even outperforming many methods using sequence profile. Therefore, our method works for proteome-wide disorder prediction while yielding similar or better accuracy than the others.

### AUCpreD Model/Method
This article formulates IDR prediction as a sequence labeling problem and employs a new machine learning method called Deep Convolutional Neural Fields (DeepCNF) to solve it. DeepCNF is an integration of deep convolutional neural networks (DCNN) and conditional random fields (CRF); it can model not only complex sequence–structure relationship in a hierarchical manner, but also correlation among adjacent residues. To deal with highly imbalanced order/disorder ratio, instead of training DeepCNF by widely used maximum-likelihood, we develop a novel approach to train it by maximizing area under the ROC curve (AUC), which is an unbiased measure for class-imbalanced data.
