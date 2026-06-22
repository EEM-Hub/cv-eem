---
source: sources/wiki-Feature_detection_computer_vision.md
source_url: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
chunk: 1/2
---

Piece of information about the content of an image See also: [Feature (machine learning)](./Feature_(machine_learning)) 

 
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

 
| Feature detection |
| --- |
| Edge detection |
| CannyDericheDifferentialSobelPrewittRobinsonRoberts cross |
| Corner detection |
| Harris operatorShi and TomasiLevel curve curvatureHessian feature strength measuresSUSANFAST |
| Blob detection |
| Laplacian of Gaussian (LoG)Difference of Gaussians (DoG)Determinant of Hessian  (DoH)Maximally stable extremal regionsPCBR |
| Ridge detection |
| Hough transform |
| Hough transformGeneralized Hough transform |
| Structure tensor |
| Structure tensorGeneralized structure tensor |
| Affine invariant feature detection |
| Affine shape adaptationHarris affineHessian affine |
| Feature description |
| SIFTSURFGLOHHOG |
| Scale space |
| Scale-space axiomsImplementation detailsPyramids |
| vte |

 

In [computer vision](./Computer_vision) and [image processing](./Image_processing), a **feature** is a piece of information about the content of an image; typically about whether a certain region of the image has certain properties. Features may be specific structures in the image such as points, edges or objects. Features may also be the result of a general [neighborhood operation](./Neighborhood_operation) or **feature detection** applied to the image. Other examples of features are related to motion in image sequences, or to shapes defined in terms of curves or boundaries between different image regions.

 

More broadly a *feature* is any piece of information that is relevant for solving the computational task related to a certain application. This is the same sense as [feature](./Feature_(machine_learning)) in [machine learning](./Machine_learning) and [pattern recognition](./Pattern_recognition) generally, though image processing has a very sophisticated collection of features. The feature concept is very general and the choice of features in a particular computer vision system may be highly dependent on the specific problem at hand.

 

## Definition

 

There is no universal or exact definition of what constitutes a feature, and the exact definition often depends on the problem or the type of application. Nevertheless, a feature is typically defined as an "interesting" part of an [image](./Digital_image), and features are used as a starting point for many computer vision algorithms. 

 

Since features are used as the starting point and main primitives for subsequent algorithms, the overall algorithm will often only be as good as its feature detector. Consequently, the desirable property for a feature detector is *[repeatability](./Repeatability)*: whether or not the same feature will be detected in two or more different images of the same scene.

 

Feature detection is a low-level [image processing](./Image_processing) operation. That is, it is usually performed as the first operation on an image and examines every [pixel](./Pixel) to see if there is a feature present at that pixel. If this is part of a larger algorithm, then the algorithm will typically only examine the image in the region of the features. As a built-in pre-requisite to feature detection, the input image is usually smoothed by a [Gaussian](./Gaussian_blur) kernel in a [scale-space representation](./Scale_space) and one or several feature images are computed, often expressed in terms of local [image derivative](./Image_derivative) operations.

 

Occasionally, when feature detection is [computationally expensive](./Computationally_expensive) and there are time constraints, a higher-level algorithm may be used to guide the feature detection stage so that only certain parts of the image are searched for features.

 

There are many computer vision algorithms that use feature detection as the initial step, so as a result, a very large number of feature detectors have been developed. These vary widely in the kinds of feature detected, the computational complexity and the repeatability.

 

When features are defined in terms of local neighborhood operations applied to an image, a procedure commonly referred to as **feature extraction**, one can distinguish between feature detection approaches that produce local decisions whether there is a feature of a given type at a given image point or not, and those who produce non-binary data as result.  The distinction becomes relevant when the resulting detected features are relatively sparse. Although local decisions are made, the output from a feature detection step does not need to be a binary image. The result is often represented in terms of sets of (connected or unconnected) coordinates of the image points where features have been detected, sometimes with subpixel accuracy.

 

When feature extraction is done without local decision making, the result is often referred to as a *feature image*.  Consequently, a feature image can be seen as an image in the sense that it is a function of the same spatial (or temporal) variables as the original image, but where the pixel values hold information about image features instead of intensity or color.  This means that a feature image can be processed in a similar way as an ordinary image generated by an image sensor. Feature images are also often computed as integrated step in algorithms for feature detection.

 

