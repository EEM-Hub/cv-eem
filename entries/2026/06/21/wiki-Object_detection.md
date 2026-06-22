---
source: sources/wiki-Object_detection.md
source_url: https://en.wikipedia.org/wiki/Object_detection
---

## Object Detection in Computer Vision

Object detection is a core computer vision task that identifies and localizes instances of semantic object classes (e.g., humans, cars, buildings) in images and videos. It combines classification (what is it?) with localization (where is it?), and underpins applications from video surveillance and autonomous driving to face recognition and activity recognition.

## Key Concepts

- **Object detection** = classification + localization — the system must both identify the object class and draw a bounding box around it
- **Intersection over Union (IoU)** — the primary metric for evaluating localization accuracy; computed as the area of overlap between predicted and ground-truth bounding boxes divided by their union
- **True positive** — a predicted bounding box with IoU above a threshold (commonly 0.5) and correct class label
- **False positive** — a prediction with IoU below threshold, or a duplicate prediction for an already-matched ground truth
- **False negative** — a ground-truth object with no matching prediction above the IoU threshold
- **Mean Average Precision (mAP)** — the standard benchmark metric; average of per-class AP, where AP is the area under the precision-recall curve as confidence threshold varies
- **Domain gap** — performance degrades when test images come from a different distribution than training data; addressed via unsupervised domain adaptation techniques (e.g., CycleGAN for image-to-image translation)
- **Feature-based classification** — objects are detected by identifying class-specific visual features (shape, texture, color, spatial relationships)

## Commands and Syntax

Not applicable (conceptual topic). However, a common practical example referenced:

- **OpenCV DNN module** can load a YOLOv3 model trained on COCO to detect 80 common object classes

## Relationships

- **Parent field**: Computer vision, image processing
- **Evaluation metrics**: IoU, precision-recall curves, mAP — shared with information retrieval evaluation
- **Feature extraction**: Connects to feature detection (SIFT, HOG, Haar features) for non-neural methods
- **Downstream tasks**: Image annotation, activity recognition, video tracking, video surveillance, pedestrian detection, face detection/recognition, autonomous driving
- **Model families**:
  - **Two-stage detectors** (region proposal): R-CNN → Fast R-CNN → Faster R-CNN → Cascade R-CNN
  - **One-stage detectors**: YOLO, SSD, RefineDet, RetinaNet
  - **Transformer-based**: DETR (Detection Transformer) uses vision transformers
  - **Classical/non-neural**: Viola-Jones (Haar), SIFT, HOG + SVM
- **Domain adaptation**: CycleGAN, adversarial training — connects to generative models and transfer learning
- **Related subtasks**: Moving object detection, small object detection, video object co-segmentation

## Exam-Relevant Points

- **IoU threshold of 0.5** is the standard for determining true positives in object localization
- **mAP** is the primary benchmark metric — know that it averages per-class AP values, each computed as area under the precision-recall curve
- **Two-stage vs. one-stage detectors**: Two-stage (R-CNN family) first propose regions then classify; one-stage (YOLO, SSD) predict boxes and classes in a single pass, trading some accuracy for speed
- **R-CNN evolution**: R-CNN → Fast R-CNN → Faster R-CNN represents progressive improvements in speed by sharing computation (RoI pooling, Region Proposal Networks)
- **YOLO** = "You Only Look Once" — frames detection as a single regression problem, enabling real-time detection
- **RetinaNet** introduced **focal loss** to address class imbalance between foreground and background in dense detection
- **DETR** applies transformers to detection, eliminating the need for hand-designed components like anchor boxes and NMS
- **Non-neural methods** (Viola-Jones, HOG+SVM, SIFT) require explicit feature engineering; neural methods learn features end-to-end
- **When multiple predictions exist** for a single ground truth, only the highest-IoU prediction (if above threshold) counts as a true positive; all others are false positives
- **Domain adaptation** is critical for real-world deployment — models trained on synthetic data (e.g., video games) can transfer to real-world scenes (e.g., autonomous driving) using techniques like CycleGAN
