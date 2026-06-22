---
source: sources/wiki-Harris_corner_detector.md
source_url: https://en.wikipedia.org/wiki/Harris_corner_detector
---

## Harris Corner Detector

The Harris corner detector is a foundational feature detection algorithm in computer vision, introduced by Chris Harris and Mike Stephens in 1988. It identifies corners — points where two dominant edge directions meet — by analyzing the structure tensor (second-moment matrix) of image intensity gradients within a local window. It improved upon Moravec's corner detector by computing differential corner scores directly rather than using shifted patches at discrete 45-degree angles, yielding better discrimination between edges and corners.

## Key Concepts

- **Corner definition**: A point whose local neighborhood has two dominant, different edge directions; equivalently, the junction of two edges where image brightness changes sharply.
- **Corners as interest points**: Invariant to translation, rotation, and illumination; contain the most important information for restoring image content despite being a small fraction of pixels.
- **Structure tensor (M)**: A 2×2 matrix constructed from sums of products of image gradients Ix and Iy over a local window W. Encodes local gradient distribution.
  - M = [[sum(Ix²), sum(IxIy)], [sum(IxIy), sum(Iy²)]]
- **Eigenvalue interpretation**: The two eigenvalues of M characterize the local image structure:
  - Both large → corner
  - One large, one small → edge
  - Both small → flat region
- **Harris response function (R)**: R = det(M) - k·tr(M)², where k is an empirical constant in [0.04, 0.06]. Avoids explicit eigenvalue computation.
- **Alternative response**: λ_min ≈ det(M) / tr(M), which approximates the smaller eigenvalue.
- **SSD (Sum of Squared Differences)**: The underlying measure — quantifies intensity change when a window is shifted by (Δx, Δy), approximated via first-order Taylor expansion.
- **Advantage over KLT**: Better repeatability under illumination and rotation changes; more commonly used in stereo matching and image retrieval.

## Commands and Syntax

**Five-step Harris detection pipeline:**

1. **Color to grayscale**: Convert using weighted sum — Gray = 0.299R + 0.587G + 0.114B
2. **Spatial derivative calculation**: Compute Ix and Iy using Sobel operators
3. **Structure tensor setup**: Build M from Ix², Iy², and IxIy products summed over window W
4. **Harris response calculation**: Compute R = det(M) - k·tr(M)² for each pixel
5. **Non-maximum suppression**: Find local maxima within a 3×3 window to select final corner points

**OpenCV Python example** (from referenced tutorials):
```python
import cv2
import numpy as np

img = cv2.imread('image.png')
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
gray = np.float32(gray)

# blockSize=2, ksize=3 (Sobel kernel), k=0.04
dst = cv2.cornerHarris(gray, 2, 3, 0.04)

# Dilate to mark corners, threshold at 1% of max
dst = cv2.dilate(dst, None)
img[dst > 0.01 * dst.max()] = [0, 0, 255]
```

## Relationships

- **Moravec's corner detector**: Direct predecessor; Harris improved it by replacing discrete shift-based scoring with continuous gradient analysis.
- **KLT (Kanade-Lucas-Tomasi) tracker**: Closely related; both use the structure tensor. KLT is used more for tracking, Harris for detection with better rotation/illumination invariance.
- **Structure tensor**: The core mathematical object shared across Harris, KLT, and other local feature methods.
- **Sobel operator**: Used in the spatial derivative step to approximate image gradients.
- **Harris-Laplace detector**: Extension that adds scale selection via Laplacian-of-Gaussian, enabling multi-scale corner detection.
- **Harris affine region detector**: Further extension for affine-invariant detection.
- **SIFT/SURF**: Later feature descriptors that build on interest point detection concepts pioneered by Harris.
- **Applications downstream**: Image stitching, stereo vision, 3D reconstruction, motion detection, object recognition, video tracking, content-based image retrieval.

## Exam-Relevant Points

- The Harris response R = det(M) - k·tr(M)² avoids computing eigenvalues explicitly; k is typically 0.04–0.06.
- The structure tensor M is a 2×2 symmetric matrix built from gradient products summed over a window.
- Corner vs. edge vs. flat classification depends on eigenvalue magnitudes of M (both large = corner, one large = edge, both small = flat).
- Harris detector is invariant to rotation and illumination changes but **not scale-invariant** (Harris-Laplace adds scale invariance).
- Grayscale conversion weights: R=0.299, G=0.587, B=0.114.
- Non-maximum suppression uses a 3×3 local window.
- The Taylor expansion approximation converts the SSD into a quadratic form involving the structure tensor, which is the key mathematical insight.
- Harris (1988) improved Moravec by using gradient-based analysis instead of patch shifting at 45-degree intervals.
- det(M) = λ1·λ2 and tr(M) = λ1 + λ2 — these identities connect the response formula to eigenvalue interpretation without requiring eigendecomposition.