### Feature vectors and feature spaces

 

In some applications, it is not sufficient to extract only one type of feature to obtain the relevant information from the image data.  Instead, two or more different features are extracted, resulting in two or more feature descriptors at each image point.  A common practice is to organize the information provided by all these descriptors as the elements of one single vector, commonly referred to as a **feature vector**.  The set of all possible feature vectors constitutes a **feature space**.[[1]](./Feature_(computer_vision)#cite_note-Umbaugh2005-1)

 

A common example of feature vectors appears when each image point is to be classified as belonging to a specific class.  Assuming that each image point has a corresponding feature vector based on a suitable set of features, meaning that each class is well separated in the corresponding feature space, the classification of each image point can be done using standard [classification](./Statistical_classification) method.

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Simplified_neural_network_training_example.svg/250px-Simplified_neural_network_training_example.svg.png)](./File:Simplified_neural_network_training_example.svg)Simplified example of training a neural network in object detection: The network is trained by multiple images that are known to depict [starfish](./Starfish) and [sea urchins](./Sea_urchin), which are correlated with "nodes" that represent visual features. The starfish match with a ringed texture and a star outline, whereas most sea urchins match with a striped texture and oval shape. However, the instance of a ring textured sea urchin creates a weakly weighted association between them.[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Simplified_neural_network_example.svg/250px-Simplified_neural_network_example.svg.png)](./File:Simplified_neural_network_example.svg)Subsequent run of the network on an input image (left):[[2]](./Feature_(computer_vision)#cite_note-2) The network correctly detects the starfish. However, the weakly weighted association between ringed texture and sea urchin also confers a weak signal to the latter from one of two features. In addition, a shell that was not included in the training gives a weak signal for the oval shape, also resulting in a weak signal for the sea urchin output. These weak signals may result in a [false positive](./False_positive) result for sea urchin.
In reality, textures and outlines would not be represented by single nodes, but rather by associated weight patterns of multiple nodes. 

Another and related example occurs when [neural network](./Artificial_neural_network)-based processing is applied to images.  The input data fed to the neural network is often given in terms of a feature vector from each image point, where the vector is constructed from several different features extracted from the image data.  During a learning phase, the network can itself find which combinations of different features are useful for solving the problem at hand.

 

## Types

 

### Edges

 

Edges are points where there is a boundary (or an edge) between two image regions. In general, an edge can be of almost arbitrary shape, and may include junctions. In practice, edges are usually defined as sets of points in the image that have a strong [gradient](./Gradient) magnitude. Furthermore, some common algorithms will then chain high gradient points together to form a more complete description of an edge. These algorithms usually place some constraints on the properties of an edge, such as shape, smoothness, and gradient value.

 

Locally, edges have a one-dimensional structure.

 

### Corners/interest points

 

The terms corners and interest points are used somewhat interchangeably and refer to point-like features in an image, which have a local two-dimensional structure. The name "Corner" arose since early algorithms first performed [edge detection](./Edge_detection), and then analyzed the edges to find rapid changes in direction (corners). These algorithms were then developed so that explicit edge detection was no longer required, for instance by looking for high levels of [curvature](./Curvature) in the [image gradient](./Image_gradient). It was then noticed that the so-called corners were also being detected on parts of the image that were not corners in the traditional sense (for instance a small bright spot on a dark background may be detected). These points are frequently known as interest points, but the term "corner" is used by tradition[*[citation needed](./Wikipedia:Citation_needed)*].

 

### Blobs / regions of interest points

 

Blobs provide a complementary description of image structures in terms of regions, as opposed to corners that are more point-like. Nevertheless, blob descriptors may often contain a preferred point (a local maximum of an operator response or a center of gravity) which means that many blob detectors may also be regarded as interest point operators. Blob detectors can detect areas in an image that are too smooth to be detected by a corner detector.

 

Consider shrinking an image and then performing corner detection. The detector will respond to points that are sharp in the shrunk image, but may be smooth in the original image. It is at this point that the difference between a corner detector and a blob detector becomes somewhat vague. To a large extent, this distinction can be remedied by including an appropriate notion of scale. Nevertheless, due to their response properties to different types of image structures at different scales, the LoG and DoH  [blob detectors](./Blob_detection) are also mentioned in the article on [corner detection](./Corner_detection).

 

### Ridges

 

For elongated objects, the notion of *ridges* is a natural tool. A ridge descriptor computed from a grey-level image can be seen as a generalization of a [medial axis](./Medial_axis). From a practical viewpoint, a ridge can be thought of as a one-dimensional curve that represents an axis of symmetry, and in addition has an attribute of local ridge width associated with each ridge point. Unfortunately, however, it is algorithmically harder to extract ridge features from general classes of grey-level images than edge-, corner- or blob features. Nevertheless, ridge descriptors are frequently used for road extraction in aerial images and for extracting blood vessels in medical images—see [ridge detection](./Ridge_detection).

 

## Detection 

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Writing_Desk_with_Harris_Detector.png/250px-Writing_Desk_with_Harris_Detector.png)](./File:Writing_Desk_with_Harris_Detector.png) 

