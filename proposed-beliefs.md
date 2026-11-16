# Proposed Beliefs

Review each entry: change `[ACCEPT]` to `[ACCEPT]` to keep, or vice versa.
Then run: `expert-build accept-beliefs`

---

**Generated:** 2026-06-21
**Source:** 10 entries from entries/
**Model:** claude

### [ACCEPT] semantic-seg-assigns-class-per-pixel
Semantic segmentation assigns a class label to every pixel but does not distinguish individual object instances.
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] instance-seg-distinguishes-objects
Instance segmentation identifies each distinct object instance per pixel, assigning different labels to different instances of the same class.
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] panoptic-seg-combines-semantic-instance
Panoptic segmentation combines semantic and instance segmentation, assigning every pixel both a class label and an instance-level identity.
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] otsu-maximizes-interclass-variance
Otsu's thresholding method selects the optimal threshold by maximizing inter-class variance between foreground and background pixel intensities.
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] kmeans-converges-not-global-optimum
K-means clustering is guaranteed to converge but is not guaranteed to find the global optimum; solution quality depends on initialization and choice of K.
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] mean-shift-no-cluster-count-required
Mean Shift clustering does not require specifying the number of clusters a priori, unlike K-means.
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] laplacian-isolated-point-kernel
The discrete Laplacian operator for isolated point detection sums 4 neighbors minus 4 times the center pixel: nabla^2 f(x,y) = f(x+1,y) + f(x-1,y) + f(x,y+1) + f(x,y-1) - 4f(x,y).
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] histogram-segmentation-single-pass
Histogram-based segmentation methods require only one pass through the pixels, making them the most efficient category of segmentation algorithms.
- Source: entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation

### [ACCEPT] object-detection-classification-plus-localization
Object detection combines classification (identifying the object class) with localization (drawing a bounding box around it).
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] iou-overlap-over-union
Intersection over Union (IoU) is computed as the area of overlap between predicted and ground-truth bounding boxes divided by the area of their union.
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] iou-threshold-0.5-standard
The standard IoU threshold for determining a true positive detection in object localization is 0.5.
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] map-averages-per-class-ap
Mean Average Precision (mAP) is computed by averaging per-class AP values, where each AP is the area under the precision-recall curve as the confidence threshold varies.
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] two-stage-detectors-propose-then-classify
Two-stage detectors (R-CNN family) first propose candidate regions then classify each region, while one-stage detectors (YOLO, SSD) predict boxes and classes in a single pass.
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] rcnn-evolution-progressive-speedup
The R-CNN evolution (R-CNN → Fast R-CNN → Faster R-CNN) achieved progressive speed improvements by sharing computation via RoI pooling and Region Proposal Networks.
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] yolo-single-regression-realtime
YOLO (You Only Look Once) frames object detection as a single regression problem over the entire image, enabling real-time detection.
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] retinanet-focal-loss-class-imbalance
RetinaNet introduced focal loss to address the severe class imbalance between foreground objects and background in dense one-stage detection.
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] detr-eliminates-anchors-and-nms
DETR (Detection Transformer) applies transformers to object detection, eliminating hand-designed components like anchor boxes and non-maximum suppression (NMS).
- Source: entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection

### [ACCEPT] aperture-problem-one-eq-two-unknowns
The aperture problem in optical flow arises because the brightness constancy constraint provides one equation but two unknowns (u, v) per pixel, requiring additional constraints.
- Source: entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow

### [ACCEPT] horn-schunck-global-dense-flow
Horn-Schunck is a global/regularized optical flow method that produces dense flow fields by minimizing a cost function combining a data term and a smoothness penalty with quadratic regularization Ψ(x) = x².
- Source: entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow

### [ACCEPT] lucas-kanade-local-sparse-flow
Lucas-Kanade is a local/parametric optical flow method that assumes purely translational motion within rectangular patches, producing sparse flow estimates.
- Source: entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow

### [ACCEPT] optical-flow-linearization-small-displacement
The linearization of the brightness constancy constraint via first-order Taylor expansion (Ix·u + Iy·v + It = 0) is only valid for small displacements; coarse-to-fine pyramids are the standard remedy.
- Source: entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow

### [ACCEPT] raft-replaces-coarse-to-fine-with-gru
RAFT replaced coarse-to-fine pyramids with iterative GRU-based updates at a fixed 1/8 resolution, improving fine detail preservation and fast-motion robustness.
- Source: entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow

### [ACCEPT] optical-flow-alpha-smoothness-tradeoff
In optical flow regularization, the parameter α controls the trade-off between data fidelity and flow smoothness — higher α yields smoother but potentially less accurate flow fields.
- Source: entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow

### [ACCEPT] gibson-coined-optic-flow-1950
James J. Gibson coined the term 'optic flow' in 1950, based on research into pilot vision during landing originating in WWII.
- Source: entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow

### [ACCEPT] 6dof-pose-3rot-3trans
A full 6DoF pose consists of 3 rotation parameters and 3 translation parameters.
- Source: entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation

### [ACCEPT] posit-single-uncalibrated-noncoplanar
The POSIT algorithm (Dementhon & Davis, 1995) estimates 3D pose from a single uncalibrated image using iterative correction, but requires non-coplanar 3D model points.
- Source: entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation

### [ACCEPT] icp-iterative-pose-refinement
ICP-based pose estimation iteratively refines correspondences between 2D projection rays and 3D contour points to estimate object pose.
- Source: entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation

### [ACCEPT] pose-occlusion-rigid-coupling
Handling partial occlusion in ICP-based pose estimation requires the assumption that object contours are rigidly coupled, so the pose of one visible contour constrains occluded ones.
- Source: entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation

### [ACCEPT] database-pose-recognizes-not-determines
Database comparison methods for pose estimation recognize pose by matching against pre-computed examples rather than analytically determining it, limiting accuracy to stored poses.
- Source: entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation

### [ACCEPT] slam-joint-pose-and-map-estimation
SLAM jointly estimates both agent pose and environment map from sensor observations and control inputs, with neither known a priori.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] ekf-slam-gaussian-linearization-limitation
EKF SLAM assumes Gaussian noise and fails under high uncertainty because linearization errors accumulate.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] graphslam-sparse-information-matrix
GraphSLAM builds a factor graph of observation interdependencies and solves via sparse optimization, exploiting the sparsity of the information matrix.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] loop-closure-corrects-drift-bow-sift
Loop closure in SLAM recognizes previously visited locations to correct accumulated drift, commonly using bag-of-words over SIFT features for revisit detection.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] active-slam-entropy-exploration
Active SLAM combines mapping with exploration planning, using entropy reduction to decide where the agent should move next to maximize information gain.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] slam-acronym-coined-1995
The acronym SLAM was coined in 1995; foundational work on spatial uncertainty by Smith and Cheeseman was published in 1986.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] self-driving-simplifies-slam-to-localization
Modern self-driving cars often simplify SLAM to localization-only by using pre-collected HD maps, avoiding the need for simultaneous mapping.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] sfm-offline-slam-online-counterpart
Structure from Motion (SfM) is the offline counterpart to SLAM; SLAM solves the same reconstruction problem in real-time.
- Source: entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping

### [ACCEPT] cv-field-began-late-1960s
Computer vision as a field began in the late 1960s at universities pioneering artificial intelligence research.
- Source: entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] 1966-summer-vision-project-underestimated-cv
The 1966 MIT 'Summer Vision Project' famously underestimated computer vision, believing it could be solved in one undergraduate summer project.
- Source: entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] image-processing-vs-cv-distinction
Image processing transforms images to images (2D focus), while computer vision extracts 3D understanding and scene interpretations from images.
- Source: entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cv-inverse-of-computer-graphics
Computer graphics produces images from 3D models; computer vision produces 3D models from images — they are inverse problems of each other.
- Source: entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] neocognitron-fukushima-1970s-visual-cortex
The Neocognitron (Fukushima, 1970s) was an early neural network directly inspired by the primary visual cortex, bridging neurobiology and computer vision.
- Source: entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cv-market-2024-industry-5-22b
By 2024, computer vision application market sizes were: Industry ($5.22B), Medicine ($2.6B), Military ($996.2M).
- Source: entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] machine-vision-industrial-controlled-conditions
Machine vision is the systems-engineering discipline focused on industrial applications (inspection, process control, robot guidance) with more controlled external conditions than general computer vision.
- Source: entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision

### [ACCEPT] cnn-weight-sharing-parameter-efficiency
CNNs achieve parameter efficiency through weight sharing: a 100x100 image needs 10,000 weights per neuron in a fully connected layer but only 25 weights per 5x5 convolutional kernel.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-translation-equivariant-not-invariant
CNNs produce translation-equivariant feature maps but are generally NOT translation-invariant due to downsampling operations.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] cnn-correlation-called-convolution
Modern CNN implementations actually perform correlation and call it convolution — mathematically equivalent for learned weights since weight reversal doesn't affect the final learned function.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] depthwise-separable-convolution-definition
Depthwise separable convolution consists of a spatial convolution applied independently per channel (depthwise), followed by a 1x1 convolution (pointwise), reducing computational cost.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] transpose-convolution-checkerboard-artifacts
Transpose convolution (deconvolution) is prone to checkerboard artifacts; the fix is to upscale then convolve instead.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] dilated-convolution-expands-receptive-field
Dilated (atrous) convolution expands the receptive field without increasing parameters by interleaving visible and blind regions in the kernel.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] lenet5-1995-deployed-us-banks
LeNet-5 (1995) was a 7-layer CNN for check reading that was deployed in US banks.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] alexnet-2012-imagenet-deep-learning-revolution
AlexNet (2012) was a GPU-trained deep CNN that won the ImageNet competition, triggering the deep learning revolution in computer vision.
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] neocognitron-1980-first-trainable-cnn
The Neocognitron (1980, Fukushima) was the first trainable CNN architecture, introducing the two fundamental layer types: convolutional (S-layer) and downsampling/pooling (C-layer).
- Source: entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network

### [ACCEPT] feature-detector-repeatability-most-important
Repeatability is the single most important property of a feature detector — the same feature should be detected across multiple images of the same scene.
- Source: entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)

### [ACCEPT] four-major-feature-types
The four major feature types in computer vision are edges, corners (interest points), blobs (regions of interest), and ridges.
- Source: entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)

### [ACCEPT] feature-detector-capability-matrix
Feature detector capabilities: Canny detects edges only; Harris detects edges+corners; FAST detects corners only (designed for speed); MSER detects blobs only; LoG/DoG/DoH detect corners+blobs.
- Source: entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)

### [ACCEPT] sift-uses-dog-multiscale
SIFT (Scale-Invariant Feature Transform) is the canonical example of multi-scale feature extraction, using Difference of Gaussians (DoG) for scale-invariant detection.
- Source: entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)

### [ACCEPT] structure-tensor-averageable-angle-not
The structure tensor provides an averageable representation of orientation; angle-based orientation representations have discontinuities and are NOT averageable.
- Source: entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)

### [ACCEPT] ridges-harder-to-extract-than-other-features
Ridges are algorithmically harder to extract than edges, corners, or blobs; they are used for road extraction in aerial images and blood vessel extraction in medical images.
- Source: entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)

### [ACCEPT] gan-introduced-goodfellow-june-2014
Generative adversarial networks (GANs) were introduced by Ian Goodfellow et al. in June 2014.
- Source: entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-zero-sum-game-generator-discriminator
A GAN is a two-player zero-sum game where the generator minimizes and the discriminator maximizes the same objective function L(G, D).
- Source: entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-optimal-discriminator-jensen-shannon
The optimal GAN discriminator effectively computes the Jensen-Shannon divergence between the real and generated distributions.
- Source: entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-implicit-generative-model-no-inversion
GANs are implicit generative models — they do not explicitly model the likelihood function and cannot find the latent variable for a given sample (no inversion).
- Source: entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-single-pass-generation
GANs generate a complete sample in one forward pass, unlike autoregressive models (WaveNet, PixelRNN) which require multiple sequential passes.
- Source: entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] gan-asymptotically-consistent
GANs are asymptotically consistent due to the universal approximation theorem for neural networks.
- Source: entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network

### [ACCEPT] eigenface-1990s-first-statistical-face-recognition
Eigenface (1990s) was the first practical application of statistical learning for face recognition in computer vision.
- Source: entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification

### [ACCEPT] bundle-adjustment-originated-photogrammetry
Bundle adjustment theory originated in photogrammetry, not computer vision — CV rediscovered and adopted it for camera calibration and 3D reconstruction.
- Source: entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification

### [ACCEPT] graph-cuts-image-segmentation-1990s
Graph cuts were introduced for image segmentation in the 1990s as part of the computer vision pipeline.
- Source: entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification


---

**Generated:** 2026-06-21
**Source:** 28 entries from entries/
**Model:** claude

### [ACCEPT] harris-response-avoids-eigendecomposition
The Harris corner response R = det(M) - k·tr(M)² (k typically 0.04–0.06) detects corners without explicit eigenvalue computation, using det(M) = λ1·λ2 and tr(M) = λ1 + λ2.
- Source: entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector

