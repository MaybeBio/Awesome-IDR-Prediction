# Björn Wallner LAB

[← Back to list](../README.md#linköping-university)

## rawMSA

### rawMSA Abstract 
In the last decades, huge efforts have been made in the bioinformatics community to develop machine learning-based methods for the prediction of structural features of proteins in the hope of answering fundamental questions about the way proteins function and their involvement in several illnesses. The recent advent of Deep Learning has renewed the interest in neural networks, with dozens of methods being developed taking advantage of these new architectures. However, most methods are still heavily based pre-processing of the input data, as well as extraction and integration of multiple hand-picked, and manually designed features. Multiple Sequence Alignments (MSA) are the most common source of information in de novo prediction methods. Deep Networks that automatically refine the MSA and extract useful features from it would be immensely powerful. In this work, we propose a new paradigm for the prediction of protein structural features called rawMSA. The core idea behind rawMSA is borrowed from the field of natural language processing to map amino acid sequences into an adaptively learned continuous space. This allows the whole MSA to be input into a Deep Network, thus rendering pre-calculated features such as sequence profiles and other features calculated from MSA obsolete. We showcased the rawMSA methodology on three different prediction problems: secondary structure, relative solvent accessibility and inter-residue contact maps. We have rigorously trained and benchmarked rawMSA on a large set of proteins and have determined that it outperforms classical methods based on position-specific scoring matrices (PSSM) when predicting secondary structure and solvent accessibility, while performing on par with methods using more pre-calculated features in the inter-residue contact map prediction category in CASP12 and CASP13. Clearly demonstrating that rawMSA represents a promising development that can pave the way for improved methods using rawMSA instead of sequence profiles to represent evolutionary information in the coming years.

datasets, dataset generation code, evaluation code and models are available at: https://bitbucket.org/clami66/rawmsa.

### rawMSA Model/Method
rawMSA_disorder is part of a suite of methods for the prediction of structural features of proteins. Here, the input is not a set of pre-determined features, such as evolutionary profiles or predicted secondary structure, as in classical ML-based methods for structure prediction. Instead, the whole MSA is used as a textual input to the neural network so that the evolutionary information is not compressed in any way and the feature extraction can be automatically performed by the deep network. The mapping between amino acid letters to floating point vectors is done in the first layer of the deep network with an embedding layer. The input is not split into windows, and all predictions are done at the same time for all input amino acids so that long disordered / ordered regions are not split up at prediction stage. The final prediction is result of ensembling a number of pretrained models by averaging their outputs.

## rawMSA-disorder

### rawMSA-disorder Abstract 
N/A

### rawMSA-disorder Model/Method
It is a neural network based on previous work (rawMSA), trained to predict disorder from multiple sequence alignments. The alignments are now generated with MMseqs2, which is much faster than HHblits. The network is trained on DisProt and the PDB.