**Feature detection** includes methods for computing abstractions of image information and making local decisions at every image point whether there is an image feature of a given type at that point or not. The resulting features will be subsets of the image domain, often in the form of isolated points, continuous curves or connected regions.

 

The extraction of features are sometimes made over several scalings. One of these methods is the [scale-invariant feature transform](./Scale-invariant_feature_transform) (SIFT).

 
| Feature detector | Edge | Corner | Blob | Ridge |
| --- | --- | --- | --- | --- |
| Canny[3] | Yes | No | No | No |
|  |
| Sobel | Yes | No | No | No |
|  |
| Harris & Stephens / Plessey[4] | Yes | Yes | No | No |
| SUSAN[5] | Yes | Yes | No | No |
| Shi & Tomasi[6] | No | Yes | No | No |
| Level curve curvature[7] | No | Yes | No | No |
| FAST[8] | No | Yes | No | No |
| Laplacian of Gaussian[7] | No | Yes | Yes | No |
| Difference of Gaussians[9][10] | No | Yes | Yes | No |
| Determinant of Hessian[7] | No | Yes | Yes | No |
| Hessian strength feature measures[11][12] | No | Yes | Yes | No |
| MSER[13] | No | No | Yes | No |
| Principal curvature ridges[14][15][16] | No | No | No | Yes |
| Grey-level blobs[17] | No | No | Yes | No |

 

## Extraction

 For broader coverage of this topic, see [Feature extraction (machine learning)](./Feature_extraction_(machine_learning)). 

Once features have been detected, a local image patch around the feature can be extracted. This extraction may involve quite considerable amounts of image processing. The result is known as a feature descriptor or feature vector. Among the approaches that are used to feature description, one can mention [*N*-jets](./N-jet) and local histograms (see [scale-invariant feature transform](./Scale-invariant_feature_transform) for one example of a local histogram descriptor). In addition to such attribute information, the feature detection step by itself may also provide complementary attributes, such as the edge orientation and gradient magnitude in edge detection and the polarity and the strength of the blob in blob detection.

 

### Low-level

 
- [Edge detection](./Edge_detection)
- [Corner detection](./Corner_detection)
- [Blob detection](./Blob_detection)
- [Ridge detection](./Ridge_detection)
- [Scale-invariant feature transform](./Scale-invariant_feature_transform)

 

#### Curvature

 
- Edge direction, changing intensity, [autocorrelation](./Autocorrelation).

 

#### Image motion

 
- [Motion detection](./Motion_detection). Area based, differential approach. [Optical flow](./Optical_flow).

 

### Shape based

 
- [Thresholding](./Thresholding_(image_processing))
- [Blob extraction](./Blob_extraction)
- [Template matching](./Template_matching)
- [Hough transform](./Hough_transform) 
- Lines
- Circles/ellipses
- Arbitrary shapes (generalized Hough transform)
- Works with any parameterizable feature (class variables, cluster detection, etc..)

- [Generalised Hough transform](./Generalised_Hough_transform)

 