### [ACCEPT] harris-eigenvalue-corner-edge-flat
The structure tensor's eigenvalues classify local image structure: both large = corner, one large and one small = edge, both small = flat region.
- Source: entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector

### [ACCEPT] harris-rotation-illumination-invariant-not-scale
The Harris detector is invariant to rotation and illumination changes but not scale-invariant; the Harris-Laplace extension adds scale invariance via Laplacian-of-Gaussian.
- Source: entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector

### [ACCEPT] harris-improved-moravec-gradient-vs-patch
Harris (1988) improved Moravec's corner detector by replacing discrete patch shifting at 45-degree intervals with continuous gradient-based differential analysis of the structure tensor.
- Source: entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector

### [ACCEPT] structure-tensor-2x2-gradient-product-matrix
The structure tensor M = [[Σ(Ix²), Σ(IxIy)], [Σ(IxIy), Σ(Iy²)]] is a 2×2 symmetric matrix built from image gradient products summed over a local window, encoding local gradient distribution.
- Source: entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector

### [ACCEPT] harris-pipeline-five-steps
The Harris detection pipeline has five steps: grayscale conversion (0.299R + 0.587G + 0.114B), Sobel spatial derivatives, structure tensor construction, Harris response computation, and non-maximum suppression in a 3×3 window.
- Source: entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector

### [ACCEPT] hough-rho-theta-avoids-unbounded-slope
The Hough transform for lines uses the Hesse normal form r = x·cos(θ) + y·sin(θ), avoiding the unbounded-slope problem of y = mx + b for vertical lines.
- Source: entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform

### [ACCEPT] hough-point-maps-to-sinusoid-in-parameter-space
A single image point maps to a sinusoidal curve in (r, θ) Hough space; collinear points produce sinusoids that intersect at the same (r, θ), converting collinear-point detection to concurrent-curve detection.
- Source: entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform

### [ACCEPT] hough-mathematically-equivalent-to-radon
The Hough transform is mathematically equivalent to the Radon transform in 2D.
- Source: entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform

### [ACCEPT] hough-accumulator-dims-equal-shape-params
Hough accumulator dimensionality equals the number of shape parameters: 2 for lines (r, θ), 3 for circles with unknown radius (a, b, r), 3 for planes (θ, φ, ρ).
- Source: entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform

### [ACCEPT] hough-robust-to-noise-gaps-occlusion
The Hough transform handles noise, gaps, and partial occlusion because it accumulates evidence globally rather than relying on local edge-linking; ignoring negative evidence enables partial-occlusion robustness.
- Source: entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform

### [ACCEPT] generalized-hough-r-table-arbitrary-shapes
The Generalized Hough Transform (Ballard, 1981) detects arbitrary non-analytic shapes using a precomputed R-table look-up so features vote for position, orientation, and scale of template shapes.
- Source: entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform

### [ACCEPT] hough-returns-infinite-lines-no-endpoints
The Hough transform returns infinite lines with no endpoint information; a post-processing step is required to determine which image segments correspond to detected lines.
- Source: entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform

### [ACCEPT] gaussian-pyramid-smooth-subsample-by-two
A Gaussian pyramid is built by applying Gaussian blur then subsampling by factor 2 in each dimension (4× area reduction per level); each level has lower resolution and increased smoothing.
- Source: entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid

### [ACCEPT] laplacian-pyramid-difference-plus-coarsest
A Laplacian pyramid stores difference images between adjacent Gaussian pyramid levels plus the coarsest Gaussian level directly, enabling full image reconstruction from coarse to fine (Burt & Adelson, 1983).
- Source: entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid

### [ACCEPT] pyramid-canonical-binomial-kernel
The binomial kernel [1/4, 1/2, 1/4] is the canonical smoothing filter for image pyramid generation, derived from binomial coefficients.
- Source: entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid

### [ACCEPT] pyramids-discrete-scales-vs-continuous-scalespace
Image pyramids provide representations only at discrete fixed scale levels (powers of 2), unlike continuous scale-space which allows representation at arbitrary scales; pyramids are computationally efficient approximations to full scale-space.
- Source: entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid

### [ACCEPT] steerable-pyramid-orientation-selective
The steerable pyramid (Simoncelli) is a multi-scale, multi-orientation bandpass filter bank that adds orientation selectivity to the Laplacian pyramid concept using steerable filters at each level.
- Source: entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid

### [ACCEPT] registration-intensity-vs-feature-based
Image registration methods divide into intensity-based (comparing intensity patterns via correlation metrics over entire images) and feature-based (finding correspondences between distinct features then computing a geometric transformation).
- Source: entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration

### [ACCEPT] mutual-information-preferred-multimodal-registration
Mutual information is the preferred similarity measure for multi-modality image registration (e.g., CT/MRI fusion); cross-correlation and SSD are used for same-modality registration.
- Source: entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration

### [ACCEPT] phase-correlation-fft-noise-resilient
Phase correlation performs image registration in the frequency domain using FFT; it is resilient to noise and occlusions, and extends to rotation/scaling detection via log-polar coordinates.
- Source: entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration

### [ACCEPT] diffeomorphisms-topology-preserving-via-flows
Diffeomorphisms are smooth, invertible, topology-preserving transformations composed via function composition (not addition), generated via flows; central to LDDMM methods in computational anatomy.
- Source: entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration

### [ACCEPT] rigid-registration-six-degrees-of-freedom
Rigid image registration (e.g., in radiation therapy) uses 6 degrees of freedom: 3 translational and 3 rotational parameters.
- Source: entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration

### [ACCEPT] image-restoration-four-distinct-subfields
Image restoration is an umbrella term spanning four distinct areas: physical photograph conservation, digital photograph restoration, AI-based image restoration, and iterative reconstruction (commonly used in medical imaging).
- Source: entries/2026/06/21/wiki-Image_restoration.md
- Source URL: https://en.wikipedia.org/wiki/Image_restoration

### [ACCEPT] data-augmentation-origin-statistical-1977
Data augmentation originated as a statistical method for maximum likelihood estimation from incomplete data (Dempster, Laird, Rubin, 1977) before becoming standard in deep learning.
- Source: entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation

### [ACCEPT] smote-interpolates-in-feature-space
SMOTE generates synthetic minority class samples by interpolating between nearest neighbors along line segments in feature space, not pixel space — addressing class imbalance without duplicating existing samples.
- Source: entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation

### [ACCEPT] data-augmentation-is-implicit-regularization
Data augmentation functions as implicit regularization alongside dropout, weight decay, and batch normalization, preventing the model from memorizing training data.
- Source: entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation

### [ACCEPT] augmentation-label-preserving-requirement
Data augmentation requires that transformed images retain correct class labels (label-preserving property); some geometric transforms can change semantic meaning (e.g., horizontally flipping a '6' creates a different digit), making label preservation context-dependent.
- Source: entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation

### [ACCEPT] augmentation-training-time-only
Data augmentation is applied at training time only; test data should not be augmented, except in test-time augmentation (TTA), which is a separate technique.
- Source: entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation

### [ACCEPT] elastic-distortion-simard-2003
Elastic distortion for data augmentation was introduced by Simard et al. (2003) for visual document analysis, complementing affine transformations and proving particularly effective for handwritten character recognition.
- Source: entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation

### [ACCEPT] only-three-absolute-depth-cues
Only three depth cues provide absolute distance information: convergence, accommodation, and familiar size; all other monocular and binocular depth cues yield only relative depth.
- Source: entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation

### [ACCEPT] accommodation-below-2m-convergence-below-10m
Accommodation (ciliary muscle lens adjustment) is effective as a depth cue only below approximately 2 meters; convergence (angle between eye axes) is effective only below approximately 10 meters — motivating use of other cues at longer ranges.
- Source: entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation

### [ACCEPT] kinetic-depth-effect-basis-for-sfm
The kinetic depth effect — recovering 3D structure from 2D projected feature motion — is the perceptual basis for Structure from Motion (SfM) algorithms in computer vision.
- Source: entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation

### [ACCEPT] occlusion-ordinal-depth-only
Occlusion (interposition) provides only ordinal depth information (relative ordering of surfaces) but not metric depth — an important constraint for occlusion-based reasoning in CV systems.
- Source: entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation

### [ACCEPT] aerial-perspective-contrast-reduction-blue-shift
Aerial perspective (atmospheric scattering) reduces contrast and shifts color toward blue at distance — rendered as 'distance fog' in computer graphics and relevant to outdoor scene understanding and dehazing algorithms.
- Source: entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation

### [ACCEPT] monocular-vs-binocular-maps-to-cv-systems
The monocular/binocular depth cue distinction maps directly to CV system design: monocular cues work from a single image (monocular depth estimation), while binocular cues require a stereo pair with known geometry (stereo vision).
- Source: entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation

### [ACCEPT] diffusion-forward-process-no-learning
The forward diffusion process requires no learning — it is a fixed Markov chain defined by the noise schedule β_t that gradually adds Gaussian noise until data becomes approximately N(0,I).
- Source: entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model

### [ACCEPT] diffusion-reparameterization-direct-sampling
In diffusion models, x_t can be sampled directly from x_0 in one step via x_t = √ᾱ_t · x_0 + σ_t · ε (where ε ~ N(0,I)), avoiding sequential computation through intermediate steps during training.
- Source: entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model

### [ACCEPT] ddpm-2020-original-diffusion-2015
DDPM (Denoising Diffusion Probabilistic Model, Ho et al., 2020) made diffusion models practical via variational inference; the original diffusion model concept dates to 2015 (Sohl-Dickstein et al.) using non-equilibrium thermodynamics.
- Source: entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model

### [ACCEPT] diffusion-reverse-posterior-tractable-gaussian
The reverse posterior q(x_{t-1}|x_t, x_0) in diffusion models is tractable as a closed-form Gaussian with known mean and variance, which is what makes training via variational inference feasible.
- Source: entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model

### [ACCEPT] diffusion-sampling-iterative-slower-than-gans
Diffusion model sampling requires T iterative reverse denoising steps, making it significantly slower than single-pass generators like GANs — the main computational drawback of the approach.
- Source: entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model

### [ACCEPT] diffusion-three-equivalent-prediction-targets
Diffusion models can equivalently learn to predict: the noise ε added at each step, the clean data x_0, or the score function ∇_x log p(x_t) — three mathematically equivalent training objectives.
- Source: entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model

### [ACCEPT] diffusion-four-equivalent-formalisms
Diffusion models have four equivalent mathematical formalisms: Markov chains, denoising diffusion probabilistic models, noise-conditioned score networks, and stochastic differential equations (SDEs).
- Source: entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model

### [ACCEPT] canny-three-optimality-criteria
The Canny edge detector optimizes three criteria: detection (find all true edges), localization (detected edges close to true position), and minimal response (single response per edge). Its optimal filter is a sum of four exponentials, well-approximated by the first derivative of Gaussian.
- Source: entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection

### [ACCEPT] hysteresis-thresholding-two-thresholds
Hysteresis thresholding uses two thresholds: an upper threshold to start an edge and a lower threshold to continue tracing it — this dual-threshold approach distinguishes the Canny detector from simple single-threshold methods.
- Source: entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection

### [ACCEPT] edge-detection-two-categories-by-derivative-order
Edge detection methods fall into two main categories: search-based (first-order derivatives / gradient magnitude with local maxima search) and zero-crossing-based (second-order derivatives / Laplacian with zero-crossing detection).
- Source: entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection

### [ACCEPT] non-maximum-suppression-produces-thin-edges
Non-maximum suppression in edge detection defines edge points as local gradient magnitude maxima in the gradient direction, producing thin (1-pixel-wide) edges without requiring post-processing thinning.
- Source: entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection

### [ACCEPT] edge-blur-three-physical-sources
Real image edges deviate from ideal step functions due to three blur sources: focal blur (depth-of-field/PSF), penumbral blur (shadow from non-zero-radius light source), and shading on smooth objects — modeled as a Gaussian-smoothed step edge.
- Source: entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection

### [ACCEPT] face-recognition-four-step-pipeline
Facial recognition operates through a four-step pipeline: (1) face detection, (2) alignment (normalize pose/size/illumination), (3) feature extraction (landmark measurement → feature vector), (4) matching against database.
- Source: entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system

### [ACCEPT] eigenfaces-pca-fisherfaces-lda
Eigenfaces represent faces via PCA (orthogonal basis faces capturing global variance); Fisherfaces (1997) improved on this using LDA to optimize between-class vs. within-class variance for better discriminability.
- Source: entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system

### [ACCEPT] viola-jones-2001-first-realtime-face-detection
The Viola-Jones framework (2001) was the first real-time frontal face detector, combining Haar-like features with an AdaBoost cascade classifier — enabling deployment on handheld and embedded devices by 2015.
- Source: entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system

### [ACCEPT] deepface-97-percent-vs-fbi-85
Facebook's DeepFace (9-layer DNN, 120M+ weights, trained on 4M images) achieved 97% face recognition accuracy compared to the FBI's NGI system at 85%.
- Source: entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system

