---
source: https://en.wikipedia.org/wiki/Data_augmentation
fetched: 2026-06-21
---

Data analysis technique 
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

 
|  | This article'stone or style may not reflect theencyclopedic toneused on Wikipedia.See Wikipedia'sguide to writing better articlesfor suggestions.(February 2024)(Learn how and when to remove this message) |
| --- | --- |

 

**Data augmentation** is a statistical technique which allows [maximum likelihood estimation](./Maximum_likelihood_estimation) from incomplete data.[[1]](./Data_augmentation#cite_note-1)[[2]](./Data_augmentation#cite_note-2) Data augmentation has important applications in [Bayesian analysis](./Bayesian_inference),[[3]](./Data_augmentation#cite_note-3) and the technique is widely used in [machine learning](./Machine_learning) to reduce [overfitting](./Overfitting) when training machine learning models,[[4]](./Data_augmentation#cite_note-Big_Data_2019_6:60-4) achieved by training models on several slightly-modified copies of existing data.

 

## Synthetic oversampling techniques for traditional machine learning

 Main article: [Oversampling and undersampling in data analysis § Oversampling techniques for classification problems](./Oversampling_and_undersampling_in_data_analysis#Oversampling_techniques_for_classification_problems)

Synthetic Minority Over-sampling Technique (SMOTE) is a method used to address imbalanced [datasets](./Data_set) in machine learning. In such datasets, the number of samples in different classes varies significantly, leading to biased model performance. For example, in a medical diagnosis dataset with 90 samples representing healthy individuals and only 10 samples representing individuals with a particular disease, traditional algorithms may struggle to accurately classify the minority class. SMOTE rebalances the dataset by generating synthetic samples for the minority class. For instance, if there are 100 samples in the majority class and 10 in the minority class, SMOTE can create synthetic samples by randomly selecting a minority class sample and its nearest neighbors, then generating new samples along the line segments joining these neighbors. This process helps increase the representation of the minority class, improving model performance.[[5]](./Data_augmentation#cite_note-5)

 

## Data augmentation for image classification

 

When [convolutional neural networks](./Convolutional_neural_networks) grew larger in mid-1990s, there was a lack of data to use, especially considering that some part of the overall dataset should be spared for later testing. It was proposed to perturb existing data with [affine transformations](./Affine_transformation) to create new examples with the same labels,[[6]](./Data_augmentation#cite_note-6) which were complemented by so-called elastic distortions in 2003,[[7]](./Data_augmentation#cite_note-elastic_distortion-7) and the technique was widely used as of 2010s.[[8]](./Data_augmentation#cite_note-8) Data augmentation can enhance CNN performance and acts as a countermeasure against CNN profiling attacks.[[9]](./Data_augmentation#cite_note-9)

 

Data augmentation has become fundamental in image classification, enriching [training dataset](./Training_dataset) diversity to improve model generalization and performance. The evolution of this practice has introduced a broad spectrum of techniques, including geometric transformations, color space adjustments, and noise injection.[[10]](./Data_augmentation#cite_note-10)

 

### Geometric Transformations

 

Geometric transformations alter the spatial properties of images to simulate different perspectives, orientations, and scales. Common techniques include:

 
- **[Affine Transformation](./Affine_transformation)** 
- **[Rotation](./Rotation_(mathematics))**: Rotating images by a specified degree to help models recognize objects at various angles.
- **[Reflection](./Reflection_(mathematics))**: Reflecting images horizontally or vertically to introduce variability in orientation.
- **[Translation](./Translation_(geometry))**: Shifting images in different directions to teach models positional invariance.
- **[Scaling](./Scaling_(geometry))**
- **[Shear Mapping](./Shear_mapping)**

- **Cropping**: Removing sections of the image to focus on particular features or simulate closer views.
- **Elastic Distortion**[[7]](./Data_augmentation#cite_note-elastic_distortion-7)
- **Morphing** **within the same class**: Generating new samples by applying morphing techniques between two images belonging to the same class, thereby increasing intra-class diversity.[[11]](./Data_augmentation#cite_note-11)

 

### Color Space Transformations

 

Color space transformations modify the color properties of images, addressing variations in lighting, [color saturation](./Color_saturation), and contrast. Techniques include:

 
- **Brightness Adjustment**: Varying the image's brightness to simulate different lighting conditions.
- **Contrast Adjustment**: Changing the contrast to help models recognize objects under various clarity levels.
- **Saturation Adjustment**: Altering saturation to prepare models for images with diverse color intensities.
- **Color Jittering**: Randomly adjusting brightness, contrast, saturation, and [hue](./Hue) to introduce color variability.

 

### Noise Injection

 

Injecting noise into images simulates real-world imperfections, teaching models to ignore irrelevant variations. Techniques involve:

 
- **Gaussian Noise**: Adding [Gaussian noise](./Gaussian_noise) mimics sensor noise or graininess.
- **Salt and Pepper Noise**: Introducing black or white [pixels](./Pixel) at random simulates sensor dust or [dead pixels](./Dead_pixels).

 

## Data augmentation for signal processing

 

[Residual or block bootstrap](./Bootstrapping_(statistics)) can be used for time series augmentation.

 

### Biological signals

 

Synthetic data augmentation is of paramount importance for machine learning classification, particularly for biological data, which tend to be high dimensional and scarce. The applications of robotic control and augmentation in disabled and able-bodied subjects still rely mainly on subject-specific analyses. Data scarcity is notable in signal processing problems such as for Parkinson's Disease [Electromyography](./Electromyography) signals, which are difficult to source - Zanini, et al. noted that it is possible to use a [generative adversarial network](./Generative_adversarial_network) (in particular, a DCGAN) to perform style transfer in order to generate synthetic electromyographic signals that corresponded to those exhibited by sufferers of Parkinson's Disease.[[12]](./Data_augmentation#cite_note-Anicet_ZaniniLuna_Colombini2020-12)

 

The approaches are also important in [electroencephalography](./Electroencephalography) (brainwaves). Wang, et al. explored the idea of using deep [convolutional neural networks](./Convolutional_neural_network) for EEG-Based Emotion Recognition, results show that emotion recognition was improved when data augmentation was used.[[13]](./Data_augmentation#cite_note-WangZhong2018-13)

 

A common approach is to generate synthetic signals by re-arranging components of real data. Lotte[[14]](./Data_augmentation#cite_note-Lotte2015-14) proposed a method of *"Artificial Trial Generation Based on Analogy"* where three data examples      x  1   ,  x  2   ,  x  3     {\displaystyle x_{1},x_{2},x_{3}}  ![{\displaystyle x_{1},x_{2},x_{3}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/9d4102ba3aa87d8bd353467896b23eae57f4fb06) provide examples and an artificial      x  s y n t h e t i c     {\displaystyle x_{synthetic}}  ![{\displaystyle x_{synthetic}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d09413cd12bcca0213a2e3a82cefcbadbe235c8d) is formed which is to      x  3     {\displaystyle x_{3}}  ![{\displaystyle x_{3}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/766d09a498699be10e276ad49145c921f8cbe335) what      x  2     {\displaystyle x_{2}}  ![{\displaystyle x_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7af1b928f06e4c7e3e8ebfd60704656719bd766) is to      x  1     {\displaystyle x_{1}}  ![{\displaystyle x_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8788bf85d532fa88d1fb25eff6ae382a601c308). A transformation is applied to      x  1     {\displaystyle x_{1}}  ![{\displaystyle x_{1}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a8788bf85d532fa88d1fb25eff6ae382a601c308) to make it more similar to      x  2     {\displaystyle x_{2}}  ![{\displaystyle x_{2}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d7af1b928f06e4c7e3e8ebfd60704656719bd766), the same transformation is then applied to      x  3     {\displaystyle x_{3}}  ![{\displaystyle x_{3}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/766d09a498699be10e276ad49145c921f8cbe335) which generates      x  s y n t h e t i c     {\displaystyle x_{synthetic}}  ![{\displaystyle x_{synthetic}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d09413cd12bcca0213a2e3a82cefcbadbe235c8d). This approach was shown to improve performance of a Linear Discriminant Analysis classifier on three different datasets.

 

Current research shows great impact can be derived from relatively simple techniques. For example, Freer[[15]](./Data_augmentation#cite_note-FreerYang2020-15) observed that introducing noise into gathered data to form additional data points improved the learning ability of several models which otherwise performed relatively poorly. Tsinganos et al.[[16]](./Data_augmentation#cite_note-TsinganosCornelis2020-16) studied the approaches of magnitude warping, wavelet decomposition, and synthetic surface EMG models (generative approaches) for hand gesture recognition, finding classification performance increases of up to +16% when augmented data was introduced during training. More recently, data augmentation studies have begun to focus on the field of deep learning, more specifically on the ability of generative models to create artificial data which is then introduced during the classification model training process. In 2018, Luo et al.[[17]](./Data_augmentation#cite_note-LuoLu2018-17) observed that useful EEG signal data could be generated by Conditional Wasserstein Generative Adversarial Networks (GANs) which was then introduced to the training set in a classical train-test learning framework. The authors found classification performance was improved when such techniques were introduced.

 

### Mechanical  signals

 

The prediction of mechanical signals based on data augmentation brings a new generation of [technological](./Technology) innovations, such as new energy dispatch, 5G communication field, and robotics control engineering.[[18]](./Data_augmentation#cite_note-YangYang2022-18) In 2022, Yang et al.[[18]](./Data_augmentation#cite_note-YangYang2022-18) integrate constraints, optimization and control into a deep network framework based on data augmentation and data pruning with spatio-temporal data correlation, and improve the interpretability, safety and controllability of deep learning in real industrial projects through explicit mathematical programming equations and analytical solutions.

 

## See also

 
- [Oversampling and undersampling in data analysis](./Oversampling_and_undersampling_in_data_analysis)
- [Surrogate data](./Surrogate_data)
- [Generative adversarial network](./Generative_adversarial_network)
- [Variational autoencoder](./Variational_autoencoder)
- [Data pre-processing](./Data_pre-processing)
- [Convolutional neural network](./Convolutional_neural_network)
- [Regularization (mathematics)](./Regularization_(mathematics))
- [Data preparation](./Data_preparation)
- [Data fusion](./Data_fusion)

 

## References

  
1. [↑](./Data_augmentation#cite_ref-1) Dempster, A.P.; Laird, N.M.; Rubin, D.B. (1977). ["Maximum Likelihood from Incomplete Data Via the EM Algorithm"](https://rss.onlinelibrary.wiley.com/doi/abs/10.1111/j.2517-6161.1977.tb01600.x). *Journal of the Royal Statistical Society. Series B (Methodological)*. **39** (1): 1–22. [doi](./Doi_(identifier)):[10.1111/j.2517-6161.1977.tb01600.x](https://doi.org/10.1111%2Fj.2517-6161.1977.tb01600.x). [Archived](https://web.archive.org/web/20221010051829/https://rss.onlinelibrary.wiley.com/doi/abs/10.1111/j.2517-6161.1977.tb01600.x) from the original on 2022-10-10. Retrieved 2024-08-28.
2. [↑](./Data_augmentation#cite_ref-2) Rubin, Donald (1987). ["Comment: The Calculation of Posterior Distributions by Data Augmentation"](https://www.jstor.org/stable/2289460). *Journal of the American Statistical Association*. **82** (398). [doi](./Doi_(identifier)):[10.2307/2289460](https://doi.org/10.2307%2F2289460). [JSTOR](./JSTOR_(identifier)) [2289460](https://www.jstor.org/stable/2289460). [Archived](https://web.archive.org/web/20240807015222/https://www.jstor.org/stable/2289460) from the original on 2024-08-07. Retrieved 2024-08-28.
3. [↑](./Data_augmentation#cite_ref-3) Jackman, Simon (2009). [*Bayesian Analysis for the Social Sciences*](https://www.wiley.com/en-au/Bayesian+Analysis+for+the+Social+Sciences-p-9780470011546). John Wiley & Sons. p. 236. [ISBN](./ISBN_(identifier)) [978-0-470-01154-6](./Special:BookSources/978-0-470-01154-6).
4. [↑](./Data_augmentation#cite_ref-Big_Data_2019_6:60_4-0) Shorten, Connor; Khoshgoftaar, Taghi M. (2019). ["A survey on Image Data Augmentation for Deep Learning"](https://doi.org/10.1186%2Fs40537-019-0197-0). *Mathematics and Computers in Simulation*. **6** 60. springer. [doi](./Doi_(identifier)):[10.1186/s40537-019-0197-0](https://doi.org/10.1186%2Fs40537-019-0197-0).
5. [↑](./Data_augmentation#cite_ref-5) Wang, Shujuan; Dai, Yuntao; Shen, Jihong; Xuan, Jingxue (2021-12-15). ["Research on expansion and classification of imbalanced data based on SMOTE algorithm"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8674253). *Scientific Reports*. **11** (1): 24039. [Bibcode](./Bibcode_(identifier)):[2021NatSR..1124039W](https://ui.adsabs.harvard.edu/abs/2021NatSR..1124039W). [doi](./Doi_(identifier)):[10.1038/s41598-021-03430-5](https://doi.org/10.1038%2Fs41598-021-03430-5). [ISSN](./ISSN_(identifier)) [2045-2322](https://search.worldcat.org/issn/2045-2322). [PMC](./PMC_(identifier)) [8674253](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8674253). [PMID](./PMID_(identifier)) [34912009](https://pubmed.ncbi.nlm.nih.gov/34912009).
6. [↑](./Data_augmentation#cite_ref-6) Yann Lecun; et al. (1995). [*Learning algorithms for classification: A comparison on handwritten digit recognition*](https://nyuscholars.nyu.edu/en/publications/learning-algorithms-for-classification-a-comparison-on-handwritte) (Conference paper). World Scientific. pp. 261–276. Retrieved 14 May 2023. `{{cite book}}`: `|website=` ignored ([help](./Help:CS1_errors#periodical_ignored))
7. [1](./Data_augmentation#cite_ref-elastic_distortion_7-0) [2](./Data_augmentation#cite_ref-elastic_distortion_7-1) Simard, P.Y.; Steinkraus, D.; Platt, J.C. (2003). "Best practices for convolutional neural networks applied to visual document analysis". *Seventh International Conference on Document Analysis and Recognition, 2003. Proceedings*. Vol. 1. pp. 958–963. [doi](./Doi_(identifier)):[10.1109/ICDAR.2003.1227801](https://doi.org/10.1109%2FICDAR.2003.1227801). [ISBN](./ISBN_(identifier)) [0-7695-1960-1](./Special:BookSources/0-7695-1960-1). [S2CID](./S2CID_(identifier)) [4659176](https://api.semanticscholar.org/CorpusID:4659176).
8. [↑](./Data_augmentation#cite_ref-8) Hinton, Geoffrey E.; Srivastava, Nitish; Krizhevsky, Alex; Sutskever, Ilya; Salakhutdinov, Ruslan R. (2012). "Improving neural networks by preventing co-adaptation of feature detectors". [arXiv](./ArXiv_(identifier)):[1207.0580](https://arxiv.org/abs/1207.0580) [[cs.NE](https://arxiv.org/archive/cs.NE)].
9. [↑](./Data_augmentation#cite_ref-9) Cagli, Eleonora; Dumas, Cécile; Prouff, Emmanuel (2017). ["Convolutional Neural Networks with Data Augmentation Against Jitter-Based Countermeasures: Profiling Attacks Without Pre-processing"](https://zenodo.org/record/1404232). In Fischer, Wieland; Homma, Naofumi (eds.). *Cryptographic Hardware and Embedded Systems – CHES 2017*. Lecture Notes in Computer Science. Vol. 10529. Cham: Springer International Publishing. pp. 45–68. [doi](./Doi_(identifier)):[10.1007/978-3-319-66787-4_3](https://doi.org/10.1007%2F978-3-319-66787-4_3). [ISBN](./ISBN_(identifier)) [978-3-319-66787-4](./Special:BookSources/978-3-319-66787-4). [S2CID](./S2CID_(identifier)) [54088207](https://api.semanticscholar.org/CorpusID:54088207).
10. [↑](./Data_augmentation#cite_ref-10) Shorten, Connor; Khoshgoftaar, Taghi M. (2019-07-06). ["A survey on Image Data Augmentation for Deep Learning"](https://doi.org/10.1186%2Fs40537-019-0197-0). *[Journal of Big Data](./Journal_of_Big_Data)*. **6** (1): 60. [doi](./Doi_(identifier)):[10.1186/s40537-019-0197-0](https://doi.org/10.1186%2Fs40537-019-0197-0). [ISSN](./ISSN_(identifier)) [2196-1115](https://search.worldcat.org/issn/2196-1115).
11. [↑](./Data_augmentation#cite_ref-11) Ghorbel, Emna; Ghorbel, Faouzi (2024-06-01). ["Data augmentation based on shape space exploration for low-size datasets: application to 2D shape classification"](https://doi.org/10.1007/s00521-024-09798-5). *Neural Computing and Applications*. **36** (17): 10031–10054. [doi](./Doi_(identifier)):[10.1007/s00521-024-09798-5](https://doi.org/10.1007%2Fs00521-024-09798-5). [ISSN](./ISSN_(identifier)) [1433-3058](https://search.worldcat.org/issn/1433-3058).
12. [↑](./Data_augmentation#cite_ref-Anicet_ZaniniLuna_Colombini2020_12-0) Anicet Zanini, Rafael; Luna Colombini, Esther (2020). ["Parkinson's Disease EMG Data Augmentation and Simulation with DCGANs and Style Transfer"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7248755). *Sensors*. **20** (9): 2605. [Bibcode](./Bibcode_(identifier)):[2020Senso..20.2605A](https://ui.adsabs.harvard.edu/abs/2020Senso..20.2605A). [doi](./Doi_(identifier)):[10.3390/s20092605](https://doi.org/10.3390%2Fs20092605). [ISSN](./ISSN_(identifier)) [1424-8220](https://search.worldcat.org/issn/1424-8220). [PMC](./PMC_(identifier)) [7248755](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7248755). [PMID](./PMID_(identifier)) [32375217](https://pubmed.ncbi.nlm.nih.gov/32375217).
13. [↑](./Data_augmentation#cite_ref-WangZhong2018_13-0) Wang, Fang; Zhong, Sheng-hua; Peng, Jianfeng; Jiang, Jianmin; Liu, Yan (2018). "Data Augmentation for EEG-Based Emotion Recognition with Deep Convolutional Neural Networks". *MultiMedia Modeling*. Lecture Notes in Computer Science. Vol. 10705. pp. 82–93. [doi](./Doi_(identifier)):[10.1007/978-3-319-73600-6_8](https://doi.org/10.1007%2F978-3-319-73600-6_8). [ISBN](./ISBN_(identifier)) [978-3-319-73599-3](./Special:BookSources/978-3-319-73599-3). [ISSN](./ISSN_(identifier)) [0302-9743](https://search.worldcat.org/issn/0302-9743).
14. [↑](./Data_augmentation#cite_ref-Lotte2015_14-0) Lotte, Fabien (2015). ["Signal Processing Approaches to Minimize or Suppress Calibration Time in Oscillatory Activity-Based Brain–Computer Interfaces"](https://hal.inria.fr/hal-01159171/file/lotte_sigProcCalibReduction-final.pdf) (PDF). *Proceedings of the IEEE*. **103** (6): 871–890. [doi](./Doi_(identifier)):[10.1109/JPROC.2015.2404941](https://doi.org/10.1109%2FJPROC.2015.2404941). [ISSN](./ISSN_(identifier)) [0018-9219](https://search.worldcat.org/issn/0018-9219). [S2CID](./S2CID_(identifier)) [22472204](https://api.semanticscholar.org/CorpusID:22472204). [Archived](https://web.archive.org/web/20230403215441/https://hal.inria.fr/hal-01159171/file/lotte_sigProcCalibReduction-final.pdf) (PDF) from the original on 2023-04-03. Retrieved 2022-11-05.
15. [↑](./Data_augmentation#cite_ref-FreerYang2020_15-0) Freer, Daniel; Yang, Guang-Zhong (2020). "Data augmentation for self-paced motor imagery classification with C-LSTM". *[Journal of Neural Engineering](./Journal_of_Neural_Engineering)*. **17** (1): 016041. [Bibcode](./Bibcode_(identifier)):[2020JNEng..17a6041F](https://ui.adsabs.harvard.edu/abs/2020JNEng..17a6041F). [doi](./Doi_(identifier)):[10.1088/1741-2552/ab57c0](https://doi.org/10.1088%2F1741-2552%2Fab57c0). [hdl](./Hdl_(identifier)):[10044/1/75376](https://hdl.handle.net/10044%2F1%2F75376). [ISSN](./ISSN_(identifier)) [1741-2552](https://search.worldcat.org/issn/1741-2552). [PMID](./PMID_(identifier)) [31726440](https://pubmed.ncbi.nlm.nih.gov/31726440). [S2CID](./S2CID_(identifier)) [208034533](https://api.semanticscholar.org/CorpusID:208034533).
16. [↑](./Data_augmentation#cite_ref-TsinganosCornelis2020_16-0) Tsinganos, Panagiotis; Cornelis, Bruno; Cornelis, Jan; Jansen, Bart; Skodras, Athanassios (2020). ["Data Augmentation of Surface Electromyography for Hand Gesture Recognition"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7506981). *Sensors*. **20** (17): 4892. [Bibcode](./Bibcode_(identifier)):[2020Senso..20.4892T](https://ui.adsabs.harvard.edu/abs/2020Senso..20.4892T). [doi](./Doi_(identifier)):[10.3390/s20174892](https://doi.org/10.3390%2Fs20174892). [ISSN](./ISSN_(identifier)) [1424-8220](https://search.worldcat.org/issn/1424-8220). [PMC](./PMC_(identifier)) [7506981](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7506981). [PMID](./PMID_(identifier)) [32872508](https://pubmed.ncbi.nlm.nih.gov/32872508).
17. [↑](./Data_augmentation#cite_ref-LuoLu2018_17-0) Luo, Yun; Lu, Bao-Liang (2018). "EEG Data Augmentation for Emotion Recognition Using a Conditional Wasserstein GAN". *2018 40th Annual International Conference of the IEEE Engineering in Medicine and Biology Society (EMBC)*. Vol. 2018. pp. 2535–2538. [doi](./Doi_(identifier)):[10.1109/EMBC.2018.8512865](https://doi.org/10.1109%2FEMBC.2018.8512865). [ISBN](./ISBN_(identifier)) [978-1-5386-3646-6](./Special:BookSources/978-1-5386-3646-6). [PMID](./PMID_(identifier)) [30440924](https://pubmed.ncbi.nlm.nih.gov/30440924). [S2CID](./S2CID_(identifier)) [53105445](https://api.semanticscholar.org/CorpusID:53105445).
18. [1](./Data_augmentation#cite_ref-YangYang2022_18-0) [2](./Data_augmentation#cite_ref-YangYang2022_18-1) Yang, Yang (2022). "Wind speed forecasting with correlation network pruning and augmentation: A two-phase deep learning method". *Renewable Energy*. **198** (1): 267–282. [arXiv](./ArXiv_(identifier)):[2306.01986](https://arxiv.org/abs/2306.01986). [Bibcode](./Bibcode_(identifier)):[2022REne..198..267Y](https://ui.adsabs.harvard.edu/abs/2022REne..198..267Y). [doi](./Doi_(identifier)):[10.1016/j.renene.2022.07.125](https://doi.org/10.1016%2Fj.renene.2022.07.125). [ISSN](./ISSN_(identifier)) [0960-1481](https://search.worldcat.org/issn/0960-1481). [S2CID](./S2CID_(identifier)) [251511199](https://api.semanticscholar.org/CorpusID:251511199).

 
| vteData |
| --- |
| Information, data, and value | InformationMetaTypeStructureEcosystemLibraryInfrastructureValue |
| Data categories and semantic structure | Data categoriesMaster dataMaster data managementReference dataTransaction dataAnalytical dataMetadataCode tablesControlled vocabularyCrosswalksHierarchiesObservation dataDark dataTrade and market data |
| Data management and governance | ManagementGovernanceCooperativesEthicsStewardshipLineageCurationLocalizationPreservationRetentionPublishingOpen dataMaster data managementReference data |
| Data quality, trust, and protection | QualityInformation qualityValidationCleansingScrubbingIntegrityProtection (privacy)SecurityAnonymizationDe-identificationRe-identificationMinimizationErasureRemanenceCorruptionDegradationLossRecovery |
| Quality dimensions | AccuracyCompletenessConsistencyTimelinessValidityUniquenessIntegrityConformityRelevance |
| Data engineering and movement | EngineeringIntegrationStorageETL/ELTExtractTransformLoadMigrationSynchronizationCompressionFusionFormat management |
| Data preparation and operations | AcquisitionAugmentationCollectionAnnotationEditingDeduplicationPre-processingPreparationProcessingReductionRedundancyWrangling/mungingScrapingRescue |
| Analysis, science, and interpretation | BigAnalysisExplorationMiningScienceTopological data analysisWarehouseBusiness intelligence |
| Data economy and exchange | Data economySharingOpen dataPhilanthropyData as a serviceData brokerResponsible reuse |
| Exchange, use, and public context | ExhaustFarmingArchaeology |
| Distributed data, domains, and digital twins | Data meshData productData domainsData categoriesData digital twinsDigital threadOperational twinsAnalytical twins |
| Vendors and actors | Data vendorsData technology vendorsData service providersData brokersChief data officersInformation professionalsCollibraInformaticaIBMSAPOracleSASQlikExperianAlationAtaccamaPrecisely |
| Category |

 
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