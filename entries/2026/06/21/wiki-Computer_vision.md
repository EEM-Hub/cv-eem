---
source: sources/wiki-Computer_vision.md
source_url: https://en.wikipedia.org/wiki/Computer_vision
---

## Computer Vision: Field Overview and Foundations

Computer vision is the interdisciplinary field concerned with enabling computers to extract high-level understanding from digital images and video. It encompasses acquiring, processing, analyzing, and understanding visual data to produce numerical or symbolic information that can drive decisions and actions. The field draws on geometry, physics, statistics, and learning theory to transform raw image data into structured scene descriptions.

## Key Concepts

- **Core definition**: Automating tasks the human visual system can do — extracting, analyzing, and understanding useful information from images or image sequences
- **Image understanding** = disentangling symbolic information from image data using models from geometry, physics, statistics, and learning theory
- **Input modalities**: video sequences, multi-camera views, 3D scanner data, LiDAR point clouds, medical imaging devices
- **Subdisciplines**: scene reconstruction, object detection, event detection, activity recognition, video tracking, object recognition, 3D pose estimation, motion estimation, visual servoing, 3D scene modeling, image restoration
- **Computer vision vs. image processing**: Image processing transforms images to images (2D focus); computer vision extracts 3D understanding and scene interpretations from images
- **Computer vision vs. machine vision**: Machine vision is the systems-engineering discipline focused on industrial applications (inspection, process control, robot guidance) with more controlled conditions; terms are converging
- **Computer vision vs. computer graphics**: Graphics produces images from 3D models; CV produces 3D models from images — inverse problems of each other
- **Deep learning impact**: CNNs and deep learning have surpassed prior methods on benchmarks for classification, segmentation, and optical flow

## Commands and Syntax

No specific commands — this is a conceptual overview article. Relevant tooling includes:
- **MediaPipe**: Google's open-source framework for AI edge-device computing (face detection, image classification, object detection)
- **Vision Transformers (ViT)**: Used for domain-specific classification (e.g., crop disease detection at 98.4% accuracy)
- **SLAM** (Simultaneous Localization and Mapping): Navigation algorithm family for autonomous vehicles

## Relationships

- **Solid-state physics**: Image sensors detect electromagnetic radiation (visible, IR, UV); quantum physics governs sensor design and image formation
- **Neurobiology**: Biological vision systems inspired CV algorithms; neural networks and deep learning originated from neuroscience models; the Neocognitron (1970s, Fukushima) drew directly from primary visual cortex
- **Signal processing**: Many 1D signal processing methods extend to 2D/multi-dimensional image signals, but CV has unique methods with no 1D counterpart
- **Robotics/Navigation**: CV provides high-level environment understanding for autonomous path planning and robot guidance
- **Photogrammetry**: Overlaps significantly (stereophotogrammetry vs. computer stereo vision); bundle adjustment theory from photogrammetry informed 3D reconstruction methods
- **Pattern recognition**: Uses statistical and neural network methods to extract information from signals, with substantial image-data applications
- **Augmented reality**: Combines computer graphics and computer vision (tracking surfaces/planes in 3D)

## Exam-Relevant Points

- **Historical timeline**: CV began late 1960s at AI-pioneering universities; 1970s established edge detection, optical flow, motion estimation; 1980s introduced scale-space, snakes (active contour models), regularization, MRFs; 1990s brought camera calibration, sparse/dense 3D reconstruction, graph cuts for segmentation, Eigenface for face recognition; 2010s+ deep learning revolution
- **The 1966 "Summer Vision Project"**: Famously underestimated — believed CV could be solved in one undergraduate summer project
- **Key distinction triple**: Image processing (image→image, 2D), Computer vision (image→understanding, 2D→3D), Machine vision (CV applied to industrial automation with controlled conditions)
- **Computer graphics is the inverse of computer vision**: Graphics: 3D models → images; CV: images → 3D models
- **Application domains by 2024 market size**: Industry ($5.22B), Medicine ($2.6B), Military ($996.2M)
- **Medical CV**: Tumor detection, organ measurement, image enhancement (ultrasound, X-ray); CNNs improved disease detection in cardiology, pathology, dermatology, radiology
- **Autonomous vehicles**: Use CV for navigation (SLAM), obstacle detection, event detection; applies to submersibles, land vehicles, aerial/UAV, and space rovers (Curiosity, Yutu-2)
- **Optical sorting**: Machine vision application in agriculture for removing undesirable foodstuff from bulk material
- **Neocognitron** (Fukushima, 1970s): Early neural network directly inspired by primary visual cortex — bridges neurobiology and CV
