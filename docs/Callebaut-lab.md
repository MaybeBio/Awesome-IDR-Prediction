# Isabelle Callebaut LAB

[← Back to list](../README.md#sorbonne-university)

## pyHCA

### pyHCA Abstract
Detecting protein domains sharing no similarity to known domains, as stored in domain databases, is a challenging problem, particularly for unannotated proteomes, domains emerged recently, fast diverging proteins or domains with intrinsically disordered regions.

We developed pyHCA and HCAtk, a python API and standalone tool gathering together improved versions of previously developed methodologies, with new functionalities. The developed tools can be either used from command line or from a python API.

HCAtk and pyHCA are available at https://github.com/T-B-F/pyHCA under the CeCILL-C license.

### pyHCA Model/Method
pyHCA (disorder mode) predicts intrinsically disordered regions at the amino acid level by combining information on physico-chemical properties of amino acids with features derived from Hydrophobic Cluster Analysis (HCA). HCA provides information on the foldability of a protein, based on the density of hydrophobic clusters, using its single amino acid sequence (without considering sequence profiles) (see for recent papers Bitard-Feidel et al Proteomics 2018 doi: 10.1002/pmic.201800054 and Bruley et al. Proteins 2023 doi: 10.1002/prot.26441). Machine learning features were extracted based on a subset of AAIndex and HCA annotations. Thus, the features cover physico-chemical and topological properties at different levels (amino acids, hydrophobic clusters, foldable domains and windows of fixed lengths). PyHCA-disorder classified each amino acid as intrinsically disordered or not using a gradient boosting decision tree algorithm trained using lightgbm on a non-redunant set of MobiDB sequences.