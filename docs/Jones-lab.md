# David T. Jones Lab

[← Back to list](../README.md#university-college-london)

## DISOPRED3

### DISOPRED3 Abstract
A sizeable fraction of eukaryotic proteins contain intrinsically disordered regions (IDRs), which act in unfolded states or by undergoing transitions between structured and unstructured conformations. Over time, sequence-based classifiers of IDRs have become fairly accurate and currently a major challenge is linking IDRs to their biological roles from the molecular to the systems level.

We describe DISOPRED3, which extends its predecessor with new modules to predict IDRs and protein-binding sites within them. Based on recent CASP evaluation results, DISOPRED3 can be regarded as state of the art in the identification of IDRs, and our self-assessment shows that it significantly improves over DISOPRED2 because its predictions are more specific across the whole board and more sensitive to IDRs longer than 20 amino acids. Predicted IDRs are annotated as protein binding through a novel SVM based classifier, which uses profile data and additional sequence-derived features. Based on benchmarking experiments with full cross-validation, we show that this predictor generates precise assignments of disordered protein binding regions and that it compares well with other publicly available tools.

### DISOPRED3 Model/Method
DISOPRED3 combines three predictors: the original DISOPRED feed-forward neural network, DISOPRED2 SVM and a nearest neighbor classifier. A small second-stage neural network combines three predictors into a single output. Three independent SVM classifiers identify binding positions based on: (i) single sequences alone, Blosum62 values; (ii) PSSM from PSI-BLAST against UniRef90; (iii) PSSM plus the length and start/end of the region, a flag for windows outside protein termini and amino acid composition. Disorder training data was derived from Disprot v5.0 (only NMR or biophysical methods) and from the PDB (February 2010), redundancy-reduced, percentage sequence identity <90%, ≤2.2Å, chains longer than 24 residues. Missing residues and those with occupancy zero, were treated as disordered. Binding data was derived from Disfani et al., 2012. Less than 30% identity with other regions for a total of 397 PDB chains (372 UniProtKB). Negative training examples were obtained from unbound protein domain linker regions in known protein structures. Linkers annotated in CATH v.3.5, spanning between 5 and 60 amino acids and lacking interactions with other molecules in the same PDB file (atoms closer than 6Å; 3.9Å for ligands and metal ions) and with less than 30% sequence identity to other regions.

DISOPRED3 represents the latest release of our successful machine-learning
based approach to the detection of intrinsically disordered regions. The
method was originally trained on evolutionarily conserved sequence features
of disordered regions from missing residues in high-resolution X-ray structures.
DISOPRED2 mainly addressed the marked class imbalance between ordered and
disordered amino acids as well as the different sequence patterns associated
with terminal and internal disordered regions using SVMs.

DISOPRED3 extends the previous architecture with two independent predictors of
intrinsic disorder - a neural network and a nearest neighbour classifier - which
were trained to identify long intrinsically disordered regions using data from
the PDB and DisProt databases. The intermediate results are integrated by an
additional neural network.

To provide insights into the biological roles of proteins, DISOPRED3 also predicts
protein binding sites within disordered regions using a SVM that examines patterns
of evolutionary sequence conservation, positional information and amino acid
composition of putative disordered regions.