### Flexible methods

 
- Deformable, parameterized shapes
- Active contours (snakes)

 

## Representation

 Main article: [Visual descriptor](./Visual_descriptor) 

A specific image feature, defined in terms of a specific structure in the image data, can often be represented in different ways.  For example, an edge can be represented as a [Boolean variable](./Boolean_variable) in each image point that describes whether an edge is present at that point.  Alternatively, we can instead use a representation that provides a [certainty measure](./Measurement_uncertainty) instead of a Boolean statement of the edge's existence and combine this with information about the [orientation](./Orientation_(geometry)) of the edge.  Similarly, the color of a specific region can either be represented in terms of the average color (three scalars) or a [color histogram](./Color_histogram) (three functions).

 

When a computer vision system or computer vision algorithm is designed the choice of feature representation can be a critical issue.  In some cases, a higher level of detail in the description of a feature may be necessary for solving the problem, but this comes at the cost of having to deal with more data and more demanding processing.  Below, some of the factors which are relevant for choosing a suitable representation are discussed.  In this discussion, an instance of a feature representation is referred to as a *feature descriptor*, or simply *descriptor*.

 

### Certainty or confidence

 

Two examples of image features are local edge orientation and local velocity in an image sequence.  In the case of orientation, the value of this feature may be more or less undefined if more than one edge are present in the corresponding neighborhood.  Local velocity is undefined if the corresponding image region does not contain any spatial variation.  As a consequence of this observation, it may be relevant to use a feature representation that includes a measure of certainty or confidence related to the statement about the feature value.  Otherwise, it is a typical situation that the same descriptor is used to represent feature values of low certainty and feature values close to zero, with a resulting ambiguity in the interpretation of this descriptor.  Depending on the application, such an ambiguity may or may not be acceptable.

 

In particular, if a featured image will be used in subsequent processing, it may be a good idea to employ a feature representation that includes information about [certainty](./Certainty) or [confidence](./Confidence).  This enables a new feature descriptor to be computed from several descriptors, for example, computed at the same image point but at different scales, or from different but neighboring points, in terms of a weighted average where the weights are derived from the corresponding certainties.  In the simplest case, the corresponding computation can be implemented as a low-pass filtering of the featured image.  The resulting feature image will, in general, be more stable to noise.

 

### Averageability

 

In addition to having certainty measures included in the representation, the representation of the corresponding feature values may itself be suitable for an [averaging](./Averaging) operation or not. Most feature representations can be averaged in practice, but only in certain cases can the resulting descriptor be given a correct interpretation in terms of a feature value.  Such representations are referred to as *averageable*.

 

For example, if the orientation of an edge is represented in terms of an angle, this representation must have a discontinuity where the angle wraps from its maximal value to its minimal value.  Consequently, it can happen that two similar orientations are represented by angles that have a mean that does not lie close to either of the original angles and, hence, this representation is not averageable.  There are other representations of edge orientation, such as the [structure tensor](./Structure_tensor), which are averageable.

 

Another example relates to motion, where in some cases only the normal velocity relative to some edge can be extracted.  If two such features have been extracted and they can be assumed to refer to same true velocity, this velocity is not given as the average of the normal velocity vectors.  Hence, normal velocity vectors are not averageable.  Instead, there are other representations of motions, using matrices or tensors, that give the true velocity in terms of an average operation of the normal velocity descriptors.[*[citation needed](./Wikipedia:Citation_needed)*]

 

## Matching

 Main article: [Correspondence problem](./Correspondence_problem) 

Features detected in each image can be matched across multiple images to establish *corresponding features* such as *corresponding points*.

 

