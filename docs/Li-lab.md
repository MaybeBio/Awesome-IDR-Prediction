# Min Li LAB

[← Back to list](../README.md#central-south-university-中南大学)

## DisoPred

### DisoPred Abstract
N/A

### DisoPred Model/Method
DisoPred combines two predictors: the predictor of IDRs and the predictor of IDPs. DisoPred apples the 5-fold cross validation to train two predictors with same input profiles and deep learning model consisting of the muti-CNN block and the transformer layer. Considering the length of IDRs and IDPs, the input window sizes of two predictors are different. The average of predictions from the two predictors is used as the final prediction. Cross-validation and fusion results help improve accuracy of performance and robustness.