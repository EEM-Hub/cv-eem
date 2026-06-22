---
source: sources/wiki-Image_classification.md
source_url: https://en.wikipedia.org/wiki/Image_classification
---

## Computer Vision: Field Overview and Foundations

Computer vision is an interdisciplinary field concerned with enabling computers to extract high-level understanding from digital images and video. It encompasses acquiring, processing, analyzing, and understanding visual data to produce numerical or symbolic information that can drive decisions and actions. The field draws on geometry, physics, statistics, and learning theory to transform raw image data into structured descriptions of the world.

## Key Concepts

- **Core definition**: Transformation of visual images into world descriptions that can elicit appropriate action — "disentangling symbolic information from image data"
- **Input modalities**: Video sequences, multi-camera views, 3D scanner data, LiDAR point clouds, medical imaging
- **Subdisciplines**: Scene reconstruction, object detection, event detection, activity recognition, video tracking, object recognition, 3D pose estimation, motion estimation, visual servoing, 3D scene modeling, image restoration
- **Distinction from image processing**: Image processing transforms images to images (2D); computer vision extracts 3D understanding and semantic interpretation from images
- **Machine vision**: Systems engineering discipline applying CV in industrial/factory automation contexts with controlled conditions
- **Computer graphics is the inverse**: Graphics produces images from 3D models; CV produces 3D models from images
- **Deep learning revolution**: Deep learning methods now surpass prior approaches on benchmark tasks including classification, segmentation, and optical flow

## Historical Milestones

- **1966**: MIT summer project attempted to have a computer "describe what it saw" — dramatically underestimated the problem's difficulty
- **1970s**: Edge detection, optical flow, motion estimation, polyhedral modeling, line labeling
- **1980s**: Scale-space theory, shape-from-shading, active contour models (snakes), regularization, Markov random fields
- **1990s**: Camera calibration via bundle adjustment, sparse/dense 3D reconstruction, graph cuts for segmentation, Eigenface for face recognition, image-based rendering, panoramic stitching
- **2000s–present**: Feature-based methods combined with machine learning; deep learning (CNNs, vision transformers) dramatically improved accuracy

## Commands and Syntax

No specific CLI commands in this source. Key algorithmic/framework references:

- **MediaPipe**: Google's open-source framework for AI edge computing (face detection, image classification, object detection)
- **SLAM** (Simultaneous Localization and Mapping): Navigation algorithm for autonomous vehicles
- **Vision Transformers (ViT)**: Architecture achieving high accuracy (e.g., 98.4% on strawberry disease detection)

## Relationships

- **Solid-state physics**: Image sensors rely on quantum physics for electromagnetic radiation detection (visible, IR, UV light)
- **Neurobiology**: Inspired neural network architectures; Neocognitron (1970s, Fukushima) modeled primary visual cortex; CNNs and deep learning trace lineage here
- **Signal processing**: Many 1D signal processing methods extend to 2D/multi-dimensional image signals, though CV has unique methods with no 1D counterpart
- **Robotics/Navigation**: CV provides environmental understanding for path planning, obstacle detection, autonomous navigation
- **Photogrammetry**: Overlaps significantly — stereophotogrammetry parallels computer stereo vision; bundle adjustment originated in photogrammetry
- **Pattern recognition**: Statistical and neural network methods for extracting information from signals, heavily applied to image data
- **Augmented reality**: Convergence point of computer vision and computer graphics

## Exam-Relevant Points

- Computer vision input is images/video; output is understanding, decisions, or enhanced representations — this distinguishes it from image processing (image-to-image)
- The 1966 MIT summer project is a canonical example of underestimating CV complexity
- **Eigenface** (1990s) was the first practical use of statistical learning for face recognition
- **Bundle adjustment** originated in photogrammetry, not computer vision — CV rediscovered it for camera calibration
- Leading application markets (2024): Industry ($5.22B), Medicine ($2.6B), Military ($996.2M)
- Key application domains: medical imaging (tumor detection, diagnostics), machine vision (quality control, wafer inspection, optical sorting), autonomous vehicles (SLAM, obstacle detection), military (missile guidance, battlefield awareness)
- **Graph cuts** were used for image segmentation in the 1990s
- The **Neocognitron** (Fukushima, 1970s) is the earliest example of CV architecture directly inspired by the visual cortex
- Machine vision differs from general CV in having more controlled external conditions (lighting, positioning), enabling different algorithmic approaches
- Autonomous vehicles use CV for: navigation, environment mapping (SLAM), obstacle detection, and task-specific event detection
