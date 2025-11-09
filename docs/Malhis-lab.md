# Nawar Malhis (Gsponer Lab) Tools

[← Back to list](../README.md#university-of-british-columbia)

## IPA (IDR Probabilistic Annotation)

### IPA Abstract
This paper introduces a novel platform for IDR Probabilistic Annotation (IPA). The IPA
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

### IPA Model/Method
The IPA platform provides probabilistic annotation of features related to intrinsically disordered regions (IDRs). It standardizes computational feature prediction using a reverse Bayes approach to transform logistic regression outputs into true probabilities, effectively removing the influence of training data priors.
