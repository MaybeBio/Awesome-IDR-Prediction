# Jianlin (Jack) Cheng Lab

[← Back to list](../README.md#university-of-missouri)

## PreDisorder

### PreDisorder Abstract
Disordered regions are segments of the protein chain which do not adopt stable structures. Such segments are often of interest because they have a close relationship with protein expression and functionality. As such, protein disorder prediction is important for protein structure prediction, structure determination and function annotation.

This paper presents our protein disorder prediction server, PreDisorder. It is based on our ab initio prediction method (MULTICOM-CMFR) which, along with our meta (or consensus) prediction method (MULTICOM), was recently ranked among the top disorder predictors in the eighth edition of the Critical Assessment of Techniques for Protein Structure Prediction (CASP8). We systematically benchmarked PreDisorder along with 26 other protein disorder predictors on the CASP8 data set and assessed its accuracy using a number of measures. The results show that it compared favourably with other ab initio methods and its performance is comparable to that of the best meta and clustering methods.

PreDisorder is a fast and reliable server which can be used to predict protein disordered regions on genomic scale. It is available at http://casp.rnet.missouri.edu/predisorder.html.

### PreDisorder Model/Method
PreDisorder is a bidirectional recurrent neural network method for predicting if a residue in a protein is disordered. Given the sequence of a protein as input, it uses PSI-BLAST to generate the sequence profile and SCRATCH to predict the secondary structure and relative solvent accessibility for the protein. The sequence profile, secondary structure and relative solvent accessibility are used by a bidirectional recurrent neural network to generate hidden features to represent every residue, its N-terminal context, and its C-terminal context to predict its probability of being disordered. The output is a list of predicted disordered probabilities for all the residues in the protein. Users can set a threshold (e.g., 0.5) on the probabilities to assign the residues to disordered or ordered states. Different thresholds lead to different precision and recall (or specificity and sensitivity) of disorder prediction.