### [ACCEPT] 3d-face-recognition-lighting-invariant
3D face recognition using structured light sensors to capture face shape (eye socket contours, nose, chin) is invariant to lighting changes and works across viewing angles including profile view.
- Source: entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system

### [ACCEPT] feret-1993-standardized-face-evaluation
The FERET program (1993), sponsored by DARPA/ARL, established standardized evaluation of face recognition systems and helped spawn the commercial face recognition industry.
- Source: entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system

### [ACCEPT] face-recognition-less-accurate-than-iris-fingerprint
Facial recognition is less accurate than iris and fingerprint biometrics but is widely adopted due to its contactless, non-cooperative capture capability — it can identify subjects without their active participation.
- Source: entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system

### [ACCEPT] mic-analyzes-not-acquires-images
Medical image computing (MIC) focuses on computational analysis of medical images, not their acquisition — image acquisition is the domain of medical imaging.
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] medical-images-16bit-regular-grids
Medical images are uniformly sampled data on regular x-y-z grids (2D images, 3D volumes), typically stored as 16-bit integers but ranging from 8-bit to 32-bit float, with sample meaning dependent on modality (CT = radiodensity, MRI = T1/T2-weighted signal).
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] ssd-optimal-same-modality-gaussian-noise
Sum of Squared Distances (SSD) is the optimal similarity metric for same-modality image registration with Gaussian noise; multi-modal registration requires mutual information or learned representations like CoMIRs.
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] registration-transformation-hierarchy
Image registration transformation models form a hierarchy of increasing flexibility: rigid (rotation + translation) < affine (+ scaling/shearing) < deformable (B-spline, thin plate spline, dense displacement fields); diffeomorphisms are deformable transformations that guarantee invertibility with smooth inverse.
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] manual-segmentation-gold-standard
Manual segmentation remains the gold standard for medical image segmentation; CNN methods (especially U-Net) are the leading automated approach.
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] mni-template-standard-brain-atlas
The MNI template is the standard single-template atlas for brain MRI, used for spatial normalization in neuroimaging studies.
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] voxelwise-analysis-requires-multiple-comparison-correction
Voxel-wise group analysis (e.g., comparing control vs. disease cohorts after registration to common coordinates) requires multiple comparison correction due to the massive number of voxels tested simultaneously.
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] longitudinal-imaging-symmetric-processing-required
Longitudinal medical image analysis must treat all time points identically to avoid processing bias — asymmetric interpolation from resampling causes spurious effects that overestimate change; linear mixed effects models are more powerful than repeated-measures ANOVA for this data.
- Source: entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing

### [ACCEPT] nerf-5d-input-density-and-color-output
A NeRF maps 5D input (3D spatial position x,y,z + 2D viewing direction θ,Φ) to volume density σ (view-independent) and RGB color (view-dependent, capturing specular effects), composited into images via classical volume rendering.
- Source: entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field

### [ACCEPT] nerf-requires-per-scene-retraining
A standard NeRF must be retrained for every new scene — it is a per-scene optimization, not a generalizable model out of the box.
- Source: entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field

### [ACCEPT] positional-encoding-overcomes-nerf-spectral-bias
Raw MLPs suffer from spectral bias (struggling with high-frequency detail); Fourier feature mapping / positional encoding lifts low-dimensional inputs into higher-dimensional space, enabling the network to learn sharp details in NeRF.
- Source: entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field

### [ACCEPT] plenoxels-proved-mlp-not-essential
Plenoxels (2022) proved the neural network is not essential to NeRF-quality results — direct SGD optimization of sparse voxel coefficients matches NeRF quality, demonstrating that the differentiable volume rendering pipeline, not the MLP, is the critical component.
- Source: entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field

### [ACCEPT] gaussian-splatting-primary-nerf-alternative
3D Gaussian Splatting (2023) represents scenes as sparse 3D Gaussians optimized via SGD, achieving real-time rendering and often surpassing NeRF fidelity; it is the primary modern alternative to NeRF using explicit point-based rather than implicit volumetric representation.
- Source: entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field

### [ACCEPT] instant-ngp-hash-encoding-real-time-training
Instant NGP (Nvidia, 2022) uses multi-resolution hash encoding with O(1) lookups and GPU parallelism to achieve real-time NeRF training, while PlenOctrees (2021) achieved 3000× faster rendering via octree baking for real-time inference.
- Source: entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field

### [ACCEPT] nerf-excels-on-reflective-transparent-objects
NeRF excels over traditional photogrammetry on reflective and transparent objects but does not inherently produce dimensionally accurate geometry.
- Source: entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field

### [ACCEPT] icp-aligns-point-clouds-rigid-transform
ICP (Iterative Closest Point) is the classic algorithm for aligning two overlapping point clouds separated by a rigid transformation; NICP extends it to non-rigid/elastic transforms; deep learning approaches (e.g., DeepVCP) can perform end-to-end registration.
- Source: entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud

### [ACCEPT] surface-reconstruction-vertex-vs-volumetric
Point cloud surface reconstruction follows two approaches: vertex-based methods (Delaunay triangulation, alpha shapes, ball pivoting) that build triangle networks over existing point vertices, and volumetric methods that convert to a voxel distance field then extract the implicit surface via marching cubes.
- Source: entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud

### [ACCEPT] mpeg-pcc-gpcc-static-vpcc-dynamic
MPEG Point Cloud Compression defines two codecs: G-PCC (ISO/IEC 23090-9) compresses geometry directly for static and LiDAR point clouds, while V-PCC (ISO/IEC 23090-5) projects point clouds onto 2D patches and leverages video codecs for dynamic point cloud data.
- Source: entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud

### [ACCEPT] point-cloud-acquisition-active-and-passive
Point clouds are produced by both active sensing (LiDAR, structured light, time-of-flight 3D scanners) and passive sensing (photogrammetry from multi-view RGB images, e.g., Agisoft Photoscan, Pix4D, DroneDeploy).
- Source: entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud

### [ACCEPT] point-clouds-feed-dems-and-gdt
In GIS, point clouds are a primary input for generating digital elevation models (DEMs); in industrial metrology, point clouds are aligned to CAD models to extract geometric dimensions and tolerances (GD&T).
- Source: entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud

### [ACCEPT] rnn-hidden-state-distinguishes-from-feedforward
RNNs maintain a hidden state vector updated at each time step based on current input and previous state — f_θ(x_t, h_t) → (y_t, h_{t+1}) — which is what distinguishes them from feedforward networks and enables temporal dependency capture.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] vanishing-gradient-motivated-lstm-gru
The vanishing gradient problem — gradients shrinking exponentially during backpropagation through time (BPTT) — is the primary limitation of vanilla RNNs and motivated the development of LSTM (Hochreiter & Schmidhuber, 1997) and GRU.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] lstm-three-gates-gru-two-gates
LSTM uses three gates (input, forget, output) plus a cell state to preserve gradients over long sequences; GRU uses two gates (reset, update) and is computationally cheaper — both solve the vanishing gradient problem through gating mechanisms.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] elman-hidden-feedback-jordan-output-feedback
Elman networks (Simple RNN) feed back from the hidden layer, while Jordan networks feed back from the output layer — both are called Simple Recurrent Networks (SRNs) but differ in their recurrent connection source.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] seq2seq-preceded-transformers-2014-2017
The encoder-decoder (seq2seq) architecture — two coupled RNNs where the encoder compresses input to a context vector and the decoder generates output — was state of the art for machine translation from 2014-2017; attention mechanisms developed to address its fixed-length bottleneck led directly to transformers.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] bidirectional-rnn-requires-full-sequence
Bidirectional RNNs process sequences in both directions and concatenate outputs; they require the full sequence to be available upfront and are therefore not suitable for real-time or online processing.
- Source: entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network

### [ACCEPT] resnet-skip-connection-identity-residual
ResNet's core innovation is the residual/skip connection x → f(x) + x, where the network learns the residual (difference from identity) rather than the full transformation; when dimensions differ, a learned linear projection P(x) replaces the identity skip.
- Source: entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network

### [ACCEPT] degradation-problem-distinct-from-vanishing-gradient
The degradation problem (deeper plain networks having higher training error) is distinct from the vanishing gradient problem — degradation is caused by the optimizer's inability to learn identity mappings in parameterized layers, not by gradient magnitude decay.
- Source: entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network

### [ACCEPT] resnet-bottleneck-vs-basic-block
ResNet basic blocks use two 3×3 convolutions (ResNet-18/34); bottleneck blocks use three convolutions (1×1 reduction → 3×3 → 1×1 restoration) and are used in ResNet-50/101/152.
- Source: entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network

### [ACCEPT] pre-activation-residual-adopted-by-transformers
Pre-activation residual blocks apply BN/ReLU before the weight layers (not after), enabling training of 200-1000+ layer networks; this design was adopted by GPT-2 and subsequent transformers as 'pre-normalization' and consistently outperforms post-activation variants.
- Source: entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network

### [ACCEPT] resnet-gradient-always-has-additive-identity
In ResNet, the gradient of loss with respect to any shallow layer always includes a direct additive term from deeper layers (∂E/∂x_ℓ includes ∂E/∂x_L), preventing gradient from vanishing entirely regardless of network depth.
- Source: entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network

### [ACCEPT] lstm-cell-state-is-residual-connection
LSTM memory cells (c_{t+1} = c_t + F(x_t)) function as generalized residual connections; highway networks are LSTMs unfolded in time applied to feedforward nets; ResNet is mathematically equivalent to an open-gated highway network.
- Source: entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network

### [ACCEPT] resnet-skip-connections-adopted-across-dl
The residual connection motif from ResNet has become foundational across deep learning, appearing in transformers (BERT, GPT), AlphaGo Zero, AlphaStar, AlphaFold, and Vision Transformers — very deep transformers cannot train without them.
- Source: entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network

### [ACCEPT] scaled-dot-product-attention-formula
Scaled dot-product attention computes Attention(Q,K,V) = softmax(QK^T / sqrt(d_k)) * V, where scaling by sqrt(d_k) prevents dot products from growing large and collapsing softmax into a hard max on a single token.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] attention-matrix-quadratic-sequence-length
The attention matrix is O(n^2) in sequence length, which is the primary computational and memory bottleneck for long sequences in transformer models.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] self-attention-permutation-equivariant-queries
QKV self-attention is permutation equivariant with respect to queries and permutation invariant with respect to key-value pairs, which is why positional encodings are required to inject sequence order information.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] transformer-introduced-2017-vaswani
The Transformer architecture was introduced by Vaswani et al. in 'Attention Is All You Need' (2017), replacing sequential recurrence with parallel self-attention and becoming the foundation for BERT, GPT, T5, and vision transformers.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] flash-attention-tiling-linear-memory
Flash Attention reduces attention memory from O(n^2) to O(n) by partitioning computation into blocks that fit GPU SRAM, achieving exact results without approximation.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] bahdanau-additive-luong-multiplicative
Bahdanau attention (2014) uses additive scoring via v^T tanh(W[s;h]) concatenating decoder and encoder states, while Luong attention (2015) uses multiplicative scoring via s^T W h with a learned weight matrix.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] attention-output-convex-hull-values
Attention output rows are confined to the convex hull of value vectors because attention produces weighted averages, never generating values outside the span of V.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] attention-precursors-nonlocal-means-bilateral
Non-local means (2005) in image denoising and bilateral filters (1998) are precursors to attention in computer vision, using affinity matrices for relevance-weighted propagation across spatial locations.
- Source: entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)

### [ACCEPT] autoencoder-encoder-decoder-architecture
An autoencoder consists of an encoder E_φ mapping input space X (R^m) to latent space Z (R^n) and a decoder D_θ mapping Z back to X, trained unsupervised to minimize reconstruction loss (typically MSE/L2) via gradient descent.
- Source: entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder

### [ACCEPT] autoencoder-undercomplete-overcomplete
Undercomplete autoencoders have dim(Z) < dim(X), forcing compression; overcomplete autoencoders have dim(Z) >= dim(X) and risk learning the identity function unless regularized, though experiments show they can still learn useful features.
- Source: entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder

### [ACCEPT] vae-latent-distributions-not-vectors
Variational autoencoders (VAEs) model the latent space as probability distributions (mixture of distributions) rather than fixed vectors, belonging to variational Bayesian methods and enabling generative modeling via p_θ(x) = ∫ p_θ(x,z) dz.
- Source: entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder

### [ACCEPT] sparse-autoencoder-sparsity-methods
Sparse autoencoders enforce sparsity via either hard k-sparse top-k selection (zeroing gradients for inactive units, generalizing ReLU) or soft regularization (KL divergence or L1/L2 penalty), and may have more hidden units than inputs.
- Source: entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder

### [ACCEPT] autoencoder-nonlinear-generalization-pca
Autoencoders perform a nonlinear generalization of PCA for dimensionality reduction, related to factor analysis, ICA, NMF, and t-SNE.
- Source: entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder

### [ACCEPT] sae-j3016-six-automation-levels
SAE J3016 defines six levels of vehicular automation (0-5), where the level is determined by the combination of Operational Design Domain (ODD) and dynamic driving requirement, not solely by vehicle capability.
- Source: entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving

