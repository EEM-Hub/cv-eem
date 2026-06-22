---
source: https://en.wikipedia.org/wiki/U-Net
fetched: 2026-06-21
---

Type of convolutional neural network 
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

 

**U-Net** is a [convolutional neural network](./Convolutional_neural_network) that was developed for [image segmentation](./Image_segmentation).[[1]](./U-Net#cite_note-Ronneberger_2015-1) The network is based on a fully [convolutional neural network](./Convolutional_neural_network)[[2]](./U-Net#cite_note-Shelhamer_2017-2) whose architecture was modified and extended to work with fewer training images and to yield more precise [segmentation](./Image_segmentation). Segmentation of a 512 × 512 image takes less than a second on a modern (2015) [GPU](./Graphics_processing_unit) using the U-Net architecture.[[1]](./U-Net#cite_note-Ronneberger_2015-1)[[3]](./U-Net#cite_note-3)[[4]](./U-Net#cite_note-4)[[5]](./U-Net#cite_note-5)

 

The U-Net architecture has also been employed in [diffusion models](./Diffusion_models) for iterative image denoising.[[6]](./U-Net#cite_note-6) This technology underlies many modern image generation models, such as [DALL-E](./DALL-E), [Midjourney](./Midjourney), and [Stable Diffusion](./Stable_Diffusion).

 

U-Net is also being explored for [language models](./Language_models).[[7]](./U-Net#cite_note-7) [Tokenization](./Large_language_model#Tokenization) is not a separate step, allowing the model to more easily understand spelling and concurrently [vectorizing](./Vectorization)[*[disambiguation needed](./Wikipedia:WikiProject_Disambiguation/Fixing_links)*] / tokenizing higher level concepts.

 

## Description

 

The U-Net architecture stems from the so-called "fully convolutional network".[[2]](./U-Net#cite_note-Shelhamer_2017-2)

 

The main idea is to supplement a usual contracting network by successive layers, where [pooling](./Pooling_layer) operations are replaced by [upsampling](./Upsampling) operators. Hence these layers increase the resolution of the output. A successive convolutional layer can then learn to assemble a precise output based on this information.[[1]](./U-Net#cite_note-Ronneberger_2015-1)

 

One important modification in U-Net is that there are a large number of feature channels in the upsampling part, which allow the network to propagate context information to higher resolution layers. As a consequence, the expansive path is more or less symmetric to the contracting part, and yields a u-shaped architecture. The network only uses the valid part of each [convolution](./Convolution) without any fully connected layers.[[2]](./U-Net#cite_note-Shelhamer_2017-2) To predict the pixels in the border region of the image, the missing context is extrapolated by mirroring the input image. This tiling strategy is important to apply the network to large images, since otherwise the resolution would be limited by the [GPU](./Graphics_processing_unit) memory. Recently, there had also been an interest in receptive field based U-Net models for medical image segmentation.[[8]](./U-Net#cite_note-8)

 

## Network architecture

 

The network consists of a contracting path and an expansive path, which gives it the u-shaped architecture. The contracting path is a typical convolutional network that consists of repeated application of [convolutions](./Convolutions), each followed by a [rectified linear unit](./Rectified_linear_unit) (ReLU) and a [max pooling](./Max_pooling) operation. During the contraction, the spatial information is reduced while feature information is increased. The expansive pathway combines the feature and spatial information through a sequence of up-convolutions and concatenations with high-resolution features from the contracting path.[[9]](./U-Net#cite_note-9)

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/2b/Example_architecture_of_U-Net_for_producing_k_256-by-256_image_masks_for_a_256-by-256_RGB_image.png/250px-Example_architecture_of_U-Net_for_producing_k_256-by-256_image_masks_for_a_256-by-256_RGB_image.png)](./File:Example_architecture_of_U-Net_for_producing_k_256-by-256_image_masks_for_a_256-by-256_RGB_image.png)This is an example architecture of U-Net for producing k 256-by-256 image masks for a 256-by-256 RGB image. 

## Applications

 

There are many applications of U-Net in biomedical [image segmentation](./Image_segmentation), such as brain image segmentation (''BRATS''[[10]](./U-Net#cite_note-10)) and liver image segmentation ("siliver07"[[11]](./U-Net#cite_note-11)) as well as protein binding site prediction.[[12]](./U-Net#cite_note-Nazem_2021-12) U-Net implementations have also found use in the physical sciences, for example in the analysis of micrographs of materials.[[13]](./U-Net#cite_note-13)[[14]](./U-Net#cite_note-14)[[15]](./U-Net#cite_note-15) Variations of the U-Net have also been applied for medical image reconstruction.[[16]](./U-Net#cite_note-16) Here are some variants and applications of U-Net as follows:

 
1. Pixel-wise regression using U-Net and its application on pansharpening;[[17]](./U-Net#cite_note-ref1-17)
2. 3D U-Net: Learning Dense Volumetric Segmentation from Sparse Annotation;[[18]](./U-Net#cite_note-Çiçek_2016-18)
3. TernausNet: U-Net with VGG11 Encoder Pre-Trained on ImageNet for Image Segmentation.[[19]](./U-Net#cite_note-Iglovikov_2018-19)
4. Image-to-image translation to estimate fluorescent stains [[20]](./U-Net#cite_note-20)
5. In binding site prediction of protein structure.[[12]](./U-Net#cite_note-Nazem_2021-12)

 

## History

 

U-Net was created by Olaf Ronneberger, Philipp Fischer, Thomas Brox in 2015 and reported in the paper "U-Net: Convolutional Networks for Biomedical Image Segmentation".[[1]](./U-Net#cite_note-Ronneberger_2015-1) It is an improvement and development of FCN: Evan Shelhamer, Jonathan Long, Trevor Darrell (2014). "Fully convolutional networks for semantic segmentation".[[2]](./U-Net#cite_note-Shelhamer_2017-2)

 

## References

  
1. [1](./U-Net#cite_ref-Ronneberger_2015_1-0) [2](./U-Net#cite_ref-Ronneberger_2015_1-1) [3](./U-Net#cite_ref-Ronneberger_2015_1-2) [4](./U-Net#cite_ref-Ronneberger_2015_1-3) Ronneberger O, Fischer P, Brox T (2015). "U-Net: Convolutional Networks for Biomedical Image Segmentation". [arXiv](./ArXiv_(identifier)):[1505.04597](https://arxiv.org/abs/1505.04597) [[cs.CV](https://arxiv.org/archive/cs.CV)].
2. [1](./U-Net#cite_ref-Shelhamer_2017_2-0) [2](./U-Net#cite_ref-Shelhamer_2017_2-1) [3](./U-Net#cite_ref-Shelhamer_2017_2-2) [4](./U-Net#cite_ref-Shelhamer_2017_2-3) Shelhamer E, Long J, Darrell T (Nov 2014). "Fully Convolutional Networks for Semantic Segmentation". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **39** (4): 640–651. [arXiv](./ArXiv_(identifier)):[1411.4038](https://arxiv.org/abs/1411.4038). [doi](./Doi_(identifier)):[10.1109/TPAMI.2016.2572683](https://doi.org/10.1109%2FTPAMI.2016.2572683). [PMID](./PMID_(identifier)) [27244717](https://pubmed.ncbi.nlm.nih.gov/27244717). [S2CID](./S2CID_(identifier)) [1629541](https://api.semanticscholar.org/CorpusID:1629541).
3. [↑](./U-Net#cite_ref-3) Nazem, Fatemeh; Ghasemi, Fahimeh; Fassihi, Afshin; Mehri Dehnavi, Alireza (2021). "3D U-Net: A Voxel-based method in binding site prediction of protein structure". *Journal of Bioinformatics and Computational Biology*. **19** (2). [doi](./Doi_(identifier)):[10.1142/S0219720021500062](https://doi.org/10.1142%2FS0219720021500062). [PMID](./PMID_(identifier)) [33866960](https://pubmed.ncbi.nlm.nih.gov/33866960).
4. [↑](./U-Net#cite_ref-4) Nazem, Fatemeh; Ghasemi, Fahimeh; Fassihi, Afshin; Mehri Dehnavi, Alireza (2023). ["A GU-Net-Based Architecture Predicting Ligand–Protein-Binding Atoms"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10246592). *Journal of Medical Signals & Sensors*. **13** (1): 1–10. [doi](./Doi_(identifier)):[10.4103/jmss.jmss_142_21](https://doi.org/10.4103%2Fjmss.jmss_142_21). [PMC](./PMC_(identifier)) [10246592](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10246592). [PMID](./PMID_(identifier)) [37292445](https://pubmed.ncbi.nlm.nih.gov/37292445).
5. [↑](./U-Net#cite_ref-5) Nazem, Fatemeh; Ghasemi, Fahimeh; Fassihi, Afshin; Mehri Dehnavi, Alireza (2024). "Deep attention network for identifying ligand-protein binding sites". *Journal of Computational Science*. **81** 102368. [doi](./Doi_(identifier)):[10.1016/j.jocs.2024.102368](https://doi.org/10.1016%2Fj.jocs.2024.102368).
6. [↑](./U-Net#cite_ref-6) Ho, Jonathan (2020). "Denoising Diffusion Probabilistic Models". [arXiv](./ArXiv_(identifier)):[2006.11239](https://arxiv.org/abs/2006.11239) [[cs.LG](https://arxiv.org/archive/cs.LG)].
7. [↑](./U-Net#cite_ref-7) Videau, Mathurin; Badr Youbi Idrissi; Leite, Alessandro; Schoenauer, Marc; Teytaud, Olivier; Lopez-Paz, David (2025). "From Bytes to Ideas: Language Modeling with Autoregressive U-Nets". [arXiv](./ArXiv_(identifier)):[2506.14761](https://arxiv.org/abs/2506.14761) [[cs.CL](https://arxiv.org/archive/cs.CL)].
8. [↑](./U-Net#cite_ref-8) Loos, Vincent; Pardasani, Rohit; Awasthi, Navchetan (2024-10-29). ["Demystifying the effect of receptive field size in U-Net models for medical image segmentation"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11520766). *Journal of Medical Imaging*. **11** (5). [doi](./Doi_(identifier)):[10.1117/1.jmi.11.5.054004](https://doi.org/10.1117%2F1.jmi.11.5.054004). [ISSN](./ISSN_(identifier)) [2329-4302](https://search.worldcat.org/issn/2329-4302). [PMC](./PMC_(identifier)) [11520766](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11520766). [PMID](./PMID_(identifier)) [39478790](https://pubmed.ncbi.nlm.nih.gov/39478790).
9. [↑](./U-Net#cite_ref-9) ["U-Net code"](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/).
10. [↑](./U-Net#cite_ref-10) ["MICCAI BraTS 2017: Scope | Section for Biomedical Image Analysis (SBIA) | Perelman School of Medicine at the University of Pennsylvania"](https://www.med.upenn.edu/sbia/brats2017.html). *www.med.upenn.edu*. Retrieved 2018-12-24.
11. [↑](./U-Net#cite_ref-11) ["SLIVER07 : Home"](http://www.sliver07.org/). *www.sliver07.org*. Retrieved 2018-12-24.
12. [1](./U-Net#cite_ref-Nazem_2021_12-0) [2](./U-Net#cite_ref-Nazem_2021_12-1) Nazem F, Ghasemi F, Fassihi A, Dehnavi AM (April 2021). "3D U-Net: A voxel-based method in binding site prediction of protein structure". *Journal of Bioinformatics and Computational Biology*. **19** (2): 2150006. [doi](./Doi_(identifier)):[10.1142/S0219720021500062](https://doi.org/10.1142%2FS0219720021500062). [PMID](./PMID_(identifier)) [33866960](https://pubmed.ncbi.nlm.nih.gov/33866960). [S2CID](./S2CID_(identifier)) [233300145](https://api.semanticscholar.org/CorpusID:233300145).
13. [↑](./U-Net#cite_ref-13) Chen, Fu-Xiang Rikudo; Lin, Chia-Yu; Siao, Hui-Ying; Jian, Cheng-Yuan; Yang, Yong-Cheng; Lin, Chun-Liang (2023-02-14). ["Deep learning based atomic defect detection framework for two-dimensional materials"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9929095). *Scientific Data*. **10** (1): 91. [Bibcode](./Bibcode_(identifier)):[2023NatSD..10...91C](https://ui.adsabs.harvard.edu/abs/2023NatSD..10...91C). [doi](./Doi_(identifier)):[10.1038/s41597-023-02004-6](https://doi.org/10.1038%2Fs41597-023-02004-6). [ISSN](./ISSN_(identifier)) [2052-4463](https://search.worldcat.org/issn/2052-4463). [PMC](./PMC_(identifier)) [9929095](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9929095). [PMID](./PMID_(identifier)) [36788235](https://pubmed.ncbi.nlm.nih.gov/36788235).
14. [↑](./U-Net#cite_ref-14) Shi, Peng; Duan, Mengmeng; Yang, Lifang; Feng, Wei; Ding, Lianhong; Jiang, Liwu (2022-06-22). ["An Improved U-Net Image Segmentation Method and Its Application for Metallic Grain Size Statistics"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9267311). *Materials*. **15** (13): 4417. [Bibcode](./Bibcode_(identifier)):[2022Mate...15.4417S](https://ui.adsabs.harvard.edu/abs/2022Mate...15.4417S). [doi](./Doi_(identifier)):[10.3390/ma15134417](https://doi.org/10.3390%2Fma15134417). [ISSN](./ISSN_(identifier)) [1996-1944](https://search.worldcat.org/issn/1996-1944). [PMC](./PMC_(identifier)) [9267311](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9267311). [PMID](./PMID_(identifier)) [35806543](https://pubmed.ncbi.nlm.nih.gov/35806543).
15. [↑](./U-Net#cite_ref-15) Patrick, Matthew J; Eckstein, James K; Lopez, Javier R; Toderas, Silvia; Asher, Sarah A; Whang, Sylvia I; Levine, Stacey; Rickman, Jeffrey M; Barmak, Katayun (2023-11-15). ["Automated Grain Boundary Detection for Bright-Field Transmission Electron Microscopy Images via U-Net"](https://academic.oup.com/mam/advance-article/doi/10.1093/micmic/ozad115/7422794). *Microscopy and Microanalysis*. **29** (6): 1968–1979. [arXiv](./ArXiv_(identifier)):[2312.09392](https://arxiv.org/abs/2312.09392). [doi](./Doi_(identifier)):[10.1093/micmic/ozad115](https://doi.org/10.1093%2Fmicmic%2Fozad115). [ISSN](./ISSN_(identifier)) [1431-9276](https://search.worldcat.org/issn/1431-9276). [PMID](./PMID_(identifier)) [37966960](https://pubmed.ncbi.nlm.nih.gov/37966960).
16. [↑](./U-Net#cite_ref-16) Andersson J, Ahlström H, Kullberg J (September 2019). ["Separation of water and fat signal in whole-body gradient echo scans using convolutional neural networks"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6618066). *Magnetic Resonance in Medicine*. **82** (3): 1177–1186. [doi](./Doi_(identifier)):[10.1002/mrm.27786](https://doi.org/10.1002%2Fmrm.27786). [PMC](./PMC_(identifier)) [6618066](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6618066). [PMID](./PMID_(identifier)) [31033022](https://pubmed.ncbi.nlm.nih.gov/31033022).
17. [↑](./U-Net#cite_ref-ref1_17-0) Yao W, Zeng Z, Lian C, Tang H (2018-10-27). "Pixel-wise regression using U-Net and its application on pansharpening". *Neurocomputing*. **312**: 364–371. [doi](./Doi_(identifier)):[10.1016/j.neucom.2018.05.103](https://doi.org/10.1016%2Fj.neucom.2018.05.103). [ISSN](./ISSN_(identifier)) [0925-2312](https://search.worldcat.org/issn/0925-2312). [S2CID](./S2CID_(identifier)) [207119255](https://api.semanticscholar.org/CorpusID:207119255).
18. [↑](./U-Net#cite_ref-Çiçek_2016_18-0) Çiçek Ö, Abdulkadir A, Lienkamp SS, Brox T, Ronneberger O (2016). "3D U-Net: Learning Dense Volumetric Segmentation from Sparse Annotation". [arXiv](./ArXiv_(identifier)):[1606.06650](https://arxiv.org/abs/1606.06650) [[cs.CV](https://arxiv.org/archive/cs.CV)].
19. [↑](./U-Net#cite_ref-Iglovikov_2018_19-0) Iglovikov V, Shvets A (2018). "TernausNet: U-Net with VGG11 Encoder Pre-Trained on ImageNet for Image Segmentation". [arXiv](./ArXiv_(identifier)):[1801.05746](https://arxiv.org/abs/1801.05746) [[cs.CV](https://arxiv.org/archive/cs.CV)].
20. [↑](./U-Net#cite_ref-20) Kandel ME, He YR, Lee YJ, Chen TH, Sullivan KM, Aydin O, et al. (December 2020). ["Phase imaging with computational specificity (PICS) for measuring dry mass changes in sub-cellular compartments"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7721808). *Nature Communications*. **11** (1) 6256. [arXiv](./ArXiv_(identifier)):[2002.08361](https://arxiv.org/abs/2002.08361). [Bibcode](./Bibcode_(identifier)):[2020NatCo..11.6256K](https://ui.adsabs.harvard.edu/abs/2020NatCo..11.6256K). [doi](./Doi_(identifier)):[10.1038/s41467-020-20062-x](https://doi.org/10.1038%2Fs41467-020-20062-x). [PMC](./PMC_(identifier)) [7721808](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7721808). [PMID](./PMID_(identifier)) [33288761](https://pubmed.ncbi.nlm.nih.gov/33288761).

 

## Implementations

 
- [Tensorflow Unet](https://github.com/jakeret/tf_unet) by J Akeret (2017)
- [U-Net source code](https://lmb.informatik.uni-freiburg.de/people/ronneber/u-net/) from Pattern Recognition and Image Processing at Computer Science Department of the University of Freiburg, Germany.