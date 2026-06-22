---
source: https://en.wikipedia.org/wiki/Visual_odometry
fetched: 2026-06-21
---

Determining the position and orientation of a robot by analyzing associated camera images [![](//upload.wikimedia.org/wikipedia/commons/thumb/1/10/Optical_flow_example_v2.png/250px-Optical_flow_example_v2.png)](./File:Optical_flow_example_v2.png)The [optical flow](./Optical_flow) vector of a moving object in a video sequence 

In [robotics](./Robotics) and [computer vision](./Computer_vision), **visual odometry** is the process of determining the position and orientation of a robot or other computer-based system by analyzing a set of camera images taken by the system of its environment. It has been used in a wide variety of robotic applications, such as on the [Mars Exploration Rovers](./Mars_Exploration_Rover).[[1]](./Visual_odometry#cite_note-Maimone2007-1)

 

Uses for visual odometry include [augmented reality](./Augmented_reality) and robotics.[[2]](./Visual_odometry#cite_note-o870-2)

 

It is called **visual-inertial odometry** (**VIO**) if it uses an inertial measurement unit.

 

## Overview

 

In [navigation](./Navigation), [odometry](./Odometry) is the use of data from the movement of actuators to estimate change in position over time through devices such as [rotary encoders](./Rotary_encoder) to measure wheel rotations. While useful for many wheeled or tracked vehicles, traditional odometry techniques cannot be applied to [mobile robots](./Mobile_robot) with non-standard locomotion methods, such as [legged robots](./Legged_robot). In addition, odometry universally suffers from precision problems, since wheels tend to slip and slide on the floor creating a non-uniform distance traveled as compared to the wheel rotations. The error is compounded when the vehicle operates on non-smooth surfaces. Odometry readings become increasingly unreliable as these errors accumulate and compound over time.

 

Visual odometry is the process of determining equivalent odometry information using sequential camera images to estimate the distance traveled. Visual odometry allows for enhanced navigational accuracy in robots or vehicles using any type of locomotion on any[*[citation needed](./Wikipedia:Citation_needed)*] surface.

 

## Types

 

There are various types of VO.

 

### Monocular and stereo

 

Depending on the camera setup, VO can be categorized as Monocular VO (single camera), Stereo VO (two camera in stereo setup).

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/c/cd/VIO_sensor_in_various_commercial_quadcopters_.jpg/250px-VIO_sensor_in_various_commercial_quadcopters_.jpg)](./File:VIO_sensor_in_various_commercial_quadcopters_.jpg)VIO is widely used in commercial quadcopters, which provide localization in GPS denied situations. 

### Feature-based and direct method

 

Traditional VO's visual information is obtained by the feature-based method, which extracts the image feature points and tracks them in the image sequence. Recent developments in VO research provided an alternative, called the direct method, which uses pixel intensity in the image sequence directly as visual input. There are also hybrid methods.

 

### Visual inertial odometry

 

If an [inertial measurement unit](./Inertial_measurement_unit) (IMU) is used within the VO system, it is commonly referred to as Visual Inertial Odometry (VIO).

 

## Algorithm

 

Most existing approaches to visual odometry are based on the following stages.

 
1. Acquire input images: using either [single cameras](./Single_camera).,[[3]](./Visual_odometry#cite_note-ChhaniyaraS-3)[[4]](./Visual_odometry#cite_note-Nister:2004p211-4) [stereo cameras](./Stereo_camera),[[4]](./Visual_odometry#cite_note-Nister:2004p211-4)[[5]](./Visual_odometry#cite_note-Comport10-5) or [omnidirectional cameras](./Omnidirectional_camera).[[6]](./Visual_odometry#cite_note-ScaramuzzaIEEE-TRO08-6)[[7]](./Visual_odometry#cite_note-Corke-7)
2. Image correction: apply [image processing](./Image_processing) techniques for lens distortion removal, etc.
3. [Feature detection](./Feature_detection_(computer_vision)): define interest operators, and match features across frames and construct [optical flow](./Optical_flow) field.

1. [Feature extraction](./Feature_extraction) and correlation. 

- Use correlation, not long term [feature tracking](./Feature_tracking), to establish [correspondence](./Correspondence_problem) of two images.

2. Construct optical flow field ([Lucas–Kanade method](./Lucas–Kanade_method)).

4. Check flow field vectors for potential tracking errors and remove outliers.[[8]](./Visual_odometry#cite_note-Campbell-8)
5. Estimation of the camera motion from the optical flow.[[9]](./Visual_odometry#cite_note-Sunderhauf2005-9)[[10]](./Visual_odometry#cite_note-Konolige2006-10)[[11]](./Visual_odometry#cite_note-Olson2002-11)[[12]](./Visual_odometry#cite_note-Cheng2006-12) 
1. Choice 1: [Kalman filter](./Kalman_filter) for state estimate distribution maintenance.
2. Choice 2: find the geometric and 3D properties of the features that minimize a [cost function](./Loss_function) based on the re-projection error between two adjacent images. This can be done by mathematical minimization or [random sampling](./Random_sampling).

6. Periodic repopulation of trackpoints to maintain coverage across the image.

 

An alternative to feature-based methods is the "direct" or appearance-based visual odometry technique which minimizes an error directly in sensor space and subsequently avoids feature matching and extraction.[[5]](./Visual_odometry#cite_note-Comport10-5)[[13]](./Visual_odometry#cite_note-13)[[14]](./Visual_odometry#cite_note-14)

 

Another method, coined 'visiodometry' estimates the planar roto-translations between images using [Phase correlation](./Phase_correlation) instead of extracting features.[[15]](./Visual_odometry#cite_note-ZamanICRA-15)[[16]](./Visual_odometry#cite_note-ZamanJRAS-16)

 

## Egomotion

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/e/e1/Egomotion-odometry.gif/250px-Egomotion-odometry.gif)](./File:Egomotion-odometry.gif)Egomotion estimation using [corner detection](./Corner_detection) 

**Egomotion** is defined as the 3D motion of a camera within an environment.[[17]](./Visual_odometry#cite_note-irani-17) In the field of [computer vision](./Computer_vision), egomotion refers to estimating a camera's motion relative to a rigid scene.[[18]](./Visual_odometry#cite_note-18) An example of egomotion estimation would be estimating a car's moving position relative to lines on the road or street signs being observed from the car itself. The estimation of egomotion is important in [autonomous robot navigation](./Autonomous_robot#Autonomous_navigation) applications.[[19]](./Visual_odometry#cite_note-19)

 

### Overview

 

The goal of estimating the egomotion of a camera is to determine the 3D motion of that camera within the environment using a sequence of images taken by the camera.[[20]](./Visual_odometry#cite_note-20) The process of estimating a camera's motion within an environment involves the use of visual odometry techniques on a sequence of images captured by the moving camera.[[21]](./Visual_odometry#cite_note-milella-21) This is typically done using [feature detection](./Feature_detection_(computer_vision)) to construct an [optical flow](./Optical_flow) from two image frames in a sequence[[17]](./Visual_odometry#cite_note-irani-17) generated from either single cameras or stereo cameras.[[21]](./Visual_odometry#cite_note-milella-21) Using stereo image pairs for each frame helps reduce error and provides additional depth and scale information.[[22]](./Visual_odometry#cite_note-olson-22)[[23]](./Visual_odometry#cite_note-23)

 

Features are detected in the first frame, and then matched in the second frame. This information is then used to make the optical flow field for the detected features in those two images. The optical flow field illustrates how features diverge from a single point, the *focus of expansion*. The focus of expansion can be detected from the optical flow field, indicating the direction of the motion of the camera, and thus providing an estimate of the camera motion.

 

There are other methods of extracting egomotion information from images as well, including a method that avoids feature detection and optical flow fields and directly uses the image intensities.[[17]](./Visual_odometry#cite_note-irani-17)

 

## See also

 
- [Dead reckoning](./Dead_reckoning)
- [Odometry](./Odometry)
- [Optical flow](./Optical_flow)
- [Optical motion capture](./Optical_motion_capture)
- [Perspective-n-Point](./Perspective-n-Point)

 

## References

 
1. [↑](./Visual_odometry#cite_ref-Maimone2007_1-0) Maimone, M.; Cheng, Y.; Matthies, L. (2007). ["Two years of Visual Odometry on the Mars Exploration Rovers"](https://www-robotics.jpl.nasa.gov/publications/Mark_Maimone/rob-06-0081.R4.pdf) (PDF). *Journal of Field Robotics*. **24** (3): 169–186. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.104.3110](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.104.3110). [doi](./Doi_(identifier)):[10.1002/rob.20184](https://doi.org/10.1002%2Frob.20184). [S2CID](./S2CID_(identifier)) [17544166](https://api.semanticscholar.org/CorpusID:17544166). Retrieved 2008-07-10.
2. [↑](./Visual_odometry#cite_ref-o870_2-0) ["The TUM VI Benchmark for Evaluating Visual-Inertial Odometry"](https://ieeexplore.ieee.org/document/8593419/). *IEEE Xplore*. 2019-01-06. Retrieved 2025-12-20.
3. [↑](./Visual_odometry#cite_ref-ChhaniyaraS_3-0) Chhaniyara, Savan; KASPAR ALTHOEFER; LAKMAL D. SENEVIRATNE (2008). ["Visual Odometry Technique Using Circular Marker Identification For Motion Parameter Estimation"](https://web.archive.org/web/20120224015522/http://eproceedings.worldscinet.com/9789812835772/9789812835772_0128.html). *Advances in Mobile Robotics: Proceedings of the Eleventh International Conference on Climbing and Walking Robots and the Support Technologies for Mobile Machines, Coimbra, Portugal*. [The Eleventh International Conference on Climbing and Walking Robots and the Support Technologies for Mobile Machines](https://books.google.com/books?id=8L7izBmmCuQC&q=savan+chhaniyara&pg=PA1069). Vol. 11. World Scientific, 2008. Archived from [the original](http://eproceedings.worldscinet.com/9789812835772/9789812835772_0128.html) on 2012-02-24. Retrieved 2010-01-22.
4. [1](./Visual_odometry#cite_ref-Nister:2004p211_4-0) [2](./Visual_odometry#cite_ref-Nister:2004p211_4-1) Nister, D; Naroditsky, O.; Bergen, J (Jan 2004). *Visual Odometry*. Computer Vision and Pattern Recognition, 2004. CVPR 2004. Vol. 1. pp. I–652 – I–659 Vol.1. [doi](./Doi_(identifier)):[10.1109/CVPR.2004.1315094](https://doi.org/10.1109%2FCVPR.2004.1315094).
5. [1](./Visual_odometry#cite_ref-Comport10_5-0) [2](./Visual_odometry#cite_ref-Comport10_5-1) Comport, A.I.; Malis, E.; Rives, P. (2010). F. Chaumette; P. Corke; P. Newman (eds.). "Real-time Quadrifocal Visual Odometry". *International Journal of Robotics Research*. **29** (2–3): 245–266. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.720.3113](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.720.3113). [doi](./Doi_(identifier)):[10.1177/0278364909356601](https://doi.org/10.1177%2F0278364909356601). [S2CID](./S2CID_(identifier)) [15139693](https://api.semanticscholar.org/CorpusID:15139693).
6. [↑](./Visual_odometry#cite_ref-ScaramuzzaIEEE-TRO08_6-0) Scaramuzza, D.; Siegwart, R. (October 2008). "Appearance-Guided Monocular Omnidirectional Visual Odometry for Outdoor Ground Vehicles". *IEEE Transactions on Robotics*. **24** (5): 1015–1026. [Bibcode](./Bibcode_(identifier)):[2008ITRob..24.1015S](https://ui.adsabs.harvard.edu/abs/2008ITRob..24.1015S). [doi](./Doi_(identifier)):[10.1109/TRO.2008.2004490](https://doi.org/10.1109%2FTRO.2008.2004490). [hdl](./Hdl_(identifier)):[20.500.11850/14362](https://hdl.handle.net/20.500.11850%2F14362). [S2CID](./S2CID_(identifier)) [13894940](https://api.semanticscholar.org/CorpusID:13894940).
7. [↑](./Visual_odometry#cite_ref-Corke_7-0) Corke, P.; Strelow, D.; Singh, S. "Omnidirectional visual odometry for a planetary rover". *Intelligent Robots and Systems, 2004.(IROS 2004). Proceedings. 2004 IEEE/RSJ International Conference on*. Vol. 4. [doi](./Doi_(identifier)):[10.1109/IROS.2004.1390041](https://doi.org/10.1109%2FIROS.2004.1390041).
8. [↑](./Visual_odometry#cite_ref-Campbell_8-0) Campbell, J.; Sukthankar, R.; Nourbakhsh, I.; Pittsburgh, I.R. "Techniques for evaluating optical flow for visual odometry in extreme terrain". *Intelligent Robots and Systems, 2004.(IROS 2004). Proceedings. 2004 IEEE/RSJ International Conference on*. Vol. 4. [doi](./Doi_(identifier)):[10.1109/IROS.2004.1389991](https://doi.org/10.1109%2FIROS.2004.1389991).
9. [↑](./Visual_odometry#cite_ref-Sunderhauf2005_9-0) Sunderhauf, N.; Konolige, K.; Lacroix, S.; Protzel, P. (2005). "Visual odometry using sparse bundle adjustment on an autonomous outdoor vehicle". In Levi; Schanz; Lafrenz; Avrutin (eds.). [*Tagungsband Autonome Mobile Systeme 2005*](https://web.archive.org/web/20090211031719/http://www.tu-chemnitz.de/etit/proaut/index.download.df493a7bc2c27263f7d8ff467ea84879.pdf) (PDF). Reihe Informatik aktuell. Springer Verlag. pp. 157–163. Archived from [the original](http://www.tu-chemnitz.de/etit/proaut/index.download.df493a7bc2c27263f7d8ff467ea84879.pdf) (PDF) on 2009-02-11. Retrieved 2008-07-10.
10. [↑](./Visual_odometry#cite_ref-Konolige2006_10-0) Konolige, K.; Agrawal, M.; Bolles, R.C.; Cowan, C.; Fischler, M.; Gerkey, B.P. (2008). "Outdoor Mapping and Navigation Using Stereo Vision". *Experimental Robotics*. Springer Tracts in Advanced Robotics. Vol. 39. pp. 179–190. [doi](./Doi_(identifier)):[10.1007/978-3-540-77457-0_17](https://doi.org/10.1007%2F978-3-540-77457-0_17). [ISBN](./ISBN_(identifier)) [978-3-540-77456-3](./Special:BookSources/978-3-540-77456-3).
11. [↑](./Visual_odometry#cite_ref-Olson2002_11-0) Olson, C.F.; Matthies, L.; Schoppers, M.; Maimone, M.W. (2002). ["Rover navigation using stereo ego-motion"](http://faculty.washington.edu/cfolson/papers/pdf/ras03.pdf) (PDF). *Robotics and Autonomous Systems*. **43** (4): 215–229. [doi](./Doi_(identifier)):[10.1016/s0921-8890(03)00004-6](https://doi.org/10.1016%2Fs0921-8890%2803%2900004-6). Retrieved 2010-06-06.
12. [↑](./Visual_odometry#cite_ref-Cheng2006_12-0) Cheng, Y.; Maimone, M.W.; Matthies, L. (2006). "Visual Odometry on the Mars Exploration Rovers". *IEEE Robotics and Automation Magazine*. **13** (2): 54–62. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.297.4693](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.297.4693). [doi](./Doi_(identifier)):[10.1109/MRA.2006.1638016](https://doi.org/10.1109%2FMRA.2006.1638016). [S2CID](./S2CID_(identifier)) [15149330](https://api.semanticscholar.org/CorpusID:15149330).
13. [↑](./Visual_odometry#cite_ref-13) Engel, Jakob; Schöps, Thomas; Cremers, Daniel (2014). ["LSD-SLAM: Large-Scale Direct Monocular SLAM"](https://vision.in.tum.de/_media/spezial/bib/engel14eccv.pdf) (PDF). In Fleet D.; Pajdla T.; Schiele B.; Tuytelaars T. (eds.). *Computer Vision*. European Conference on Computer Vision 2014. Lecture Notes in Computer Science. Vol. 8690. [doi](./Doi_(identifier)):[10.1007/978-3-319-10605-2_54](https://doi.org/10.1007%2F978-3-319-10605-2_54).
14. [↑](./Visual_odometry#cite_ref-14) Engel, Jakob; Sturm, Jürgen; Cremers, Daniel (2013). ["Semi-Dense Visual Odometry for a Monocular Camera"](https://vision.in.tum.de/_media/spezial/bib/engel2013iccv.pdf) (PDF). *IEEE International Conference on Computer Vision (ICCV)*. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.402.6918](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.402.6918). [doi](./Doi_(identifier)):[10.1109/ICCV.2013.183](https://doi.org/10.1109%2FICCV.2013.183).
15. [↑](./Visual_odometry#cite_ref-ZamanICRA_15-0) Zaman, M. (2007). "High Precision Relative Localization Using a Single Camera". *Proceedings 2007 IEEE International Conference on Robotics and Automation*. pp. 3908–3914. [doi](./Doi_(identifier)):[10.1109/ROBOT.2007.364078](https://doi.org/10.1109%2FROBOT.2007.364078). [ISBN](./ISBN_(identifier)) [978-1-4244-0602-9](./Special:BookSources/978-1-4244-0602-9).
16. [↑](./Visual_odometry#cite_ref-ZamanJRAS_16-0) Zaman, M. (2007). "High resolution relative localisation using two cameras". *Journal of Robotics and Autonomous Systems*. **55** (9): 685–692. [doi](./Doi_(identifier)):[10.1016/j.robot.2007.05.008](https://doi.org/10.1016%2Fj.robot.2007.05.008).
17. [1](./Visual_odometry#cite_ref-irani_17-0) [2](./Visual_odometry#cite_ref-irani_17-1) [3](./Visual_odometry#cite_ref-irani_17-2) Irani, M.; Rousso, B.; Peleg S. (June 1994). ["Recovery of Ego-Motion Using Image Stabilization"](http://www.vision.huji.ac.il/papers/ego-mtn-cvpr94.pdf) (PDF). *IEEE Computer Society Conference on Computer Vision and Pattern Recognition*: 21–23. Retrieved 7 June 2010.
18. [↑](./Visual_odometry#cite_ref-18) Burger, W.; Bhanu, B. (Nov 1990). "Estimating 3D egomotion from perspective image sequence". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **12** (11): 1040–1058. [doi](./Doi_(identifier)):[10.1109/34.61704](https://doi.org/10.1109%2F34.61704). [S2CID](./S2CID_(identifier)) [206418830](https://api.semanticscholar.org/CorpusID:206418830).
19. [↑](./Visual_odometry#cite_ref-19) Shakernia, O.; Vidal, R.; Shankar, S. (2003). ["Omnidirectional Egomotion Estimation from Back-projection Flow"](http://cis.jhu.edu/~rvidal/publications/OMNIVIS03-backflow.pdf) (PDF). *2003 Conference on Computer Vision and Pattern Recognition Workshop*. Vol. 7. p. 82. [CiteSeerX](./CiteSeerX_(identifier)) [10.1.1.5.8127](https://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.5.8127). [doi](./Doi_(identifier)):[10.1109/CVPRW.2003.10074](https://doi.org/10.1109%2FCVPRW.2003.10074). [S2CID](./S2CID_(identifier)) [5494756](https://api.semanticscholar.org/CorpusID:5494756). Retrieved 7 June 2010.
20. [↑](./Visual_odometry#cite_ref-20) Tian, T.; Tomasi, C.; Heeger, D. (1996). ["Comparison of Approaches to Egomotion Computation"](https://web.archive.org/web/20080808123021/http://www.cs.duke.edu/%7Etomasi/papers/tian/tianCvpr96.pdf) (PDF). *IEEE Computer Society Conference on Computer Vision and Pattern Recognition*: 315. Archived from [the original](http://www.cs.duke.edu/~tomasi/papers/tian/tianCvpr96.pdf) (PDF) on August 8, 2008. Retrieved 7 June 2010.
21. [1](./Visual_odometry#cite_ref-milella_21-0) [2](./Visual_odometry#cite_ref-milella_21-1) Milella, A.; Siegwart, R. (January 2006). ["Stereo-Based Ego-Motion Estimation Using Pixel Tracking and Iterative Closest Point"](https://web.archive.org/web/20100917151342/http://asl.epfl.ch/aslInternalWeb/ASL/publications/uploadedFiles/21_amilella_EgoMotion_rev_publication.pdf) (PDF). *IEEE International Conference on Computer Vision Systems*: 21. Archived from [the original](http://asl.epfl.ch/aslInternalWeb/ASL/publications/uploadedFiles/21_amilella_EgoMotion_rev_publication.pdf) (PDF) on 17 September 2010. Retrieved 7 June 2010.
22. [↑](./Visual_odometry#cite_ref-olson_22-0) Olson, C. F.; Matthies, L.; Schoppers, M.; Maimoneb M. W. (June 2003). ["Rover navigation using stereo ego-motion"](http://faculty.washington.edu/cfolson/papers/pdf/ras03.pdf) (PDF). *Robotics and Autonomous Systems*. **43** (9): 215–229. [doi](./Doi_(identifier)):[10.1016/s0921-8890(03)00004-6](https://doi.org/10.1016%2Fs0921-8890%2803%2900004-6). Retrieved 7 June 2010.
23. [↑](./Visual_odometry#cite_ref-23) Dinesh, Sudin; Koteswara Rao, K.; Unnikrishnan, Manju; Brinda v; Lalithambika v.r; Dhekane, M.V (2013). "Improvements in visual odometry algorithm for planetary exploration rovers". *2013 International Conference on Emerging Trends in Communication, Control, Signal Processing and Computing Applications (C2SPCA)*. pp. 1–6. [doi](./Doi_(identifier)):[10.1109/C2SPCA.2013.6749359](https://doi.org/10.1109%2FC2SPCA.2013.6749359). [ISBN](./ISBN_(identifier)) [978-1-4799-1085-4](./Special:BookSources/978-1-4799-1085-4).

 
| vteComputer vision |
| --- |
| Categories | DatasetsDigital geometryCommercial systemsFeature detectionGeometryImage sensor technologyLearningMorphologyMotion analysisNoise reduction techniquesRecognition and categorizationResearch infrastructureResearchersSegmentationSoftware |
| Technologies | Computer stereo visionMotion captureObject recognition3D object recognition |
| Applications | 3D reconstruction3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture3D pose estimationActivity recognitionAudio-visual speech recognitionAutomatic image annotationAutomatic number-plate recognitionAutomated species identificationAugmented realityBioimage informaticsBlob detectionComputer-aided diagnosisContent-based image retrievalReverse image searchEye trackingFace recognitionForeground detectionGesture recognitionImage denoisingImage restorationLandmark detectionMedical image computingObject detectionMoving object detectionPedestrian detectionSmall object detectionOptical character recognitionPose trackingRemote sensingRobotic mappingAutonomous vehiclesVideo browsingVideo content analysisVideo motion analysisVideo surveillanceVideo synopsisVideo tracking | 3D reconstruction | 3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture |
| 3D reconstruction | 3D reconstruction from multiple images2D to 3D conversionGaussian splattingNeural radiance fieldShape from focusSimultaneous localization and mappingStructure from motionView synthesisVisual hull4D reconstructionFree viewpoint televisionVolumetric capture |
| Main category |