### [ACCEPT] sae-level3-critical-transition
SAE Level 3 (conditional automation) is the critical transition point: the system monitors the environment and controls all driving, but the driver must respond to intervention requests — creating the most complex liability questions.
- Source: entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving

### [ACCEPT] sae-level4-vs-level5-no-production-level5
Level 4 automation operates under specific ODD constraints and can stop safely if the driver doesn't respond; Level 5 handles all conditions with no human needed, but no production Level 5 vehicles exist.
- Source: entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving

### [ACCEPT] autonomous-vehicle-three-core-modules
Autonomous driving software consists of three core modules: Perception (interpreting camera, LiDAR, RADAR, SONAR data), Localization (precise positioning via 3D point clouds, GPS, IMU, maps), and Planning (computing velocity and steering actions).
- Source: entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving

### [ACCEPT] lidar-vs-camera-only-bounding-box-tradeoff
In autonomous driving perception, camera-only systems can rival LiDAR performance but produce less accurate bounding boxes, while LiDAR provides precise per-point distance measurements.
- Source: entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving

### [ACCEPT] stanford-cart-first-autonomous-vehicle
The Stanford Cart (late 1970s, Hans Moravec) was the first experimental autonomous vehicle and a precursor to NASA planetary rovers; ALVINN (Carnegie Mellon) was an early neural-network-based autonomous driving system using camera and laser range finder.
- Source: entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving

### [ACCEPT] batch-norm-learned-scale-shift-parameters
Batch normalization (Ioffe & Szegedy, 2015) normalizes each layer's inputs to zero mean and unit variance within each mini-batch, then applies two learned parameters per dimension — γ (scale) and β (shift) — to restore representational capacity.
- Source: entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization

### [ACCEPT] batch-norm-inference-uses-population-statistics
At inference time, batch normalization uses population statistics (running mean/variance accumulated during training with Bessel's correction m/(m-1)) instead of batch statistics, collapsing to a deterministic fixed linear transform.
- Source: entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization

### [ACCEPT] internal-covariate-shift-explanation-disputed
The original 'internal covariate shift' explanation for batch normalization's effectiveness is disputed; the loss landscape smoothing explanation (bounding gradient magnitudes and Hessian curvature via Lipschitz continuity) has stronger empirical support, including a VGG-16 experiment with injected noise.
- Source: entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization

### [ACCEPT] batch-norm-conv-per-channel-across-spatial
In convolutional networks, batch normalization computes statistics shared across spatial dimensions (H, W) and the batch dimension (N) but separately per channel, implemented in PyTorch as nn.BatchNorm2d(num_features).
- Source: entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization

### [ACCEPT] batch-norm-breaks-iid-regularizes
Batch normalization introduces inter-sample statistical dependence within a batch (breaking the iid assumption), but this acts as implicit regularization that can reduce or eliminate the need for dropout, and enables higher learning rates.
- Source: entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization

### [ACCEPT] canny-five-stage-pipeline
The Canny edge detector (John F. Canny, 1986) uses a five-stage pipeline: (1) Gaussian smoothing, (2) gradient magnitude/direction computation, (3) non-maximum suppression, (4) double thresholding, (5) hysteresis edge tracking.
- Source: entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector

### [ACCEPT] canny-three-design-criteria
Canny's three formal criteria for optimal edge detection are: low error rate (detect real edges with few false positives), accurate localization (detected edge at true center), and single response (each edge marked once, noise should not create false edges).
- Source: entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector

### [ACCEPT] canny-nms-along-gradient-four-bins
Non-maximum suppression in the Canny detector compares gradient magnitude along the gradient direction (not perpendicular), with gradient directions quantized to four discrete bins (0°, 45°, 90°, 135°) for neighbor lookup.
- Source: entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector

### [ACCEPT] canny-hysteresis-weak-strong-connectivity
Canny's hysteresis edge tracking classifies pixels as strong (above high threshold), weak (between thresholds), or suppressed (below low threshold), preserving weak edges only when connected via 8-connectivity to strong edges.
- Source: entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector

### [ACCEPT] canny-gaussian-noise-localization-tradeoff
In Canny edge detection, larger Gaussian kernel width (σ) provides more noise suppression but degrades edge localization accuracy — a fundamental tradeoff inherent to the algorithm.
- Source: entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector

### [ACCEPT] canny-optimal-filter-gaussian-approximation
Canny's optimal edge filter derived via calculus of variations is theoretically a sum of four exponential terms, but is practically approximated by the first derivative of a Gaussian.
- Source: entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector

### [ACCEPT] deriche-iir-canny-reformulation
The Deriche edge detector is a recursive (IIR) reformulation of Canny's FIR filter that is computationally faster for large smoothing kernels and suitable for real-time FPGA/DSP implementations, but can introduce rotational asymmetry bias.
- Source: entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector

### [ACCEPT] unet-skip-connections-over-fcn
U-Net's defining architectural innovation over FCN is skip connections that concatenate high-resolution encoder features with upsampled decoder features at corresponding resolution levels, combining spatial and semantic information.
- Source: entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net

### [ACCEPT] unet-denoising-backbone-diffusion-models
U-Net serves as the iterative denoising network in diffusion-based generative models including DDPM, Stable Diffusion, DALL-E, and Midjourney.
- Source: entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net

### [ACCEPT] unet-designed-for-few-training-images
U-Net was designed to yield precise segmentation with very few labeled training images, a critical advantage in biomedical imaging where labeled data is scarce.
- Source: entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net

### [ACCEPT] unet-mirror-padding-tiling-arbitrary-size
U-Net uses mirror padding at image borders to enable a tiling strategy that allows segmentation of arbitrarily large images without GPU memory limitations.
- Source: entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net

### [ACCEPT] unet-fully-convolutional-encoder-decoder
U-Net is fully convolutional with no fully connected layers, consisting of a contracting path (repeated Conv2D→ReLU→MaxPool2D doubling channels) and an expansive path (UpConv2D→concatenate skip→Conv2D→ReLU) with a 1×1 Conv2D output layer.
- Source: entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net

### [ACCEPT] vit-patches-not-pixels-for-attention
Vision Transformers split images into fixed-size patches (typically 16×16 or 32×32 pixels), each linearly projected into an embedding vector, to make self-attention computationally feasible by reducing the O(n²) cost compared to per-pixel attention.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] vit-encoder-only-like-bert
The original Vision Transformer (ViT) uses a BERT-like encoder-only transformer architecture with a prepended CLS token whose output feeds the classification head, not the full encoder-decoder structure.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] vit-less-data-efficient-higher-capacity-than-cnn
ViTs lack the built-in spatial locality and translation equivariance of CNNs, making them less data-efficient, but have higher model capacity with the largest models reaching 22 billion parameters.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] mae-75-percent-masking-unmasked-only
Masked Autoencoder (MAE) self-supervised ViT training masks 75% of image patches and processes only the unmasked 25% through the encoder during training; the decoder used for reconstruction is discarded entirely at inference time.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] dino-ema-teacher-sharpening-centering
DINO is a self-supervised self-distillation method where the teacher network is an exponential moving average of the student (not a separate model), using sharpening (low-temperature softmax) and centering (running average of outputs) to prevent representation collapse.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] swin-shifted-window-local-attention
Swin Transformer uses shifted-window self-attention (local, not global) with hierarchical merging layers that concatenate 2×2 neighboring tokens then project (analogous to CNN pooling), achieving SOTA on COCO object detection.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] dinov3-gram-anchoring-dense-features
DINOv3 (August 2025) introduced Gram anchoring to fix dense feature map degradation that occurred even as global task performance improved, plus axial RoPE with jittering, image-text alignment similar to CLIP, and scaling to 7B parameters on 1.7B images.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] gap-map-outperform-cls-token-pooling
Global Average Pooling (GAP) and Multihead Attention Pooling (MAP) both outperform the original CLS token approach for converting ViT output embeddings to classification predictions.
- Source: entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer

### [ACCEPT] monocular-vo-lacks-absolute-scale
Monocular visual odometry using a single camera cannot directly recover absolute scale, while stereo VO with two cameras provides both depth and scale information with reduced error.
- Source: entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry

### [ACCEPT] vo-feature-based-vs-direct-methods
Visual odometry methods divide into feature-based (extract and track keypoints across frames), direct/appearance-based (use pixel intensities directly, e.g., LSD-SLAM), and hybrid approaches combining both families.
- Source: entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry

### [ACCEPT] vo-six-stage-canonical-pipeline
The canonical visual odometry pipeline has six stages: image acquisition, image correction (lens distortion removal), feature detection and matching, outlier removal, camera motion estimation (via Kalman filter or reprojection error minimization/RANSAC), and trackpoint repopulation.
- Source: entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry

### [ACCEPT] vio-fuses-camera-and-imu
Visual-Inertial Odometry (VIO) fuses camera data with an inertial measurement unit (IMU), widely used in commercial quadcopters for GPS-denied localization.
- Source: entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry

### [ACCEPT] vo-inherently-drifts-without-loop-closure
All visual odometry methods suffer from cumulative drift over time since they estimate incremental motion; loop closure or global optimization (as in full SLAM) is required for long-term trajectory consistency.
- Source: entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry

### [ACCEPT] vo-validated-mars-exploration-rovers
Visual odometry was validated on NASA's Mars Exploration Rovers (Maimone et al., 2007), demonstrating real-world robustness for autonomous navigation in planetary exploration.
- Source: entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry

### [ACCEPT] sift-descriptor-128-dimensions
The SIFT descriptor is 128-dimensional, computed from a 16×16 pixel neighborhood divided into 4×4 sub-regions with 8-bin orientation histograms each (4×4×8 = 128), normalized to unit length for illumination invariance.
- Source: entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform

### [ACCEPT] sift-dog-approximates-scale-normalized-log
SIFT detects keypoints as local extrema of Difference of Gaussians (DoG) images across multiple scales, where DoG approximates the scale-normalized Laplacian of Gaussian; each candidate keypoint is compared against 26 neighbors (8 spatial at same scale + 9 at each adjacent scale).
- Source: entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform

### [ACCEPT] sift-distance-ratio-test-0-8
SIFT's distance ratio test accepts a feature match only if the ratio of nearest-neighbor distance to second-nearest-neighbor distance is below 0.8, which eliminates approximately 90% of false matches while losing less than 5% of correct ones.
- Source: entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform

### [ACCEPT] sift-edge-rejection-hessian-r10
SIFT rejects edge responses using the 2×2 Hessian matrix at each keypoint: if Tr(H)²/Det(H) exceeds (r+1)²/r with threshold ratio r=10, the point is discarded as lying on an edge, avoiding explicit eigenvalue decomposition.
- Source: entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform

### [ACCEPT] sift-orientation-36-bins-80pct-peaks
SIFT assigns keypoint orientation from a 36-bin gradient direction histogram (10° per bin) weighted by gradient magnitude and a Gaussian window at 1.5× keypoint scale; peaks above 80% of the maximum create additional keypoints at those alternate orientations.
- Source: entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform

### [ACCEPT] sift-lowe-1999-patent-expired-2020
SIFT was invented by David Lowe in 1999 (full paper published 2004) and its patent expired in 2020; OpenCV exposes it via cv2.SIFT_create().
- Source: entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform

### [ACCEPT] sift-bbf-200-cutoff-hough-3-votes
SIFT's Best-Bin-First (BBF) k-d tree search cuts off after 200 candidates (~100× speedup, <5% match loss); matched features vote via Hough transform for object pose, requiring clusters of 3+ consistent votes with minimum 3 feature matches for affine model estimation (6 parameters).
- Source: entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform

### [ACCEPT] ssl-generates-supervision-from-data-structure
Self-supervised learning (SSL) generates its own supervisory signals by exploiting inherent structure, correlations, or metadata within unlabeled data — no external annotation required — sitting between supervised and unsupervised learning.
- Source: entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning

### [ACCEPT] ssl-pretext-then-downstream-two-step
SSL follows a two-step training process: (1) solve a pretext task using pseudo-labels derived from the data to initialize model parameters, then (2) fine-tune on the actual downstream task using supervised or unsupervised learning.
- Source: entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning

### [ACCEPT] ssl-contrastive-positive-and-negative-pairs
Contrastive SSL uses both positive and negative example pairs, minimizing distance between positive pairs and maximizing distance between negative pairs; InfoNCE loss uses one positive sample and N-1 negative samples in a softmax-style ratio based on Noise Contrastive Estimation.
- Source: entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning

### [ACCEPT] ssl-noncontrastive-positive-only-asymmetric
Non-contrastive SSL (e.g., BYOL, DirectPred) uses only positive example pairs and avoids trivial collapse through architectural asymmetry such as an asymmetric predictor network and stop-gradient on the target branch.
- Source: entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning

### [ACCEPT] jepa-predicts-masked-latent-representations
Joint-Embedding Predictive Architectures (JEPA), introduced by Yann LeCun in 2022, predict masked latent representations from visible context, operating in latent space rather than pixel space to focus on semantic structure and avoid pixel-level noise.
- Source: entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning

### [ACCEPT] barlow-twins-vicreg-covariance-no-negatives
Barlow Twins and VICReg are joint-embedding SSL methods that enforce covariance constraints to learn representations without requiring negative sampling; Deep CCA is the foundational technique behind joint-embedding architectures.
- Source: entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning

