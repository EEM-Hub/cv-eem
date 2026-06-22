---
source: https://en.wikipedia.org/wiki/Self-supervised_learning
fetched: 2026-06-21
---

Machine learning paradigm Not to be confused with [Semi-supervised learning](./Semi-supervised_learning). 
|  | This articlemay be too technical for most readers to understand.Pleasehelp improve ittomake it understandable to non-experts, without removing the technical details.(July 2025)(Learn how and when to remove this message) |
| --- | --- |

 

 
| Part of a series on |
| --- |
| Machine learninganddata mining |
| ParadigmsSupervised learningUnsupervised learningSemi-supervised learningSelf-supervised learningReinforcement learningMeta-learningOnline learningBatch learningCurriculum learningRule-based learningNeuro-symbolic AINeuromorphic engineeringQuantum machine learning |
| ProblemsClassificationGenerative modelingRegressionClusteringDimensionality reductionDensity estimationAnomaly detectionData cleaningAutoMLAssociation rulesSemantic analysisStructured predictionFeature engineeringFeature learningLearning to rankGrammar inductionOntology learningMultimodal learning |
| Supervised learning(classification•regression)Apprenticeship learningDecision treesEnsemblesBaggingBoostingRandom forestk-NNLinear regressionNaive BayesArtificial neural networksLogistic regressionPerceptronRelevance vector machine (RVM)Support vector machine (SVM) |
| ClusteringBIRCHCUREHierarchicalk-meansFuzzyExpectation–maximization (EM)DBSCANOPTICSMean shift |
| Dimensionality reductionFactor analysisCCAICALDANMFPCAPGDt-SNESDL |
| Structured predictionGraphical modelsBayes netConditional random fieldHidden Markov |
| Anomaly detectionRANSACk-NNLocal outlier factorIsolation forest |
| Neural networksAutoencoderDeep learningFeedforward neural networkRecurrent neural networkLSTMGRUESNreservoir computingBoltzmann machineRestrictedGANDiffusion modelSOMConvolutional neural networkU-NetLeNetAlexNetDeepDreamNeural fieldNeural radiance fieldPhysics-informed neural networksTransformerVisionMambaSpiking neural networkMemtransistorElectrochemical RAM(ECRAM) |
| Reinforcement learningQ-learningPolicy gradientSARSATemporal difference (TD)Multi-agentSelf-play |
| Learning with humansActive learningCrowdsourcingHuman-in-the-loopMechanistic interpretabilityRLHF |
| Model diagnosticsCoefficient of determinationConfusion matrixLearning curveROC curve |
| Mathematical foundationsKernel machinesBias–variance tradeoffComputational learning theoryEmpirical risk minimizationOccam learningPAC learningStatistical learningVC theoryTopological deep learning |
| Journals and conferencesAAAICVPRECCVECML PKDDEMNLPICCVNeurIPSICMLICLRIJCAIMLJMLR |
| Related articlesGlossary of artificial intelligenceList of datasets for machine-learning researchList of datasets in computer vision and image processingOutline of machine learning |
| vte |

 

