---
source: sources/wiki-Image_classification.md
source_url: https://en.wikipedia.org/wiki/Image_classification
chunk: 1/4
---

Computerized information extraction from images 
| Part ofa serieson |
| --- |
| Artificial intelligence (AI) |
| Major goalsArtificial general intelligenceIntelligent agentRecursive self-improvementPlanningComputer visionGeneral game playingKnowledge representationNatural language processingRoboticsAI safety |
| ApproachesMachine learningSymbolicDeep learningBayesian networksEvolutionary algorithmsNeuro-symbolic AISystems integrationOpen-sourceAI data centers |
| ApplicationsBioinformaticsDeepfakeEarth sciencesFinanceGenerative AIArtAudioMusicGovernmentHealthcareIndustrySoftware developmentTranslationMilitaryPhysicsProjects |
| PhilosophyAI alignmentArtificial consciousnessThe bitter lessonChinese roomFriendly AIEthicsExistential riskTuring testUncanny valleyHuman–AI interaction |
| HistoryTimelineProgressAI winterAI boomAI bubble |
| ControversiesDeepfake pornographyTaylor Swift deepfake pornography controversyGrok sexual deepfake scandalGoogle Gemini image generation controversyIt's the Most Terrible Time of the YearPause Giant AI ExperimentsRemoval of Sam Altman from OpenAIStatement on AI RiskTay (chatbot)Théâtre D'opéra SpatialVoiceverse NFT plagiarism scandal |
| GlossaryGlossary |
| vte |

 