### [ACCEPT] semantic-seg-per-pixel-class-no-instances
Semantic segmentation classifies every pixel by category (e.g., all 'person' pixels get one label) but does not distinguish between separate instances of the same class.
- Source: entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation

### [ACCEPT] panoptic-seg-unifies-semantic-and-instance
Panoptic segmentation assigns every pixel both a class label and an instance ID, unifying semantic segmentation (per-pixel class) and instance segmentation (per-object identity) into a single framework.
- Source: entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation

### [ACCEPT] region-growing-sensitive-to-seeds-and-noise
Region growing segmentation starts from seed pixels and iteratively adds neighbors satisfying a similarity criterion; results are sensitive to seed placement and noise. Statistical Region Merging (SRM) variant builds a 4-connected pixel graph and sorts edges by intensity difference.
- Source: entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation

### [ACCEPT] edge-detection-requires-contour-closing
Edge detection produces disconnected edges from intensity discontinuities; additional processing is required to close contours for use in complete image segmentation.
- Source: entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation

### [ACCEPT] compression-segmentation-minimizes-coding-length
Compression-based segmentation operates on the principle that optimal segmentation minimizes coding length, modeling boundary smoothness via Huffman-coded chain codes and texture via multivariate normal entropy (maximum entropy among distributions with given mean and covariance).
- Source: entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation

### [ACCEPT] stereopsis-horizontal-disparity-6-5cm
Stereopsis derives depth from horizontal binocular disparity caused by the approximately 6.5 cm inter-ocular distance; Wheatstone demonstrated this in 1838 using line stereograms viewed in a stereoscope.
- Source: entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision

### [ACCEPT] horopter-crossed-vs-parallel-disparity
The horopter is the locus of zero disparity (a circle through both eyes and fixation point); crossed (negative) disparity indicates objects nearer than the horopter, while parallel (positive) disparity indicates objects farther.
- Source: entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision

### [ACCEPT] fine-stereopsis-parvo-what-pathway
Fine (patent) stereopsis enables magnitude judgment of depth with a linear depth-disparity relationship for small disparities, processed by the parvocellular pathway through inferior temporal cortex (the 'what' pathway for shape and object recognition).
- Source: entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision

### [ACCEPT] coarse-stereopsis-magno-where-pathway
Coarse (qualitative) stereopsis enables relative depth order judgment but not magnitude, processed by the magnocellular pathway through posterior parietal cortex (the 'where'/'how' pathway for spatial localization and motion).
- Source: entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision

### [ACCEPT] julesz-random-dot-stereogram-depth-before-form
Julesz's random dot stereograms (1971) proved that stereoscopic depth perception is computed before form recognition — each eye sees only random dots, but binocular viewing reveals a 3D shape, demonstrating depth without monocular form cues.
- Source: entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision

### [ACCEPT] disparity-tuned-neurons-barlow-1967
Barlow, Blakemore & Pettigrew (1967) discovered disparity-tuned neurons in cat visual cortex, providing the neural basis of stereopsis; Poggio later found V2 neurons responding to random-dot stereogram depth in monkeys.
- Source: entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision

### [ACCEPT] transfer-learning-different-domain-or-task
Transfer learning applies when source and target differ in either domain (feature space X or marginal distribution P(X)) or task (label space Y or predictive function f), reusing source knowledge to improve target performance.
- Source: entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] negative-transfer-degrades-target
Negative transfer occurs when source knowledge degrades target task performance; Zoph et al. (2020) showed that pre-training can sometimes hurt accuracy, with self-training being preferable in certain settings.
- Source: entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] transfer-learning-first-paper-bozinovski-1976
The first paper on transfer learning in neural networks was by Bozinovski and Fulgosi in 1976; Andrew Ng at NIPS 2016 predicted transfer learning would be the next major driver of ML commercial success after supervised learning.
- Source: entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning

### [ACCEPT] transfer-learning-improves-initial-and-asymptotic
Transfer learning improves both initial performance (compared to random weight initialization) and final asymptotic performance after training on the target task.
- Source: entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning


---

