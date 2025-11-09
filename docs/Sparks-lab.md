# Yaoqi Zhou/Sparks LAB

[← Back to list](../README.md#institute-for-systems-and-physical-biology-shenzhen-bay-laboratory)

## SPOT-Disorder

### SPOT-Disorder Abstract
Capturing long-range interactions between structural but not sequence neighbors of proteins is a long-standing challenging problem in bioinformatics. Recently, long short-term memory (LSTM) networks have significantly improved the accuracy of speech and image classification problems by remembering useful past information in long sequential events. Here, we have implemented deep bidirectional LSTM recurrent neural networks in the problem of protein intrinsic disorder prediction.

The new method, named SPOT-Disorder, has steadily improved over a similar method using a traditional, window-based neural network (SPINE-D) in all datasets tested without separate training on short and long disordered regions. Independent tests on four other datasets including the datasets from critical assessment of structure prediction (CASP) techniques and >10 000 annotated proteins from MobiDB, confirmed SPOT-Disorder as one of the best methods in disorder prediction. Moreover, initial studies indicate that the method is more accurate in predicting functional sites in disordered regions. These results highlight the usefulness combining LSTM with deep bidirectional recurrent neural networks in capturing non-local, long-range interactions for bioinformatics applications.

SPOT-disorder is available as a web server and as a standalone program at: http://sparks-lab.org/server/SPOT-disorder/index.php.

### SPOT-Disorder Model/Method
SPOT-Disorder is a previous version of SPOT-Disorder2 that was trained on DM4229 from SPINE-D, but with simpler neural networks of LSTM and fully-connected layers only. Input features were PSSM from PSI-BLAST, predicted structural properties from SPIDER2 and physicochemical properties for each amino acid at its position in the polypeptide chain.

## SPOT-Disorder-Single

### SPOT-Disorder-Single Abstract
Recognizing the widespread existence of intrinsically disordered regions in proteins spurred the development of computational techniques for their detection. All existing techniques can be classified into methods relying on single-sequence information and those relying on evolutionary sequence profiles generated from multiple-sequence alignments. The methods based on sequence profiles are, in general, more accurate because the presence or absence of conserved amino acid residues in a protein sequence provides important information on the structural and functional roles of the residues. However, the wide applicability of profile-based techniques is limited by time-consuming calculation of sequence profiles. Here we demonstrate that the performance gap between profile-based techniques and single-sequence methods can be reduced by using an ensemble of deep recurrent and convolutional neural networks that allow whole-sequence learning. In particular, the single-sequence method (called SPOT-Disorder-Single) is more accurate than SPOT-Disorder (a profile-based method) for proteins with few homologous sequences and comparable for proteins in predicting long-disordered regions. The method performance is robust across four independent test sets with different amounts of short- and long-disordered regions. SPOT-Disorder-Single is available as a Web server and as a standalone program at http://sparks-lab.org/jack/server/SPOT-Disorder-Single.

# ### SPOT-Disorder-Single Model/Method
SPOT-Disorder-Single are made of eight independent trained models consisting of ResNets and/or LSTM BRNNs with input feature of one-hot encoding only. The dataset trained for SPOT-Disorder was employed for training SPOT-Disorder-Single.

## SPOT-Disorder2

### SPOT-Disorder2 Abstract
Intrinsically disordered or unstructured proteins (or regions in proteins) have been found to be important in a wide range of biological functions and implicated in many diseases. Due to the high cost and low efficiency of experimental determination of intrinsic disorder and the exponential increase of unannotated protein sequences, developing complementary computational prediction methods has been an active area of research for several decades. Here, we employed an ensemble of deep Squeeze-and-Excitation residual inception and long short-term memory (LSTM) networks for predicting protein intrinsic disorder with input from evolutionary information and predicted one-dimensional structural properties. The method, called SPOT-Disorder2, offers substantial and consistent improvement not only over our previous technique based on LSTM networks alone, but also over other state-of-the-art techniques in three independent tests with different ratios of disordered to ordered amino acid residues, and for sequences with either rich or limited evolutionary information. More importantly, semi-disordered regions predicted in SPOT-Disorder2 are more accurate in identifying molecular recognition features (MoRFs) than methods directly designed for MoRFs prediction. SPOT-Disorder2 is available as a web server and as a standalone program at https://sparks-lab.org/server/spot-disorder2/.

### SPOT-Disorder2 Model/Method
SPOT-Disorder2 is a method for predicting intrinsically disordered residues in a protein sequence. The method is made of five neural network models trained separately by different combinations of IncReSeNet, LSTM, and fully-connected layers. The output from these five models was averaged to produce the final prediction. These models were trained, validated, and tested on 2615, 293, and 1185 proteins that include high-resolution X-ray structures and some fully disordered proteins from DisProt v5.0. It was further tested on three additional independent test datasets (SL250, Mobi9414, and DisProt228) for a fair comparison against other methods. The input features for the method are the position-specific substitution matrix (PSSM) profile from PSI-BLAST, the hidden Markov model (HMM) profile from HHblits , predicted structural properties from SPOT-1D.





