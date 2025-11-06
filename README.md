# Awesome IDR Prediction: Labs & Tools 

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
 ![MIT License](https://img.shields.io/badge/license-MIT-brightgreen.svg) 
 [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com) 

## Repository Introduction
🤩 Welcome to our curated list of Computational Protein Intrinsic Disorder Prediction labs AND tools!

This repository is a **specialized, community-maintained** resource focused exclusively on **computational prediction of Intrinsically Disordered Regions (IDRs)**—a core subfield of IDR research. Unlike broad IDR hubs, it zeroes in on tools, methods, and labs that solve the critical challenge of identifying IDRs from protein sequences (residue-level disorder probability, segment-level disorder boundaries, or context-specific disorder).  
Our focus is on **actionable computational resources**: every entry includes direct access to tools (web servers/GitHub repos), links to the labs driving innovation, and supporting publications to validate method credibility. Whether you are a student new to IDR prediction or a researcher seeking state-of-the-art tools for your analysis, this repo centralizes the resources you need to avoid redundant searches and accelerate your work.  


> 📝 Note: The "Tools Section" of the list is based primarily on [CAID](https://caid.idpcentral.org/methods) (a community-based blind **test** to determine the state of the art in prediction of intrinsically disordered regions and the subset of residues involved in binding).


## Table of Contents

<!-- TOC -->
Quick links: 

[North America](#north-america)

[South America](#south-america)

[EMEA](#emea)

[Asia](#asia)
<!-- /TOC -->


## North America
### United States

#### Washington University in St. Louis     
<details>
<summary>Alex S. Holehouse</summary>

- Lab website: [holehouse lab](https://www.holehouselab.com/)

- Tools
  - Metapredict: Metapredict-v1, v2, v3
    - Paper: 
      - [Metapredict: a fast, accurate, and easy-to-use predictor of consensus disorder and structure](https://www.cell.com/biophysj/fulltext/S0006-3495(21)00725-6?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0006349521007256%3Fshowall%3Dtrue) (Biophysical Journal, 2021)
      - [Metapredict enables accurate disorder prediction across the Tree of Life](https://www.biorxiv.org/content/10.1101/2024.11.05.622168v1) (⚠️ bioRxiv preprint, 2024)
    - Abstract: Intrinsically disordered proteins and protein regions make up a substantial fraction of many proteomes in which they play a wide variety of essential roles. A critical first step in understanding the role of disordered protein regions in biological function is to identify those disordered regions correctly. Computational methods for disorder prediction have emerged as a core set of tools to guide experiments, interpret results, and develop hypotheses. Given the multiple different predictors available, consensus scores have emerged as a popular approach to mitigate biases or limitations of any single method. Consensus scores integrate the outcome of multiple independent disorder predictors and provide a per-residue value that reflects the number of tools that predict a residue to be disordered. Although consensus scores help mitigate the inherent problems of using any single disorder predictor, they are computationally expensive to generate. They also necessitate the installation of multiple different software tools, which can be prohibitively difficult. To address this challenge, we developed a deep-learning-based predictor of consensus disorder scores. Our predictor, metapredict, utilizes a bidirectional recurrent neural network trained on the consensus disorder scores from 12 proteomes. By benchmarking metapredict using two orthogonal approaches, we found that metapredict is among the most accurate disorder predictors currently available. Metapredict is also remarkably fast, enabling proteome-scale disorder prediction in minutes. Importantly, metapredict is a fully open source and is distributed as a Python package, a collection of command-line tools, and a web server, maximizing the potential practical utility of the predictor. We believe metapredict offers a convenient, accessible, accurate, and high-performance predictor for single-proteins and proteomes alike.
    - Description/Method: Metapredict (v1,2,3) is a deep-learning-based disorder predictor that was trained using both consensus disorder predictions and structural predictions. Metapredict V2 uses a long-short-term memory bi-directional recurrent network (LSTM-BRNN) architecture and was trained in two steps. First, two initial LSTM-BRNN models were trained: a consensus disorder predictor (trained on consensus disorder from eight different predictors across twelve proteomes) and a pLDDT predictor (trained on AlphaFold2 pLDDT scores across twenty-one different proteomes). These two models were then combined using a consensus confidence approach, providing a per-residue score based on the combination of structural uncertainty and disorder prediction. Finally, a new LSTM-BRNN was trained on the consensus confidence scores, yielding a single model that was indirectly trained on both disorder predictions and structural predictions.
    - Access:
      - Web server: https://metapredict.net/ | https://colab.research.google.com/drive/1UOrOxun9i23XDE8lFo_4I89Tw8P3Z1D-?usp=sharing
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/idptools/metapredict | [Documentation](https://metapredict.readthedocs.io/en/latest/)
      - Others: https://pypi.org/project/metapredict/ | https://bio.tools/metapredict
</details>


#### Virginia Commonwealth University     
<details>
<summary>Lukasz Kurgan</summary>

- Lab website: [Biomine Kurgan Lab](https://biomine.cs.vcu.edu/)

- Tools
  - APOD
    - Paper: [APOD: accurate sequence-based predictor of disordered flexible linkers](https://academic.oup.com/bioinformatics/article/36/Supplement_2/i754/6055918?login=false) (Bioinformatics, 2020)
    - Abstract: Disordered flexible linkers (DFLs) are abundant and functionally important intrinsically disordered regions that connect protein domains and structural elements within domains and which facilitate disorder-based allosteric regulation. Although computational estimates suggest that thousands of proteins have DFLs, they were annotated experimentally in <200 proteins. This substantial annotation gap can be reduced with the help of accurate computational predictors. The sole predictor of DFLs, DFLpred, trade-off accuracy for shorter runtime by excluding relevant but computationally costly predictive inputs. Moreover, it relies on the local/window-based information while lacking to consider useful protein-level characteristics. 

      We conceptualize, design and test APOD (Accurate Predictor Of DFLs), the first highly accurate predictor that utilizes both local- and protein-level inputs that quantify propensity for disorder, sequence composition, sequence conservation and selected putative structural properties. Consequently, APOD offers significantly more accurate predictions when compared with its faster predecessor, DFLpred, and several other alternative ways to predict DFLs. These improvements stem from the use of a more comprehensive set of inputs that cover the protein-level information and the application of a more sophisticated predictive model, a well-parametrized support vector machine. APOD achieves area under the curve = 0.82 (28% improvement over DFLpred) and Matthews correlation coefficient = 0.42 (180% increase over DFLpred) when tested on an independent/low-similarity test dataset. Consequently, APOD is a suitable choice for accurate and small-scale prediction of DFLs.
    - Description/Method: APOD (Accurate Predictor Of DFLs) is a machine learning-derived predictor of disordered flexible linkers (DFLs). APOD uses a two-step process to predict DFLs from protein sequences. First, the input sequence is converted into an information-rich profile that covers conservation, amino acid composition, and putative secondary structure, solvent accessibility and intrinsic disorder. This profile is processed to generate inputs to the predictive model using a small sliding window and protein-level putative disorder content, where the latter provides a protein-level bias for the window-based input. Second, a well-parametrized support vector machine model is used to generate DFL predictions from these inputs.
    - Access:
      - Web server: https://yanglab.qd.sdu.edu.cn/APOD/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: https://yanglab.nankai.edu.cn/tmp/CAID2_packages/APOD_20220524_CAID2.tar.gz
  - flDPnn: 
    - Paper: [flDPnn: Accurate intrinsic disorder prediction with putative propensities of disorder functions](https://www.nature.com/articles/s41467-021-24773-7) (Nature Communications, 2021)
    - Abstract: Identification of intrinsic disorder in proteins relies in large part on computational predictors, which demands that their accuracy should be high. Since intrinsic disorder carries out a broad range of cellular functions, it is desirable to couple the disorder and disorder function predictions. We report a computational tool, flDPnn, that provides accurate, fast and comprehensive disorder and disorder function predictions from protein sequences. The recent Critical Assessment of protein Intrinsic Disorder prediction (CAID) experiment and results on other test datasets demonstrate that flDPnn offers accurate predictions of disorder, fully disordered proteins and four common disorder functions. These predictions are substantially better than the results of the existing disorder predictors and methods that predict functions of disorder. Ablation tests reveal that the high predictive performance stems from innovative ways used in flDPnn to derive sequence profiles and encode inputs. flDPnn’s webserver is available at http://biomine.cs.vcu.edu/servers/flDPnn/.
    - Description/Method: flDPnn (function- and linker-based Disorder Prediction using deep neural network) generates accurate and fast disorder and disorder function predictions from protein sequence using a three-step process. First, the input sequence is converted into a profile that covers conservation, putative secondary structure, and initial predictions of disorder, disordered linkers and disordered binding. Second, the profile is encoded into three distinct input types: 1) residue-level data using a sliding window; 2) window-level data using hand-crafted features that aggregate data from the window; and 3) protein-level information that quantifies overall bias for disordered and disorder functions. Third, these inputs are processed with a simple 4-layer deep feedforward neural network to generate disorder predictions. Moreover, four random forest models are used to predict propensities for protein binding, RNA binding, DNA binding and disordered linkers for the putative disordered residues predicted by the deep network.
    - Access:
      - Web server: https://biomine.cs.vcu.edu/server-handler/?type=servers&target=flDPnn/
      - REST API: N/A
      - Docker image: https://gitlab.com/sina.ghadermarzi/fldpnn_docker
      - GitHub repository
      - Others: [source codes](https://gitlab.com/sina.ghadermarzi/fldpnn) | https://bio.tools/fldpnn
  - flDPlr、flDPlr2:
    - Description/Method: flDPlr (function- and linker-based Disorder Prediction using logistic regression) is a variant of the flDPnn method that uses logistic regression instead of the neural network to predict disorder
  - flDPnn2
    - Paper: [flDPnn2: Accurate and Fast Predictor of Intrinsic Disorder in Proteins](https://www.sciencedirect.com/science/article/abs/pii/S0022283624002006?via%3Dihub) (Journal of Molecular Biology, 2024)
    - Abstract: Prediction of the intrinsic disorder in protein sequences is an active research area, with well over 100 predictors that were released to date. These efforts are motivated by the functional importance and high levels of abundance of intrinsic disorder, combined with relatively low amounts of experimental annotations. The disorder predictors are periodically evaluated by independent assessors in the Critical Assessment of protein Intrinsic Disorder prediction (CAID) experiments. The recently completed CAID2 experiment assessed close to 40 state-of-the-art methods demonstrating that some of them produce accurate results. In particular, flDPnn2 method, which is the successor of flDPnn that performed well in the CAID1 experiment, secured the overall most accurate results on the Disorder-NOX dataset in CAID2. flDPnn2 implements a number of improvements when compared to its predecessor including changes to the inputs, increased size of the deep network model that we retrained on a larger training set, and addition of an alignment module. Using results from CAID2, we show that flDPnn2 produces accurate predictions very quickly, modestly improving over the accuracy of flDPnn and reducing the runtime by half, to about 27 s per protein. flDPnn2 is freely available as a convenient web server at http://biomine.cs.vcu.edu/servers/flDPnn2/.
    - Description/Method: N/A
    - Access:
      - Web server: https://biomine.cs.vcu.edu/servers/flDPnn2/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: N/A
  - flDPnn3: flDPnn3a, flDPnn3b 
    - Note: ⚠️ No peer‑reviewed publication yet. 
    
      Latest results: [CAID Competition/Leaderboard](https://caid.idpcentral.org/methods). 
    
      Status: experimental.
    - Paper: N/A
    - Abstract: N/A
    - Description/Method: flDPnn3a is a predictor that predicts disorder using an innovative deep neural network. It incorporates predictions from disorder functions and disordered linkers, along with embeddings from the large protein language model ESM-2 as inputs.
    
      flDPnn3b is a predictor that predicts disorder using an transformer model. It incorporates predictions from disorder functions and disordered linkers, along with embeddings from the large protein language model ESM-2 as inputs.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others
 
</details>


#### Toyota Technological Institute at Chicago     
<details>
<summary>Jinbo Xu 许锦波</summary>

- Lab website: [Profile](https://home.ttic.edu/~jinbo/)

- Tools
  - AUCpreD
    - Paper: [AUCpreD: proteome-level protein disorder prediction by AUC-maximized deep convolutional neural fields](https://academic.oup.com/bioinformatics/article/32/17/i672/2450776?login=false) (Bioinformatics, 2016)
    - Abstract: Protein intrinsically disordered regions (IDRs) play an important role in many biological processes. Two key properties of IDRs are (i) the occurrence is proteome-wide and (ii) the ratio of disordered residues is about 6%, which makes it challenging to accurately predict IDRs. Most IDR prediction methods use sequence profile to improve accuracy, which prevents its application to proteome-wide prediction since it is time-consuming to generate sequence profiles. On the other hand, the methods without using sequence profile fare much worse than using sequence profile.

      Our experimental results show that our IDR prediction method AUCpreD outperforms existing popular disorder predictors. More importantly, AUCpreD works very well even without sequence profile, comparing favorably to or even outperforming many methods using sequence profile. Therefore, our method works for proteome-wide disorder prediction while yielding similar or better accuracy than the others.  
    - Description: This article formulates IDR prediction as a sequence labeling problem and employs a new machine learning method called Deep Convolutional Neural Fields (DeepCNF) to solve it. DeepCNF is an integration of deep convolutional neural networks (DCNN) and conditional random fields (CRF); it can model not only complex sequence-structure relationship in a hierarchical manner, but also correlation among adjacent residues. To deal with highly imbalanced order/disorder ratio, instead of training DeepCNF by widely used maximum-likelihood, we develop a novel approach to train it by maximizing area under the ROC curve (AUC), which is an unbiased measure for class-imbalanced data.
    - Access:
      - Web server: http://raptorx2.uchicago.edu/StructurePropertyPred/predict/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository
https://github.com/realbigws/RaptorX_Property_Fast
      - Others: https://bio.tools/aucpred
</details>


#### University of New Orleans     
<details>   
<summary>Md Tamjidul Hoque</summary>

- Lab website: [PI lab](https://tamjidul.github.io/)

- Tools
  - DisPredict2
    - Paper: [Estimation of Position Specific Energy as a Feature of Protein Residues from Sequence Alone for Structural Classification](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0161452) (PLoS ONE, 2016)
    - Abstract: A set of features computed from the primary amino acid sequence of proteins, is crucial in the process of inducing a machine learning model that is capable of accurately predicting three-dimensional protein structures. Solutions for existing protein structure prediction problems are in need of features that can capture the complexity of molecular level interactions. With a view to this, we propose a novel approach to estimate position specific estimated energy (PSEE) of a residue using contact energy and predicted relative solvent accessibility (RSA). Furthermore, we demonstrate PSEE can be reasonably estimated based on sequence information alone. PSEE is useful in identifying the structured as well as unstructured or, intrinsically disordered region of a protein by computing favorable and unfavorable energy respectively, characterized by appropriate threshold. The most intriguing finding, verified empirically, is the indication that the PSEE feature can effectively classify disorder versus ordered residues and can segregate different secondary structure type residues by computing the constituent energies. PSEE values for each amino acid strongly correlate with the hydrophobicity value of the corresponding amino acid. Further, PSEE can be used to detect the existence of critical binding regions that essentially undergo disorder-to-order transitions to perform crucial biological functions. Towards an application of disorder prediction using the PSEE feature, we have rigorously tested and found that a support vector machine model informed by a set of features including PSEE consistently outperforms a model with an identical set of features with PSEE removed. In addition, the new disorder predictor, DisPredict2, shows competitive performance in predicting protein disorder when compared with six existing disordered protein predictors.
    - Description/Method: 文献计算方法描述(主要是model架构)
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/tamjidul/DisPredict2_PSEE
      - Others: https://bio.tools/dispredict2
  - DisPredict3 
    - Paper: [DisPredict3.0: Prediction of intrinsically disordered regions/proteins using protein language model](https://www.sciencedirect.com/science/article/abs/pii/S0096300324001024?via%3Dihub) (Applied Mathematics and Computation, 2024)
    - Abstract: Intrinsically disordered proteins (IDPs) or protein regions (IDRs) do not have a stable three-dimensional structure, even though they exhibit important biological functions. They are structurally and functionally very different from ordered proteins and can cause many critical diseases. Accurate identification of disordered proteins/regions significantly impacts fields such as drug design, protein engineering, protein design, and related research. However, experimental identification of IDRs is complex and time-consuming, necessitating the development of an accurate and efficient computational method. The recent development of deep learning methods for protein language models shows the ability to learn evolutionary information from billions of protein sequences. This motivates us to develop a computational method, named DisPredict3.0, to predict proteins’ disordered regions (IDRs) using evolutionary information from a protein language model. Compared to the state-of-the-art method in the CAID (2018) assessment, DisPredict3.0 has an improvement of 2.51 %, 16.13 %, 17.98 %, and 11.94 % in terms of AUC, F1-score, MCC, and kappa, respectively. In addition, in the CAID-2 assessment (2022), DisPredict3.0 shows promising results and is ranked first for disorder residue prediction on the Disorder-NOX dataset. The DisPredict3.0 webserver is available at https://bmll.cs.uno.edu.
    - Description/Method: We develop a computational method named Dispredict3.0 to predict proteins’ disordered regions (IDRs) using evolutionary information from a protein language model. Dispredict3.0 is developed based on the representation of a protein language model and the features extracted from the flDPnn method. We further transformed the high-dimensional protein representation into a lower dimension with Principal Component Analysis (PCA) and trained an optimized Light gradient boosting Machine model.
    - Access:
      - Web server: https://caid.idpcentral.org/portal
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/wasicse/Dispredict3.0
      - Others 
  - ESMDisPred: ESMDisPred-1, ESMDisPred-2, ESMDisPred-2PDB
    - Note: ⚠️ No peer‑reviewed publication yet. 
    
      Latest results: [CAID Competition/Leaderboard](https://caid.idpcentral.org/methods). 
    
      Status: experimental.
    - Paper: N/A
    - Abstract: ESMDisPred: Enhanced Prediction of Disordered Regions Utilizing Representations from a Large Protein Language Model.
    - Description/Method: ESMDisPred is a deep learning framework that integrates convolutional and Transformer-based architectures to predict intrinsically disordered regions in proteins. By combining sequence embeddings, evolutionary features, and structural information, ESMDisPred achieves high predictive accuracy and generalization across diverse protein families.
      - ESMDisPred-1: Utilizes sequence-based features from DisPredict3.0 and ESM-1 embeddings.
      - ESMDisPred-2: Extends ESMDisPred-1 by incorporating ESM-2 embeddings, providing richer contextual protein representations.
      - ESMDisPred-2PDB: Builds upon ESMDisPred-2 by integrating structural-related features derived from PDB data, enhancing structural context awareness.
      - ESMDisPred-DNN: A comprehensive CNN–Transformer hybrid model trained using all feature types from DisPredict3.0, ESM-1, ESM-2, and PDB-derived structural descriptors.This variant captures both local residue patterns (via CNNs) and long-range dependencies (via Transformers), resulting in superior predictive performance.
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: https://hub.docker.com/r/wasicse/esmdispred
      - GitHub repository: https://github.com/wasicse/ESMDisPred
      - Others 
</details>


#### University of Missouri     
<details>
<summary>Jianlin (Jack) Cheng 程建林</summary>

- Lab website: [Bioinformatics and Machine Learning Laboratory](https://calla.rnet.missouri.edu/cheng/jianlin.cheng.html)

- Tools
  - PreDisorder
    - Paper: [PreDisorder: ab initio sequence-based prediction of protein disordered regions](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/1471-2105-10-436) (BMC Bioinformatics, 2009)
    - Abstract: Disordered regions are segments of the protein chain which do not adopt stable structures. Such segments are often of interest because they have a close relationship with protein expression and functionality. As such, protein disorder prediction is important for protein structure prediction, structure determination and function annotation.

      This paper presents our protein disorder prediction server, PreDisorder. It is based on our ab initio prediction method (MULTICOM-CMFR) which, along with our meta (or consensus) prediction method (MULTICOM), was recently ranked among the top disorder predictors in the eighth edition of the Critical Assessment of Techniques for Protein Structure Prediction (CASP8). We systematically benchmarked PreDisorder along with 26 other protein disorder predictors on the CASP8 data set and assessed its accuracy using a number of measures. The results show that it compared favourably with other ab initio methods and its performance is comparable to that of the best meta and clustering methods.

      PreDisorder is a fast and reliable server which can be used to predict protein disordered regions on genomic scale. It is available at http://casp.rnet.missouri.edu/predisorder.html.
    - Description/Method: PreDisorder is a bidirectional recurrent neural network method for predicting if a residue in a protein is disordered. Given the sequence of a protein as input, it uses PSI-BLAST to generate the sequence profile and SCRATCH to predict the secondary structure and relative solvent accessibility for the protein. The sequence profile, secondary structure and relative solvent accessibility are used by a bidirectional recurrent neural network to generate hidden features to represent every residue, its N-terminal context, and its C-terminal context to predict its probability of being disordered. The output is a list of predicted disordered probabilities for all the residues in the protein. Users can set a threshold (e.g., 0.5) on the probabilities to assign the residues to disordered or ordered states. Different thresholds lead to different precision and recall (or specificity and sensitivity) of disorder prediction.
    - Access:
      - Web server: http://casp.rnet.missouri.edu/predisorder.html
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others: https://bio.tools/predisorder | https://multicom-toolbox.mu.hekademeia.org/tools.html#license
</details>




### Canada
#### University of British Columbia     
<details>
<summary>Nawar Malhis</summary>

- Lab website: [Gsponer Lab - Michael Smith Laboratories](https://gsponerlab.msl.ubc.ca/) | [Profile](https://gsponerlab.msl.ubc.ca/people/nawar-malhis/)

- Tools
  - IPA(IDR Probabilistic Annotation): IPA-AF2-Linker
    - Note: ⚠️ No peer‑reviewed publication yet. 
      
        Latest results: see Paper below  
    - Paper: [Probabilistic Annotations of Protein Sequences for Intrinsically Disordered Features](https://www.biorxiv.org/content/10.1101/2024.12.18.629275v2.full) (bioRxiv preprint, 2025)
    - Abstract: This paper introduces a novel platform for IDR Probabilistic Annotation (IPA). The IPA
platform now encompasses tools for predicting 'Linker' regions and 'nucleic', 'protein', and
'all' (protein or nucleic) IDR binding sites within protein amino acid sequences. Despite its
simplicity and computational efficiency, results demonstrate that IPA performs competitively
with leading tools in predicting 'protein' and 'all' IDR binding sites while considerably
outperforming all tools in identifying Linker regions and nucleic binding sites. An important
contribution of this work is the introduction of a new output paradigm for computational
feature predictions. Traditional tools typically express predictions as scores, with higher
values indicating greater probabilities. However, these scores lack true probabilistic meaning
and interpretability, even derived from logistic regression models. This limitation arises
primarily because training data priors differ from broader populations' unknown priors. This
paper proposes applying a reverse Bayes Rule to logistic regression outputs, effectively
normalizing for the priors in the training data. This adjustment produces scores representing
actual probabilities, assuming 50% priors in the general population. Such scores are
interpretable in isolation and enable comparability and integration across different tools,
marking a significant step toward standardization in feature prediction methodologies.
    - Description/Method: The IPA platform provides probabilistic annotation of features related to intrinsically disordered regions (IDRs). It standardizes computational feature prediction using a reverse Bayes approach to transform logistic regression outputs into true probabilities, effectively removing the influence of training data priors.
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/NawarMalhis/IPA
      - Others: orca.msl.ubc.ca/nmshare/ipa.tar.gz | https://bio.tools/ipa_idr_probabilistic_annotations
</details>


## South America
### Argentina
#### IIBIO, CONICET-UNSAM     
<details>
<summary>Lucia Beatriz Chemes</summary>

- Lab website: [Profile](https://bicyt.conicet.gov.ar/fichas/p/lucia-beatriz-chemes)

- Tools
  - LINKER-Pred: LINKER-Pred, LINKER-Pred-Lite, LINKER-Pred2
    - Note: ⚠️ No peer‑reviewed publication yet. 
  
        Latest results: see Paper below
    - Paper: [LINKER-Pred: A Public Web Server for Accurate Prediction of Disordered Flexible Linkers in Proteins](https://www.biorxiv.org/content/10.1101/2025.10.29.685455v1) (bioRxiv preprint, 2025)
    - Abstract: Disordered Flexible Linkers (DFLs) are unstructured regions that play critical roles in interdomain communication and multivalent protein interactions. Despite their biological
significance, the accurate identification of DFLs remains challenging due to limited
experimental annotations and sparsity of dedicated prediction tools. Here we introduce
LINKER-Pred, a publicly available web server featuring two convolutional neural networkbased predictors trained on a novel large-scale dataset of linkers connecting folded domains
(DLD dataset) and DisProt linkers. LINKER-Pred2 combines ProtTrans and MSA-Transformer
embeddings within an ensemble CNN framework, achieving state-of-the-art performance on
CAID2 and CAID3 benchmarks. LINKER-Pred-Lite excludes MSA-based features, improving
speed while maintaining competitive predictive accuracy. LINKER-Pred predictors offer robust
residue-level DFL predictions directly from sequence, providing a scalable solution for DFL
annotation across proteomes. The LINKER-Pred web server and associated resources are
freely available at https://pcrgwd.ucd.ie/linker_pred/, offering the research community an
accessible tool for studying protein disorder and modularity.
    - Description/Method: 
      - LINKER-Pred: LINKER-Pred is a Linker only predictor trained on our DLD linker dataset and Disprot Linker dataset. 
      - LINKER-Pred-Lite: A fast Linker predictor. Do not need Multiple Sequence Alignment. Generate one prediction in seconds.
      - LINKER-Pred2: Linker predictor. An updated version of LINKER-Pred.
    - Access:
      - Web server: https://pcrgwd.ucd.ie/linker_pred/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/deemeng/punch_linker
      - Others 
</details>



## EMEA

### United Kingdom
#### University College London     
<details>
<summary>David T. Jones</summary>

- Lab website: [UCL Bioinformatics Group](https://bioinf.cs.ucl.ac.uk/) | [Profile](http://www0.cs.ucl.ac.uk/staff/d.jones/)

- Tools
  - DISOPRED3: DISOPRED3-diso
    - Paper: [DISOPRED3: precise disordered region predictions with annotated protein-binding activity](https://academic.oup.com/bioinformatics/article/31/6/857/215129?login=false) (Bioinformatics, 2014)
    - Abstract: A sizeable fraction of eukaryotic proteins contain intrinsically disordered regions (IDRs), which act in unfolded states or by undergoing transitions between structured and unstructured conformations. Over time, sequence-based classifiers of IDRs have become fairly accurate and currently a major challenge is linking IDRs to their biological roles from the molecular to the systems level.
      
      We describe DISOPRED3, which extends its predecessor with new modules to predict IDRs and protein-binding sites within them. Based on recent CASP evaluation results, DISOPRED3 can be regarded as state of the art in the identification of IDRs, and our self-assessment shows that it significantly improves over DISOPRED2 because its predictions are more specific across the whole board and more sensitive to IDRs longer than 20 amino acids. Predicted IDRs are annotated as protein binding through a novel SVM based classifier, which uses profile data and additional sequence-derived features. Based on benchmarking experiments with full cross-validation, we show that this predictor generates precise assignments of disordered protein binding regions and that it compares well with other publicly available tools.
    - Description/Method: DISOPRED3 combines three predictors: the original DISOPRED feed-forward neural network, DISOPRED2 SVM and a nearest neighbor classifier. A small second-stage neural network combines three predictors into a single output. Three independent SVM classifiers identify binding positions based on: (i) single sequences alone, Blosum62 values; (ii) PSSM from PSI-BLAST against UniRef90; (iii) PSSM plus the length and start/end of the region, a flag for windows outside protein termini and amino acid composition. Disorder training data was derived from Disprot v5.0 (only NMR or biophysical methods) and from the PDB (February 2010), redundancy-reduced, percentage sequence identity <90%, ≤2.2Å, chains longer than 24 residues. Missing residues and those with occupancy zero, were treated as disordered. Binding data was derived from Disfani et al., 2012. Less than 30% identity with other regions for a total of 397 PDB chains (372 UniProtKB). Negative training examples were obtained from unbound protein domain linker regions in known protein structures. Linkers annotated in CATH v.3.5, spanning between 5 and 60 amino acids and lacking interactions with other molecules in the same PDB file (atoms closer than 6Å; 3.9Å for ligands and metal ions) and with less than 30% sequence identity to other regions.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository: https://github.com/psipred/disopred
      - Others: https://bioinf.cs.ucl.ac.uk/downloads/DISOPRED/ | https://bio.tools/disopred3 
</details>


#### University of Exeter     
<details>
<summary>Zheng Rong Yang</summary>

- Lab website: [Profile](https://scholargps.com/scholars/45992467342875/zheng-rong-yang | https://www.scilit.com/scholars/172034)

- Tools
  - RONN
    - Paper: [RONN: the bio-basis function neural network technique applied to the detection of natively disordered regions in proteins](https://academic.oup.com/bioinformatics/article/21/16/3369/215577?login=false) (Bioinformatics, 2005)
    - Abstract: 文献摘要
    - Description/Method: 文献计算方法描述(主要是model架构)
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others 
</details>

### Germany
#### Humboldt-Universität zu Berlin     
<details>
<summary>Rune Linding</summary>

- Lab website: [co-PI of the Klipp-Linding Lab](https://rumo.biologie.hu-berlin.de/tbp/index.php/en/)

- Tools
  - DisEMBL: DisEMBL-dis465, DisEMBL-disHL
    - Paper: [Protein disorder prediction: implications for structural proteomics](https://www.cell.com/structure/fulltext/S0969-2126(03)00235-1?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0969212603002351%3Fshowall%3Dtrue) (Structure, 2003)
    - Abstract: A great challenge in the proteomics and structural genomics era is to predict protein structure and function, including identification of those proteins that are partially or wholly unstructured. Disordered regions in proteins often contain short linear peptide motifs (e.g., SH3 ligands and targeting signals) that are important for protein function. We present here DisEMBL, a computational tool for prediction of disordered/unstructured regions within a protein sequence. As no clear definition of disorder exists, we have developed parameters based on several alternative definitions and introduced a new one based on the concept of "hot loops," i.e., coils with high temperature factors. Avoiding potentially disordered segments in protein expression constructs can increase expression, foldability, and stability of the expressed protein. DisEMBL is thus useful for target selection and the design of constructs as needed for many biochemical studies, particularly structural biology and structural genomics projects. The tool is freely available via a web interface (http://dis.embl.de) and can be downloaded for use in large-scale studies.(⚠️ for DisEMBL, 2003)
    - Description/Method: Ensemble of five artificial neural networks trained on each the three data sets: i) loops/coils as defined by DSSP; ii) Hot loops, a refined subset of the above with a high degree of mobility based on Cα temperature factors (B factors) using Smith et al., 2003 scales; iii) Missing coordinates in X-Ray structure as defined by remark465 entries in PDB. Artificial neural networks were trained on symmetric sequence windows centered at the position to be predicted. All neural networks were trained with a learning rate of 0.005. The size of these windows was systematically varied from 3 to 51 residues. For each window size the number of hidden units was varied in the range 5–50. The performance of every such combination was evaluated by 5-fold cross-validation and best parameter combinations were selected based on ROC curves. Window 19 and 30 hidden units for the coils predictor. 41 residues and 5 hidden neurons for the hot-loops. 21 residues and 30 hidden units for the remark465. The score distributions of positive and negative test examples were estimated using Gaussian kernel density estimation. For coil prediction a prior probability of 43% (the composition of the training data set) was used while a prior probability of 20% was used in the case of hot loop prediction.
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: http://dis.embl.de/ | https://bio.tools/disembl
</details>



###  Hungary
####  Eötvös Loránd University

<details>
<summary>Zsuzsanna Dosztányi</summary>

- Lab website: [Dosztányi lab](https://dlab.elte.hu/)
- Tools:
  - AIUPred
    - Paper: [AIUPred: combining energy estimation with deep learning for the enhanced prediction of protein disorder](https://academic.oup.com/nar/article/52/W1/W176/7673484) (Nucleic Acids Research, 2024)
    - Abstract: Intrinsically disordered proteins and protein regions (IDPs/IDRs) carry out important biological functions without relying on a single well-defined conformation. As these proteins are a challenge to study experimentally, computational methods play important roles in their characterization. One of the commonly used tools is the IUPred web server which provides prediction of disordered regions and their binding sites. IUPred is rooted in a simple biophysical model and uses a limited number of parameters largely derived on globular protein structures only. This enabled an incredibly fast and robust prediction method, however, its limitations have also become apparent in light of recent breakthrough methods using deep learning techniques. Here, we present AIUPred, a novel version of IUPred which incorporates deep learning techniques into the energy estimation framework. It achieves improved performance while keeping the robustness of the original method. Based on the evaluation of recent benchmark datasets, AIUPred scored amongst the top three single sequence based methods. With a new web server we offer fast and reliable visual analysis for users as well as options to analyze whole genomes in mere seconds with the downloadable package. AIUPred is available at https://aiupred.elte.hu.
    - Description: AIUPred uses a statistical potential based energy prediction to assess whether an amino acid can form favorable interactions with its sequential environment. The energy prediction is achieved by a series of convolutional neural networks with residual connections. The input sequences are embedded using a 21 dimension Word2Vec embedding. The output energies are then fed to a logistic regression module to obtain disorder propensity scores.
    - Access:
      - Web server: https://aiupred.elte.hu/
      - REST API: [API docs](https://aiupred.elte.hu/help)
      - Docker image: N/A
      - GitHub repository: https://github.com/doszilab/AIUPred
  - IUPred3
    - Paper: [IUPred3: prediction of protein disorder enhanced with unambiguous experimental annotation and visualization of evolutionary conservation](https://academic.oup.com/nar/article/49/W1/W297/6287841?login=false) (Nucleic Acids Research, 2021)
    - Abstract: Intrinsically disordered proteins and protein regions (IDPs/IDRs) exist without a single well-defined conformation. They carry out important biological functions with multifaceted roles which is also reflected in their evolutionary behavior. Computational methods play important roles in the characterization of IDRs. One of the commonly used disorder prediction methods is IUPred, which relies on an energy estimation approach. The IUPred web server takes an amino acid sequence or a Uniprot ID/accession as an input and predicts the tendency for each amino acid to be in a disordered region with an option to also predict context-dependent disordered regions. In this new iteration of IUPred, we added multiple novel features to enhance the prediction capabilities of the server. First, learning from the latest evaluation of disorder prediction methods we introduced multiple new smoothing functions to the prediction that decreases noise and increases the performance of the predictions. We constructed a dataset consisting of experimentally verified ordered/disordered regions with unambiguous annotations which were added to the prediction. We also introduced a novel tool that enables the exploration of the evolutionary conservation of protein disorder coupled to sequence conservation in model organisms. The web server is freely available to users and accessible at https://iupred3.elte.hu.
    - Description: IUPred3 predicts protein disorder based on an energy estimation approach utilizing statistical potentials. The parameters of the method are derived from a collection of known structures only and disordered regions are recognized based on their unfavorable estimated energies. IUPred3 is a fast and robust method that carries out predictions for single protein sequences without using evolutionary information.
    - Access:
      - Web server: https://iupred3.elte.hu/
      - REST API: [API docs](https://iupred3.elte.hu/help_new)
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: https://bio.tools/iupred3
  - AIUPred-2-disorder
    - Note: ⚠️ No peer‑reviewed publication yet. 
    
      Latest results: [CAID Competition/Leaderboard](https://caid.idpcentral.org/methods). 
    
      Status: experimental. 
    - Paper: N/A
    - Abstract: N/A
    - Description: AIUPred-2 utilizes a novel energy embedding technique that was trained on energy like quantities derived globular structures. The embedding was than used for transfer learning to achieve fast and accurate single sequence prediction.
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: N/A
</details>

### Italy
#### University of Padua     
<details>
<summary>Silvio C. E. Tosatto</summary>

- Lab website: [Profile](https://biocomputingup.it/person/silvio-c-e-tosatto/ | https://protein.bio.unipd.it/people/silvio)

- Tools
  - AlphaFold-disorder: AlphaFold-pLDDT, AlphaFold-rsa, AlphaFold-binding
    - Paper: [Intrinsic protein disorder and conditional folding in AlphaFoldDB](https://pmc.ncbi.nlm.nih.gov/articles/PMC9601767/) (Protein Sci, 2022)
    - Abstract: Intrinsically disordered regions (IDRs) defying the traditional protein structure-function paradigm have been difficult to analyze. The availability of accurate structure predictions on a large scale in AlphaFoldDB offers a fresh perspective on IDR prediction. Here, we establish three baselines for IDR prediction from AlphaFoldDB models based on the recent CAID dataset. Surprisingly, AlphaFoldDB is highly competitive for predicting both IDRs and conditionally folded binding regions, demonstrating the plasticity of the disorder to structure continuum.
    - Description: AlphaFold-disorder generates its predictions using the AlphaFold structure as input, the method generates three outputs. i) AlphaFold-disorder provides disorder propability as 1 - pLDDT and the default threshold is 0.312 (representing pLDDT <68.8%), optimized by maximizing the F1-Score performance on the CAID-1 DisProt dataset. ii) AlphaFold-RSA predicts as disordered those residues with a high solvent accessible surface. The relative solvent accessibility (RSA) is calculated over a local window (25 residues). The optimal classification threshold for AlphaFold-RSA is 0.581. iii) AlphaFold-binding Visual inspection also shows that some “ribbon” regions have high RSA yet retain some local secondary structure and have a relatively high pLDDT score, suggesting the possibility to act as disordered binding regions. The combination of both features is used to identify regions with a tendency to be simultaneously accessible (RSA) and structured (pLDDT), which may indicate disordered binding regions or conditional folding. (AlphaFold-binding is not for disorder prediction).
    In short, Disorder and binding region detection from AlphaFold predicted structures. The script parses and processes PDB files generated by AlphaFold. It expects the pLDDT score in the B-factor column. As intermediate (mandatory) step it calculates the Relative Solvent Accessibility (RSA) as provided by DSSP and BioPython.
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/BioComputingUP/AlphaFold-disorder
  - AlphaFold3-disorder: AlphaFold-binding, AlphaFold-pLDDT, AlphaFold-rsa 
    - Description: See AlphaFold-disorder above. In this case structures are not download from AlphaFoldDB but generated manually from the AlphaFold3 web server.
  - ESpritz: ESpritz-D, ESpritz-N, ESpritz-X
    - Paper: [ESpritz: accurate and fast prediction of protein disorder](https://academic.oup.com/bioinformatics/article/28/4/503/211681) (Bioinformatics, 2011)
    - Abstract: Intrinsically disordered regions are key for the function of numerous proteins, and the scant available experimental annotations suggest the existence of different disorder flavors. While efficient predictions are required to annotate entire genomes, most existing methods require sequence profiles for disorder prediction, making them cumbersome for high-throughput applications.
  
      ESpritz predicts three flavors of disorder at two distinct false positive rates, either with a fast or slower and slightly more accurate approach. Given its state-of-the-art performance, it can be especially useful for high-throughput applications.

      Both a web server for high-throughput analysis and a Linux executable version of ESpritz are available from: http://protein.bio.unipd.it/espritz/.
    - Description/Method: In this work, we present an ensemble of protein disorder predictors called ESpritz. These are based on bidirectional recursive neural networks and trained on three different flavors of disorder, including a novel NMR flexibility predictor. ESpritz can produce fast and accurate sequence-only predictions, annotating entire genomes in the order of hours on a single processor core. Alternatively, a slower but slightly more accurate ESpritz variant using sequence profiles can be used for applications requiring maximum performance. Two levels of prediction confidence allow either to maximize reasonable disorder detection or to limit expected false positives to 5%. ESpritz performs consistently well on the recent CASP9 data, reaching a Sw measure of 54.82 and area under the receiver operator curve of 0.856. The fast predictor is four orders of magnitude faster and remains better than most publicly available CASP9 methods, making it ideal for genomic scale predictions.

      ESpritz: is based on a machine learning method which does not require sliding windows or any complex sources of information (Bi-directional Recursive Neural Networks (BRNN)). Learning proceeds by extracting the relevant information from the local context of the residue under consideration using the BRNN. The algorithm used for training was gradient descent and the backpropagation through structure algorithm. There are three types of disorder data corresponding to three different ESpritz models: X - derived from missing residues in X-ray PDB chains (1 May 2008) of length between 25 and 2,000 amino acids, resolution at least 2.5 Å and R-factor up to 25%. Sequence identity reduced with UniqueProt to an HSSP value of 0 and using the -m option to give priority to proteins with better quality. The resulting lists were merged and redundancy reduced in a similar manner leaving proteins with disordered regions as a priority. D - Each DisProt (release 5.7) entry was matched to PDB entries via the UniProtKB accession. DisProt takes preference over missing residues. N - NMR mobility/flexibility is calculated using the Mobi server. Mobi is based on a simple algorithm to find regions with different conformations among all the models. The extraction and redundancy reduction is identical to the X-ray data collection except no quality filters are considered.
    - Access:
      - Web server: http://old.protein.bio.unipd.it/espritz/
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others: https://bio.tools/espritz
  - MobiDB-lite
    - Paper: [MobiDB-lite: fast and highly specific consensus prediction of intrinsic disorder in proteins](https://academic.oup.com/bioinformatics/article/33/9/1402/2908909?login=false) (Bioinformatics, 2017)
    - Abstract: Intrinsic disorder (ID) is established as an important feature of protein sequences. Its use in proteome annotation is however hampered by the availability of many methods with similar performance at the single residue level, which have mostly not been optimized to predict long ID regions of size comparable to domains.

      Here, we have focused on providing a single consensus-based prediction, MobiDB-lite, optimized for highly specific (i.e. few false positive) predictions of long disorder. The method uses eight different predictors to derive a consensus which is then filtered for spurious short predictions. Consensus prediction is shown to outperform the single methods when annotating long ID regions. MobiDB-lite can be useful in large-scale annotation scenarios and has indeed already been integrated in the MobiDB, DisProt and InterPro databases.

      MobiDB-lite is available as part of the MobiDB database from URL: http://mobidb.bio.unipd.it/. An executable can be downloaded from URL: http://protein.bio.unipd.it/mobidblite/.
    - Description/Method: The implementation of MobiDB-lite involves two consecutive steps. In the first step, MobiDB-lite makes use of multiple prediction methods, including three variants of ESpritz, two variants of IUpred, DisEMBL and GlobPlot. The consensus is obtained by combining the results of at least 5 out of 8 methods. The second step involves refining the consensus to remove spurious regions of disorder within ordered regions and vice versa. The refinement process includes an iterative filtering step that eliminates short stretches of up to three residues of ID within ordered regions and vice versa. ID stretches flanked by ordered stretches (max 3 residues) are converted to order and vice versa. Structured stretches of up to 10 consecutive residues are then converted to ID only if they are flanked by two disordered regions of at least 20 residues. Finally, a length cutoff is applied to ID regions, and only those of at least 20 residues are kept.
    - Access:
      - Web server: https://mobidb.org/
      - REST API: [API docs](https://mobidb.org/help#swagger)
      - Docker image: 
      - GitHub repository: 
      - Others
  - MobiDB-lite 4.0
    - Paper: [MobiDB-lite 4.0: faster prediction of intrinsic protein disorder and structural compactness](https://academic.oup.com/bioinformatics/article/41/5/btaf297/8128331?login=false) (Bioinformatics, 2025)
    - Abstract: In recent years, many disorder predictors have been developed to identify intrinsically disordered regions (IDRs) in proteins, achieving high accuracy. However, it may be difficult to interpret differences in predictions across methods. Consensus methods offer a simple solution, highlighting reliable predictions while filtering out uncertain positions. Here, we present a new version of MobiDB-lite, a consensus method designed to predict long IDRs and classify them based on compositional biases and conformational properties.

      MobiDB-lite 4.0 pipeline was optimized to be ten times faster than the previous version. It now provides compactness annotations based on predicted apparent scaling exponent. The newly added features and disorder subclassifications allow the users to get a comprehensive insight into the protein’s function and characteristics. MobiDB-lite 4.0 is integrated into the MobiDB and DisProt databases. A version without the compactness predictor is integrated into InterProScan, propagating MobiDB-lite annotations to UniProtKB.
  
      The MobiDB-lite 4.0 source code and a Docker container are available from the GitHub repository: https://github.com/BioComputingUP/MobiDB-lite.
    - Description/Method: MobiDB-lite is a Python program designed to generate a consensus prediction of intrinsically disordered regions in proteins. The consensus is generated by measuring predictors agreement where at least 5/8 of predictors must agree to assign disorder state to a residue. A mathematical morphology (MM) dilation/erosion processing is applied to smooth the prediction and short regions are filtered out.

      The code is integrated into the InterProScan software. The MobiDB-lite output is available in the MobiDB, InterPro, PDBe, PDBe-KB and UniProtKB databases.

      This version of MobiDB has been developed in collaboration with Matthias Blum who optimized its execution time by 10 times. Matthias' version is available [here](https://github.com/matthiasblum/idrpred) (and called IDRPred).
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: https://github.com/BioComputingUP/MobiDB-lite_docker
      - GitHub repository: https://github.com/BioComputingUP/MobiDB-lite | [IDRPred，a modern implementation of MobiDB-lite](https://github.com/matthiasblum/idrpred)
      - Others
</details>




### Belgium
#### Vrije Universiteit Brussel     
<details>
<summary>Wim Vranken</summary>

- Lab website: [Bio2Byte group](https://bio2byte.be/info/)

- Tools
  - DisoMine
    - Paper: [Prediction of Disordered Regions in Proteins with Recurrent Neural Networks and Protein Dynamics](https://www.sciencedirect.com/science/article/abs/pii/S0022283622001590?via%3Dihub) (Journal of Molecular Biology, 2022)
    - Abstract: The role of intrinsically disordered protein regions (IDRs) in cellular processes has become increasingly evident over the last years. These IDRs continue to challenge structural biology experiments because they lack a well-defined conformation, and bioinformatics approaches that accurately delineate disordered protein regions remain essential for their identification and further investigation. Typically, these predictors use the protein amino acid sequence, without taking into account likely sequence-dependent emergent properties, such as protein backbone dynamics.
Here we present DisoMine, a method that predicts protein’long disorder’ with recurrent neural networks from simple predictions of protein dynamics, secondary structure and early folding. The tool is fast and requires only a single sequence, making it applicable for large-scale screening, including poorly studied and orphan proteins. DisoMine is a top performer in its category and compares well to disorder prediction approaches using evolutionary information.
DisoMine is freely available through an interactive webserver at https://bio2byte.be/disomine/.
    - Description/Method: DisoMine is a method that predicts protein 'long disorder' with recurrent neural networks from simple predictions of protein dynamics, secondary structure and early folding. The tool is fast and requires only a single sequence, making it applicable for large-scale screening, including poorly studied and orphan proteins.
    - Access:
      - Web server: https://bio2byte.be/b2btools/disomine/
      - REST API: [API docs](https://bio2byte.be/b2btools/documentation/disomine/)
      - Docker image: N/A
      - GitHub repository: https://github.com/bio2byte/
      - Others: https://pypi.org/project/b2bTools/ (⚠️ DisoMine is one of the available predictors the package provided) | https://bio.tools/disomine
</details>


### Poland
#### Silesian University of Technology     
<details>
<summary>Katarzyna Stapor</summary>

- Lab website: [Profile](https://english.swps.pl/katarzyna-stapor)

- Tools
  - DisorderUnetLM
    - Paper: [DisorderUnetLM: Validating ProteinUnet for efficient protein intrinsic disorder prediction](https://www.sciencedirect.com/science/article/abs/pii/S0010482524016718) (Computers in Biology and Medicine, 2024)
    - Abstract: The prediction of intrinsic disorder regions has significant implications for understanding protein functions and dynamics. It can help to discover novel protein-protein interactions essential for designing new drugs and enzymes. Recently, a new generation of predictors based on protein language models (pLMs) is emerging. These algorithms reach state-of-the-art accuracy without calculating time-consuming multiple sequence alignments (MSAs). This article introduces the new DisorderUnetLM disorder predictor, which builds upon the idea of ProteinUnet. It uses the Attention U-Net convolutional network and incorporates features from the ProtTrans pLM. DisorderUnetLM achieves top results in the direct comparison with recent predictors exploiting MSAs and pLMs. Moreover, among 43 predictors on the latest CAID-2 benchmark, it ranks 1st for the NOX subset in terms of the ROC-AUC metric (0.844) and 2nd for the AP metric (0.596). For the CAID-2 PDB subset, it ranks in the top 10 (ROC-AUC of 0.924 and AP of 0.862). The code and model are publicly available and fully reproducible at doi.org/10.24433/CO.7350682.v1.
    - Description/Method: Deep learning-based protein intrinsic disorder predictor based on the ensemble of 10 Attention U-Net convolutional neural networks and features from protein language model ProtTrans-T5-XL-U50.
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository
      - Others: https://codeocean.com/capsule/0867702/tree/v1 
</details>


### Ireland
#### University College Dublin   
<details>
<summary>Gianluca Pollastri</summary>

- Lab website: [Profile](https://people.ucd.ie/gianluca.pollastri/)

- Tools
  - PUNCH2
    - Paper: [PUNCH2: Explore the strategy for intrinsically disordered protein predictor](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0319208) (PLoS ONE, 2025)
    - Abstract: Intrinsically disordered proteins (IDPs) and their intrinsically disordered regions (IDRs) lack stable three-dimensional structures, posing significant challenges for computational prediction. This study introduces PUNCH2 and PUNCH2-light, advanced predictors designed to address these challenges through curated datasets, innovative feature extraction, and optimized neural architectures. By integrating experimental datasets from PDB (PDB_missing) and fully disordered sequences from DisProt (DisProt_FD), we enhanced model performance and robustness. Three embedding strategies—One-Hot, MSA-based, and PLM-based embeddings—were evaluated, with ProtTrans emerging as the most effective single embedding and combined embeddings achieving the best results. The predictors employ a 12-layer convolutional network (CNN_L12_narrow), offering a balance between accuracy and computational efficiency. PUNCH2 combines One-Hot, ProtTrans, and MSA-Transformer embeddings, while PUNCH2-light provides a faster alternative excluding MSA-based embeddings. PUNCH2 and its streamlined variant, PUNCH2-light, are competitive with other predictors on the CAID2 benchmark and rank as the top two predictors in the CAID3 competition. These tools provide efficient, accurate solutions to advance IDP research and understanding.
    - Description/Method: A residue-level Intrinsically Disordered Region/Protein(IDP/IDR) predictor trained on PDB and Disprot Databases.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository: https://github.com/deemeng/punch2
      - Others: [Datasets](https://huggingface.co/datasets/deeeeeeeeee/PUNCH2_data) 
  - PUNCH2-Light
    - Paper: [PUNCH2: Explore the strategy for intrinsically disordered protein predictor](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0319208) (PLoS ONE, 2025)
    - Abstract: Intrinsically disordered proteins (IDPs) and their intrinsically disordered regions (IDRs) lack stable three-dimensional structures, posing significant challenges for computational prediction. This study introduces PUNCH2 and PUNCH2-light, advanced predictors designed to address these challenges through curated datasets, innovative feature extraction, and optimized neural architectures. By integrating experimental datasets from PDB (PDB_missing) and fully disordered sequences from DisProt (DisProt_FD), we enhanced model performance and robustness. Three embedding strategies—One-Hot, MSA-based, and PLM-based embeddings—were evaluated, with ProtTrans emerging as the most effective single embedding and combined embeddings achieving the best results. The predictors employ a 12-layer convolutional network (CNN_L12_narrow), offering a balance between accuracy and computational efficiency. PUNCH2 combines One-Hot, ProtTrans, and MSA-Transformer embeddings, while PUNCH2-light provides a faster alternative excluding MSA-based embeddings. PUNCH2 and its streamlined variant, PUNCH2-light, are competitive with other predictors on the CAID2 benchmark and rank as the top two predictors in the CAID3 competition. These tools provide efficient, accurate solutions to advance IDP research and understanding.
    - Description/Method: An IDR predictor. A faster predictor compare to PUNCH2. No MSA searching required.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository: https://github.com/deemeng/punch2_light
      - Others: [Datasets](https://huggingface.co/datasets/deeeeeeeeee/PUNCH2_data) 
</details>

### France
#### Sorbonne University     
<details>
<summary>Isabelle Callebaut </summary>

- Lab website: [Profile](http://www-ext.impmc.upmc.fr/~callebau/)

- Tools
  - pyHCA: PyHCA-disorder
    - Paper: [HCAtk and pyHCA: A Toolkit and Python API for the Hydrophobic Cluster Analysis of Protein Sequences](https://www.biorxiv.org/content/10.1101/249995v1) (⚠️ bioRxiv preprint, 2018)
    - Abstract: Detecting protein domains sharing no similarity to known domains, as stored in domain databases, is a challenging problem, particularly for unannotated proteomes, domains emerged recently, fast diverging proteins or domains with intrinsically disordered regions.

      We developed pyHCA and HCAtk, a python API and standalone tool gathering together improved versions of previously developed methodologies, with new functionalities. The developed tools can be either used from command line or from a python API.

      HCAtk and pyHCA are available at https://github.com/T-B-F/pyHCA under the CeCILL-C license.
    - Description/Method: pyHCA (disorder mode) predicts intrinsically disordered regions at the amino acid level by combining information on physico-chemical properties of amino acids with features derived from Hydrophobic Cluster Analysis (HCA). HCA provides information on the foldability of a protein, based on the density of hydrophobic clusters, using its single amino acid sequence (without considering sequence profiles) (see for recent papers Bitard-Feidel et al Proteomics 2018 doi: 10.1002/pmic.201800054 and Bruley et al. Proteins 2023 doi: 10.1002/prot.26441). Machine learning features were extracted based on a subset of AAIndex and HCA annotations. Thus, the features cover physico-chemical and topological properties at different levels (amino acids, hydrophobic clusters, foldable domains and windows of fixed lengths). PyHCA-disorder classified each amino acid as intrinsically disordered or not using a gradient boosting decision tree algorithm trained using lightgbm on a non-redunant set of MobiDB sequences.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository: https://github.com/T-B-F/pyHCA/
      - Others: https://bio.tools/pyhca 
</details>



### Sweden
#### Linköping University     
<details>
<summary>Björn Wallner</summary>

- Lab website: [Profile](https://liu.se/en/employee/bjowa51 | https://www.scilifelab.se/researchers/bjorn-wallner/)

- Tools
  - rawMSA
    - Paper: [rawMSA: End-to-end Deep Learning using raw Multiple Sequence Alignments](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0220182) (PLoS One, 2019)
    - Abstract: In the last decades, huge efforts have been made in the bioinformatics community to develop machine learning-based methods for the prediction of structural features of proteins in the hope of answering fundamental questions about the way proteins function and their involvement in several illnesses. The recent advent of Deep Learning has renewed the interest in neural networks, with dozens of methods being developed taking advantage of these new architectures. However, most methods are still heavily based pre-processing of the input data, as well as extraction and integration of multiple hand-picked, and manually designed features. Multiple Sequence Alignments (MSA) are the most common source of information in de novo prediction methods. Deep Networks that automatically refine the MSA and extract useful features from it would be immensely powerful. In this work, we propose a new paradigm for the prediction of protein structural features called rawMSA. The core idea behind rawMSA is borrowed from the field of natural language processing to map amino acid sequences into an adaptively learned continuous space. This allows the whole MSA to be input into a Deep Network, thus rendering pre-calculated features such as sequence profiles and other features calculated from MSA obsolete. We showcased the rawMSA methodology on three different prediction problems: secondary structure, relative solvent accessibility and inter-residue contact maps. We have rigorously trained and benchmarked rawMSA on a large set of proteins and have determined that it outperforms classical methods based on position-specific scoring matrices (PSSM) when predicting secondary structure and solvent accessibility, while performing on par with methods using more pre-calculated features in the inter-residue contact map prediction category in CASP12 and CASP13. Clearly demonstrating that rawMSA represents a promising development that can pave the way for improved methods using rawMSA instead of sequence profiles to represent evolutionary information in the coming years.

      datasets, dataset generation code, evaluation code and models are available at: https://bitbucket.org/clami66/rawmsa.
    - Description/Method: rawMSA_disorder is part of a suite of methods for the prediction of structural features of proteins. Here, the input is not a set of pre-determined features, such as evolutionary profiles or predicted secondary structure, as in classical ML-based methods for structure prediction. Instead, the whole MSA is used as a textual input to the neural network so that the evolutionary information is not compressed in any way and the feature extraction can be automatically performed by the deep network. The mapping between amino acid letters to floating point vectors is done in the first layer of the deep network with an embedding layer. The input is not split into windows, and all predictions are done at the same time for all input amino acids so that long disordered / ordered regions are not split up at prediction stage. The final prediction is result of ensembling a number of pretrained models by averaging their outputs.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository: https://github.com/yhgon/rawMSA
      - Others: https://bitbucket.org/clami66/rawmsa | https://bio.tools/rawmsa
  - rawMSA-disorder
    - Paper: [文献标题](url) (期刊名, 年份)
    - Abstract: 文献摘要
    - Description/Method: It is a neural network based on previous work (rawMSA), trained to predict disorder from multiple sequence alignments. The alignments are now generated with MMseqs2, which is much faster than HHblits. The network is trained on DisProt and the PDB.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others  
</details>








## Asia 
### China
#### Beijing Institute of Technology 北京理工大学     
<details>
<summary>Bin Liu 刘滨</summary>

- Lab website: [Profile](https://cs.bit.edu.cn/szdw/jsml/bssds/d2d14d4b951947658e978f683975861b.htm)

- Tools
  - DeepIDP-2L
    - Paper: [DeepIDP-2L: protein intrinsically disordered region prediction by combining convolutional attention network and hierarchical attention network](https://academic.oup.com/bioinformatics/article/38/5/1252/6448216?login=false) (Bioinformatics, 2021)
    - Abstract: Intrinsically disordered regions (IDRs) are widely distributed in proteins. Accurate prediction of IDRs is critical for the protein structure and function analysis. The IDRs are divided into long disordered regions (LDRs) and short disordered regions (SDRs) according to their lengths. Previous studies have shown that LDRs and SDRs have different proprieties. However, the existing computational methods fail to extract different features for LDRs and SDRs separately. As a result, they achieve unstable performance on datasets with different ratios of LDRs and SDRs.

      For the convenience of most experimental scientists, a user-friendly and publicly accessible web-server for the new predictor has been established at http://bliulab.net/DeepIDP-2L/. It is anticipated that DeepIDP-2L will become a very useful tool for identification of intrinsically disordered regions.
    - Description: In this study, a two-layer predictor was proposed called DeepIDP-2L. In the first layer, two kinds of attention-based models are used to extract different features for LDRs and SDRs, respectively. The hierarchical attention network is used to capture the distribution pattern features of LDRs, and convolutional attention network is used to capture the local correlation features of SDRs. The second layer of DeepIDP-2L maps the feature extracted in the first layer into a new feature space. Convolutional network and bidirectional long short term memory are used to capture the local and long-range information for predicting both SDRs and LDRs. Experimental results show that DeepIDP-2L can achieve more stable performance than other exiting predictors on independent test sets with different ratios of SDRs and LDRs.
  
      DeepIDP-2L is a two-layer predictor. In the first layer, two kinds of attention-based models are used to extract different features for LDRs and SDRs, respectively. The hierarchical attention network (HAN) is used to capture the distribution pattern features of LDRs, and convolutional attention network (CAN) is used to capture the local correlation features of SDRs. The second layer of DeepIDP-2L maps the feature extracted in the first layer into a new feature space. Convolutional network (CNN) and bidirectional long short term memory (Bi-LSTM) are employed to capture the local and long-range information for predicting both SDRs and LDRs.
    - Access:
      - Web server: http://bliulab.net/DeepIDP-2L/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository
      - Others: https://bio.tools/deepidp-2l
  - DisoFLAG: DisoFLAG-DFL, DisoFLAG-IDR
    - Paper: [DisoFLAG: accurate prediction of protein intrinsic disorder and its functions using graph-based interaction protein language model](https://bmcbiol.biomedcentral.com/articles/10.1186/s12915-023-01803-y) (BMC Biology, 2024)
    - Abstract: Intrinsically disordered proteins and regions (IDPs/IDRs) are functionally important proteins and regions that exist as highly dynamic conformations under natural physiological conditions. IDPs/IDRs exhibit a broad range of molecular functions, and their functions involve binding interactions with partners and remaining native structural flexibility. The rapid increase in the number of proteins in sequence databases and the diversity of disordered functions challenge existing computational methods for predicting protein intrinsic disorder and disordered functions. A disordered region interacts with different partners to perform multiple functions, and these disordered functions exhibit different dependencies and correlations. In this study, we introduce DisoFLAG, a computational method that leverages a graph-based interaction protein language model (GiPLM) for jointly predicting disorder and its multiple potential functions. GiPLM integrates protein semantic information based on pre-trained protein language models into graph-based interaction units to enhance the correlation of the semantic representation of multiple disordered functions. The DisoFLAG predictor takes amino acid sequences as the only inputs and provides predictions of intrinsic disorder and six disordered functions for proteins, including protein-binding, DNA-binding, RNA-binding, ion-binding, lipid-binding, and flexible linker. We evaluated the predictive performance of DisoFLAG following the Critical Assessment of protein Intrinsic Disorder (CAID) experiments, and the results demonstrated that DisoFLAG offers accurate and comprehensive predictions of disordered functions, extending the current coverage of computationally predicted disordered function categories. The standalone package and web server of DisoFLAG have been established to provide accurate prediction tools for intrinsic disorders and their associated functions.
    - Description/Method: N/A
    - Access:
      - Web server: http://bliulab.net/DisoFLAG/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/YihePang/DisoFLAG
      - Others: N/A
  - IDP-Fusion
    - Paper: [Protein intrinsically disordered region prediction by combining neural architecture search and multi-objective genetic algorithm](https://bmcbiol.biomedcentral.com/articles/10.1186/s12915-023-01672-5) (BMC Biology, 2023)
    - Abstract: Intrinsically disordered regions (IDRs) are widely distributed in proteins and related to many important biological functions. Accurately identifying IDRs is of great significance for protein structure and function analysis. Because the long disordered regions (LDRs) and short disordered regions (SDRs) share different characteristics, the existing predictors fail to achieve better and more stable performance on datasets with different ratios between LDRs and SDRs. There are two main reasons. First, the existing predictors construct network structures based on their own experiences such as convolutional neural network (CNN) which is used to extract the feature of neighboring residues in protein, and long short-term memory (LSTM) is used to extract the long-distance dependencies feature of protein residues. But these networks cannot capture the hidden feature associated with the length-dependent between residues. Second, many algorithms based on deep learning have been proposed but the complementarity of the existing predictors is not fully explored and used.

      In this study, the neural architecture search (NAS) algorithm was employed to automatically construct the network structures so as to capture the hidden features in protein sequences. In order to stably predict both the LDRs and SDRs, the model constructed by NAS was combined with length-dependent models for capturing the unique features of SDRs or LDRs and general models for capturing the common features between LDRs and SDRs. A new predictor called IDP-Fusion was proposed.

      Experimental results showed that IDP-Fusion can achieve more stable performance than the other existing predictors on independent test sets with different ratios between SDRs and LDRs.
    - Description/Method: IDP-Fusion combines six base predictors. The features between these predictors are complementary. Furthermore, the base method using neural architecture search method DARTS can capture the hidden features failed to be captured by the other models. During the training process, IDP-Fusion considers the influence of different ratios between SDR proteins and LDR proteins by using the multi-objective genetic ensemble algorithm and therefore, IDP-Fusion achieves stable performance on different independent test datasets.
    - Access:
      - Web server: http://bliulab.net/IDP-Fusion/home/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: [Zenodo](https://zenodo.org/records/8190096)
</details>  

#### Central South University 中南大学     
<details>
<summary>Min Li</summary>

- Lab website: [Profile](https://faculty.csu.edu.cn/limin1/en/index.htm)

- Tools
  - DisoPred
    - Note: ⚠️ No peer‑reviewed publication yet. 
  
      Latest results: [CAID Competition/Leaderboard](https://caid.idpcentral.org/methods). 
      
      Status: experimental. 
    - Paper: N/A
    - Abstract: N/A
    - Description/Method: DisoPred combines two predictors: the predictor of IDRs and the predictor of IDPs. DisoPred apples the 5-fold cross validation to train two predictors with same input profiles and deep learning model consisting of the muti-CNN block and the transformer layer. Considering the length of IDRs and IDPs, the input window sizes of two predictors are different. The average of predictions from the two predictors is used as the final prediction. Cross-validation and fusion results help improve accuracy of performance and robustness.
    - Access:
      - Web server: https://caid.idpcentral.org/portal (⚠️ integrated into the CAID Prediction Portal)
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository
      - Others 
</details>


#### Sun Yat-sen University 中山大学
<details>
<summary>Yuedong Yang 杨跃东</summary>

- Lab website: [Supercomputing+AI for Life science, SAIL Lab](http://biomed.nscc-gz.cn/sail/home) | [Profile](https://cse.sysu.edu.cn/teacher/YangYuedong)

- Tools
  - LMDisorder 
    - Paper: [Fast and accurate protein intrinsic disorder prediction by using a pretrained language model](https://academic.oup.com/bib/article/24/4/bbad173/7171415) (Briefings in Bioinformatics, 2023)
    - Abstract: Determining intrinsically disordered regions of proteins is essential for elucidating protein biological functions and the mechanisms of their associated diseases. As the gap between the number of experimentally determined protein structures and the number of protein sequences continues to grow exponentially, there is a need for developing an accurate and computationally efficient disorder predictor. However, current single-sequence-based methods are of low accuracy, while evolutionary profile-based methods are computationally intensive. Here, we proposed a fast and accurate protein disorder predictor LMDisorder that employed embedding generated by unsupervised pretrained language models as features. We showed that LMDisorder performs best in all single-sequence-based methods and is comparable or better than another language-model-based technique in four independent test sets, respectively. Furthermore, LMDisorder showed equivalent or even better performance than the state-of-the-art profile-based technique SPOT-Disorder2. In addition, the high computation efficiency of LMDisorder enabled proteome-scale analysis of human, showing that proteins with high predicted disorder content were associated with specific biological functions. The datasets, the source codes, and the trained model are available at https://github.com/biomed-AI/LMDisorder.
    - Description/Method: LMDisorder is a fast and accurate protein disorder predictor that employed embedding generated by unsupervised pretrained language models as features.We showed that LMDisorder essentially surpassed the single-sequence-based methods by more than 6.0% and 18.0% on AUROC in two independent test sets, respectively. Furthermore, LMDisor-der showed equivalent or even better performance than the state-of-the-art profile-based technique SPOT-Disorder2.
    - Access:
      - Web server: N/A
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/biomed-AI/LMDisorder
      - Others 
</details>


### Japan
#### Maebashi Institute of Technology     
<details>
<summary>Satoshi Fukuchi</summary>

- Lab website: [Profile](https://www.researchgate.net/profile/Satoshi-Fukuchi?ev=brs_overview)    

- Tools
  - DARUMA
    - Note: ⚠️ No peer‑reviewed publication yet. Latest results: see Paper below 
    - Paper: [DARUMA: Your gateway to fast and easy prediction of intrinsically disordered regions](https://www.researchsquare.com/article/rs-5414158/v1) (Research Square preprint, 2024)
    - Abstract: Intrinsically disordered proteins (IDPs) are proteins that contain intrinsically disordered regions (IDRs), which lack stable three-dimensional structures under physiological conditions. These regions are known to play crucial roles in many biological processes. While IDRs can be predicted from their amino acid sequences, and several accurate IDR prediction programs have been developed, such programs often require substantial computational resources, including long execution time, large databases for homology searches, and advanced computer architectures. Since DNA sequence data continues to grow rapidly, particularly at a genomic scale, there is an increasing need for fast and accurate IDR prediction programs that demand fewer computational resources.
  
      DARUMA is a fast, accurate, and user-friendly IDR prediction tool available as both a web interface and a stand-alone distribution at https://antepontem.org/daruma/. Its unique features make it accessible to a wide range of users and a valuable tool for IDR research.
    - Description/Method: In this study, we developed DARUMA (Disorder order clAssifier by Rapid and User-friendly MAchine), an IDR prediction program designed for speed and ease of use. DARUMA achieves fast performance by avoiding iterative homology searches while delivering accuracy comparable to the latest predictors that use sequence profiles. In addition to the advantage of execution time, DARUMA requires no additional homology search programs and operates using standard Python libraries, making it easy to install and run on users’ own environments without the need for specialized computational resources.
    
      DARUMA enables rapid prediction by using a simple convolutional neural network that uses physicochemical properties of amino acids as features.

    - Access:
      - Web server: https://antepontem.org/daruma/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: https://github.com/antepontem/DARUMA-Additional-Data | https://github.com/antepontem/DARUMA | https://github.com/shimizuitsuki0316/DARUMA | https://github.com/shimizuitsuki0316/DARUMA-Additional-Data_test
      - Others: https://pypi.org/project/daruma/
  - NeProc: NeProc-disorder
    - Paper: [NeProc predicts binding segments in intrinsically disordered regions without learning binding region sequences](https://www.jstage.jst.go.jp/article/biophysico/17/0/17_BSJ-2020026/_article/-char/en) (Biophysics and Physicobiology, 2020)
    - Abstract: Intrinsically disordered proteins are those proteins with intrinsically disordered regions. One of the unique characteristics of intrinsically disordered proteins is the existence of functional segments in intrinsically dis­ordered regions. These segments are involved in binding to partner molecules, such as protein and DNA, and play important roles in signaling pathways and/or transcriptional regulation. Although there are databases that gather information on such disordered binding regions, data remain limited. Therefore, it is desirable to develop programs to predict the disordered binding regions without using data for the binding regions. We developed a program, NeProc, to predict the disordered binding regions, which can be regarded as intrinsically disordered regions with a structural propensity. We only used data for the structural domains and intrinsically disordered regions to detect such regions. NeProc accepts a query amino acid sequence converted into a position specific score matrix, and uses two neural networks that employ different window sizes, a neural network of short windows, and a neural network of long windows. The performance of NeProc was comparable to that of existing programs of the disordered binding region prediction. This result presents the possibility to overcome the shortage of the disordered binding region data in the development of the prediction programs for these binding regions. NeProc is available at http://flab.neproc.org/neproc/index.html.
    - Description/Method: NeProc (Next ProS classifier) predicts intrinsically disordered regions and their functional segments that can undergo a disorder-to-order transition upon binding with partner proteins.
    - Access:
      - Web server: https://antepontem.org/neproc/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository
      - Others
  - NeProc2: NeProc2-beta-disorder
    - Note: ⚠️ No peer‑reviewed publication yet. 
     
      Latest results: [CAID Competition/Leaderboard](https://caid.idpcentral.org/methods). 
      
      Status: experimental.
    - Paper: [文献标题](url) (期刊名, 年份)
    - Abstract: 文献摘要
    - Description/Method: NeProc2 employs transfer learning, that learns the six outcomes of the neural networks in the original NeProc along with its final output.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others
</details>


### Russia 
#### Institute of Protein Research, RAS     
<details>
<summary>Oxana Valerianovna Galzitskaya</summary>

- Lab website: [Profile](https://www.researchgate.net/profile/Oxana-Galzitskaya/research?_tp=eyJjb250ZXh0Ijp7InBhZ2UiOiJwcm9maWxlIiwicHJldmlvdXNQYWdlIjpudWxsfX0)

- Tools
  - FoldUnfold
    - Paper: [FoldUnfold: web server for the prediction of disordered regions in protein chain](https://academic.oup.com/bioinformatics/article/22/23/2948/279361?login=false) (Bioinformatics, 2006)
    - Abstract: Identification of disordered regions in polypeptide chains is very important because such regions are essential for protein function. A new parameter, namely mean packing density of residues has been introduced to detect disordered regions in a protein sequence. We have demonstrated that regions with weak expected packing density would be responsible for the appearance of disordered regions. Our method (FoldUnfold) has been tested on datasets of globular proteins (559 proteins) and long disordered protein segments (129 proteins) and showed improved performance over some other widely used methods, such as DISOPRED, PONDR VL3H, IUPred and GlobPlot.

      The FoldUnfold server is available for users at [Author Webpage](http://skuld.protres.ru/~mlobanov/ogu/ogu.cgi). There is a link to our server through the web site of DisProt ([Author Webpage](https://www.disprot.org/predictors.php)).
    - Description/Method: The method is based on the statistics of the average number of contacts for each type of amino acid residues. It takes into account the fact that, on average, amino acids with few contacts are more often unfolded. For prediction, the program uses the sliding window method. The optimal window size is 11 residues.
    - Access:
      - Web server: https://www.disprot.org/predictors.php | http://bioinfo.protres.ru/ogu/
      - REST API: N/A
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: https://bio.tools/foldunfold 
  - IsUnstruct
    - Paper: [The Ising model for prediction of disordered residues from protein sequence alone](https://iopscience.iop.org/article/10.1088/1478-3975/8/3/035004) (Physical Biology, 2011)
    - Abstract: Intrinsically disordered regions serve as molecular recognition elements, which play an
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
    - Description/Method: The method is based on the Ising model. Each residue of the protein chain can be either structured or unstructured state. Each of the amino acids type has the potential to transition from one state to another. The energy of the boundary between the folded and unfolded states, and the energy of initiation of the unfolded state at the N- and C-terminals of the protein chain are also taken into account. Parameters optimized on PDB 2012. In addition, the method takes into account 171 disordered patterns, these are sequences that we always predict unfolded.
    - Access:
      - Web server: http://bioinfo.protres.ru/IsUnstruct/
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: https://bio.tools/isunstruct
</details>


### North Korea
#### University of Sciences, Pyongyang     
<details>
<summary>Kun-Sop Han</summary>

- Lab website: [Profile](https://www.scopus.com/authid/detail.uri?authorId=57210213218)

- Tools
  - PredIDR: PredIDR-long, PredIDR-short 
    - Paper: [PredIDR: Accurate prediction of protein intrinsic disorder regions using deep convolutional neural network](https://www.sciencedirect.com/science/article/abs/pii/S0141813024084757?via%3Dihub) (International Journal of Biological Macromolecules, 2024)
    - Abstract: The involvement of protein intrinsic disorder in essential biological processes, it is well known in structural biology. However, experimental methods for detecting intrinsic structural disorder and directly measuring highly dynamic behavior of protein structure are limited. To address this issue, several computational methods to predict intrinsic disorder from protein sequences were developed and their performance is evaluated by the Critical Assessment of protein Intrinsic Disorder (CAID). In this paper, we describe a new computational method, PredIDR, which provides accurate prediction of intrinsically disordered regions in proteins, mimicking experimental X-ray missing residues. Indeed, missing residues in Protein Data Bank (PDB) were used as positive examples to train a deep convolutional neural network which produces two types of output for short and long regions. PredIDR took part in the second round of CAID and was as accurate as the top state-of-the-art IDR prediction methods. PredIDR can be freely used through the CAID Prediction Portal available at https://caid.idpcentral.org/portal or downloaded as a Singularity container from https://biocomputingup.it/shared/caid-predictors/.
    - Description/Method: PredIDR is a program which employs deep convolutional neural network to predict IDR. IDR chains are extracted from PDB non-homologous set by comparing primary sequences and 3D coordinates. The 8,850 IDRs of training set are divided into 3 groups according to the position of IDR in the sequence: IDR_C, IDR_M and IDR_N group. The 8,850 artificial STRs corresponding to 8,850 IDRs are also made. The input features of deep convolutional neural network are profile, secondary structure and solvent accessibility predicted from 229,752 sliding windows (L1=15 residues) from 8,850 IDRs and 8,850 artificial STRs. The predictions from the ensemble of 10 top-performing models are averaged within the second window (L2=9 or 19). The final prediction with L2=9 is PredIDR_S which is used to predict short and long IDRs (L > 4) whereas the one with L2=19 is PredIDR_L which is used to predict long IDRs (L > 10).
    - Access:
      - Web server: https://caid.idpcentral.org/portal
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others: https://protein.bio.unipd.it/shared/caid-predictors/ 
  - PredIDR2-Prof: PredIDR2-Prof-Art, PredIDR2-Prof-Rnd
    - Paper: [PredIDR2: Improving accuracy of protein intrinsic disorder prediction by updating deep convolutional neural network and supplementing DisProt data](https://www.sciencedirect.com/science/article/pii/S0141813025023529) (International Journal of Biological Macromolecules, 2025)
    - Abstract: Intrinsically disordered proteins (IDPs) or regions (IDRs) are widespread in proteomes, and involved in several important biological processes and implicated in many diseases. Many computational methods for IDR prediction are being developed to decrease the gap between the low speed of experimental determination of annotated proteins and the rapid increase of non-annotated proteins, and their performances are blindly tested by the community-driven experiment, the Critical Assessment of protein Intrinsic Disorder (CAID). In this paper, we developed PredIDR2 series, an updated version of PredIDR tested in CAID2 in order to accurately predict intrinsically disordered regions from protein sequence. It includes four methods depending on the input features and the producing mode of the negative samples of the training set. PredIDR2 series (AUC_ROC = 0.952) perform remarkably better than our previous PredIDR (AUC_ROC = 0.933) for Disorder-PDB dataset of CAID2, which seems to be mainly attributed to the introduction of a new deep convolutional neural network and the augmentation of the training data, especially from DisProt database. PredIDR2 series outperform the state-of-the-art IDR prediction methods participated in CAID2 in terms of AUC_ROC, AUC_PR and DC_mae and belong to the seven top-performing methods in terms of MCC. PredIDR2 series can be freely used through the CAID Prediction Portal available at https://caid.idpcentral.org/portal or downloaded as a Singularity container from https://biocomputingup.it/shared/caid-predictors/.
    - Description/Method: PredIDR2-Prof is a program for predicting IDRs in protein sequences based on convolutional neural network. The PredIDR2-Prof is the updated version of PredIDR1.0 developed in 2022 and tested in CAID2.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others 
  - PredIDR2-Seq: PredIDR2-Seq-Art, PredIDR2-Seq-Rnd
    - Paper: [PredIDR2: Improving accuracy of protein intrinsic disorder prediction by updating deep convolutional neural network and supplementing DisProt data](https://www.sciencedirect.com/science/article/pii/S0141813025023529) (International Journal of Biological Macromolecules, 2025)
    - Abstract: Intrinsically disordered proteins (IDPs) or regions (IDRs) are widespread in proteomes, and involved in several important biological processes and implicated in many diseases. Many computational methods for IDR prediction are being developed to decrease the gap between the low speed of experimental determination of annotated proteins and the rapid increase of non-annotated proteins, and their performances are blindly tested by the community-driven experiment, the Critical Assessment of protein Intrinsic Disorder (CAID). In this paper, we developed PredIDR2 series, an updated version of PredIDR tested in CAID2 in order to accurately predict intrinsically disordered regions from protein sequence. It includes four methods depending on the input features and the producing mode of the negative samples of the training set. PredIDR2 series (AUC_ROC = 0.952) perform remarkably better than our previous PredIDR (AUC_ROC = 0.933) for Disorder-PDB dataset of CAID2, which seems to be mainly attributed to the introduction of a new deep convolutional neural network and the augmentation of the training data, especially from DisProt database. PredIDR2 series outperform the state-of-the-art IDR prediction methods participated in CAID2 in terms of AUC_ROC, AUC_PR and DC_mae and belong to the seven top-performing methods in terms of MCC. PredIDR2 series can be freely used through the CAID Prediction Portal available at https://caid.idpcentral.org/portal or downloaded as a Singularity container from https://biocomputingup.it/shared/caid-predictors/.
    - Description/Method: PredIDR2-Seq is a program for predicting IDRs in protein sequences based on convolutional neural network. The PredIDR2-Seq is faster than the PredIDR2-Prof. The sequences of PDB, DisProt release_2023_06 and CAID2 dataset are used for making a training, validation and testing data. The PredIDR2-Seq uses secondary structure, solvent accesibility and protein sequence as inputs of the neural network. The program produces outputs of two methods: PredIDR2-Seq_Art and PredIDR2-Seq_Rnd, which are different in ways of making the training data. The convolutional neural network consists of four 2D convolutional layers, four batch normalization layers and two dense layers. A sliding window of size 31 and 32-dimensional features are used, resulting in an input tensor of size (31,1,32) for convolutional neural network. In each of two methods, about 10 top-performing networks are chosen to make an ensemble and smoothing with window size 19 on the ensemble results in the final output.
    - Access:
      - Web server: N/A
      - REST API: N/A[API docs]
      - Docker image: N/A
      - GitHub repository
      - Others 
</details>



## Region
### National
#### University     
<details>
<summary>PI name</summary>

- Lab website: [PI lab](url link) | [PI profile](url link)

- Tools
  - toolname
    - Note: ⚠️ No peer‑reviewed publication yet? Latest results: Compile essential first-hand sources (official docs, tutorials, and direct links) for this tool—only verified, publisher-provided resources.
    - Paper: [paper title](url) (Journal name, Publish year)
    - Abstract: A summary of the original literature from which the tool came (mainly about what the tool does)
    - Description/Method: Summary of computational aspects, such as model architecture design involved in the tool, or algorithmic innovation
    - Access:
      - Web server: N/A
      - REST API: N/A | [API docs](Link to the api docs/help page)
      - Docker image: N/A
      - GitHub repository: N/A
      - Others: Any package or bio-tools link url | N/A
</details>