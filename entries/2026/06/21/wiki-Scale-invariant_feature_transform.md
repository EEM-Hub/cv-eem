---
source: sources/wiki-Scale-invariant_feature_transform.md
source_url: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform
---

## Scale-Invariant Feature Transform (SIFT)

SIFT is a computer vision algorithm invented by David Lowe (1999) that detects, describes, and matches local features in images. It produces feature descriptors that are invariant to uniform scaling, rotation, and illumination changes, and partially invariant to affine distortion. Applications include object recognition, image stitching, 3D modeling, robotic mapping, gesture recognition, and video tracking. The patent expired in 2020.

## Key Concepts

- **Feature invariance**: SIFT descriptors are invariant to scale, rotation, and illumination; partially invariant to affine distortion. This is the core property that makes SIFT useful.
- **Difference of Gaussians (DoG)**: Keypoints are detected as local extrema (maxima/minima) of DoG images across multiple scales. DoG approximates the scale-normalized Laplacian of Gaussian.
- **Scale space**: The image is convolved with Gaussian filters at increasing scales, grouped into **octaves** (each octave doubles sigma). A fixed number of blurred images per octave produces the DoG pyramid.
- **Keypoint localization**: Candidate keypoints are refined via quadratic Taylor expansion of the DoG function for sub-pixel accuracy. Low-contrast points (|D(x)| < 0.03) and edge responses are discarded.
- **Edge elimination via principal curvature ratio**: Uses the 2x2 Hessian matrix at each keypoint. If the ratio of principal curvatures exceeds a threshold r (Lowe used r=10), the point lies on an edge and is rejected. The test uses Tr(H)^2 / Det(H) < (r+1)^2 / r to avoid computing eigenvalues.
- **Orientation assignment**: Each keypoint is assigned a dominant orientation from a 36-bin histogram of local gradient directions, weighted by gradient magnitude and a Gaussian window (1.5x the keypoint scale). Peaks above 80% of the maximum create additional keypoints at alternate orientations.
- **128-dimensional descriptor**: A 16x16 neighborhood around each keypoint is divided into 4x4 sub-regions. Each sub-region gets an 8-bin orientation histogram, yielding 4x4x8 = 128 values. The descriptor is normalized to unit length for illumination invariance.
- **Matching via distance ratio test**: A match is accepted only if the ratio of nearest-neighbor distance to second-nearest-neighbor distance is below 0.8. This eliminates 90% of false matches while losing less than 5% of correct ones.
- **Best-Bin-First (BBF) search**: Modified k-d tree search that explores bins in order of closest distance to the query, using a heap-based priority queue. Cuts off after 200 candidates, giving ~100x speedup over exact search with <5% match loss.
- **Hough transform voting**: Matched features vote for object pose (location, scale, orientation) in a hash table. Clusters of 3+ consistent votes are candidate detections. Bin sizes: 30 degrees orientation, factor-of-2 scale, 0.25x projected dimension for location.
- **Model verification**: Affine transformation (6 parameters: m1-m4, tx, ty) is solved via linear least squares using the pseudoinverse: x_hat = (A^T A)^(-1) A^T b. Minimum 3 matches required.
- **Outlier rejection**: Iteratively discard matches exceeding half the Hough bin error range, re-solve least squares, repeat. Reject if fewer than 3 inliers remain.
- **Bayesian acceptance**: Final hypothesis accepted if probability of correct interpretation exceeds 0.98, based on expected false match rate given projected model size and feature density.

## Commands and Syntax

No CLI commands — SIFT is an algorithm, not a tool. Key mathematical formulations:

- **DoG computation**: D(x,y,σ) = L(x,y,k_i·σ) − L(x,y,k_j·σ), where L = G * I (Gaussian-blurred image)
- **Keypoint interpolation** (Taylor expansion): D(x) = D + (∂D/∂x)^T x + (1/2) x^T (∂²D/∂x²) x
- **Extremum offset**: x_hat = −(∂²D/∂x²)^(-1) (∂D/∂x); re-center if offset > 0.5 in any dimension
- **Edge test** (Hessian): Tr(H)²/Det(H) < (r+1)²/r, where r = ratio threshold (typically 10)
- **Affine model**: [u; v] = [m1 m2; m3 m4][x; y] + [tx; ty]
- **Least squares solution**: x_hat = (A^T A)^(-1) A^T b

Common implementations: OpenCV `cv2.SIFT_create()`, VLFeat.

## Relationships

- **Difference of Gaussians** — approximation to the **Laplacian of Gaussian (LoG)** used in blob detection (Lindeberg). The DoG pyramid is computationally cheaper.
- **Scale space theory** — SIFT builds on Lindeberg's scale-space axioms and scale selection framework. Octaves and scale sampling come from this theory.
- **Hough transform** — used for geometric consistency clustering after feature matching, connecting SIFT to classical shape detection.
- **Affine transformation / least squares** — model verification stage connects to projective geometry and robust estimation.
- **Competing/successor descriptors**: SURF (speed-optimized approximation using box filters and integral images), GLOH (gradient-based extension), HOG (histogram of oriented gradients, used in pedestrian detection), ORB (binary descriptor, patent-free alternative).
- **k-d trees / nearest-neighbor search** — the BBF variant is critical to making SIFT matching scalable.
- **Harris/Hessian affine detectors** — affine-invariant feature detection extends SIFT's similarity-transform model to full affine.
- **Blob detection family**: SIFT's DoG keypoint detection is a specific instance alongside LoG, DoH, and MSER methods.

## Exam-Relevant Points

- SIFT descriptor dimensionality is **128** (4x4 spatial bins x 8 orientation bins).
- Keypoints are detected as extrema of **Difference of Gaussians**, not raw Gaussians or Laplacians.
- DoG approximates the **scale-normalized Laplacian of Gaussian**.
- Each candidate keypoint is compared to **26 neighbors** (8 spatial at same scale + 9 at each adjacent scale).
- The **distance ratio test** threshold is **0.8** (nearest / second-nearest neighbor distance).
- Edge rejection uses the **trace and determinant of the Hessian**, not eigenvalue decomposition; threshold ratio r = **10**.
- Low-contrast rejection threshold: |D(x_hat)| < **0.03**.
- Minimum **3 feature matches** required for pose estimation and Hough cluster acceptance.
- Orientation histogram uses **36 bins** (10 degrees each); peaks above **80%** of max spawn additional keypoints.
- Hough transform bin sizes: **30 degrees** orientation, **factor of 2** scale.
- BBF search cuts off after **200** nearest-neighbor candidates.
- Model acceptance requires Bayesian probability > **0.98**.
- SIFT is invariant to **scale, rotation, illumination**; *partially* invariant to **affine distortion**.
- The affine model has **6 parameters** (4 affine + 2 translation), requiring at least 3 point correspondences (each gives 2 equations).
- Patent expired in **2020**; invented by David Lowe in **1999**, full paper in **2004**.