**Computer vision** tasks include methods for [acquiring](./Image_sensor), [processing](./Image_processing), [analyzing](./Image_analysis), and understanding [digital images](./Digital_image), and extraction of [high-dimensional](./High-dimensional) data from the real world in order to produce numerical or symbolic information, e.g. in the form of decisions.[[1]](./Computer_vision#cite_note-Klette-2014-1)[[2]](./Computer_vision#cite_note-Shapiro-Stockman-2001-2)[[3]](./Computer_vision#cite_note-Morris-2004-3)[[4]](./Computer_vision#cite_note-Jahne-Haussecker-2000-4) "Understanding" in this context signifies the transformation of visual images into descriptions of the world that make sense to thought processes and can elicit appropriate action. This image understanding can be seen as the disentangling of symbolic information from image data using models constructed with the aid of [geometry](./Geometry), [physics](./Physics), [statistics](./Statistics), and learning theory.

 

The [scientific discipline](./Scientific_discipline) of computer vision is concerned with the theory behind artificial systems that extract information from images. Image data can take many forms, such as video sequences, views from multiple cameras, multi-dimensional data from a [3D scanner](./3D_scanning), 3D point clouds from [LiDaR](./Lidar) sensors, or medical scanning devices. The technological discipline of computer vision seeks to apply its theories and models to the construction of computer vision systems.

 

Subdisciplines of computer vision include [scene reconstruction](./3D_reconstruction), [object detection](./Object_detection), [event detection](./Event_detection), [activity recognition](./Activity_recognition), [video tracking](./Video_tracking), [object recognition](./Object_recognition), [3D pose estimation](./3D_pose_estimation), learning, indexing, [motion estimation](./Motion_estimation), [visual servoing](./Visual_servoing), [3D scene modeling](./3D_modeling), and [image restoration](./Digital_photograph_restoration).

 

## Definition

 

Computer vision is an [interdisciplinary field](./Interdisciplinarity) that deals with how computers can be made to gain high-level understanding from [digital images](./Digital_image) or [videos](./Video). From the perspective of [engineering](./Engineering), it seeks to automate tasks that the [human visual system](./Human_visual_system) can do.[[5]](./Computer_vision#cite_note-Ballard-Brown-1982-5)[[6]](./Computer_vision#cite_note-Huang-1996-6)[[7]](./Computer_vision#cite_note-Sonka-Hlavac-Boyle-2008-7) "Computer vision is concerned with the automatic extraction, analysis, and understanding of useful information from a single image or a sequence of images. It involves the development of a theoretical and algorithmic basis to achieve automatic visual understanding."[[8]](./Computer_vision#cite_note-bmva-8) As a [scientific discipline](./Scientific_discipline), computer vision is concerned with the theory behind artificial systems that extract information from images. The image data can take many forms, such as video sequences, views from multiple cameras, or multi-dimensional data from a [medical scanner](./Medical_scanner).[[9]](./Computer_vision#cite_note-9) As a technological discipline, computer vision seeks to apply its theories and models for the construction of computer vision systems. [Machine vision](./Machine_vision) refers to a systems engineering discipline, especially in the context of factory automation. In more recent times, the terms computer vision and machine vision have converged to a greater degree.[[10]](./Computer_vision#cite_note-davies5-10): 13 

 

## History

 

In the late 1960s, computer vision began at universities that were pioneering [artificial intelligence](./Artificial_intelligence). It was meant to mimic the [human visual system](./Human_visual_system) as a stepping stone to endowing robots with intelligent behavior.[[11]](./Computer_vision#cite_note-Szeliski2010-11) In 1966, it was believed that this could be achieved through an undergraduate summer project,[[12]](./Computer_vision#cite_note-12) by attaching a camera to a computer and having it "describe what it saw".[[13]](./Computer_vision#cite_note-Seymour1966-13)[[14]](./Computer_vision#cite_note-Boden2006-14)

 

What distinguished computer vision from the prevalent field of [digital image processing](./Digital_image_processing) at that time was a desire to extract [three-dimensional](./Three-dimensional) structure from images with the goal of achieving full scene understanding. Studies in the 1970s formed the early foundations for many of the computer vision [algorithms](./Algorithm) that exist today, including [extraction of edges](./Edge_detection) from images, labeling of lines, non-polyhedral and [polyhedral modeling](./Polyhedron_model), representation of objects as interconnections of smaller structures, [optical flow](./Optical_flow), and [motion estimation](./Motion_estimation).[[11]](./Computer_vision#cite_note-Szeliski2010-11)

 

The next decade saw studies based on more rigorous mathematical analysis and quantitative aspects of computer vision. These include the concept of [scale-space](./Scale_space), the inference of shape from various cues such as [shading](./Shading), texture and focus, and [contour models known as snakes](./Active_contour_model). Researchers also realized that many of these mathematical concepts could be treated within the same optimization framework as [regularization](./Regularization_(mathematics)) and [Markov random fields](./Markov_random_field).[[15]](./Computer_vision#cite_note-Kanade20122-15)
By the 1990s, some of the previous research topics became more active than others. Research in [projective](./Projective_geometry) [3-D reconstructions](./3D_reconstruction) led to better understanding of [camera calibration](./Camera_resectioning). With the advent of optimization methods for camera calibration, it was realized that a lot of the ideas were already explored in [bundle adjustment](./Bundle_adjustment) theory from the field of [photogrammetry](./Photogrammetry). This led to methods for sparse [3-D reconstructions of scenes from multiple images](./3D_reconstruction_from_multiple_images). Progress was made on the dense stereo [correspondence problem](./Correspondence_problem) and further multi-view stereo techniques. At the same time, [variations of graph cut](./Graph_cuts_in_computer_vision) were used to solve [image segmentation](./Image_segmentation). This decade also marked the first time statistical learning techniques were used in practice to recognize faces in images (see [Eigenface](./Eigenface)). Toward the end of the 1990s, a significant change came about with the increased interaction between the fields of [computer graphics](./Computer_graphics_(computer_science)) and computer vision. This included [image-based rendering](./Image-based_rendering), [image morphing](./Morphing), view interpolation, [panoramic image stitching](./Image_stitching) and early [light-field rendering](./Light_field).[[11]](./Computer_vision#cite_note-Szeliski2010-11)

 

Recent work has seen the resurgence of [feature](./Feature_(computer_vision))-based methods used in conjunction with machine learning techniques and complex optimization frameworks.[[16]](./Computer_vision#cite_note-Sebe2005-16)[[17]](./Computer_vision#cite_note-Freeman2008-17) 
The advancement of [Deep Learning](./Deep_learning) techniques has brought further life to the field of computer vision. The accuracy of deep learning algorithms on several benchmark computer vision data sets for tasks ranging from classification,[[18]](./Computer_vision#cite_note-NatureBengio-18) segmentation and optical flow has surpassed prior methods.[[19]](./Computer_vision#cite_note-19)[[20]](./Computer_vision#cite_note-20)

 

## Related fields

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Intersection_over_Union_-_object_detection_bounding_boxes.jpg/250px-Intersection_over_Union_-_object_detection_bounding_boxes.jpg)](./File:Intersection_over_Union_-_object_detection_bounding_boxes.jpg)[Object detection](./Object_detection) in a photograph 

### Solid-state physics

 

[Solid-state physics](./Solid-state_physics) is another field that is closely related to computer vision. Most computer vision systems rely on [image sensors](./Image_sensors), which detect [electromagnetic radiation](./Electromagnetic_radiation), which is typically in the form of either [visible](./Visible_light), [infrared](./Infrared_light) or [ultraviolet light](./Ultraviolet_light). The sensors are designed using [quantum physics](./Quantum_physics). The process by which light interacts with surfaces is explained using physics. Physics explains the behavior of [optics](./Optics) which are a core part of most imaging systems. Sophisticated image sensors even require [quantum mechanics](./Quantum_mechanics) to provide a complete understanding of the image formation process.[[11]](./Computer_vision#cite_note-Szeliski2010-11) Also, various measurement problems in physics can be addressed using computer vision, for example, motion in fluids.

 

### Neurobiology

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/0/0c/Simplified_neural_network_training_example.svg/250px-Simplified_neural_network_training_example.svg.png)](./File:Simplified_neural_network_training_example.svg)Simplified example of training a neural network in object detection: The network is trained by multiple images that are known to depict [starfish](./Starfish) and [sea urchins](./Sea_urchin), which are correlated with "nodes" that represent visual [features](./Feature_(computer_vision)). The starfish match with a ringed texture and a star outline, whereas most sea urchins match with a striped texture and oval shape. However, the instance of a ring-textured sea urchin creates a weakly weighted association between them.[![](//upload.wikimedia.org/wikipedia/commons/thumb/b/b7/Simplified_neural_network_example.svg/250px-Simplified_neural_network_example.svg.png)](./File:Simplified_neural_network_example.svg)Subsequent run of the network on an input image (left):[[21]](./Computer_vision#cite_note-21) The network correctly detects the starfish. However, the weakly weighted association between ringed texture and sea urchin also confers a weak signal to the latter from one of two intermediate nodes. In addition, a shell that was not included in the training gives a weak signal for the oval shape, also resulting in a weak signal for the sea urchin output. These weak signals may result in a [false positive](./False_positive) result for sea urchin.
In reality, textures and outlines would not be represented by single nodes, but rather by associated weight patterns of multiple nodes. 

[Neurobiology](./Neurobiology) has greatly influenced the development of computer vision algorithms. Over the last century, there has been an extensive study of eyes, neurons, and brain structures devoted to the processing of visual stimuli in both humans and various animals. This has led to a coarse yet convoluted description of how natural vision systems operate in order to solve certain vision-related tasks. These results have led to a sub-field within computer vision where artificial systems are designed to mimic the processing and behavior of biological systems at different levels of complexity. Also, some of the learning-based methods developed within computer vision (*e.g.* [neural net](./Artificial_neural_network) and [deep learning](./Deep_learning) based image and feature analysis and classification) have their background in neurobiology.  The [Neocognitron](./Neocognitron), a neural network developed in the 1970s by [Kunihiko Fukushima](./Kunihiko_Fukushima), is an early example of computer vision taking direct inspiration from neurobiology, specifically the [primary visual cortex](./Visual_cortex#Primary_visual_cortex_(V1)).

 

Some strands of computer vision research are closely related to the study of [biological vision](./Biological_vision)—indeed, just as many strands of [AI](./Artificial_intelligence) research are closely tied with research into human intelligence and the use of stored knowledge to interpret, integrate, and utilize visual information. The field of biological vision studies and models the physiological processes behind visual perception in humans and other animals. Computer vision, on the other hand, develops and describes the algorithms implemented in software and hardware behind artificial vision systems. An interdisciplinary exchange between biological and computer vision has proven fruitful for both fields.[[22]](./Computer_vision#cite_note-TextbookP1-22)

 

### Signal processing

 

Yet another field related to computer vision is [signal processing](./Signal_processing). Many methods for processing one-variable signals, typically temporal signals, can be extended in a natural way to the processing of two-variable signals or multi-variable signals in computer vision. However, because of the specific nature of images, there are many methods developed within computer vision that have no counterpart in the processing of one-variable signals. Together with the multi-dimensionality of the signal, this defines a subfield in signal processing as a part of computer vision.

 

### Robotic navigation

 

[Robot navigation](./Robot_navigation) sometimes deals with autonomous [path planning](./Path_planning) or deliberation for robotic systems to [navigate through an environment](./Robotic_navigation).[[23]](./Computer_vision#cite_note-23) A detailed understanding of these environments is required to navigate through them. Information about the environment could be provided by a computer vision system, acting as a vision sensor and providing high-level information about the environment and the robot

 

### Visual computing

 This section is an excerpt from [Visual computing](./Visual_computing).[[edit](https://en.wikipedia.org/w/index.php?title=Visual_computing&action=edit)] 

[Visual computing](./Visual_computing) is a generic term for all computer science disciplines dealing with images and [3D models](./3D_model), such as [computer graphics](./Computer_graphics), [image processing](./Image_processing), [visualization](./Visualization_(graphics)), computer vision, [virtual](./Virtual_reality) and [augmented reality](./Augmented_reality), [video processing](./Video_processing), and [computational visualistics](./Computational_visualistics). Visual computing also includes aspects of [pattern recognition](./Pattern_recognition), human computer interaction, machine learning and digital libraries. The core challenges are the acquisition, processing, analysis and rendering of visual information (mainly images and video). Application areas include industrial quality control, [medical image processing](./Medical_image_processing) and visualization, surveying, [robotics](./Robotics), multimedia systems, virtual heritage, special effects in movies and television, and [ludology](./Ludology). Visual computing also includes [digital art](./Digital_art) and [digital media](./Digital_media) studies.

   

### Other fields

 

Besides the above-mentioned views on computer vision, many of the related research topics can also be studied from a purely mathematical point of view. For example, many methods in computer vision are based on [statistics](./Statistics), [optimization](./Optimization_(mathematics)) or [geometry](./Geometry). Finally, a significant part of the field is devoted to the implementation aspect of computer vision; how existing methods can be realized in various combinations of software and hardware, or how these methods can be modified in order to gain processing speed without losing too much performance. Computer vision is also used in fashion eCommerce, inventory management, patent search, furniture, and the beauty industry.[[24]](./Computer_vision#cite_note-24)

 

### Distinctions

 

The fields most closely related to computer vision are [image processing](./Image_processing), [image analysis](./Image_analysis) and [machine vision](./Machine_vision). There is a significant overlap in the range of techniques and applications that these cover. This implies that the basic techniques that are used and developed in these fields are similar, something which can be interpreted as there is only one field with different names. On the other hand, it appears to be necessary for research groups, scientific journals, conferences, and companies to present or market themselves as belonging specifically to one of these fields and, hence, various characterizations which distinguish each of the fields from the others have been presented. In image processing, the input and output are both images, whereas in computer vision, the input is an image or video, and the output could be an enhanced image, an analysis of the image's content, or even a system's behavior based on that analysis.

 

[Computer graphics](./Computer_graphics) produces image data from 3D models, and computer vision often produces 3D models from image data.[[25]](./Computer_vision#cite_note-3DVAE-25) There is also a trend towards a combination of the two disciplines, *e.g.*, as explored in [augmented reality](./Augmented_reality).

 

The following characterizations appear relevant but should not be taken as universally accepted:

 
- [Image processing](./Image_processing) and [image analysis](./Image_analysis) tend to focus on 2D images, how to transform one image to another, *e.g.*, by pixel-wise operations such as contrast enhancement, local operations such as edge extraction or noise removal, or geometrical transformations such as rotating the image. This characterization implies that image processing/analysis neither requires assumptions nor produces interpretations about the image content.
- Computer vision includes 3D analysis from 2D images. This analyzes the 3D scene projected onto one or several images, *e.g.*, how to reconstruct structure or other information about the 3D scene from one or several images. Computer vision often relies on more or less complex assumptions about the scene depicted in an image.
- [Machine vision](./Machine_vision) is the process of applying a range of technologies and methods to provide imaging-based automatic inspection, process control, and robot guidance[[26]](./Computer_vision#cite_note-NASAarticle-26) in industrial applications.[[22]](./Computer_vision#cite_note-TextbookP1-22) Machine vision tends to focus on applications, mainly in manufacturing, *e.g.*, vision-based robots and systems for vision-based inspection, measurement, or picking (such as [bin picking](./Bin_picking)[[27]](./Computer_vision#cite_note-27)). This implies that image sensor technologies and control theory often are integrated with the processing of image data to control a robot and that real-time processing is emphasized by means of efficient implementations in hardware and software. It also implies that external conditions such as lighting can be and are often more controlled in machine vision than they are in general computer vision, which can enable the use of different algorithms.
- There is also a field called [imaging](./Imaging_science) which primarily focuses on the process of producing images, but sometimes also deals with the processing and analysis of images. For example, [medical imaging](./Medical_imaging) includes substantial work on the analysis of image data in medical applications. Progress in [convolutional neural networks](./Convolutional_neural_network) (CNNs) has improved the accurate detection of disease in medical images, particularly in cardiology, pathology, dermatology, and radiology.[[28]](./Computer_vision#cite_note-28)
- Finally, [pattern recognition](./Pattern_recognition) is a field that uses various methods to extract information from signals in general, mainly based on statistical approaches and [artificial neural networks](./Artificial_neural_networks).[[29]](./Computer_vision#cite_note-29) A significant part of this field is devoted to applying these methods to image data.

 

[Photogrammetry](./Photogrammetry) also overlaps with computer vision, e.g., [stereophotogrammetry](./Stereophotogrammetry) vs. [computer stereo vision](./Computer_stereo_vision).

 


