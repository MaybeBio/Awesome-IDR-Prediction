# Gianluca Pollastri LAB

[← Back to list](../README.md#university-college-dublin)

## PUNCH2

### PUNCH2 Abstract
Intrinsically disordered proteins (IDPs) and their intrinsically disordered regions (IDRs) lack stable three-dimensional structures, posing significant challenges for computational prediction. This study introduces PUNCH2 and PUNCH2-light, advanced predictors designed to address these challenges through curated datasets, innovative feature extraction, and optimized neural architectures. By integrating experimental datasets from PDB (PDB_missing) and fully disordered sequences from DisProt (DisProt_FD), we enhanced model performance and robustness. Three embedding strategies—One-Hot, MSA-based, and PLM-based embeddings—were evaluated, with ProtTrans emerging as the most effective single embedding and combined embeddings achieving the best results. The predictors employ a 12-layer convolutional network (CNN_L12_narrow), offering a balance between accuracy and computational efficiency. PUNCH2 combines One-Hot, ProtTrans, and MSA-Transformer embeddings, while PUNCH2-light provides a faster alternative excluding MSA-based embeddings. PUNCH2 and its streamlined variant, PUNCH2-light, are competitive with other predictors on the CAID2 benchmark and rank as the top two predictors in the CAID3 competition. These tools provide efficient, accurate solutions to advance IDP research and understanding.

### PUNCH2 Model/Method
- PUNCH2: A residue-level Intrinsically Disordered Region/Protein(IDP/IDR) predictor trained on PDB and Disprot Databases.

    PUNCH2 project belongs to a serious of PUNCH projects which focus on the Structure and Function prediction of Intrisically Diordered Protein/Region (IDP/IDR). Currently we have PUNCH2 for IDR structure prediction, and PUNCH_Linker and PUNCH_Linker_Light for DFL prediction.

- PUNCH2-Light: An IDR predictor. A faster predictor compare to PUNCH2. No MSA searching required.