**Generated:** 2026-11-11
**Source:** 38 entries from /home/forge/workspace/entries/
**Model:** openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] soft-attention-dynamic-hard-attention-fixed
Hard attention weights are learned during backpropagation and fixed at inference, while soft attention weights are computed dynamically during the forward pass and change with every input.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] alignment-matrix-off-diagonal-reordering
In attention alignment, off-diagonal dominance in the alignment matrix indicates non-trivial source-to-target reordering, such as 'I love you' to 'je t'aime'.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] context-vector-weighted-linear-combination-encoder-hidden-states
The attention context vector is computed as c = H * w, a weighted linear combination of encoder hidden states where w is the attention weight vector.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] qkv-learned-projections-role-definitions
QKV attention uses three learned projections of input embeddings: queries ask what to look for, keys answer what is contained, and values carry the information.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] self-attention-intra-sequence-vs-cross-attention-decoder-query
Self-attention captures global intra-sequence dependencies by having each element attend to all others in the same sequence, whereas cross-attention uses queries from the decoder and keys/values from the encoder.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] multi-head-attention-parallel-learned-projections
Multi-head attention runs multiple parallel attention functions with different learned projections.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] attention-rollout-recursive-dot-product-layers
Attention rollout combines attention maps across all layers by recursively taking their dot product to produce a single visualization.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] graph-attention-networks-extend-attention-to-graphs
Graph Attention Networks (GAT, 2018) extend attention mechanisms to graph-structured data.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Attention_machine_learning.md
- Source URL: https://en.wikipedia.org/wiki/Attention_(machine_learning)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] autoencoder-one-layer-mlp-encoder-formula
A one-layer MLP autoencoder encoder computes E_phi(x) = sigma(Wx + b), where sigma is an activation function, W is a weight matrix, and b is a bias vector.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] autoencoder-l2-reconstruction-loss-formula
The L2 reconstruction loss for an autoencoder is L(theta, phi) = (1/N) * sum_i ||x_i - D_theta(E_phi(x_i))||^2.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sparse-autoencoder-lambda-sparsity-strength
Sparse autoencoder training minimizes L(theta, phi) + lambda * L_sparse(theta, phi), where lambda controls sparsity strength.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sparse-autoencoder-kl-divergence-sparsity-loss-formula
The KL divergence sparsity loss used in sparse autoencoders is s(rho, rho_hat) = rho log(rho/rho_hat) + (1-rho) log((1-rho)/(1-rho_hat)).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sparse-autoencoder-neuroscience-sparse-coding-hypothesis
Sparse autoencoders are motivated by the sparse coding hypothesis in neuroscience that only a small subset of neurons fire for any given input.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] autoencoder-training-empirical-distribution-reference
Autoencoder training typically uses the empirical distribution of the training dataset as the reference distribution while minimizing reconstruction loss.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] autoencoder-latent-code-z-notation
In an autoencoder, the intermediate code z = E_phi(x) is called the latent variable, latent vector, or code.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autoencoder.md
- Source URL: https://en.wikipedia.org/wiki/Autoencoder
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vehicular-automation-assists-or-replaces-operators
Vehicular automation is technology that assists or replaces human vehicle operators, spanning semi-autonomous assisted modes and autonomous modes that require no human operator.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sae-level1-steering-or-speed-level2-both
SAE Level 1 driver assistance controls either steering or speed, while SAE Level 2 partial automation controls both steering and speed with the driver monitoring.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sensor-fusion-improves-accuracy-reliability
Sensor fusion in autonomous driving combines multiple sensor types to improve accuracy and reliability across conditions.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] autonomous-navigation-sparse-maps-vs-hd-maps
Autonomous navigation approaches include using sparse maps combined with real-time perception, or highly detailed HD maps that reduce real-time decision-making.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] rtk-ppp-sub-meter-positioning
RTK and PPP GNSS enhancement techniques provide sub-meter positioning accuracy, which is critical for autonomous navigation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] tam-factors-autonomous-vehicle-adoption
Technology Acceptance Model factors for autonomous vehicle adoption are usefulness, ease of use, trust, and social influence, all positively correlated with adoption intent.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vienna-convention-automated-driving-system-definition
The proposed Vienna Convention amendment defines an automated driving system as hardware and software exercising sustained dynamic control, where dynamic control covers real-time operational and tactical functions for lateral and longitudinal motion, road monitoring, event response, and maneuver planning.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vienna-convention-amendment-entered-force-july-2022
The Vienna Convention amendment defining automated driving systems entered into force in July 2022.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Autonomous_driving.md
- Source URL: https://en.wikipedia.org/wiki/Autonomous_driving
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] batch-norm-normalization-step-epsilon-formula
Batch normalization normalizes each input as x_hat = (x - mu_B) / sqrt(sigma_B^2 + epsilon), where mu_B and sigma_B^2 are the mini-batch mean and variance and epsilon is a small constant for numerical stability.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] batch-norm-backprop-gamma-beta-input-gradients
Batch normalization backpropagation computes dL/dgamma = sum_i (dL/dy_i) * x_hat_i and dL/dbeta = sum_i (dL/dy_i), while gradients with respect to the input include terms from the normalized output, the variance, and the mean.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] batch-norm-gradient-explosion-mitigated-by-skip-connections
In very deep networks, batch normalization can initially cause gradient explosion, which skip connections such as those in ResNets mitigate.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] layer-instance-group-norm-avoid-batch-size-dependence
Layer Normalization, Instance Normalization, and Group Normalization are alternatives to batch normalization that avoid batch-size dependence, which is important for small-batch or sequence-model settings.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] batch-norm-placement-before-after-activation
The batch normalization transform can be applied before or after the activation function, and its placement affects training dynamics.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] batch-norm-per-dimension-across-minibatch
Batch normalization normalizes per dimension across the mini-batch, not across dimensions within a single sample.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Batch_normalization.md
- Source URL: https://en.wikipedia.org/wiki/Batch_normalization
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] canny-gaussian-kernel-formula-2k1-window
For a (2k+1) by (2k+1) Gaussian window, the Canny smoothing kernel is H[i,j] = (1 / (2*pi*sigma^2)) * exp(-((i-(k+1))^2 + (j-(k+1))^2) / (2*sigma^2)).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] canny-5x5-gaussian-kernel-sigma2-159
For a 5x5 Gaussian kernel with sigma=2, Canny smoothing uses the normalized matrix (1/159) * [[2,4,5,4,2],[4,9,12,9,4],[5,12,15,12,5],[4,9,12,9,4],[2,4,5,4,2]].
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] canny-gradient-magnitude-atan2-direction
Canny gradient computation uses magnitude G = sqrt(Gx^2 + Gy^2) and direction Theta = atan2(Gy, Gx).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] opencv-canny-low-high-threshold-call
In OpenCV Python, Canny edge detection is invoked as cv2.Canny(image, low_threshold, high_threshold).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] canny-otsu-automatic-high-threshold-half-low
Otsu's method can automatically select Canny's high threshold from the non-maximum-suppressed gradient magnitude image, with the low threshold set to the high threshold divided by 2.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] scale-space-differential-edge-detection-subpixel-lindeberg-1998
Differential edge detection formulated in scale space by Lindeberg (1998) provides sub-pixel accuracy using second- and third-order derivatives.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] canny-morphological-thinning-mallat-zhong
Mathematical morphology post-processing by Mallat and Zhong can further thin Canny edges to enforce the single-response criterion.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] curvelets-alternative-gaussian-multiscale-noise-reduction
Curvelets are an alternative to Gaussian filtering for edge detection that decompose signals into multi-scale components, so dropping fine scales reduces noise while preserving edge structure.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Canny_edge_detector.md
- Source URL: https://en.wikipedia.org/wiki/Canny_edge_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] computer-vision-extracts-high-level-understanding-from-images-and-video
Computer vision is the interdisciplinary field concerned with enabling computers to extract high-level understanding from digital images and video.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] computer-vision-input-modalities-include-video-multicamera-lidar-medical-imaging
Computer vision input modalities include video sequences, multi-camera views, 3D scanner data, LiDAR point clouds, and medical imaging devices.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cv-subdisciplines-include-scene-reconstruction-object-detection-and-tracking
Computer vision subdisciplines include scene reconstruction, object detection, event detection, activity recognition, video tracking, object recognition, 3D pose estimation, motion estimation, visual servoing, 3D scene modeling, and image restoration.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] deep-learning-surpassed-prior-methods-on-classification-segmentation-optical-flow
CNNs and deep learning have surpassed prior methods on benchmarks for classification, segmentation, and optical flow.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] augmented-reality-combines-computer-graphics-and-computer-vision
Augmented reality combines computer graphics and computer vision, including tracking surfaces and planes in 3D.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Computer_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cnn-is-feedforward-neural-network-learning-spatial-features-via-kernel-optimization
Convolutional neural networks are a class of feedforward neural networks that learn spatial features through filter/kernel optimization rather than full connectivity.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cnn-input-tensor-shape-batch-height-width-channels
CNN input tensors have shape (batch) x (height) x (width) x (channels), and a convolution outputs a feature map with shape (batch) x (map height) x (map width) x (map channels).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cnn-biological-inspiration-simple-complex-cells-hubel-wiesel
CNN architecture mirrors the visual cortex: simple cells respond to edges in small receptive fields, while complex cells have larger fields insensitive to exact edge position (Hubel & Wiesel, 1950s-60s).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] max-pooling-takes-maximum-average-pooling-takes-mean
Max pooling selects the maximum value in a region, while average pooling computes the mean; both are common pooling layer types.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] effective-receptive-field-grows-with-network-depth
The effective receptive field in a CNN grows with network depth as convolutions compound.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] backpropagation-primary-cnn-training-since-lecun-1989
Backpropagation has been the primary training method for CNNs since LeCun et al. (1989).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Convolutional_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Convolutional_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] data-augmentation-artificially-expands-training-datasets-via-modified-copies
Data augmentation artificially expands training datasets by creating modified copies of existing data.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] geometric-augmentation-includes-rotation-reflection-translation-scaling-shear-cropping
Geometric data augmentation transformations include rotation, reflection, translation, scaling, shear, cropping, elastic distortion, and intra-class morphing.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] color-space-augmentation-includes-brightness-contrast-saturation-color-jittering
Color space data augmentation includes brightness, contrast, and saturation adjustment, as well as color jittering.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gaussian-noise-simulates-sensor-noise-salt-pepper-simulates-dead-pixels
In data augmentation, Gaussian noise simulates sensor noise and salt-and-pepper noise simulates dead pixels or sensor dust.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-style-transfer-can-synthesize-augmented-training-samples
Generative augmentation using GANs (including DCGANs and conditional Wasserstein GANs) and style transfer can synthesize realistic training samples.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Data_augmentation.md
- Source URL: https://en.wikipedia.org/wiki/Data_augmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] motion-parallax-provides-absolute-depth-if-observer-motion-known
Motion parallax — the relative apparent motion of objects at different distances during observer movement — provides absolute depth if observer velocity and direction are known.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] depth-from-optical-expansion-enables-time-to-contact-estimation
Depth from optical expansion occurs when approaching objects produce expanding retinal projections, enabling time-to-contact estimation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] linear-perspective-parallel-lines-converge-at-vanishing-points
Linear perspective is a monocular depth cue in which parallel lines converge at vanishing points, enabling relative depth reconstruction.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] familiar-size-known-object-size-plus-visual-angle-yields-absolute-depth
Familiar size combines known object size with visual angle to yield absolute depth.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] defocus-blur-depth-cue-used-by-jumping-spiders
Defocus blur — out-of-focus regions signaling depth difference from the focal plane — is used as a primary depth cue by some spiders such as jumping spiders.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Depth_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Depth_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] diffusion-model-two-phase-forward-noise-reverse-denoise
Diffusion models are latent variable generative models with a forward process that gradually adds Gaussian noise to data and a learned reverse process that iteratively denoises random noise back into samples.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] diffusion-forward-noise-schedule-beta-in-zero-one
The forward diffusion process uses a fixed noise schedule β₁,...,βT ∈ (0,1) and produces increasingly noisy versions x₁,...,xT until xT approximates N(0,I).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] diffusion-reverse-process-learned-gaussian-mean-covariance
The reverse diffusion process parameterizes p_θ(x_{t-1}|x_t) as a Gaussian with learned mean μ_θ and covariance Σ_θ.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] diffusion-backbone-typically-unet-or-transformer
The denoising network in diffusion models is typically a U-Net or Transformer backbone.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] diffusion-score-based-formulation-learns-score-function
In the score-based formulation of diffusion models, the model learns the score function ∇_x log p(x), the gradient of the log probability density.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Diffusion_model.md
- Source URL: https://en.wikipedia.org/wiki/Diffusion_model
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] edge-defined-by-brightness-discontinuity
An edge is a curve in a digital image where image brightness changes sharply or has a discontinuity.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] viewpoint-independent-edges-reflect-3d-properties
Viewpoint-independent edges reflect inherent 3D object properties such as surface markings and surface shape and do not change with viewpoint.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] viewpoint-dependent-edges-occlusion-boundaries
Viewpoint-dependent edges change as viewpoint changes and reflect scene geometry such as occlusion boundaries.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] edge-vs-line-ridge-detector
An edge is a boundary between two regions, whereas a line is a thin feature with an edge on each side and is detected by ridge detectors rather than edge detectors.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] edge-thinning-8-connectivity-multipass
Edge thinning reduces thick edges to one-pixel-wide elements using connectivity analysis typically with 8-connectivity and multi-pass directional removal.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] marr-hildreth-false-edges-gradient-minima
The Marr-Hildreth algorithm produces false edges at local gradient minima and has poor localization at curved edges.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] kovalevsky-color-channel-differences
The Kovalevsky method uses color channel differences rather than brightness and can detect edges between pixels of equal brightness but different colors.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] canny-deriche-recursive-filters
The Canny-Deriche detector is derived from criteria similar to Canny but uses recursive filters instead of Gaussian or exponential filters.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Edge_detection.md
- Source URL: https://en.wikipedia.org/wiki/Edge_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ebgm-gabor-filters-structural-grid-zn-face
Elastic Bunch Graph Matching (EBGM) uses Gabor filters to record facial features and computes a structural grid linking them, and was commercialized as ZN-Face.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] face-hallucination-super-resolution-cctv
Face hallucination is a super-resolution technique that enhances low-resolution CCTV faces using example-based machine learning and can remove disguises such as sunglasses before recognition.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] thermal-face-recognition-infrared-lighting-independent
Thermal face recognition uses infrared cameras to capture face shape independent of lighting conditions and accessories.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cross-spectrum-synthesis-thermal-visible-30-percent
Cross-spectrum synthesis developed by ARL in 2018 bridges thermal-to-visible face matching with approximately 30% improvement over baselines using combined global and local facial features.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] geometric-vs-photometric-face-recognition
Geometric facial recognition analyzes spatial relationships between landmarks, while photometric facial recognition uses statistical methods to distill images into values compared against templates.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] holistic-vs-feature-based-face-models
Holistic face models recognize the face as a whole, while feature-based models decompose the face into components such as eyes, nose, and mouth and analyze each plus spatial relationships.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] clearview-ai-government-agencies-only
Clearview AI is a commercial facial recognition platform whose database is restricted to government agencies for law enforcement and national security.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] faceit-visionics-minnesota-mugshot-1999
FaceIT by Visionics was deployed in Minnesota's mugshot booking system in 1999.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Facial_recognition_system.md
- Source URL: https://en.wikipedia.org/wiki/Facial_recognition_system
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] feature-definition-task-dependent
A feature in computer vision is a piece of information about image content such as a point, edge, or region deemed interesting for a given task, and there is no universal definition independent of application.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] feature-detection-low-level-first-step
Feature detection is a low-level image processing operation that examines every pixel to determine if a feature is present and is typically the first step in a computer vision pipeline.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] feature-extraction-binary-or-continuous-feature-images
Feature extraction applies local neighborhood operations to produce either binary decisions of feature presence or continuous-valued feature images.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] feature-vector-and-feature-space-definition
A feature vector aggregates multiple feature descriptors at each image point into a single vector, and the set of all possible feature vectors forms the feature space.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] feature-descriptor-instance-sift-hog
A feature descriptor is a specific instance of a feature representation, such as a SIFT descriptor or HOG descriptor.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] feature-matching-establishes-correspondences
Feature matching establishes correspondences between features detected in different images of the same scene.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] edges-are-locally-one-dimensional-structures
Edges are image boundaries with locally one-dimensional structure identified by strong gradient magnitude.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] blobs-complement-corners-detect-smooth-regions
Blob detectors are complementary to corner detectors and can detect regions that are too smooth for corner detectors.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Feature_detection_computer_vision.md
- Source URL: https://en.wikipedia.org/wiki/Feature_detection_(computer_vision)
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-generator-maps-latent-to-data-deconvolutional
In image generation, a GAN generator is typically a deconvolutional neural network that maps samples from a latent space such as Gaussian or uniform noise to the data space.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-discriminator-cnn-real-fake-output-0-1
In image generation, a GAN discriminator is typically a convolutional neural network that classifies inputs as real or fake and outputs a value in [0, 1].
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-indirect-training-fool-discriminator
A GAN generator is trained indirectly to fool the discriminator rather than to minimize distance to specific training images.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-generator-distribution-pushforward-measure
The GAN generator distribution is implemented as a pushforward measure by sampling z from a simple distribution and applying the learned function G(z).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-objective-function-formula
The GAN objective is L(G, D) = E_{x ~ μ_ref}[ln D(x)] + E_{z ~ μ_Z}[ln(1 - D(G(z)))].
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-training-alternating-independent-backprop
GAN training applies independent backpropagation alternately to the generator and discriminator networks.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-reparameterization-trick-kingma-welling
The reparameterization trick decomposes the generator distribution into a simple prior composed with a learned mapping and was independently developed alongside VAEs by Kingma and Welling.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] gan-no-function-type-restriction-vs-boltzmann
Boltzmann machines restrict the function types used by the network, whereas GANs have no such restriction on function type.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Generative_adversarial_network.md
- Source URL: https://en.wikipedia.org/wiki/Generative_adversarial_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] harris-corner-definition-two-dominant-edge-directions
A Harris corner is a point whose local neighborhood has two dominant different edge directions, equivalently a junction of two edges where image brightness changes sharply.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] harris-ssd-taylor-expansion-quadratic-form
The Harris detector uses sum of squared differences to quantify intensity change under window shifts and approximates it via first-order Taylor expansion into a quadratic form involving the structure tensor.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] harris-alternative-response-det-over-tr
An alternative Harris corner response approximates the smaller structure-tensor eigenvalue as det(M) / tr(M).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] harris-better-repeatability-than-klt-stereo-retrieval
The Harris detector has better repeatability under illumination and rotation changes than KLT and is more commonly used in stereo matching and image retrieval.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] harris-affine-region-detector-affine-invariant
The Harris affine region detector extends Harris corner detection for affine-invariant detection.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] opencv-cornerharris-parameters-block-2-ksize-3-k-0-04
OpenCV's cv2.cornerHarris example uses blockSize=2, ksize=3 for the Sobel kernel, and k=0.04.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] harris-applications-span-stitching-stereo-3d-reconstruction
Harris corner detection is applied downstream in image stitching, stereo vision, 3D reconstruction, motion detection, object recognition, video tracking, and content-based image retrieval.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Harris_corner_detector.md
- Source URL: https://en.wikipedia.org/wiki/Harris_corner_detector
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hough-patented-paul-hough-1962
The Hough transform was patented by Paul Hough in 1962.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hough-duda-hart-1972-rho-theta
Duda and Hart modernized the Hough transform in 1972 with the rho-theta parameterization.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hough-gradient-direction-reduces-theta-range
Using the edge gradient direction in the Hough transform, as by O'Gorman and Clowes, constrains theta to roughly a 45-degree arc instead of the full 180-degree range, reducing computation and spurious votes.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] kernel-based-hough-transform-real-time-clustered-voting
Kernel-based Hough Transform (KHT) votes on clusters of approximately collinear pixels using oriented elliptical-Gaussian kernels and can achieve real-time performance on large images such as 1280x960.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] three-d-kht-plane-detection-point-clouds-nlogn
3DKHT extends KHT to unorganized point clouds for plane detection with O(n log n) cost using trivariate Gaussian kernels in a spherical theta-phi-rho accumulator.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hough-probabilistic-interpretation-naive-bayes-mle
The Hough transform can be interpreted as approximate naive Bayes inference with a uniform prior over shape space, independent pixel evidence whose log-likelihoods add, and peak detection as maximum likelihood estimation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hough-cylinder-detection-two-step-orientation-position-radius
Cylinder detection in point clouds with the Hough transform is a two-step process: first find cylinder orientation, then find position and radius.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hough-edge-detection-prerequisite
Edge detection such as Canny or Sobel is typically a prerequisite for the Hough transform because it provides the edge map that feeds the voting procedure.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Hough_transform.md
- Source URL: https://en.wikipedia.org/wiki/Hough_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] computer-vision-transforms-images-to-world-descriptions
Computer vision transforms visual images into world descriptions that can elicit appropriate action, i.e., disentangling symbolic information from image data.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] image-processing-image-to-image-vs-cv-3d-semantic
Image processing transforms images to images in 2D, whereas computer vision extracts 3D understanding and semantic interpretation from images.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] machine-vision-controlled-industrial-context
Machine vision is a systems engineering discipline that applies computer vision in industrial or factory automation contexts with controlled conditions.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] computer-graphics-inverse-of-computer-vision
Computer graphics is the inverse of computer vision: graphics produces images from 3D models, while computer vision produces 3D models from images.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mit-1966-summer-project-describe-what-it-saw
In 1966, an MIT summer project attempted to have a computer describe what it saw and dramatically underestimated the problem's difficulty.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] neocognitron-1970s-modeled-primary-visual-cortex
The Neocognitron, developed by Fukushima in the 1970s, modeled the primary visual cortex and is the earliest example of a computer vision architecture directly inspired by the visual cortex.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vision-transformer-98-4-strawberry-disease-detection
Vision Transformers (ViT) achieved high accuracy, with an example of 98.4% on strawberry disease detection.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mediapipe-google-ai-edge-framework
MediaPipe is Google's open-source framework for AI edge computing, used for face detection, image classification, and object detection.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_classification.md
- Source URL: https://en.wikipedia.org/wiki/Image_classification
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lowpass-pyramid-smooth-subsample-factor-two
A lowpass image pyramid is built by smoothing with a filter and then subsampling, typically by factor 2 in each dimension, producing progressively lower-resolution and more-smoothed levels.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] oversampled-hybrid-pyramid-omits-subsampling
An oversampled or hybrid image pyramid is generated by omitting the subsampling step at certain stages to create intermediate scale levels.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pyramid-trades-spatial-resolution-for-smoothing
Image pyramids trade off spatial sampling density or resolution for increased smoothing at each level.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] laplacian-detail-manipulation-halo-artifacts
Detail manipulation using Laplacian pyramids can produce halo artifacts.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bilateral-filter-alternative-to-laplacian-detail-manipulation
The bilateral filter was developed as an alternative to Laplacian pyramid detail manipulation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mipmaps-graphics-analog-image-pyramids
Mipmaps are the computer graphics analog of image pyramids for texture level-of-detail.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] adam7-png-interlacing-pyramid-progressive-rendering
Adam7 interlacing in PNG functions as a kind of pyramid for progressive rendering.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_pyramid.md
- Source URL: https://en.wikipedia.org/wiki/Image_pyramid
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] image-registration-transforms-datasets-into-single-coordinate-system
Image registration transforms different sets of data into a single coordinate system so they can be compared or integrated.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] registration-target-fixed-and-moving-source-images
In image registration, the target or fixed or sensed image remains stationary while the moving or source images are transformed to align with it.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] affine-transformations-global-cannot-model-local-differences
Affine transformations are global transforms including rotation, scaling, translation, and shearing and cannot model local geometric differences.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] nonrigid-registration-radial-basis-viscous-fluid-diffeomorphisms
Nonrigid or elastic registration locally warps the target image and includes radial basis functions such as thin-plate splines and multiquadrics, viscous fluid models, and diffeomorphisms.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] parametric-fixed-vs-nonparametric-arbitrary-displacement
Parametric registration models describe the transformation with a fixed number of parameters dictated by the model, while non-parametric models allow arbitrary per-element displacement.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] phase-correlation-single-peak-translation
In phase correlation, a single peak in the output indicates relative translation between images.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] elastix-toolbox-rigid-nonrigid-registration
elastix is a toolbox for rigid and nonrigid image registration.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ransac-robust-transformation-control-points
RANSAC is an iterative algorithm used for robust estimation of transformation parameters when control points exceed the minimum required.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_registration.md
- Source URL: https://en.wikipedia.org/wiki/Image_registration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] image-restoration-theory-inverse-problems-psf-regularization
Image restoration theory provides the mathematical foundation of inverse problems, PSF estimation, and regularization for applied image restoration subfields.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_restoration.md
- Source URL: https://en.wikipedia.org/wiki/Image_restoration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ai-restoration-replaces-handcrafted-priors-with-learned-ones
AI-based image restoration builds on classical restoration theory but replaces hand-crafted priors with learned ones using deep learning.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_restoration.md
- Source URL: https://en.wikipedia.org/wiki/Image_restoration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] physical-photograph-conservation-chemical-environmental-archival
Physical conservation and restoration of photographs involves chemical treatments, environmental controls, and archival science.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_restoration.md
- Source URL: https://en.wikipedia.org/wiki/Image_restoration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] iterative-reconstruction-overlaps-medical-and-computational-photography
Iterative reconstruction overlaps with medical imaging such as CT, MRI, and PET and with computational photography.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_restoration.md
- Source URL: https://en.wikipedia.org/wiki/Image_restoration
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] image-segmentation-partitions-pixels-by-common-characteristics
Image segmentation partitions a digital image into segments (sets of pixels) and assigns labels so that pixels sharing a label have common characteristics such as color, intensity, or texture.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] kmeans-iterative-centroid-reassignment
K-means segmentation iteratively assigns each pixel to the nearest cluster center and recomputes cluster centers by averaging assigned pixels until no pixel changes cluster.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] thresholding-converts-grayscale-to-binary
Thresholding segmentation converts a grayscale image to binary by classifying pixels relative to a threshold T; methods include maximum entropy, balanced histogram thresholding, Otsu's method, and k-means clustering.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] region-growing-seeded-assigns-by-intensity-difference
Seeded region growing provides seed pixels marking each object, compares unallocated neighboring pixels to the region mean, assigns the pixel with the smallest intensity difference, and repeats until all pixels are assigned.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] statistical-region-merging-graph-edge-merging
Statistical Region Merging (SRM) builds a 4-connected pixel graph with edges weighted by absolute intensity difference, sorts edges in a priority queue, and merges regions using a statistical predicate.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] edge-detection-produces-disconnected-edges
Edge detection produces disconnected edges that often require closure before they can serve as segmentation boundaries.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] spatial-taxons-hierarchical-figure-ground-levels
Spatial-taxons extend figure-ground segmentation to hierarchical levels including foreground, object groups, objects, and salient parts.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Image_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Image_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] medical-image-computing-core-method-groups
Medical image computing's core methods are grouped into segmentation, registration, image-based physiological modeling, visualization, and statistical analysis.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] medical-image-nonstandard-geometries
Medical images can have non-standard geometries: curved-array ultrasound produces fan-like images, gantry tilt produces sheared images, and biomechanical analysis uses unstructured meshes such as hexahedral or tetrahedral meshes.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] registration-aligns-source-to-target-via-similarity-metric
Image registration finds spatial alignment between two images by treating one as the target and transforming the other (source) to match it through iterative optimization of a similarity metric.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] atlases-statistical-population-models
Atlases in medical image computing are statistical models of image populations learned from training data, ranging from single templates such as the MNI brain template to multi-template approaches that handle anatomical variability.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] atlas-based-segmentation-transfers-labels-via-registration
Atlas-based segmentation transfers manual labels from training images to new images via registration and can be parametric (single atlas) or nonparametric (all training images used separately).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] shape-based-segmentation-deforms-template
Shape-based segmentation deforms parametric template shapes to fit new images using techniques such as Active Shape Models (ASM) and Active Appearance Models (AAM).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cnn-segmentation-methods-include-unet-segnet-transformers
CNN-based medical image segmentation methods include SegNet, U-Net, ResNet, AATSN, Transformers, and GANs, providing automated segmentation with superior performance and speed compared to manual methods.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] voxel-based-morphometry-detects-deformation-abnormalities
Voxel-based morphometry (VBM) detects anatomical deformation abnormalities, such as hippocampal shrinkage in Alzheimer's disease.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Medical_image_computing.md
- Source URL: https://en.wikipedia.org/wiki/Medical_image_computing
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] nerf-introduced-2020-mildenhall
NeRF was introduced in 2020 by Mildenhall et al. at ECCV 2020 as a neural network-based technique for reconstructing 3D scene representations from collections of 2D photographs.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] nerf-requires-known-camera-poses
NeRF training requires standard 2D images with known camera poses, which can be obtained via structure from motion (e.g., COLMAP), SLAM, GPS, or IMU; no specialized cameras are needed.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] nerf-differentiable-rendering-pipeline
A NeRF's differentiable rendering pipeline marches camera rays through the scene, samples points, queries the MLP, and uses classical volume rendering to produce pixel colors, enabling end-to-end gradient descent against ground-truth images.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] barf-jointly-optimizes-poses-and-radiance-field
BARF (Bundle-Adjusting NeRF, 2021) jointly optimizes camera poses and the radiance field using a dynamic low-pass filter in a coarse-to-fine manner.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mip-nerf-conical-frustums-anti-aliasing
mip-NeRF (2021) performs multi-scale anti-aliasing by casting conical frustums instead of single rays and fitting Gaussians to frustum sections.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] nerf-w-three-mlps-static-appearance-transient
NeRF-W (NeRF in the Wild, 2021) uses three separate MLPs for static scene, appearance embedding (lighting), and transient embedding (moving objects), enabling training on uncontrolled photo collections.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] snerg-sparse-voxel-grid-lightweight-mlp
SNeRG (2021) uses a sparse voxel grid with a lightweight MLP for view-dependent residuals and outperforms PlenOctrees.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] nerf-typical-pipeline-sfm-train-query
A typical NeRF pipeline captures images from multiple viewpoints, runs structure from motion (e.g., COLMAP) to extract camera intrinsics/extrinsics, trains the NeRF model on images plus poses, and queries the trained model for novel view synthesis or geometry extraction (e.g., marching cubes for mesh).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Neural_radiance_field.md
- Source URL: https://en.wikipedia.org/wiki/Neural_radiance_field
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] true-positive-iou-threshold-correct-class
A true positive detection is a predicted bounding box with IoU above a threshold (commonly 0.5) and the correct class label.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] false-positive-iou-below-threshold-or-duplicate
A false positive detection is a prediction with IoU below the threshold, or a duplicate prediction for an already-matched ground truth object.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] false-negative-unmatched-ground-truth
A false negative detection is a ground-truth object with no matching prediction above the IoU threshold.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] object-detection-domain-gap-unsupervised-adaptation
Object detection performance degrades when test images come from a different distribution than training data (domain gap), addressed via unsupervised domain adaptation techniques such as CycleGAN for image-to-image translation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] opencv-dnn-yolov3-coco-80-classes
The OpenCV DNN module can load a YOLOv3 model trained on COCO to detect 80 common object classes.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] multiple-predictions-only-highest-iou-true-positive
When multiple predictions exist for a single ground truth, only the highest-IoU prediction (if above threshold) counts as a true positive; all others are false positives.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] classical-object-detectors-require-explicit-feature-engineering
Classical non-neural object detection methods such as Viola-Jones (Haar), SIFT, and HOG+SVM require explicit feature engineering, whereas neural methods learn features end-to-end.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] feature-based-object-classification
Feature-based object classification detects objects by identifying class-specific visual features such as shape, texture, color, and spatial relationships.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Object_detection.md
- Source URL: https://en.wikipedia.org/wiki/Object_detection
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] optical-flow-definition-apparent-motion
Optical flow is the pattern of apparent motion of objects, surfaces, and edges in a visual scene caused by relative motion between an observer and the scene, or equivalently the distribution of apparent velocities of brightness patterns in an image.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] brightness-constancy-constraint-equation
The brightness constancy constraint assumes a point's brightness remains constant between frames: I(x,y,t) - I(x+u, y+v, t+1) = 0, where (u,v) is the displacement vector.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] coarse-to-fine-optical-flow-warping
Coarse-to-fine optical flow addresses the small-displacement limitation by downsampling, solving at a coarse scale, then refining at progressively finer scales using image warping.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] focus-of-expansion-indicates-direction-of-travel
The focus of expansion is the point in the visual field from which optic flow vectors radiate outward during forward motion, indicating the direction of travel.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] optical-flow-cost-volumes-4d-matching-costs
Cost volumes in learning-based optical flow are 4D tensors representing matching costs between all pixel pairs in two feature maps.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] horn-schunck-euler-lagrange-gauss-seidel
The Horn-Schunck energy functional E = ∫∫ (Ix·u + Iy·v + It)² + α(|∇u|² + |∇v|²) dx dy is solved via Euler-Lagrange equations discretized and iterated with Gauss-Seidel.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lucas-kanade-local-window-loss
The Lucas-Kanade method minimizes the sum of absolute brightness differences over a local rectangular region R: Σ |I(x+u, y+v, t+1) - I(x,y,t)|.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] optical-flow-benchmarks-sintel-kitti-spring
Learning-based optical flow models are evaluated on MPI Sintel, KITTI, and Spring benchmarks, while supervised training often relies on synthetic datasets FlyingChairs and FlyingThings3D.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Optical_flow.md
- Source URL: https://en.wikipedia.org/wiki/Optical_flow
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] point-cloud-definition-xyz-optional-attributes
A point cloud is a discrete set of 3D data points where each point has mandatory Cartesian X, Y, Z coordinates and may carry optional attributes such as RGB color, surface normals, timestamps, and intensity.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] point-set-registration-aligns-multiple-scans
Point set registration aligns multiple point clouds or a point cloud to a 3D model and is essential for combining partial scans into a complete scene.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mpeg-pcc-began-2017-three-categories
MPEG Point Cloud Compression standardization began in 2017 with three categories: static point clouds, dynamic point clouds, and LiDAR sequences.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pcl-bsd-cpp-library
Point Cloud Library (PCL) is a BSD-licensed C++ library for n-D point cloud and 3D geometry processing.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] meshlab-open-source-mesh-conversion
MeshLab is an open-source tool for point cloud management and conversion to triangle meshes.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cloudcompare-open-source-processing
CloudCompare is an open-source tool for viewing, editing, and processing high-density 3D point clouds.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Point_cloud.md
- Source URL: https://en.wikipedia.org/wiki/Point_cloud
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pose-estimation-predicts-rotation-translation
3D pose estimation predicts an object's rotation and translation from a reference pose given an image or 3D scan.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pose-estimation-methods-class-specific
Pose estimation methods are typically class-specific and do not generalize across object types.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] cad-model-registration-optimizes-projected-distance
CAD model registration aligns a 3D CAD model over a photograph by optimizing a distance measure between the projected model and the image using perspective or orthogonal projection.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] calibrated-camera-pose-reconstructs-projection-rays
In calibrated-camera pose estimation, projection rays are reconstructed from 2D image points and 3D points are found along these rays using ICP-based correspondence.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] foundationpose-deep-model-based-model-free
NVIDIA FoundationPose is a deep learning foundation model for 6DoF pose estimation and tracking that supports both model-based and model-free setups.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] posest-gpl-cpp-6dof-3d2d
posest is a GPL C/C++ library for 6DoF pose estimation from 3D-2D correspondences.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Pose_estimation.md
- Source URL: https://en.wikipedia.org/wiki/Pose_estimation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] teacher-forcing-feeds-ground-truth
Teacher forcing trains an RNN by feeding the ground-truth previous output as the next input rather than the model's own prediction.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bptt-and-truncated-bptt
Backpropagation Through Time (BPTT) applies backpropagation to the unrolled RNN, and truncated BPTT limits the number of time steps to reduce computational cost.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] rnn-shared-parameters-across-time
RNNs share parameters across all time steps (weight tying), unlike unrolled feedforward networks.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] stacked-rnn-layer-output-feeds-next-layer
In a stacked (deep) RNN, multiple RNN layers are stacked vertically so layer k's output sequence becomes layer k+1's input sequence.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pixelrnn-2d-image-order
PixelRNN extends RNNs to 2D data such as images by processing pixels in a defined order, for example row-by-row or diagonal.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] hopfield-symmetric-weights-convergence
Hopfield networks are fully recurrent networks with symmetric weights that guarantee convergence but do not process sequences.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Recurrent_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Recurrent_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] resnet-won-ilsvrc-2015-he-et-al
ResNet, developed by Kaiming He et al. at Microsoft Research, won the ImageNet Large Scale Visual Recognition Challenge (ILSVRC) in 2015.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] resnet-variance-stabilization-x-over-L
Replacing the residual mapping x + f(x) with x/L + f(x), where L is the total number of residual layers, stabilizes layer input variance.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] resnet-forward-signal-propagation
In ResNet, forward signal propagation follows x_L = x_ell + sum of F(x_i) for i from ell to L-1, so any deep layer has a direct signal path from any shallower layer.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] densenet-every-layer-connects-to-subsequent
DenseNet extends skip connections so that every layer connects to every subsequent layer.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] resnext-combines-inception-and-resnet
ResNeXt combines Inception modules with ResNet.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] squeeze-excitation-adds-channel-attention
Squeeze-and-Excitation Networks add channel attention (SE modules) to ResNet and won ILSVRC 2017.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Residual_neural_network.md
- Source URL: https://en.wikipedia.org/wiki/Residual_neural_network
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sift-scale-space-octaves
SIFT builds a scale space by convolving the image with Gaussian filters at increasing scales grouped into octaves, with each octave doubling sigma and a fixed number of blurred images per octave producing the DoG pyramid.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sift-model-verification-least-squares-pseudoinverse
SIFT model verification solves the affine transformation parameters via linear least squares using the pseudoinverse x_hat = (A^T A)^(-1) A^T b.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sift-outlier-rejection-half-hough-bin
SIFT outlier rejection iteratively discards matches exceeding half the Hough bin error range, re-solves least squares, and rejects the hypothesis if fewer than 3 inliers remain.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sift-bayesian-acceptance-0-98
SIFT accepts a final hypothesis if the Bayesian probability of correct interpretation exceeds 0.98, based on the expected false match rate given projected model size and feature density.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sift-hough-bin-sizes
SIFT Hough transform voting uses bin sizes of 30 degrees orientation, factor-of-2 scale, and 0.25 times projected dimension for location.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Scale-invariant_feature_transform.md
- Source URL: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ssl-autoassociative-autoencoder-reconstruction
Autoassociative SSL trains a model to reconstruct its own input using an encoder that maps to latent space and a decoder that reconstructs, with loss equal to reconstruction error such as mean squared error.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ssl-four-major-types
Self-supervised learning is categorized into four major types: autoassociative (autoencoders), contrastive (e.g., CLIP, InfoNCE), non-contrastive (e.g., BYOL, DirectPred), and Joint-Embedding Predictive Architectures (JEPA).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ssl-pseudo-labels-dual-purpose-concept-drift
Pseudo-labels (model-generated labels assigned to unlabeled data based on the model's own predictions) serve a dual purpose: SSL pretraining and adapting to concept drift in dynamic environments.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ssl-real-world-systems-wav2vec-bert-gpt3-byol
Key real-world SSL systems include wav2vec (speech, Facebook), BERT (search queries, Google), GPT-3 (language, OpenAI), and BYOL (ImageNet, non-contrastive).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Self-supervised_learning.md
- Source URL: https://en.wikipedia.org/wiki/Self-supervised_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] instance-segmentation-separates-individual-objects
Instance segmentation identifies each distinct object instance separately (e.g., person 1 vs. person 2), unlike semantic segmentation which assigns class labels only.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] isolated-point-detection-laplacian-operator
Isolated point detection uses the Laplacian operator (second derivative), classifying a point as isolated when |R(x,y)| >= T.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] segmentation-motion-based-frame-differences
Motion-based segmentation exploits frame-to-frame differences to isolate moving objects, while interactive segmentation can use robotic poking to induce motion.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] medical-imaging-dominant-segmentation-application
Medical imaging (CT, MRI, volume rendering, and 3D reconstruction via marching cubes) is the dominant application domain of image segmentation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Semantic_segmentation.md
- Source URL: https://en.wikipedia.org/wiki/Semantic_segmentation
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] slam-map-representations-topological-occupancy-landmark
SLAM uses three map representations: topological maps (connectivity/topology rather than geometry), occupancy grid maps (cells assumed statistically independent, marking occupied vs. free), and landmark-based maps (uniquely identifiable features such as Wi-Fi APs, visual features, or beacons).
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] fastslam-rao-blackwellized-particle-filter
FastSLAM is a particle-filter-based method that uses a Rao-Blackwellized particle filter to factor the SLAM problem and replaced EKF SLAM as the preferred method.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] slam-with-datmo-handles-dynamic-objects
SLAM with DATMO (Detection And Tracking of Moving Objects) extends SLAM to handle dynamic/moving objects such as vehicles and pedestrians alongside static map building.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] collaborative-slam-darpa-subterranean-2021
Collaborative SLAM combines sensor data from multiple robots or users to jointly build maps, as demonstrated in the 2021 DARPA Subterranean Challenge.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] bundle-adjustment-map-used-in-arcore
Bundle adjustment / MAP estimation jointly optimizes poses and landmarks from image data, is used in commercial systems such as Google ARCore, and computes the most likely explanation rather than the full posterior.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Simultaneous_localization_and_mapping.md
- Source URL: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] stereopsis-two-mechanisms-binocular-and-motion
Stereopsis is produced by two mechanisms: binocular depth vision (processing disparity between two eyes separated by ~6.5 cm) and motion vision (processing optical flow when the observer moves), with 'stereopsis' typically referring to the binocular mechanism.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] stereo-correspondence-prefers-surfaces-minimal-depth
The visual system solves the stereo correspondence problem by preferring surfaces (globality principle) and minimal-depth interpretations, which can cause binocular ghost images such as the double-nail illusion.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] pulfrich-illusion-delay-elliptical-depth
The Pulfrich illusion shows that a dark filter over one eye delays neural signals, causing a pendulum swinging in a flat arc to appear to move in an elliptical path in depth, demonstrating the temporal simultaneity requirement for stereopsis.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] stereopsis-conditions-horizontal-disparity-contrast-simultaneity-vergence
Conditions for stereopsis include: (1) horizontal disparity, (2) matching edges of the same contrast polarity, (3) approximate temporal simultaneity, and (4) proper vergence alignment.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] stereopsis-color-brightness-need-not-match-binocular-rivalry
Color and brightness need not match between eyes for stereopsis; opposite colors do not mix but instead produce binocular rivalry alternation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Stereo_vision.md
- Source URL: https://en.wikipedia.org/wiki/Stereo_vision
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] transfer-learning-domain-task-definitions
In transfer learning, a domain consists of a feature space X and a marginal probability distribution P(X), while a task consists of a label space Y and a predictive function f: X → Y learned from training pairs {x_i, y_i}.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] fine-tuning-most-common-tl-deep-networks
Fine-tuning — initializing a model with pre-trained weights and then continuing training on target data — is the most common mechanism for applying transfer learning with deep neural networks.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] domain-adaptation-tl-task-stays-same
Domain adaptation is a subfield of transfer learning focused specifically on bridging domain differences while the task stays the same.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] zero-shot-learning-no-target-training-data
Zero-shot learning is an extreme case of transfer learning where no target-task training data is available and performance relies entirely on transferred knowledge.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] end-users-modify-fully-connected-layers
End-users of pre-trained models can modify the structure of fully-connected layers to improve performance on their specific target task.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] emg-eeg-cross-domain-transfer-bidirectional
Cross-domain transfer between EMG (muscle) and EEG (brain) signals is possible due to their similar physical natures and works bidirectionally.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Transfer_learning.md
- Source URL: https://en.wikipedia.org/wiki/Transfer_learning
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] unet-introduced-2015-ronneberger-fischer-brox-biomedical-segmentation
U-Net was introduced in 2015 by Ronneberger, Fischer, and Brox for biomedical image segmentation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] unet-example-256-rgb-to-k-256-segmentation-masks
A U-Net example maps a 256x256 RGB image to k 256x256 segmentation masks.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] unet-expansive-path-many-feature-channels-propagate-context
U-Net's expansive path has a large number of feature channels to propagate context information to higher-resolution layers.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] unet-bottleneck-connects-encoder-and-decoder
U-Net's bottleneck is the deepest convolutional block connecting the encoder to the decoder.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] 3d-unet-volumetric-extension-sparse-annotation
3D U-Net is a volumetric extension for 3D data such as medical volumes using sparse annotation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] ternausnet-vgg11-encoder-unet-decoder-imagenet-pretraining
TernausNet combines a U-Net decoder with a VGG11 encoder pre-trained on ImageNet.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] unet-tensorflow-implementation-tf-unet-akeret-2017
A TensorFlow U-Net implementation named tf_unet was released by Akeret in 2017.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] unet-original-implementation-caffe-university-freiburg
The original U-Net source implementation was Caffe-based from the University of Freiburg.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-U-Net.md
- Source URL: https://en.wikipedia.org/wiki/U-Net
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vit-introduced-2020
The Vision Transformer (ViT) was introduced in 2020.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vit-1d-learned-position-embeddings-adopted
The original ViT paper adopted 1D learned position embeddings over 2D or relative alternatives.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vit-classification-head-linear-gelu-linear-softmax
ViT's classification head is Linear -> GeLU -> Linear -> Softmax.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] mae-75-percent-mask-optimal-imagenet-1k
MAE's 75% mask ratio is optimal for ImageNet-1K in both fine-tuning and linear probing.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] siammae-95-percent-mask-video-frame-prediction
SiamMAE uses a ~95% mask ratio for video frame prediction.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] timesformer-factorized-spatial-temporal-attention
TimeSformer uses factorized attention for video by alternating spatial attention within one frame and temporal attention for the same patch across frames.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vit-vqgan-combines-vit-vqvae-gan-discriminators
ViT-VQGAN combines ViT with VQVAE and GAN discriminators for image tokenization.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vit-vqgan-basis-google-parti-autoregressive-generation
ViT-VQGAN is the basis of Google Parti's autoregressive image generation.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Vision_transformer.md
- Source URL: https://en.wikipedia.org/wiki/Vision_transformer
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vo-overcomes-wheel-slip-non-smooth-surface-by-visual-distance
Visual odometry overcomes wheel-based odometry limitations such as wheel slip on non-smooth surfaces by using visual information to estimate distance traveled.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vo-applicable-wheeled-legged-aerial-locomotion
Visual odometry is applicable to any locomotion type, including wheeled, legged, and aerial systems.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] visiodometry-phase-correlation-planar-roto-translations
Visiodometry uses phase correlation to estimate planar roto-translations between images without explicit feature extraction.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] focus-of-expansion-indicates-camera-motion-direction
The focus of expansion is the point in the optical flow field from which features diverge, indicating the direction of camera motion.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] egomotion-camera-3d-motion-rigid-environment
Egomotion is the 3D motion of a camera within a rigid environment, closely related to visual odometry but emphasizing the camera's own motion.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] vo-uses-pnp-2d-3d-pose-estimation
Visual odometry uses Perspective-n-Point (PnP) to estimate camera pose from 2D-3D point correspondences.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] sfm-offline-global-vs-vo-sequential
Structure from Motion is offline multi-view reconstruction that shares algorithmic foundations with visual odometry but processes all images globally rather than sequentially.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

### [ACCEPT] lucas-kanade-standard-optical-flow-visual-odometry
The Lucas-Kanade method is the standard algorithm for constructing the optical flow field in visual odometry.
- Source: /home/forge/workspace/entries/2026/06/21/wiki-Visual_odometry.md
- Source URL: https://en.wikipedia.org/wiki/Visual_odometry
- Model: openai:rits/deepseek-ai/DeepSeek-V4.1-Flash-1017

