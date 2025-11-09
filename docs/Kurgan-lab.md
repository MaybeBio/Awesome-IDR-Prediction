# Lukasz Kurgan Lab

[← Back to list](../README.md#virginia-commonwealth-university)

## APOD

### APOD Abstract
Disordered flexible linkers (DFLs) are abundant and functionally important intrinsically disordered regions that connect protein domains and structural elements within domains and which facilitate disorder-based allosteric regulation. Although computational estimates suggest that thousands of proteins have DFLs, they were annotated experimentally in <200 proteins. This substantial annotation gap can be reduced with the help of accurate computational predictors. The sole predictor of DFLs, DFLpred, trade-off accuracy for shorter runtime by excluding relevant but computationally costly predictive inputs. Moreover, it relies on the local/window-based information while lacking to consider useful protein-level characteristics.

We conceptualize, design and test APOD (Accurate Predictor Of DFLs), the first highly accurate predictor that utilizes both local- and protein-level inputs that quantify propensity for disorder, sequence composition, sequence conservation and selected putative structural properties. Consequently, APOD offers significantly more accurate predictions when compared with its faster predecessor, DFLpred, and several other alternative ways to predict DFLs. These improvements stem from the use of a more comprehensive set of inputs that cover the protein-level information and the application of a more sophisticated predictive model, a well-parametrized support vector machine. APOD achieves area under the curve = 0.82 (28% improvement over DFLpred) and Matthews correlation coefficient = 0.42 (180% increase over DFLpred) when tested on an independent/low-similarity test dataset. Consequently, APOD is a suitable choice for accurate and small-scale prediction of DFLs.

### APOD Model/Method
APOD (Accurate Predictor Of DFLs) is a machine learning-derived predictor of disordered flexible linkers (DFLs). APOD uses a two-step process to predict DFLs from protein sequences. First, the input sequence is converted into an information-rich profile that covers conservation, amino acid composition, and putative secondary structure, solvent accessibility and intrinsic disorder. This profile is processed to generate inputs to the predictive model using a small sliding window and protein-level putative disorder content, where the latter provides a protein-level bias for the window-based input. Second, a well-parametrized support vector machine model is used to generate DFL predictions from these inputs.

## flDPnn

### flDPnn Abstract
Identification of intrinsic disorder in proteins relies in large part on computational predictors, which demands that their accuracy should be high. Since intrinsic disorder carries out a broad range of cellular functions, it is desirable to couple the disorder and disorder function predictions. We report a computational tool, flDPnn, that provides accurate, fast and comprehensive disorder and disorder function predictions from protein sequences. The recent Critical Assessment of protein Intrinsic Disorder prediction (CAID) experiment and results on other test datasets demonstrate that flDPnn offers accurate predictions of disorder, fully disordered proteins and four common disorder functions. These predictions are substantially better than the results of the existing disorder predictors and methods that predict functions of disorder. Ablation tests reveal that the high predictive performance stems from innovative ways used in flDPnn to derive sequence profiles and encode inputs. flDPnn’s webserver is available at http://biomine.cs.vcu.edu/servers/flDPnn/.

### flDPnn Model/Method
flDPnn (function- and linker-based Disorder Prediction using deep neural network) generates accurate and fast disorder and disorder function predictions from protein sequence using a three-step process. First, the input sequence is converted into a profile that covers conservation, putative secondary structure, and initial predictions of disorder, disordered linkers and disordered binding. Second, the profile is encoded into three distinct input types: 1) residue-level data using a sliding window; 2) window-level data using hand-crafted features that aggregate data from the window; and 3) protein-level information that quantifies overall bias for disordered and disorder functions. Third, these inputs are processed with a simple 4-layer deep feedforward neural network to generate disorder predictions. Moreover, four random forest models are used to predict propensities for protein binding, RNA binding, DNA binding and disordered linkers for the putative disordered residues predicted by the deep network.

## flDPlr / flDPlr2

### flDPlr Abstract
N/A

### flDPlr Model/Method
flDPlr (function- and linker-based Disorder Prediction using logistic regression) is a variant of the flDPnn method that uses logistic regression instead of the neural network to predict disorder.

## flDPnn2

### flDPnn2 Abstract
Prediction of the intrinsic disorder in protein sequences is an active research area, with well over 100 predictors that were released to date. These efforts are motivated by the functional importance and high levels of abundance of intrinsic disorder, combined with relatively low amounts of experimental annotations. The disorder predictors are periodically evaluated by independent assessors in the Critical Assessment of protein Intrinsic Disorder prediction (CAID) experiments. The recently completed CAID2 experiment assessed close to 40 state-of-the-art methods demonstrating that some of them produce accurate results. In particular, flDPnn2 method, which is the successor of flDPnn that performed well in the CAID1 experiment, secured the overall most accurate results on the Disorder-NOX dataset in CAID2. flDPnn2 implements a number of improvements when compared to its predecessor including changes to the inputs, increased size of the deep network model that we retrained on a larger training set, and addition of an alignment module. Using results from CAID2, we show that flDPnn2 produces accurate predictions very quickly, modestly improving over the accuracy of flDPnn and reducing the runtime by half, to about 27 s per protein. flDPnn2 is freely available as a convenient web server at http://biomine.cs.vcu.edu/servers/flDPnn2/.

### flDPnn2 Model/Method
N/A 

## flDPnn3 (flDPnn3a / flDPnn3b)

### flDPnn3 Abstract
N/A 

### flDPnn3 Model/Method
flDPnn3a: flDPnn3a is a predictor that predicts disorder using an innovative deep neural network. It incorporates predictions from disorder functions and disordered linkers, along with embeddings from the large protein language model ESM-2 as inputs. 

flDPnn3b: flDPnn3b is a predictor that predicts disorder using an transformer model. It incorporates predictions from disorder functions and disordered linkers, along with embeddings from the large protein language model ESM-2 as inputs.