The algorithm is based on comparing and analyzing point correspondences between the reference image and the target image. If any part of the cluttered scene shares correspondences greater than the threshold, that part of the cluttered scene image is targeted and considered to include the reference object there.[[18]](./Feature_(computer_vision)#cite_note-18)

 

## See also

 
- [Computer vision](./Computer_vision)
- [Automatic image annotation](./Automatic_image_annotation)
- [Feature learning](./Feature_learning)
- [Feature selection](./Feature_selection)
- [Foreground detection](./Foreground_detection)
- [Vectorization (image tracing)](./Vectorization_(image_tracing))

 

## References

  
1. [↑](./Feature_(computer_vision)#cite_ref-Umbaugh2005_1-0) Scott E Umbaugh (27 January 2005). [*Computer Imaging: Digital Image Analysis and Processing*](https://books.google.com/books?id=JNhRSAMFn6YC&q=%22feature+space%22). CRC Press. [ISBN](./ISBN_(identifier)) [978-0-8493-2919-7](./Special:BookSources/978-0-8493-2919-7).
2. [↑](./Feature_(computer_vision)#cite_ref-2) Ferrie, C., & Kaiser, S. (2019). *Neural Networks for Babies*. Sourcebooks. [ISBN](./ISBN_(identifier)) [1492671207](./Special:BookSources/1492671207).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
3. [↑](./Feature_(computer_vision)#cite_ref-Can86_3-0) [Canny, J.](./John_Canny) (1986). "A Computational Approach To Edge Detection". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **8** (6): 679–714. [doi](./Doi_(identifier)):[10.1109/TPAMI.1986.4767851](https://doi.org/10.1109%2FTPAMI.1986.4767851). [PMID](./PMID_(identifier)) [21869365](https://pubmed.ncbi.nlm.nih.gov/21869365). [S2CID](./S2CID_(identifier)) [13284142](https://api.semanticscholar.org/CorpusID:13284142).
4. [↑](./Feature_(computer_vision)#cite_ref-HarSte88_4-0) C. Harris; M. Stephens (1988). ["A combined corner and edge detector"](https://web.archive.org/web/20220401053336/http://www.bmva.org/bmvc/1988/avc-88-023.pdf) (PDF). *Proceedings of the 4th Alvey Vision Conference*. pp. 147–151. Archived from [the original](http://www.bmva.org/bmvc/1988/avc-88-023.pdf) (PDF) on 2022-04-01. Retrieved 2021-02-11.
5. [↑](./Feature_(computer_vision)#cite_ref-Sus97_5-0) S. M. Smith; J. M. Brady (May 1997). ["SUSAN - a new approach to low level image processing"](http://citeseer.ist.psu.edu/smith95susan.html). *International Journal of Computer Vision*. **23** (1): 45–78. [doi](./Doi_(identifier)):[10.1023/A:1007963824710](https://doi.org/10.1023%2FA%3A1007963824710). [S2CID](./S2CID_(identifier)) [15033310](https://api.semanticscholar.org/CorpusID:15033310).
6. [↑](./Feature_(computer_vision)#cite_ref-ShiTom94_6-0) J. Shi; C. Tomasi (June 1994). ["Good Features to Track"](http://citeseer.ist.psu.edu/shi94good.html). *9th IEEE Conference on Computer Vision and Pattern Recognition*. Springer.
7. [1](./Feature_(computer_vision)#cite_ref-Lin98_7-0) [2](./Feature_(computer_vision)#cite_ref-Lin98_7-1) [3](./Feature_(computer_vision)#cite_ref-Lin98_7-2) T. Lindeberg (1998). ["Feature detection with automatic scale selection"](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A453064&dswid=-1017) (abstract). *International Journal of Computer Vision*. **30** (2): 77–116. [doi](./Doi_(identifier)):[10.1023/A:1008045108935](https://doi.org/10.1023%2FA%3A1008045108935). [S2CID](./S2CID_(identifier)) [723210](https://api.semanticscholar.org/CorpusID:723210).
8. [↑](./Feature_(computer_vision)#cite_ref-Ros06_8-0) E. Rosten; T. Drummond (2006). "Machine learning for high-speed corner detection". *European Conference on Computer Vision*. Springer. pp. 430–443. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.60.3991](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.60.3991). [doi](./Doi_(identifier)):[10.1007/11744023_34](https://doi.org/10.1007%2F11744023_34).
9. [↑](./Feature_(computer_vision)#cite_ref-Cro84_9-0) J. L. Crowley and A. C. Parker, "[A Representation for Shape Based on Peaks and Ridges in the Difference of Low Pass Transform](http://www.dtic.mil/get-tr-doc/pdf?AD=ADA133299)[*[dead link](./Wikipedia:Link_rot)*]", IEEE Transactions on PAMI, PAMI 6 (2), pp. 156–170, March 1984.
10. [↑](./Feature_(computer_vision)#cite_ref-Low04_10-0) D. Lowe (2004). ["Distinctive Image Features from Scale-Invariant Keypoints"](http://citeseer.ist.psu.edu/654168.html). *International Journal of Computer Vision*. **60** (2): 91. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.73.2924](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.73.2924). [doi](./Doi_(identifier)):[10.1023/B:VISI.0000029664.99615.94](https://doi.org/10.1023%2FB%3AVISI.0000029664.99615.94). [S2CID](./S2CID_(identifier)) [221242327](https://api.semanticscholar.org/CorpusID:221242327).
11. [↑](./Feature_(computer_vision)#cite_ref-Lin13JMIV_11-0) [T. Lindeberg "Scale selection properties of generalized scale-space interest point detectors", Journal of Mathematical Imaging and Vision, Volume 46, Issue 2, pages 177-210, 2013.](https://doi.org/10.1007/s10851-012-0378-3)
12. [↑](./Feature_(computer_vision)#cite_ref-Lin15JMIV_12-0) [T. Lindeberg "Image matching using generalized scale-space interest points", *Journal of Mathematical Imaging and Vision*, volume 52, number 1, pages 3-36, 2015.](https://doi.org/10.1007/s10851-014-0541-0)
13. [↑](./Feature_(computer_vision)#cite_ref-Mat02_13-0) J. Matas; O. Chum; M. Urban; T. Pajdla (2002). ["Robust wide baseline stereo from maximally stable extremum regions"](http://cmp.felk.cvut.cz/~matas/papers/matas-bmvc02.pdf) (PDF). *British Machine Vision Conference*. pp. 384–393.
14. [↑](./Feature_(computer_vision)#cite_ref-Har83_14-0) R. Haralick, "[Ridges and Valleys on Digital Images](http://www.cs.unc.edu/Research/Image/MIDAG/pubs/CScourses/254-Spring2002/Haralick-Ridges-CVGIP.PDF)", Computer Vision, Graphics, and Image Processing vol. 22, no. 10, pp. 28–38, Apr. 1983. 
15. [↑](./Feature_(computer_vision)#cite_ref-Ebe94_15-0) D. Eberly, R. Gardner, B. Morse, S. Pizer, C. Scharlach, [Ridges for image analysis](http://www.cs.unc.edu/techreports/93-055.ps), Journal of Mathematical Imaging and Vision, v. 4 n. 4, pp. 353–373, Dec. 1994.
16. [↑](./Feature_(computer_vision)#cite_ref-Lin98b_16-0) T. Lindeberg (1998). ["Edge detection and ridge detection with automatic scale selection"](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A452310&dswid=5658) (abstract). *International Journal of Computer Vision*. **30** (2): 117–154. [doi](./Doi_(identifier)):[10.1023/A:1008097225773](https://doi.org/10.1023%2FA%3A1008097225773). [S2CID](./S2CID_(identifier)) [207658261](https://api.semanticscholar.org/CorpusID:207658261).
17. [↑](./Feature_(computer_vision)#cite_ref-Lin93_17-0) T. Lindeberg (1993). ["Detecting Salient Blob-Like Image Structures and Their Scales with a Scale-Space Primal Sketch: A Method for Focus-of-Attention"](http://kth.diva-portal.org/smash/record.jsf?pid=diva2%3A472969&dswid=-485) (abstract). *International Journal of Computer Vision*. **11** (3): 283–318. [doi](./Doi_(identifier)):[10.1007/BF01469346](https://doi.org/10.1007%2FBF01469346). [S2CID](./S2CID_(identifier)) [11998035](https://api.semanticscholar.org/CorpusID:11998035).
18. [↑](./Feature_(computer_vision)#cite_ref-18) ["Object Detection in a Cluttered Scene Using Point Feature Matching - MATLAB & Simulink"](https://www.mathworks.com/help/vision/examples/object-detection-in-a-cluttered-scene-using-point-feature-matching.html). *www.mathworks.com*. Retrieved 2019-07-06.

 


