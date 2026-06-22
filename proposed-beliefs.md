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

