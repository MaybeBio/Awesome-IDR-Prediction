# Satoshi Fukuchi LAB

[← Back to list](../README.md#maebashi-institute-of-technology)

## DARUMA

### DARUMA Abstract
Intrinsically disordered proteins (IDPs) are proteins that contain intrinsically disordered regions (IDRs), which lack stable three-dimensional structures under physiological conditions. These regions are known to play crucial roles in many biological processes. While IDRs can be predicted from their amino acid sequences, and several accurate IDR prediction programs have been developed, such programs often require substantial computational resources, including long execution time, large databases for homology searches, and advanced computer architectures. Since DNA sequence data continues to grow rapidly, particularly at a genomic scale, there is an increasing need for fast and accurate IDR prediction programs that demand fewer computational resources.
  
DARUMA is a fast, accurate, and user-friendly IDR prediction tool available as both a web interface and a stand-alone distribution at https://antepontem.org/daruma/. Its unique features make it accessible to a wide range of users and a valuable tool for IDR research.

### DARUMA Model/Method
In this study, we developed DARUMA (Disorder order clAssifier by Rapid and User-friendly MAchine), an IDR prediction program designed for speed and ease of use. DARUMA achieves fast performance by avoiding iterative homology searches while delivering accuracy comparable to the latest predictors that use sequence profiles. In addition to the advantage of execution time, DARUMA requires no additional homology search programs and operates using standard Python libraries, making it easy to install and run on users’ own environments without the need for specialized computational resources.
    
DARUMA enables rapid prediction by using a simple convolutional neural network that uses physicochemical properties of amino acids as features.


## NeProc 

### NeProc Abstract
Intrinsically disordered proteins are those proteins with intrinsically disordered regions. One of the unique characteristics of intrinsically disordered proteins is the existence of functional segments in intrinsically dis­ordered regions. These segments are involved in binding to partner molecules, such as protein and DNA, and play important roles in signaling pathways and/or transcriptional regulation. Although there are databases that gather information on such disordered binding regions, data remain limited. Therefore, it is desirable to develop programs to predict the disordered binding regions without using data for the binding regions. We developed a program, NeProc, to predict the disordered binding regions, which can be regarded as intrinsically disordered regions with a structural propensity. We only used data for the structural domains and intrinsically disordered regions to detect such regions. NeProc accepts a query amino acid sequence converted into a position specific score matrix, and uses two neural networks that employ different window sizes, a neural network of short windows, and a neural network of long windows. The performance of NeProc was comparable to that of existing programs of the disordered binding region prediction. This result presents the possibility to overcome the shortage of the disordered binding region data in the development of the prediction programs for these binding regions. NeProc is available at http://flab.neproc.org/neproc/index.html.

### NeProc Model/Method
NeProc (Next ProS classifier) predicts intrinsically disordered regions and their functional segments that can undergo a disorder-to-order transition upon binding with partner proteins.

## NeProc2

### NeProc2 Abstract
N/A

### NeProc2 Model/Method
NeProc2 employs transfer learning, that learns the six outcomes of the neural networks in the original NeProc along with its final output.