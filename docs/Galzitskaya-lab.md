# Oxana Valerianovna Galzitskaya LAB

[← Back to list](../README.md#institute-of-protein-research-ras)

## FoldUnfold

### FoldUnfold Abstract
Identification of disordered regions in polypeptide chains is very important because such regions are essential for protein function. A new parameter, namely mean packing density of residues has been introduced to detect disordered regions in a protein sequence. We have demonstrated that regions with weak expected packing density would be responsible for the appearance of disordered regions. Our method (FoldUnfold) has been tested on datasets of globular proteins (559 proteins) and long disordered protein segments (129 proteins) and showed improved performance over some other widely used methods, such as DISOPRED, PONDR VL3H, IUPred and GlobPlot.

The FoldUnfold server is available for users at [Author Webpage](http://skuld.protres.ru/~mlobanov/ogu/ogu.cgi). There is a link to our server through the web site of DisProt ([Author Webpage](https://www.disprot.org/predictors.php)).

### FoldUnfold Model/Method
The method is based on the statistics of the average number of contacts for each type of amino acid residues. It takes into account the fact that, on average, amino acids with few contacts are more often unfolded. For prediction, the program uses the sliding window method. The optimal window size is 11 residues.

## IsUnstruct

### IsUnstruct Abstract
Intrinsically disordered regions serve as molecular recognition elements, which play an
important role in the control of many cellular processes and signaling pathways. It is useful to
be able to predict positions of disordered residues and disordered regions in protein chains
using protein sequence alone. A new method (IsUnstruct) based on the Ising model for
prediction of disordered residues from protein sequence alone has been developed. According
to this model, each residue can be in one of two states: ordered or disordered. The model is an
approximation of the Ising model in which the interaction term between neighbors has been
replaced by a penalty for changing between states (the energy of border). The IsUnstruct has
been compared with other available methods and found to perform well. The method correctly
finds 77% of disordered residues as well as 87% of ordered residues in the CASP8 database,
and 72% of disordered residues as well as 85% of ordered residues in the DisProt database.

### IsUnstruct Model/Method
The method is based on the Ising model. Each residue of the protein chain can be either structured or unstructured state. Each of the amino acids type has the potential to transition from one state to another. The energy of the boundary between the folded and unfolded states, and the energy of initiation of the unfolded state at the N- and C-terminals of the protein chain are also taken into account. Parameters optimized on PDB 2012. In addition, the method takes into account 171 disordered patterns, these are sequences that we always predict unfolded.
