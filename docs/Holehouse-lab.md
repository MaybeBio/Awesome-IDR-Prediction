# Alex S. Holehouse Lab

[← Back to list](../README.md#washington-university-in-st-louis)

## Metapredict

### Metapredict Abstract
Intrinsically disordered proteins and protein regions make up a substantial fraction of many proteomes in which they play a wide variety of essential roles. A critical first step in understanding the role of disordered protein regions in biological function is to identify those disordered regions correctly. Computational methods for disorder prediction have emerged as a core set of tools to guide experiments, interpret results, and develop hypotheses. Given the multiple different predictors available, consensus scores have emerged as a popular approach to mitigate biases or limitations of any single method. Consensus scores integrate the outcome of multiple independent disorder predictors and provide a per-residue value that reflects the number of tools that predict a residue to be disordered. Although consensus scores help mitigate the inherent problems of using any single disorder predictor, they are computationally expensive to generate. They also necessitate the installation of multiple different software tools, which can be prohibitively difficult. To address this challenge, we developed a deep-learning-based predictor of consensus disorder scores. Our predictor, metapredict, utilizes a bidirectional recurrent neural network trained on the consensus disorder scores from 12 proteomes. By benchmarking metapredict using two orthogonal approaches, we found that metapredict is among the most accurate disorder predictors currently available. Metapredict is also remarkably fast, enabling proteome-scale disorder prediction in minutes. Importantly, metapredict is a fully open source and is distributed as a Python package, a collection of command-line tools, and a web server, maximizing the potential practical utility of the predictor. We believe metapredict offers a convenient, accessible, accurate, and high-performance predictor for single-proteins and proteomes alike.

Intrinsically disordered proteins and protein regions (collectively IDRs) are critical in
numerous cellular processes. To understand how IDRs facilitate function, we need tools
to accurately and rapidly identify them from sequence. While many methods for disorder
prediction exist, we are currently limited by throughput and accuracy for evolutionary
scale analyses. To bridge this gap, we developed metapredict V3, an updated version of
our disorder predictor that enables evolutionary-scale disorder prediction. Metapredict
V3 enables proteome-scale prediction with state-of-the-art accuracy in seconds and
was developed with a focus on usability. It is distributed as a web server, Python
software package, command-line interface, and Google Colab notebook. Here, we
leverage the accuracy and throughput of metapredict V3 to predict disorder for over
20,000 proteomes to evaluate the prevalence of disorder across the kingdoms of life.

### Metapredict Model/Method
Metapredict (v1,2,3) is a deep-learning-based disorder predictor that was trained using both consensus disorder predictions and structural predictions. Metapredict V2 uses a long-short-term memory bi-directional recurrent network (LSTM-BRNN) architecture and was trained in two steps. First, two initial LSTM-BRNN models were trained: a consensus disorder predictor (trained on consensus disorder from eight different predictors across twelve proteomes) and a pLDDT predictor (trained on AlphaFold2 pLDDT scores across twenty-one different proteomes). These two models were then combined using a consensus confidence approach, providing a per-residue score based on the combination of structural uncertainty and disorder prediction. Finally, a new LSTM-BRNN was trained on the consensus confidence scores, yielding a single model that was indirectly trained on both disorder predictions and structural predictions.