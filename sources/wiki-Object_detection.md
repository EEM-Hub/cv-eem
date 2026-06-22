---
source: https://en.wikipedia.org/wiki/Object_detection
fetched: 2026-06-21
---

Computer technology related to computer vision and image processing [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/38/Detected-with-YOLO--Schreibtisch-mit-Objekten.jpg/250px-Detected-with-YOLO--Schreibtisch-mit-Objekten.jpg)](./File:Detected-with-YOLO--Schreibtisch-mit-Objekten.jpg)Objects detected with OpenCV's Deep Neural Network module (dnn) by using a [YOLOv3](./You_Only_Look_Once) model trained on [COCO](./COCO_(dataset)) dataset capable to detect objects of 80 common classes 

**Object detection** is a computer technology related to [computer vision](./Computer_vision) and [image processing](./Image_processing) that deals with detecting instances of semantic objects of a certain class (such as humans, buildings, or cars) in digital images and videos.[[1]](./Object_detection#cite_note-1) Well-researched domains of object detection include [face detection](./Face_detection) and [pedestrian detection](./Pedestrian_detection). Object detection has applications in many areas of computer vision, including [image retrieval](./Image_retrieval) and [video surveillance](./Video_surveillance).

 

## Uses

 

It is widely used in [computer vision](./Computer_vision) tasks such as [image annotation](./Automatic_image_annotation),[[2]](./Object_detection#cite_note-GuanHe2012-2) vehicle counting,[[3]](./Object_detection#cite_note-3) [activity recognition](./Activity_recognition),[[4]](./Object_detection#cite_note-4) [face detection](./Face_detection), [face recognition](./Face_recognition), [video object co-segmentation](./Object_co-segmentation). It is also used in [tracking objects](./Video_tracking), for example tracking a ball during a football match, tracking movement of a cricket bat, or tracking a person in a video.

 

Often, the test images are sampled from a different data distribution, making the object detection task significantly more difficult.[[5]](./Object_detection#cite_note-:0-5) To address the challenges caused by the domain gap between training and test data, many unsupervised domain adaptation approaches have been proposed.[[5]](./Object_detection#cite_note-:0-5)[[6]](./Object_detection#cite_note-6)[[7]](./Object_detection#cite_note-7)[[8]](./Object_detection#cite_note-8)[[9]](./Object_detection#cite_note-9) A simple and straightforward solution for reducing the domain gap is to apply an image-to-image translation approach, such as cycle-GAN.[[10]](./Object_detection#cite_note-10) Among other uses, cross-domain object detection is applied in autonomous driving, where models can be trained on a vast amount of video game scenes, since the labels can be generated without manual labor.

 

## Concept

 

Every object class has its own special [features](./Feature_(computer_vision)) that help in classifying the class – for example all [circles](./Circle) are round.
Object class detection uses these special features. For example, when looking for circles, objects that are at a particular distance from a point (i.e. the center) are sought. Similarly, when looking for squares, objects that are [perpendicular](./Perpendicular) at corners and have equal side lengths are needed.  A similar approach is used for [face identification](./Facial_recognition_system) where eyes, nose, and lips can be found and [features](./Feature_(computer_vision)) like skin color and distance between eyes can be found.

 

## Benchmarks

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Intersection_over_Union_-_object_detection_bounding_boxes.jpg/330px-Intersection_over_Union_-_object_detection_bounding_boxes.jpg)](./File:Intersection_over_Union_-_object_detection_bounding_boxes.jpg)[![](//upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Intersection_over_Union_-_visual_equation.png/330px-Intersection_over_Union_-_visual_equation.png)](./File:Intersection_over_Union_-_visual_equation.png)[![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e6/Intersection_over_Union_-_poor%2C_good_and_excellent_score.png/330px-Intersection_over_Union_-_poor%2C_good_and_excellent_score.png)](./File:Intersection_over_Union_-_poor,_good_and_excellent_score.png)Intersection over union as a similarity measure for object detection on images –  an important task in [computer vision](./Computer_vision) 

For object localization, true positive is often measured by the thresholded [intersection over union](./Intersection_over_union). For example, if there is a traffic sign in the image, with a bounding box drawn by a human ("ground truth label"), then a neural network has detected the traffic sign (a **true positive**) at 0.5 threshold if it has drawn a bounding box whose IoU with the ground truth is above 0.5. Otherwise, the bounding box is a **false positive**.

 

If there is only a single ground truth bounding box, but multiple predictions, then the IoU of each prediction is calculated. The prediction with the highest IoU is a true positive if it is above threshold, else it is a false positive. All other predicted bounding boxes are false positives. If there is no prediction with an IoU above the threshold, then the ground truth label has a **false negative**.

 

For simultaneous object localization and classification, a true positive is one where the class label is correct, and the bounding box has an IoU exceeding the threshold.

 

Simultaneous object localization and classification is benchmarked by the **mean average precision** (mAP). The average precision (AP) of the network for a class of objects is the area under the [precision-recall curve](./Receiver_operating_characteristic) as the confidence threshold is varied. The mAP is the average of AP over all classes.

 

## Methods

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Simplified_neural_network_training_example.svg/250px-Simplified_neural_network_training_example.svg.png)](./File:Simplified_neural_network_training_example.svg)Simplified example of training a neural network in object detection: The network is trained by multiple images that are known to depict [starfish](./Starfish) and [sea urchins](./Sea_urchin), which are correlated with "nodes" that represent visual [features](./Feature_(computer_vision)). The starfish match with a ringed texture and a star outline, whereas most sea urchins match with a striped texture and oval shape. However, the instance of a ring textured sea urchin creates a weakly weighted association between them.[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Simplified_neural_network_example.svg/250px-Simplified_neural_network_example.svg.png)](./File:Simplified_neural_network_example.svg)Subsequent run of the network on an input image (left):[[11]](./Object_detection#cite_note-11) The network correctly detects the starfish. However, the weakly weighted association between ringed texture and sea urchin also confers a weak signal to the latter from one of two intermediate nodes. In addition, a shell that was not included in the training gives a weak signal for the oval shape, also resulting in a weak signal for the sea urchin output. These weak signals may result in a [false positive](./False_positive) result for sea urchin.
In reality, textures and outlines would not be represented by single nodes, but rather by associated weight patterns of multiple nodes. 

Methods for object detection generally fall into either neural network-based or non-neural approaches. For non-neural approaches, it becomes necessary to first define features using one of the methods below, then using a technique such as [support vector machine](./Support_vector_machine) (SVM) to do the classification. On the other hand, neural techniques are able to do end-to-end object detection without specifically defining features, and are typically based on [convolutional neural networks](./Convolutional_neural_network) (CNN).

 
- Non-neural approaches:

- [Viola–Jones object detection framework](./Viola–Jones_object_detection_framework) based on [Haar features](./Haar-like_feature)
- [Scale-invariant feature transform (SIFT)](./Scale-invariant_feature_transform)
- [Histogram of oriented gradients (HOG)](./Histogram_of_oriented_gradients) features[[12]](./Object_detection#cite_note-12)

- Neural network approaches:

- OverFeat.[[13]](./Object_detection#cite_note-13)
- [Region Proposals](./Region_Based_Convolutional_Neural_Networks) (R-CNN,[[14]](./Object_detection#cite_note-14) Fast R-CNN,[[15]](./Object_detection#cite_note-15) Faster R-CNN,[[16]](./Object_detection#cite_note-16) cascade R-CNN.[[17]](./Object_detection#cite_note-Pang_Chen_Shi_Feng_2019-17))
- [You Only Look Once](./You_Only_Look_Once) (YOLO).[[18]](./Object_detection#cite_note-18)
- Single Shot MultiBox Detector (SSD) [[19]](./Object_detection#cite_note-19)
- Single-Shot Refinement Neural Network for Object Detection (RefineDet) [[20]](./Object_detection#cite_note-20)
- Retina-Net [[21]](./Object_detection#cite_note-21)[[17]](./Object_detection#cite_note-Pang_Chen_Shi_Feng_2019-17)
- Deformable convolutional networks [[22]](./Object_detection#cite_note-22)[[23]](./Object_detection#cite_note-23)
- [Detection transformer (DETR)](./DETR_(DEtection_TRansformer)), which use [vision transformers](./Vision_transformer).

 

## See also

 
- [Feature detection (computer vision)](./Feature_detection_(computer_vision))
- [Moving object detection](./Moving_object_detection)
- [Small object detection](./Small_object_detection)
- [Outline of object recognition](./Outline_of_object_recognition)
- [Teknomo–Fernandez algorithm](./Teknomo–Fernandez_algorithm)

 

## References

  
1. [↑](./Object_detection#cite_ref-1) Dasiopoulou, Stamatia, et al. "[Knowledge-assisted semantic video object detection](http://www.iti.gr/~bmezaris/publications/csvt05.pdf)." IEEE Transactions on Circuits and Systems for Video Technology 15.10 (2005): 1210–1224.
2. [↑](./Object_detection#cite_ref-GuanHe2012_2-0) Ling Guan; Yifeng He; Sun-Yuan Kung (1 March 2012). [*Multimedia Image and Video Processing*](https://books.google.com/books?id=eTfNBQAAQBAJ&q=%22object+detection%22+%22image+annotation%22&pg=PA331). CRC Press. pp. 331–. [ISBN](./ISBN_(identifier)) [978-1-4398-3087-1](./Special:BookSources/978-1-4398-3087-1).
3. [↑](./Object_detection#cite_ref-3) Alsanabani, Ala; Ahmed, Mohammed; AL Smadi, Ahmad (2020). "Vehicle Counting Using Detecting-Tracking Combinations: A Comparative Analysis". *2020 the 4th International Conference on Video and Image Processing*. pp. 48–54. [doi](./Doi_(identifier)):[10.1145/3447450.3447458](https://doi.org/10.1145%2F3447450.3447458). [ISBN](./ISBN_(identifier)) [9781450389075](./Special:BookSources/9781450389075). [S2CID](./S2CID_(identifier)) [233194604](https://api.semanticscholar.org/CorpusID:233194604).
4. [↑](./Object_detection#cite_ref-4) Wu, Jianxin; Osuntogun, Adebola; Choudhury, Tanzeem; Philipose, Matthai; Rehg, James M. (2007). "A Scalable Approach to Activity Recognition based on Object Use". *2007 IEEE 11th International Conference on Computer Vision*. pp. 1–8. [doi](./Doi_(identifier)):[10.1109/ICCV.2007.4408865](https://doi.org/10.1109%2FICCV.2007.4408865). [ISBN](./ISBN_(identifier)) [978-1-4244-1630-1](./Special:BookSources/978-1-4244-1630-1).
5. [1](./Object_detection#cite_ref-:0_5-0) [2](./Object_detection#cite_ref-:0_5-1) Oza, Poojan; Sindagi, Vishwanath A.; VS, Vibashan; Patel, Vishal M. (2021-07-04). "Unsupervised Domain Adaptation of Object Detectors: A Survey". [arXiv](./ArXiv_(identifier)):[2105.13502](https://arxiv.org/abs/2105.13502) [[cs.CV](https://arxiv.org/archive/cs.CV)].
6. [↑](./Object_detection#cite_ref-6) Khodabandeh, Mehran; Vahdat, Arash; Ranjbar, Mani; Macready, William G. (2019-11-18). "A Robust Learning Approach to Domain Adaptive Object Detection". [arXiv](./ArXiv_(identifier)):[1904.02361](https://arxiv.org/abs/1904.02361) [[cs.LG](https://arxiv.org/archive/cs.LG)].
7. [↑](./Object_detection#cite_ref-7) Soviany, Petru; Ionescu, Radu Tudor; Rota, Paolo; Sebe, Nicu (2021-03-01). ["Curriculum self-paced learning for cross-domain object detection"](https://www.sciencedirect.com/science/article/pii/S1077314221000102). *Computer Vision and Image Understanding*. **204** 103166. [arXiv](./ArXiv_(identifier)):[1911.06849](https://arxiv.org/abs/1911.06849). [doi](./Doi_(identifier)):[10.1016/j.cviu.2021.103166](https://doi.org/10.1016%2Fj.cviu.2021.103166). [ISSN](./ISSN_(identifier)) [1077-3142](https://search.worldcat.org/issn/1077-3142). [S2CID](./S2CID_(identifier)) [208138033](https://api.semanticscholar.org/CorpusID:208138033).
8. [↑](./Object_detection#cite_ref-8) Menke, Maximilian; Wenzel, Thomas; Schwung, Andreas (October 2022). "Improving GAN-based Domain Adaptation for Object Detection". *2022 IEEE 25th International Conference on Intelligent Transportation Systems (ITSC)*. pp. 3880–3885. [doi](./Doi_(identifier)):[10.1109/ITSC55140.2022.9922138](https://doi.org/10.1109%2FITSC55140.2022.9922138). [ISBN](./ISBN_(identifier)) [978-1-6654-6880-0](./Special:BookSources/978-1-6654-6880-0). [S2CID](./S2CID_(identifier)) [253251380](https://api.semanticscholar.org/CorpusID:253251380).
9. [↑](./Object_detection#cite_ref-9) Menke, Maximilian; Wenzel, Thomas; Schwung, Andreas (2022-08-31). "AWADA: Attention-Weighted Adversarial Domain Adaptation for Object Detection". [arXiv](./ArXiv_(identifier)):[2208.14662](https://arxiv.org/abs/2208.14662) [[cs.CV](https://arxiv.org/archive/cs.CV)].
10. [↑](./Object_detection#cite_ref-10) Zhu, Jun-Yan; Park, Taesung; Isola, Phillip; Efros, Alexei A. (2020-08-24). "Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks". [arXiv](./ArXiv_(identifier)):[1703.10593](https://arxiv.org/abs/1703.10593) [[cs.CV](https://arxiv.org/archive/cs.CV)].
11. [↑](./Object_detection#cite_ref-11) Ferrie, C., & Kaiser, S. (2019). *Neural Networks for Babies*. Sourcebooks. [ISBN](./ISBN_(identifier)) [978-1492671206](./Special:BookSources/978-1492671206).`{{cite book}}`:  CS1 maint: multiple names: authors list ([link](./Category:CS1_maint:_multiple_names:_authors_list))
12. [↑](./Object_detection#cite_ref-12) Dalal, Navneet (2005). ["Histograms of oriented gradients for human detection"](https://hal.inria.fr/file/index/docid/548512/filename/hog_cvpr2005.pdf) (PDF). *Computer Vision and Pattern Recognition*. **1**.
13. [↑](./Object_detection#cite_ref-13) Sermanet, Pierre; Eigen, David; Zhang, Xiang; Mathieu, Michael; Fergus, Rob; LeCun, Yann (2014-02-23). "OverFeat: Integrated Recognition, Localization and Detection using Convolutional Networks". [arXiv](./ArXiv_(identifier)):[1312.6229](https://arxiv.org/abs/1312.6229) [[cs.CV](https://arxiv.org/archive/cs.CV)].
14. [↑](./Object_detection#cite_ref-14) Ross, Girshick (2014). ["Rich feature hierarchies for accurate object detection and semantic segmentation"](https://www.cv-foundation.org/openaccess/content_cvpr_2014/papers/Girshick_Rich_Feature_Hierarchies_2014_CVPR_paper.pdf) (PDF). *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition*. IEEE. pp. 580–587. [arXiv](./ArXiv_(identifier)):[1311.2524](https://arxiv.org/abs/1311.2524). [doi](./Doi_(identifier)):[10.1109/CVPR.2014.81](https://doi.org/10.1109%2FCVPR.2014.81). [ISBN](./ISBN_(identifier)) [978-1-4799-5118-5](./Special:BookSources/978-1-4799-5118-5). [S2CID](./S2CID_(identifier)) [215827080](https://api.semanticscholar.org/CorpusID:215827080).
15. [↑](./Object_detection#cite_ref-15) Girschick, Ross (2015). ["Fast R-CNN"](https://www.cv-foundation.org/openaccess/content_iccv_2015/papers/Girshick_Fast_R-CNN_ICCV_2015_paper.pdf) (PDF). *Proceedings of the IEEE International Conference on Computer Vision*. pp. 1440–1448. [arXiv](./ArXiv_(identifier)):[1504.08083](https://arxiv.org/abs/1504.08083).
16. [↑](./Object_detection#cite_ref-16) Shaoqing, Ren (2015). "Faster R-CNN". *Advances in Neural Information Processing Systems*. [arXiv](./ArXiv_(identifier)):[1506.01497](https://arxiv.org/abs/1506.01497).
17. [1](./Object_detection#cite_ref-Pang_Chen_Shi_Feng_2019_17-0) [2](./Object_detection#cite_ref-Pang_Chen_Shi_Feng_2019_17-1) Pang, Jiangmiao; Chen, Kai; Shi, Jianping; Feng, Huajun; Ouyang, Wanli; Lin, Dahua (2019-04-04). "Libra R-CNN: Towards Balanced Learning for Object Detection". [arXiv](./ArXiv_(identifier)):[1904.02701v1](https://arxiv.org/abs/1904.02701v1) [[cs.CV](https://arxiv.org/archive/cs.CV)].
18. [↑](./Object_detection#cite_ref-18) Redmon, Joseph; Divvala, Santosh; Girshick, Ross; Farhadi, Ali (2016-05-09). "You Only Look Once: Unified, Real-Time Object Detection". [arXiv](./ArXiv_(identifier)):[1506.02640](https://arxiv.org/abs/1506.02640) [[cs.CV](https://arxiv.org/archive/cs.CV)].
19. [↑](./Object_detection#cite_ref-19) Liu, Wei (October 2016). "SSD: Single Shot MultiBox Detector". *Computer Vision – ECCV 2016*. Lecture Notes in Computer Science. Vol. 9905. pp. 21–37. [arXiv](./ArXiv_(identifier)):[1512.02325](https://arxiv.org/abs/1512.02325). [doi](./Doi_(identifier)):[10.1007/978-3-319-46448-0_2](https://doi.org/10.1007%2F978-3-319-46448-0_2). [ISBN](./ISBN_(identifier)) [978-3-319-46447-3](./Special:BookSources/978-3-319-46447-3). [S2CID](./S2CID_(identifier)) [2141740](https://api.semanticscholar.org/CorpusID:2141740).
20. [↑](./Object_detection#cite_ref-20) Zhang, Shifeng (2018). "Single-Shot Refinement Neural Network for Object Detection". *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition*. pp. 4203–4212. [arXiv](./ArXiv_(identifier)):[1711.06897](https://arxiv.org/abs/1711.06897).
21. [↑](./Object_detection#cite_ref-21) Lin, Tsung-Yi (2020). "Focal Loss for Dense Object Detection". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **42** (2): 318–327. [arXiv](./ArXiv_(identifier)):[1708.02002](https://arxiv.org/abs/1708.02002). [Bibcode](./Bibcode_(identifier)):[2020ITPAM..42..318L](https://ui.adsabs.harvard.edu/abs/2020ITPAM..42..318L). [doi](./Doi_(identifier)):[10.1109/TPAMI.2018.2858826](https://doi.org/10.1109%2FTPAMI.2018.2858826). [PMID](./PMID_(identifier)) [30040631](https://pubmed.ncbi.nlm.nih.gov/30040631). [S2CID](./S2CID_(identifier)) [47252984](https://api.semanticscholar.org/CorpusID:47252984).
22. [↑](./Object_detection#cite_ref-22) Zhu, Xizhou (2018). "Deformable ConvNets v2: More Deformable, Better Results". [arXiv](./ArXiv_(identifier)):[1811.11168](https://arxiv.org/abs/1811.11168) [[cs.CV](https://arxiv.org/archive/cs.CV)].
23. [↑](./Object_detection#cite_ref-23) Dai, Jifeng (2017). "Deformable Convolutional Networks". [arXiv](./ArXiv_(identifier)):[1703.06211](https://arxiv.org/abs/1703.06211) [[cs.CV](https://arxiv.org/archive/cs.CV)].

 

## Further reading

 
- Zou, Zhengxia; Chen, Keyan; Shi, Zhenwei; Guo, Yuhong; Ye, Jieping (March 2023). "Object Detection in 20 Years: A Survey". *Proceedings of the IEEE*. **111** (3): 257–276. [doi](./Doi_(identifier)):[10.1109/JPROC.2023.3238524](https://doi.org/10.1109%2FJPROC.2023.3238524). [ISSN](./ISSN_(identifier)) [0018-9219](https://search.worldcat.org/issn/0018-9219).

 

## External links

 
- Joshi, Snehal (2023-10-24). ["Top Object Detection Models"](https://www.hitechbpo.com/blog/top-object-detection-models.php). *hitechbpo.com*.
- Weng, Lilian (2017-10-29). ["Object Detection for Dummies Part 1: Gradient Vector, HOG, and SS"](https://lilianweng.github.io/posts/2017-10-29-object-recognition-part-1/). *lilianweng.github.io*. Retrieved 2024-09-11.
- Weng, Lilian (2017-12-15). ["Object Detection for Dummies Part 2: CNN, DPM and Overfeat"](https://lilianweng.github.io/posts/2017-12-15-object-recognition-part-2/). *lilianweng.github.io*. Retrieved 2024-09-11.
- Weng, Lilian (2017-12-31). ["Object Detection for Dummies Part 3: R-CNN Family"](https://lilianweng.github.io/posts/2017-12-31-object-recognition-part-3/). *lilianweng.github.io*. Retrieved 2024-09-11.
- Weng, Lilian (2018-12-27). ["Object Detection Part 4: Fast Detection Models"](https://lilianweng.github.io/posts/2018-12-27-object-recognition-part-4/). *lilianweng.github.io*. Retrieved 2024-09-11.
- [Multiple object class detection](https://web.archive.org/web/20150418092531/http://www.mmp.rwth-aachen.de/publications/pdf/mikolajczyk-multiclass-cvpr06.pdf)
- [Spatio-temporal action localization](https://qilin-zhang.github.io/_pages/pdfs/Segment-Tube_Spatio-Temporal_Action_Localization_in_Untrimmed_Videos_with_Per-Frame_Segmentation.pdf)
- [Online Object Detection Demo](https://astica.ai/vision/object-detection/)
- [Video object detection and co-segmentation](https://qilin-zhang.github.io/_pages/pdfs/Joint_Video_Object_Discovery_and_Segmentation_by_Coupled_Dynamic_Markov_Networks.pdf)

 
| vteComputer vision |
| --- |
| Categories | DatasetsDigital geometryCommercial systemsFeature detectionGeometryImage sensor technologyLearningMorphologyMotion analysisNoise reduction techniquesRecognition and categorizationResearch infrastructureResearchersSegmentationSoftware |
| Technologies | Computer stereo visionMotion captureObject recognition3D object recognition |
| Applications | 3D reconstruction3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture3D pose estimationActivity recognitionAudio-visual speech recognitionAutomatic image annotationAutomatic number-plate recognitionAutomated species identificationAugmented realityBioimage informaticsBlob detectionComputer-aided diagnosisContent-based image retrievalReverse image searchEye trackingFace recognitionForeground detectionGesture recognitionImage denoisingImage restorationLandmark detectionMedical image computingObject detectionMoving object detectionPedestrian detectionSmall object detectionOptical character recognitionPose trackingRemote sensingRobotic mappingAutonomous vehiclesVideo browsingVideo content analysisVideo motion analysisVideo surveillanceVideo synopsisVideo tracking | 3D reconstruction | 3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture |
| 3D reconstruction | 3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture |
| Main category |