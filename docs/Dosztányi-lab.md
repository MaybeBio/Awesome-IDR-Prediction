# Zsuzsanna Dosztányi Lab

[← Back to list](../README.md#eötvös-loránd-university)

## AIUPred

### AIUPred Abstract
Intrinsically disordered proteins and protein regions (IDPs/IDRs) carry out important biological functions without relying on a single well-defined conformation. As these proteins are a challenge to study experimentally, computational methods play important roles in their characterization. One of the commonly used tools is the IUPred web server which provides prediction of disordered regions and their binding sites. IUPred is rooted in a simple biophysical model and uses a limited number of parameters largely derived on globular protein structures only. This enabled an incredibly fast and robust prediction method, however, its limitations have also become apparent in light of recent breakthrough methods using deep learning techniques. Here, we present AIUPred, a novel version of IUPred which incorporates deep learning techniques into the energy estimation framework. It achieves improved performance while keeping the robustness of the original method. Based on the evaluation of recent benchmark datasets, AIUPred scored amongst the top three single sequence based methods. With a new web server we offer fast and reliable visual analysis for users as well as options to analyze whole genomes in mere seconds with the downloadable package. AIUPred is available at https://aiupred.elte.hu.

### AIUPred Model/Method
AIUPred uses a statistical potential based energy prediction to assess whether an amino acid can form favorable interactions with its sequential environment. The energy prediction is achieved by a series of convolutional neural networks with residual connections. The input sequences are embedded using a 21 dimension Word2Vec embedding. The output energies are then fed to a logistic regression module to obtain disorder propensity scores.

## IUPred3

### IUPred3 Abstract
Intrinsically disordered proteins and protein regions (IDPs/IDRs) exist without a single well-defined conformation. They carry out important biological functions with multifaceted roles which is also reflected in their evolutionary behavior. Computational methods play important roles in the characterization of IDRs. One of the commonly used disorder prediction methods is IUPred, which relies on an energy estimation approach. The IUPred web server takes an amino acid sequence or a Uniprot ID/accession as an input and predicts the tendency for each amino acid to be in a disordered region with an option to also predict context-dependent disordered regions. In this new iteration of IUPred, we added multiple novel features to enhance the prediction capabilities of the server. First, learning from the latest evaluation of disorder prediction methods we introduced multiple new smoothing functions to the prediction that decreases noise and increases the performance of the predictions. We constructed a dataset consisting of experimentally verified ordered/disordered regions with unambiguous annotations which were added to the prediction. We also introduced a novel tool that enables the exploration of the evolutionary conservation of protein disorder coupled to sequence conservation in model organisms. The web server is freely available to users and accessible at https://iupred3.elte.hu.

### IUPred3 Model/Method
IUPred3 predicts protein disorder based on an energy estimation approach utilizing statistical potentials. The parameters of the method are derived from a collection of known structures only and disordered regions are recognized based on their unfavorable estimated energies. IUPred3 is a fast and robust method that carries out predictions for single protein sequences without using evolutionary information.

## AIUPred-2

### AIUPred-2 Abstract
N/A

### AIUPred-2 Model/Method
AIUPred-2 utilizes a novel energy embedding technique that was trained on energy like quantities derived globular structures. The embedding was than used for transfer learning to achieve fast and accurate single sequence prediction.