**Self-supervised learning** (**SSL**) is a paradigm in [machine learning](./Machine_learning) where a model is trained on a task using the data itself to generate supervisory signals, rather than relying on externally-provided labels. In the context of [neural networks](./Neural_network_(machine_learning)), self-supervised learning aims to leverage inherent structures or relationships within the input data to create meaningful training signals. SSL tasks are designed so that solving them requires capturing essential [features](./Feature_(machine_learning)) or relationships in the data. The input data is typically augmented or transformed in a way that creates pairs of related samples, where one sample serves as the input, and the other is used to formulate the supervisory signal. This augmentation can involve introducing noise, cropping, rotation, or other transformations. Self-supervised learning more closely imitates the way humans learn to classify objects.[[1]](./Self-supervised_learning#cite_note-auto3-1)

 

During SSL, the model learns in two steps. First, the task is solved based on an auxiliary or pretext classification task using pseudo-labels, which help to initialize the model [parameters](./Parameter#Artificial_intelligence).[[2]](./Self-supervised_learning#cite_note-2)[[3]](./Self-supervised_learning#cite_note-auto1-3) Next, the actual task is performed with [supervised](./Supervised_learning) or [unsupervised learning](./Unsupervised_learning).[[4]](./Self-supervised_learning#cite_note-4)[[5]](./Self-supervised_learning#cite_note-5)[[6]](./Self-supervised_learning#cite_note-6)

 

Self-supervised learning has produced promising results in recent years, and has found practical application in fields such as [audio processing](./Audio_signal_processing), and is being used by [Facebook](./Facebook) and others for [speech recognition](./Speech_recognition).[[7]](./Self-supervised_learning#cite_note-auto-7)

 

## Pseudo-labels

 

Pseudo-labels are automatically generated labels that a model assigns to unlabeled data based on its own predictions. They are widely used in self-supervised and semi-supervised learning, where ground-truth annotations are limited or unavailable. By treating predicted labels as surrogate ground truth, learning algorithms can make use of large quantities of unlabeled data in the training process.[[8]](./Self-supervised_learning#cite_note-Lee20132-8)

 

Pseudo-labeling also plays an important role in systems that must adapt to [concept drift](./Concept_drift), where the statistical properties of the data change over time. In these scenarios, the model may detect that an incoming instance deviates from previously learned behavior. The system then generates a classification result for that instance, and this predicted class is used as a pseudo-label for updating or retraining model components that are becoming outdated. This approach enables continuous adaptation in dynamic environments without requiring manual annotation.[[9]](./Self-supervised_learning#cite_note-Gama20142-9)[[10]](./Self-supervised_learning#cite_note-DroidEvolver2019-10)

 

In many [adaptive learning](./Adaptive_learning) pipelines, pseudo-labels are chosen when the classifier produces sufficiently confident predictions, reducing the risk of propagating errors. These pseudo-labeled instances are then incorporated into training to refresh or evolve the model's understanding of emerging data patterns, particularly when existing components show signs of “aging” due to drift or distributional shifts. This strategy reduces reliance on manual labeling while helping maintain long-term model performance.

 

## Types

 

### Autoassociative self-supervised learning

 

Autoassociative self-supervised learning is a specific category of self-supervised learning where a neural network is trained to reproduce or reconstruct its own input data.[[11]](./Self-supervised_learning#cite_note-:17-11) In other words, the model is tasked with learning a representation of the data that captures its essential features or structure, allowing it to regenerate the original input.

 

The term "autoassociative" comes from the fact that the model is essentially associating the input data with itself. This is often achieved using [autoencoders](./Autoencoders), which are a type of neural network architecture used for representation learning. Autoencoders consist of an *encoder* network that maps the input data to a lower-dimensional representation (latent space), and a *decoder* network that reconstructs the input from this representation.

 

The training process involves presenting the model with input data and requiring it to reconstruct the same data as closely as possible. The [loss function](./Loss_function) used during training typically penalizes the difference between the original input and the reconstructed output (e.g. [mean squared error](./Mean_squared_error)). By minimizing this reconstruction error, the autoencoder learns a meaningful representation of the data in its [latent space](./Latent_space).

 

### Contrastive self-supervised learning

 

For a [binary classification](./Binary_classification) task, [training data](./Training,_validation,_and_test_data_sets) can be divided into positive examples and negative examples. Positive examples are those that match the target. For example, if training a classifier to identify birds, the positive training data would include images that contain birds. Negative examples would be images that do not.[[12]](./Self-supervised_learning#cite_note-:0-12) Contrastive self-supervised learning uses both positive and negative examples. The loss function in contrastive learning is used to minimize the distance between positive sample pairs, while maximizing the distance between negative sample pairs.[[12]](./Self-supervised_learning#cite_note-:0-12)

 

An early example uses a pair of 1-dimensional [convolutional neural networks](./Convolutional_neural_network) to process a pair of images and maximize their agreement.[[13]](./Self-supervised_learning#cite_note-13)

 

[Contrastive Language-Image Pre-training](./Contrastive_Language-Image_Pre-training) (CLIP) allows joint pretraining of a text encoder and an image encoder, such that a matching image-text pair have image encoding vector and text encoding vector that span a small angle (having a large [cosine similarity](./Cosine_similarity)).

 

InfoNCE (Noise-Contrastive Estimation)[[14]](./Self-supervised_learning#cite_note-14) is a method to optimize two models jointly, based on Noise Contrastive Estimation (NCE).[[15]](./Self-supervised_learning#cite_note-15) Given a set     X =  {   x  1   , … …   x  N    }    {\displaystyle X=\left\{x_{1},\ldots x_{N}\right\}}  ![{\displaystyle X=\left\{x_{1},\ldots x_{N}\right\}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7d849ec68b1e76af735f241b14fd372126fbd494) of     N   {\displaystyle N}  ![{\displaystyle N}](https://wikimedia.org/api/rest_v1/media/math/render/svg/f5e3890c981ae85503089652feb48b191b57aae3) random samples containing one positive sample from     p  (   x  t + k   ∣ ∣   c  t    )    {\displaystyle p\left(x_{t+k}\mid c_{t}\right)}  ![{\displaystyle p\left(x_{t+k}\mid c_{t}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d20f778420ed366654b317dfd2d287a21caa9d37) and     N − −  1   {\displaystyle N-1}  ![{\displaystyle N-1}](https://wikimedia.org/api/rest_v1/media/math/render/svg/86aeb216b214f70df1341f34ce273cd3582ce2aa) negative samples from the 'proposal' distribution     p  (  x  t + k   )    {\displaystyle p\left(x_{t+k}\right)}  ![{\displaystyle p\left(x_{t+k}\right)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/43200da0391c2ae97d6bd4541e544d9c526ac08a), it minimizes the following loss function:

 

       L     N    = − −    E   X    [  log ⁡ ⁡      f  k    (   x  t + k   ,  c  t    )     ∑ ∑    x  j   ∈ ∈  X    f  k    (   x  j   ,  c  t    )      ]    {\displaystyle {\mathcal {L}}_{\mathrm {N} }=-\mathbb {E} _{X}\left[\log {\frac {f_{k}\left(x_{t+k},c_{t}\right)}{\sum _{x_{j}\in X}f_{k}\left(x_{j},c_{t}\right)}}\right]}  ![{\displaystyle {\mathcal {L}}_{\mathrm {N} }=-\mathbb {E} _{X}\left[\log {\frac {f_{k}\left(x_{t+k},c_{t}\right)}{\sum _{x_{j}\in X}f_{k}\left(x_{j},c_{t}\right)}}\right]}](https://wikimedia.org/api/rest_v1/media/math/render/svg/750445a118efd501656fa3ada322087a704bf862)

 

### Non-contrastive self-supervised learning

 

Non-contrastive self-supervised learning (NCSSL) uses only positive examples. Counterintuitively, NCSSL converges on a useful local minimum rather than reaching a trivial solution, with zero loss. For the example of binary classification, it would trivially learn to classify each example as positive. Effective NCSSL requires an extra predictor on the online side that does not [back-propagate](./Backpropagation) on the target side.[[12]](./Self-supervised_learning#cite_note-:0-12)

 

### Joint-Embedding and Predictive Architectures

 

A major class of self-supervised learning moves beyond contrastive pairs, instead maximizing the agreement between views while preventing collapse through statistical constraints. Rooted in Deep Canonical Correlation Analysis (Deep CCA),[[16]](./Self-supervised_learning#cite_note-16) this approach includes Joint-Embedding Architectures (JEA) like Barlow Twins[[17]](./Self-supervised_learning#cite_note-17) and VICReg,[[18]](./Self-supervised_learning#cite_note-18) which enforce covariance constraints to learn invariant representations without negative sampling. Deep Latent Variable Path Modelling (DLVPM)[[19]](./Self-supervised_learning#cite_note-19) generalizes this to multimodal systems, using path models to enforce correlation and orthogonality across diverse data types.

 

In 2022 [Yann LeCun](./Yann_LeCun) introduced Joint-Embedding Predictive Architectures (JEPA) as a step towards decision making, reasoning, and autonomous human intelligence in machines, including self-improvement through autonomous learning. Founded in representation learning, LeCun included the concept of a “[world model](./World_model_(artificial_intelligence))” in JEPA which aims to enable machines to replicate human intellect by providing machines with a concept for the world in which they exist.[[20]](./Self-supervised_learning#cite_note-20)

 

Unlike autoencoders, JEPAs operate entirely in latent space, avoiding pixel-level noise to focus on semantic structure. Rather than just learning invariance, JEPAs learn by predicting masked latent representations from visible context.[[21]](./Self-supervised_learning#cite_note-21) JEPA has been applied to domains such as image analysis,[[22]](./Self-supervised_learning#cite_note-22) audio processing,[[23]](./Self-supervised_learning#cite_note-23) and motion in images and video.[[24]](./Self-supervised_learning#cite_note-24)

 

## Comparison with other forms of machine learning

 

SSL belongs to supervised learning methods insofar as the goal is to generate a classified output from the input. At the same time, however, it does not require the explicit use of labeled input-output pairs. Instead, correlations, metadata embedded in the data, or [domain knowledge](./Domain_knowledge) present in the input are implicitly and autonomously extracted from the data. These supervisory signals, extracted from the data, can then be used for training.[[1]](./Self-supervised_learning#cite_note-auto3-1)

 

SSL is similar to unsupervised learning in that it does not require labels in the sample data. Unlike unsupervised learning, however, learning is not done using inherent data structures.

 

[Semi-supervised learning](./Semi-supervised_learning) combines supervised and unsupervised learning, requiring only a small portion of the learning data be [labeled](./Labeled_data).[[3]](./Self-supervised_learning#cite_note-auto1-3)

 

In [transfer learning](./Transfer_learning), a model designed for one task is reused on a different task.[[25]](./Self-supervised_learning#cite_note-25)

 

Training an [autoencoder](./Autoencoder) intrinsically constitutes a self-supervised process, because the output pattern needs to become an optimal reconstruction of the input pattern itself. However, in current jargon, the term 'self-supervised' often refers to tasks based on a pretext-task training setup. This involves the (human) design of such pretext task(s), unlike 
the case of fully self-contained autoencoder training.[[11]](./Self-supervised_learning#cite_note-:17-11)

 

In [reinforcement learning](./Reinforcement_learning), self-supervising learning from a combination of losses can create abstract representations where only the most important information about the state are kept in a compressed way.[[26]](./Self-supervised_learning#cite_note-26)

 

## Examples

 

Self-supervised learning is particularly suitable for speech recognition. For example, [Facebook](./Facebook) developed *wav2vec*, a self-supervised algorithm, to perform speech recognition using two deep [convolutional neural networks](./Convolutional_neural_networks) that build on each other.[[7]](./Self-supervised_learning#cite_note-auto-7)

 

[Google](./Google)'s [Bidirectional Encoder Representations from Transformers](./BERT_(language_model)) (BERT) model is used to better understand the context of search queries.[[27]](./Self-supervised_learning#cite_note-27)

 

[OpenAI](./OpenAI)'s [GPT-3](./GPT-3) is an autoregressive [language model](./Language_model) that can be used in language processing. It can be used to translate texts or answer questions, among other things.[[28]](./Self-supervised_learning#cite_note-28)

 

*Bootstrap Your Own Latent* (BYOL) is a NCSSL that produced excellent results on [ImageNet](./ImageNet) and on transfer and semi-supervised benchmarks.[[29]](./Self-supervised_learning#cite_note-29)

 

The [Yarowsky algorithm](./Yarowsky_algorithm) is an example of self-supervised learning in [natural language processing](./Natural_language_processing). From a small number of labeled examples, it learns to predict which [word sense](./Word_sense_disambiguation) of a [polysemous](./Polysemy) word is being used at a given point in text.

 

DirectPred is a NCSSL that directly sets the predictor weights instead of learning it via typical [gradient descent](./Gradient_descent).[[12]](./Self-supervised_learning#cite_note-:0-12)

 

Self-GenomeNet is an example of self-supervised learning in genomics.[[30]](./Self-supervised_learning#cite_note-30)

 

SelfAPR is an example of self-supervised learning applied to [automated program repair](./Automatic_bug_fixing), where a neural model is trained on perturbations of a previous version of the program under repair and uses test execution diagnostics to synthesize patches.[[31]](./Self-supervised_learning#cite_note-31)

 

Self-supervised learning continues to gain prominence as a new approach across diverse fields. Its ability to leverage unlabeled data effectively opens new possibilities for advancement in machine learning, especially in data-driven application domains.

 

## References

  
1. [1](./Self-supervised_learning#cite_ref-auto3_1-0) [2](./Self-supervised_learning#cite_ref-auto3_1-1) Bouchard, Louis (25 November 2020). ["What is Self-Supervised Learning? | Will machines ever be able to learn like humans?"](https://medium.com/what-is-artificial-intelligence/what-is-self-supervised-learning-will-machines-be-able-to-learn-like-humans-d9160f40cdd1). *Medium*. Retrieved 9 June 2021.
2. [↑](./Self-supervised_learning#cite_ref-2) Doersch, Carl; Zisserman, Andrew (October 2017). ["Multi-task Self-Supervised Visual Learning"](https://dx.doi.org/10.1109/iccv.2017.226). *2017 IEEE International Conference on Computer Vision (ICCV)*. IEEE. pp. 2070–2079. [arXiv](./ArXiv_(identifier)):[1708.07860](https://arxiv.org/abs/1708.07860). [doi](./Doi_(identifier)):[10.1109/iccv.2017.226](https://doi.org/10.1109%2Ficcv.2017.226). [ISBN](./ISBN_(identifier)) [978-1-5386-1032-9](./Special:BookSources/978-1-5386-1032-9). [S2CID](./S2CID_(identifier)) [473729](https://api.semanticscholar.org/CorpusID:473729).
3. [1](./Self-supervised_learning#cite_ref-auto1_3-0) [2](./Self-supervised_learning#cite_ref-auto1_3-1) Beyer, Lucas; Zhai, Xiaohua; Oliver, Avital; Kolesnikov, Alexander (October 2019). ["S4L: Self-Supervised Semi-Supervised Learning"](https://dx.doi.org/10.1109/iccv.2019.00156). *2019 IEEE/CVF International Conference on Computer Vision (ICCV)*. IEEE. pp. 1476–1485. [arXiv](./ArXiv_(identifier)):[1905.03670](https://arxiv.org/abs/1905.03670). [doi](./Doi_(identifier)):[10.1109/iccv.2019.00156](https://doi.org/10.1109%2Ficcv.2019.00156). [ISBN](./ISBN_(identifier)) [978-1-7281-4803-8](./Special:BookSources/978-1-7281-4803-8). [S2CID](./S2CID_(identifier)) [167209887](https://api.semanticscholar.org/CorpusID:167209887).
4. [↑](./Self-supervised_learning#cite_ref-4) Doersch, Carl; Gupta, Abhinav; Efros, Alexei A. (December 2015). ["Unsupervised Visual Representation Learning by Context Prediction"](https://dx.doi.org/10.1109/iccv.2015.167). *2015 IEEE International Conference on Computer Vision (ICCV)*. IEEE. pp. 1422–1430. [arXiv](./ArXiv_(identifier)):[1505.05192](https://arxiv.org/abs/1505.05192). [doi](./Doi_(identifier)):[10.1109/iccv.2015.167](https://doi.org/10.1109%2Ficcv.2015.167). [ISBN](./ISBN_(identifier)) [978-1-4673-8391-2](./Special:BookSources/978-1-4673-8391-2). [S2CID](./S2CID_(identifier)) [9062671](https://api.semanticscholar.org/CorpusID:9062671).
5. [↑](./Self-supervised_learning#cite_ref-5) Zheng, Xin; Wang, Yong; Wang, Guoyou; Liu, Jianguo (April 2018). ["Fast and robust segmentation of white blood cell images by self-supervised learning"](https://dx.doi.org/10.1016/j.micron.2018.01.010). *Micron*. **107**: 55–71. [doi](./Doi_(identifier)):[10.1016/j.micron.2018.01.010](https://doi.org/10.1016%2Fj.micron.2018.01.010). [ISSN](./ISSN_(identifier)) [0968-4328](https://search.worldcat.org/issn/0968-4328). [PMID](./PMID_(identifier)) [29425969](https://pubmed.ncbi.nlm.nih.gov/29425969). [S2CID](./S2CID_(identifier)) [3796689](https://api.semanticscholar.org/CorpusID:3796689).
6. [↑](./Self-supervised_learning#cite_ref-6) Gidaris, Spyros; Bursuc, Andrei; Komodakis, Nikos; Perez, Patrick Perez; Cord, Matthieu (October 2019). ["Boosting Few-Shot Visual Learning with Self-Supervision"](https://dx.doi.org/10.1109/iccv.2019.00815). *2019 IEEE/CVF International Conference on Computer Vision (ICCV)*. IEEE. pp. 8058–8067. [arXiv](./ArXiv_(identifier)):[1906.05186](https://arxiv.org/abs/1906.05186). [doi](./Doi_(identifier)):[10.1109/iccv.2019.00815](https://doi.org/10.1109%2Ficcv.2019.00815). [ISBN](./ISBN_(identifier)) [978-1-7281-4803-8](./Special:BookSources/978-1-7281-4803-8). [S2CID](./S2CID_(identifier)) [186206588](https://api.semanticscholar.org/CorpusID:186206588).
7. [1](./Self-supervised_learning#cite_ref-auto_7-0) [2](./Self-supervised_learning#cite_ref-auto_7-1) ["Wav2vec: State-of-the-art speech recognition through self-supervision"](https://ai.facebook.com/blog/wav2vec-state-of-the-art-speech-recognition-through-self-supervision/). *ai.facebook.com*. Retrieved 9 June 2021.
8. [↑](./Self-supervised_learning#cite_ref-Lee20132_8-0) Lee, Dong-Hyun (2013). *Pseudo-Label: The Simple and Efficient Semi-Supervised Learning Method for Deep Neural Networks*. ICML 2013 Workshop on Challenges in Representation Learning (WREPL).
9. [↑](./Self-supervised_learning#cite_ref-Gama20142_9-0) Gama, João (2014). ["A Survey on Concept Drift Adaptation"](http://repositorio.inesctec.pt/handle/123456789/5370). *ACM Computing Surveys*. **46** (4): 1–37. [doi](./Doi_(identifier)):[10.1145/2523813](https://doi.org/10.1145%2F2523813).
10. [↑](./Self-supervised_learning#cite_ref-DroidEvolver2019_10-0) Xu, K.; Li, Y.; Deng, R.; Chen, K.; Xu, J. (2019). *Self-Evolving Android Malware Detection System*. IEEE European Symposium on Security and Privacy (EuroS&P). pp. 47–62. [doi](./Doi_(identifier)):[10.1109/EuroSP.2019.00014](https://doi.org/10.1109%2FEuroSP.2019.00014).
11. [1](./Self-supervised_learning#cite_ref-:17_11-0) [2](./Self-supervised_learning#cite_ref-:17_11-1) Kramer, Mark A. (1991). ["Nonlinear principal component analysis using autoassociative neural networks"](https://www.researchgate.net/profile/Abir_Alobaid/post/To_learn_a_probability_density_function_by_using_neural_network_can_we_first_estimate_density_using_nonparametric_methods_then_train_the_network/attachment/59d6450279197b80779a031e/AS:451263696510979@1484601057779/download/NL+PCA+by+using+ANN.pdf) (PDF). *AIChE Journal*. **37** (2): 233–243. [Bibcode](./Bibcode_(identifier)):[1991AIChE..37..233K](https://ui.adsabs.harvard.edu/abs/1991AIChE..37..233K). [doi](./Doi_(identifier)):[10.1002/aic.690370209](https://doi.org/10.1002%2Faic.690370209).
12. [1](./Self-supervised_learning#cite_ref-:0_12-0) [2](./Self-supervised_learning#cite_ref-:0_12-1) [3](./Self-supervised_learning#cite_ref-:0_12-2) [4](./Self-supervised_learning#cite_ref-:0_12-3) ["Demystifying a key self-supervised learning technique: Non-contrastive learning"](https://ai.facebook.com/blog/demystifying-a-key-self-supervised-learning-technique-non-contrastive-learning/). *ai.facebook.com*. Retrieved 5 October 2021.
13. [↑](./Self-supervised_learning#cite_ref-13) Becker, Suzanna; Hinton, Geoffrey E. (January 1992). ["Self-organizing neural network that discovers surfaces in random-dot stereograms"](https://www.nature.com/articles/355161a0). *Nature*. **355** (6356): 161–163. [Bibcode](./Bibcode_(identifier)):[1992Natur.355..161B](https://ui.adsabs.harvard.edu/abs/1992Natur.355..161B). [doi](./Doi_(identifier)):[10.1038/355161a0](https://doi.org/10.1038%2F355161a0). [ISSN](./ISSN_(identifier)) [1476-4687](https://search.worldcat.org/issn/1476-4687). [PMID](./PMID_(identifier)) [1729650](https://pubmed.ncbi.nlm.nih.gov/1729650).
14. [↑](./Self-supervised_learning#cite_ref-14) Oord, Aaron van den; Li, Yazhe; Vinyals, Oriol (22 January 2019). "Representation Learning with Contrastive Predictive Coding". [arXiv](./ArXiv_(identifier)):[1807.03748](https://arxiv.org/abs/1807.03748) [[cs.LG](https://arxiv.org/archive/cs.LG)].
15. [↑](./Self-supervised_learning#cite_ref-15) Gutmann, Michael; Hyvärinen, Aapo (31 March 2010). ["Noise-contrastive estimation: A new estimation principle for unnormalized statistical models"](https://proceedings.mlr.press/v9/gutmann10a). *Proceedings of the Thirteenth International Conference on Artificial Intelligence and Statistics*. JMLR Workshop and Conference Proceedings: 297–304.
16. [↑](./Self-supervised_learning#cite_ref-16) Andrew, Galen; Arora, Raman; Bilmes, Jeff; Livescu, Karen (26 May 2013). ["Deep Canonical Correlation Analysis"](https://proceedings.mlr.press/v28/andrew13.html). *Proceedings of the 30th International Conference on Machine Learning*. PMLR: 1247–1255.
17. [↑](./Self-supervised_learning#cite_ref-17) Zbontar, Jure; Jing, Li; Misra, Ishan; LeCun, Yann; Deny, Stephane (1 July 2021). ["Barlow Twins: Self-Supervised Learning via Redundancy Reduction"](https://proceedings.mlr.press/v139/zbontar21a.html). *Proceedings of the 38th International Conference on Machine Learning*. PMLR: 12310–12320.
18. [↑](./Self-supervised_learning#cite_ref-18) Bardes, Adrien; Ponce, Jean; LeCun, Yann (11 May 2021). "VICReg: Variance-Invariance-Covariance Regularization for Self-Supervised Learning". [arXiv](./ArXiv_(identifier)):[2105.04906v3](https://arxiv.org/abs/2105.04906v3) [[cs.CV](https://arxiv.org/archive/cs.CV)].
19. [↑](./Self-supervised_learning#cite_ref-19) Ing, Alex; Andrades, Alvaro; Cosenza, Marco Raffaele; Korbel, Jan O. (July 2025). ["Integrating multimodal cancer data using deep latent variable path modelling"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12283373). *Nature Machine Intelligence*. **7** (7): 1053–1075. [doi](./Doi_(identifier)):[10.1038/s42256-025-01052-4](https://doi.org/10.1038%2Fs42256-025-01052-4). [ISSN](./ISSN_(identifier)) [2522-5839](https://search.worldcat.org/issn/2522-5839). [PMC](./PMC_(identifier)) [12283373](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12283373). [PMID](./PMID_(identifier)) [40709098](https://pubmed.ncbi.nlm.nih.gov/40709098).
20. [↑](./Self-supervised_learning#cite_ref-20) LeCun, Yann (27 June 2022). ["A Path Towards Autonomous Machine Intelligence"](https://openreview.net/pdf?id=BZ5a1r-kVsf). *OpenReview*.
21. [↑](./Self-supervised_learning#cite_ref-21) Assran, Mahmoud; Duval, Quentin; Misra, Ishan; Bojanowski, Piotr; Vincent, Pascal; Rabbat, Michael; LeCun, Yann; Ballas, Nicolas (13 April 2023). "Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture". [arXiv](./ArXiv_(identifier)):[2301.08243](https://arxiv.org/abs/2301.08243) [[cs.CV](https://arxiv.org/archive/cs.CV)].
22. [↑](./Self-supervised_learning#cite_ref-22) Garrido, Quentin; Assran, Mahmoud; Ballas, Nicolas; Bardes, Adrien; Najman, Laurent; LeCun, Yann (2024). "Learning and Leveraging World Models in Visual Representation Learning". [arXiv](./ArXiv_(identifier)):[2403.00504](https://arxiv.org/abs/2403.00504) [[cs.CV](https://arxiv.org/archive/cs.CV)].
23. [↑](./Self-supervised_learning#cite_ref-23) Fei, Zhengcong; Fan, Mingyuan; Huang, Junshi (2023). "A-JEPA: Joint-Embedding Predictive Architecture Can Listen". [arXiv](./ArXiv_(identifier)):[2311.15830](https://arxiv.org/abs/2311.15830) [[cs.SD](https://arxiv.org/archive/cs.SD)].
24. [↑](./Self-supervised_learning#cite_ref-24) Bardes, Adrien; Ponce, Jean; LeCun, Yann (2023). "MC-JEPA: A Joint-Embedding Predictive Architecture for Self-Supervised Learning of Motion and Content Features". [arXiv](./ArXiv_(identifier)):[2307.12698](https://arxiv.org/abs/2307.12698) [[cs.CV](https://arxiv.org/archive/cs.CV)].
25. [↑](./Self-supervised_learning#cite_ref-25) Littwin, Etai; Wolf, Lior (June 2016). ["The Multiverse Loss for Robust Transfer Learning"](https://dx.doi.org/10.1109/cvpr.2016.429). *2016 IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*. IEEE. pp. 3957–3966. [arXiv](./ArXiv_(identifier)):[1511.09033](https://arxiv.org/abs/1511.09033). [doi](./Doi_(identifier)):[10.1109/cvpr.2016.429](https://doi.org/10.1109%2Fcvpr.2016.429). [ISBN](./ISBN_(identifier)) [978-1-4673-8851-1](./Special:BookSources/978-1-4673-8851-1). [S2CID](./S2CID_(identifier)) [6517610](https://api.semanticscholar.org/CorpusID:6517610).
26. [↑](./Self-supervised_learning#cite_ref-26) Francois-Lavet, Vincent; Bengio, Yoshua; Precup, Doina; Pineau, Joelle (2019). "Combined Reinforcement Learning via Abstract Representations". *Proceedings of the AAAI Conference on Artificial Intelligence*. [arXiv](./ArXiv_(identifier)):[1809.04506](https://arxiv.org/abs/1809.04506).
27. [↑](./Self-supervised_learning#cite_ref-27) ["Open Sourcing BERT: State-of-the-Art Pre-training for Natural Language Processing"](http://ai.googleblog.com/2018/11/open-sourcing-bert-state-of-art-pre.html). *Google AI Blog*. 2 November 2018. Retrieved 9 June 2021.
28. [↑](./Self-supervised_learning#cite_ref-28) Wilcox, Ethan; Qian, Peng; Futrell, Richard; Kohita, Ryosuke; Levy, Roger; Ballesteros, Miguel (2020). ["Structural Supervision Improves Few-Shot Learning and Syntactic Generalization in Neural Language Models"](https://dx.doi.org/10.18653/v1/2020.emnlp-main.375). *Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP)*. Stroudsburg, PA, USA: Association for Computational Linguistics. pp. 4640–4652. [arXiv](./ArXiv_(identifier)):[2010.05725](https://arxiv.org/abs/2010.05725). [doi](./Doi_(identifier)):[10.18653/v1/2020.emnlp-main.375](https://doi.org/10.18653%2Fv1%2F2020.emnlp-main.375). [S2CID](./S2CID_(identifier)) [222291675](https://api.semanticscholar.org/CorpusID:222291675).
29. [↑](./Self-supervised_learning#cite_ref-29) Grill, Jean-Bastien; Strub, Florian; Altché, Florent; Tallec, Corentin; Richemond, Pierre H.; Buchatskaya, Elena; Doersch, Carl; Pires, Bernardo Avila; Guo, Zhaohan Daniel; Azar, Mohammad Gheshlaghi; Piot, Bilal (10 September 2020). "Bootstrap your own latent: A new approach to self-supervised Learning". [arXiv](./ArXiv_(identifier)):[2006.07733](https://arxiv.org/abs/2006.07733) [[cs.LG](https://arxiv.org/archive/cs.LG)].
30. [↑](./Self-supervised_learning#cite_ref-30) Gündüz, Hüseyin Anil; Binder, Martin; To, Xiao-Yin; Mreches, René; Bischl, Bernd; McHardy, Alice C.; Münch, Philipp C.; Rezaei, Mina (11 September 2023). ["A self-supervised deep learning method for data-efficient training in genomics"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10495322). *Communications Biology*. **6** (1): 928. [doi](./Doi_(identifier)):[10.1038/s42003-023-05310-2](https://doi.org/10.1038%2Fs42003-023-05310-2). [ISSN](./ISSN_(identifier)) [2399-3642](https://search.worldcat.org/issn/2399-3642). [PMC](./PMC_(identifier)) [10495322](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10495322). [PMID](./PMID_(identifier)) [37696966](https://pubmed.ncbi.nlm.nih.gov/37696966).
31. [↑](./Self-supervised_learning#cite_ref-31) Ye, He; Martinez, Matias; Luo, Xiapu; Zhang, Tao; Monperrus, Martin (2022). ["SelfAPR: Self-supervised Program Repair with Test Execution Diagnostics"](https://dl.acm.org/doi/10.1145/3551349.3556926). *ASE '22: 37th IEEE/ACM International Conference on Automated Software Engineering*: 1–13. [doi](./Doi_(identifier)):[10.1145/3551349.3556926](https://doi.org/10.1145%2F3551349.3556926). Retrieved 28 May 2026.

 

## Further reading

 
- Balestriero, Randall; Ibrahim, Mark; Sobal, Vlad; Morcos, Ari; Shekhar, Shashank; Goldstein, Tom; Bordes, Florian; Bardes, Adrien; Mialon, Gregoire; Tian, Yuandong; Schwarzschild, Avi; Wilson, Andrew Gordon; Geiping, Jonas; Garrido, Quentin; Fernandez, Pierre (24 April 2023). "A Cookbook of Self-Supervised Learning". [arXiv](./ArXiv_(identifier)):[2304.12210](https://arxiv.org/abs/2304.12210) [[cs.LG](https://arxiv.org/archive/cs.LG)].

 

## External links

 
- Doersch, Carl; Zisserman, Andrew (October 2017). "Multi-task Self-Supervised Visual Learning". *2017 IEEE International Conference on Computer Vision (ICCV)*. pp. 2070–2079. [arXiv](./ArXiv_(identifier)):[1708.07860](https://arxiv.org/abs/1708.07860). [doi](./Doi_(identifier)):[10.1109/ICCV.2017.226](https://doi.org/10.1109%2FICCV.2017.226). [ISBN](./ISBN_(identifier)) [978-1-5386-1032-9](./Special:BookSources/978-1-5386-1032-9). [S2CID](./S2CID_(identifier)) [473729](https://api.semanticscholar.org/CorpusID:473729).
- Doersch, Carl; Gupta, Abhinav; Efros, Alexei A. (December 2015). "Unsupervised Visual Representation Learning by Context Prediction". *2015 IEEE International Conference on Computer Vision (ICCV)*. pp. 1422–1430. [arXiv](./ArXiv_(identifier)):[1505.05192](https://arxiv.org/abs/1505.05192). [doi](./Doi_(identifier)):[10.1109/ICCV.2015.167](https://doi.org/10.1109%2FICCV.2015.167). [ISBN](./ISBN_(identifier)) [978-1-4673-8391-2](./Special:BookSources/978-1-4673-8391-2). [S2CID](./S2CID_(identifier)) [9062671](https://api.semanticscholar.org/CorpusID:9062671).
- Zheng, Xin; Wang, Yong; Wang, Guoyou; Liu, Jianguo (1 April 2018). ["Fast and robust segmentation of white blood cell images by self-supervised learning"](https://ink.library.smu.edu.sg/sis_research/5884). *Micron*. **107**: 55–71. [doi](./Doi_(identifier)):[10.1016/j.micron.2018.01.010](https://doi.org/10.1016%2Fj.micron.2018.01.010). [ISSN](./ISSN_(identifier)) [0968-4328](https://search.worldcat.org/issn/0968-4328). [PMID](./PMID_(identifier)) [29425969](https://pubmed.ncbi.nlm.nih.gov/29425969). [S2CID](./S2CID_(identifier)) [3796689](https://api.semanticscholar.org/CorpusID:3796689).
- Yarowsky, David (1995). ["Unsupervised Word Sense Disambiguation Rivaling Supervised Methods"](https://aclanthology.org/P95-1026/). *Proceedings of the 33rd Annual Meeting of the Association for Computational Linguistics*. Cambridge, MA: Association for Computational Linguistics: 189–196. [doi](./Doi_(identifier)):[10.3115/981658.981684](https://doi.org/10.3115%2F981658.981684). Retrieved 1 November 2022.

 
| vteArtificial intelligence(AI) |
| --- |
| HistorytimelineGlossaryCompaniesProjectsList of open-source AI software |
| Concepts | Automated reasoningParameterHyperparameterLoss functionsRegressionBias–variance tradeoffDouble descentOverfittingClusteringGradient descentSGDQuasi-Newton methodConjugate gradient methodBackpropagationAttentionConvolutionNormalizationBatchnormActivationSoftmaxSigmoidRectifierGatingWeight initializationRegularizationDatasetsAugmentationPrompt engineeringReinforcement learningQ-learningSARSAImitationPolicy gradientDiffusionLatent diffusion modelAutoregressionAdversaryRAGUncanny valleyRLHFSelf-supervised learningReflectionRecursive self-improvementHallucinationWord embeddingVibe codingSymbolic AINeuro-symbolic AI |
| Applications | Automated theorem provingMachine learningIn-context learningArtificial neural networkDeep learningLanguage modelLargeNMTReasoningModel Context ProtocolIntelligent agentAI agentArtificial human companionHumanity's Last ExamLethal autonomous weapons (LAWs)Generative AIWeak AIHypotheticalArtificial general intelligence (AGI)Artificial superintelligence (ASI)Agent2Agent protocol |
| Implementations | Audio–visualAlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasisTextList of large language modelsProject DebaterIBM WatsonIBM WatsonxDecisionalAlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot controlReasoning systemsDeductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systemsCognitive architecturesACT-RSoarCLARIONLIDAOpenCogKnowledge basesConceptNetWikidataDBpediaYAGO | Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis | Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx | Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control | Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems | Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog | Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis |
| Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx |
| Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control |
| Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems |
| Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog |
| Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| People | Alan TuringWarren Sturgis McCullochWalter PittsJohn von NeumannChristopher D. ManningClaude ShannonShun'ichi AmariKunihiko FukushimaTakeo KanadeMarvin MinskyJohn McCarthyNathaniel RochesterAllen NewellCliff ShawHerbert A. SimonOliver SelfridgeFrank RosenblattBernard WidrowJoseph WeizenbaumSeymour PapertSeppo LinnainmaaPaul WerbosGeoffrey HintonJohn HopfieldJürgen SchmidhuberYann LeCunYoshua BengioLotfi A. ZadehStephen GrossbergAlex GravesJames GoodnightAndrew NgFei-Fei LiAlex KrizhevskyIlya SutskeverOriol VinyalsQuoc V. LeIan GoodfellowDemis HassabisDavid SilverAndrej KarpathyAshish VaswaniNoam ShazeerAidan GomezJohn SchulmanMustafa SuleymanJan LeikeDaniel KokotajloFrançois Chollet |
| Neural network architectures | Neural Turing machineDifferentiable neural computerTransformerVision transformer (ViT)Recurrent neural network (RNN)Long short-term memory (LSTM)Gated recurrent unit (GRU)Echo state networkMultilayer perceptron (MLP)Convolutional neural network (CNN)Residual neural network (RNN)Highway networkMambaAutoencoderVariational autoencoder (VAE)Generative adversarial network (GAN)Graph neural network (GNN) |
| Political | AI Cold WarAI safety(Alignment)AI takeoverElectionsEthics of AIEUAI ActNationalismPrecautionary principleRegulation of AIUSVirtual politicianPropaganda |
| Social and economic | AI boomAI bubbleAI data centerAI effectAI literacyAI slopAI veganismAI winterAnthropomorphismArms raceCompetitionEnvironmental impactExplainable AIGenerative engine optimizationIn architectureIn educationIn fictionIn healthcareChatbot psychosisIn marketingIn video gamesIn visual artMilitary applicationsAI warfareWorkplace impact |
| Category |