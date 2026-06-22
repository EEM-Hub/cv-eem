---
source: sources/wiki-Feature_detection_computer_vision.md
source_url: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
---

## Features and Feature Detection in Computer Vision

This page covers the concept of **features** in computer vision — what they are, how they are detected, the major feature types (edges, corners, blobs, ridges), how features are represented and matched, and the key algorithms used for detection and description. Features are the fundamental building blocks that nearly all CV algorithms operate on.

## Key Concepts

- A **feature** is a piece of information about image content — a point, edge, region, or other structure deemed "interesting" for a given task. There is no universal definition; it depends on the application.
- **Feature detection** is a low-level image processing operation that examines every pixel to determine if a feature is present. It is typically the first step in a CV pipeline.
- **Repeatability** is the most desirable property of a feature detector: the same feature should be detected across multiple images of the same scene.
- Input images are usually pre-smoothed with a **Gaussian kernel** in a **scale-space representation** before feature computation.
- **Feature extraction** applies local neighborhood operations to produce either binary decisions (feature present/absent) or continuous-valued **feature images**.
- A **feature vector** aggregates multiple feature descriptors at each image point into a single vector; the set of all possible feature vectors forms the **feature space**.
- A **feature descriptor** is a specific instance of a feature representation (e.g., SIFT descriptor, HOG descriptor).
- **Feature matching** establishes correspondences between features detected in different images of the same scene.

## Feature Types (Four Major Categories)

- **Edges** — Boundaries between image regions; points with strong gradient magnitude. Locally one-dimensional structure. Detectors: Canny, Sobel, Harris.
- **Corners / Interest points** — Point-like features with local two-dimensional structure. Originally found by detecting rapid direction changes in edges, now detected directly via curvature in image gradients. Detectors: Harris & Stephens, SUSAN, Shi & Tomasi, FAST.
- **Blobs / Regions of interest** — Complementary to corners; describe regions rather than points. Can detect areas too smooth for corner detectors. Detectors: LoG, DoG, DoH, MSER.
- **Ridges** — Elongated structures representable as 1D curves with associated width (generalization of medial axis). Harder to extract algorithmically. Used for road extraction in aerial images and blood vessel extraction in medical images.

## Commands and Syntax

No CLI commands per se, but the critical **detector capability matrix**:

| Detector | Edge | Corner | Blob | Ridge |
|----------|------|--------|------|-------|
| Canny | Yes | No | No | No |
| Sobel | Yes | No | No | No |
| Harris & Stephens | Yes | Yes | No | No |
| SUSAN | Yes | Yes | No | No |
| Shi & Tomasi | No | Yes | No | No |
| FAST | No | Yes | No | No |
| LoG | No | Yes | Yes | No |
| DoG | No | Yes | Yes | No |
| DoH | No | Yes | Yes | No |
| MSER | No | No | Yes | No |
| Principal curvature | No | No | No | Yes |

**Key descriptors**: SIFT, SURF, GLOH, HOG.

**Shape-based methods**: Thresholding, blob extraction, template matching, Hough transform (lines, circles, arbitrary shapes via generalized Hough transform).

## Relationships

- **Scale-space theory** — Features are often computed across multiple scales; SIFT is the canonical example of scale-invariant detection.
- **Machine learning / Pattern recognition** — Feature vectors feed into classifiers; neural networks learn which feature combinations solve the task.
- **Edge detection** feeds into corner detection (historically); corner detection relates to blob detection at different scales.
- **Image derivatives** — Most feature detectors are expressed in terms of local derivative operations (gradient, Hessian, Laplacian).
- **Correspondence problem** — Feature matching across images is the foundation for stereo vision, structure from motion, and object recognition.
- **Structure tensor** — Provides an averageable representation of orientation; connects to affine-invariant feature detection.

## Exam-Relevant Points

- **Repeatability** is the single most important property of a feature detector.
- Know which detectors handle which feature types (the capability matrix above is high-yield).
- **Canny** = edges only. **Harris** = edges + corners. **LoG/DoG/DoH** = corners + blobs. **MSER** = blobs only. **FAST** = corners only (and is designed for speed).
- Feature detection is a **low-level** operation — first step in the pipeline, examines every pixel.
- **Feature image** vs. **feature descriptor**: a feature image maps spatial coordinates to feature information; a feature descriptor is a vector at a specific point.
- **Averageability** matters for representation choice: angle-based orientation representations have discontinuities and are NOT averageable; the structure tensor IS averageable.
- **Gaussian smoothing** in scale-space is a standard prerequisite before feature detection.
- SIFT (Scale-Invariant Feature Transform) is the canonical example of multi-scale feature extraction using DoG.
- Blob detectors can detect what corner detectors miss (smooth regions), and the distinction blurs at different scales.
- Ridges are algorithmically harder to extract than edges, corners, or blobs.
