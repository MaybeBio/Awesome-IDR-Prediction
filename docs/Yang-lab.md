# Zheng Rong Yang Lab

[← Back to list](../README.md#university-of-exeter)

## RONN

### RONN Abstract
Recent studies have found many proteins containing regions that do not form well-defined three-dimensional structures in their native states. The study and detection of such disordered regions is important both for understanding protein function and for facilitating structural analysis since disordered regions may affect solubility and/or crystallizability.

We have developed the regional order neural network (RONN) software as an application of our recently developed ‘bio-basis function neural network’ pattern recognition algorithm to the detection of natively disordered regions in proteins. The results of blind-testing a panel of nine disorder prediction tools (including RONN) against 80 protein sequences derived from the Protein Data Bank shows that, based on the probability excess measure, RONN performed the best.

RONN is available at http://www.strubi.ox.ac.uk/RONN. Requests for the RONN software and the database of disorder (XML format) can be directed to the corresponding author.

### RONN Model/Method
The method is based on the Bio-basis function neural network (BBFNN), where the network is trained on a "distance" space rather than an arbitrary feature space (such as hydrophobicity and charge). The "distances" are determined by sequence alignment from a subset of well-characterized prototype sequences. The training sub-sequences (scanning window) are aligned with each prototype in turn to maximize the non-gapped homology alignment score. The bio-basis function is used to transform this score into a normalized similarity measurement. Each prototype is considered to be an independent variable and their relationship with the labels (ordered or disordered) is assumed to be simple, allowing a linear classifier to be constructed. The discrimination threshold is optimized assuming the probability density functions follow two Gaussian distributions. A parametric method is used to approximate these two functions and an optimum threshold for discrimination is determined using Bayes' rule. The database is constructed considering missing residues mapped at the UniProtKB level and regions of at least 5 consecutive residues, further splitted into long (>20 residues) and short regions. Pretein complexes are excluded (fold-upn-binding) and only missing residues in all idencal chains are included. CD-HIT at 70% identity.
