---
source: sources/wiki-Canny_edge_detector.md
source_url: https://en.wikipedia.org/wiki/Canny_edge_detector
---

## Canny Edge Detection Algorithm

The Canny edge detector is a multi-stage algorithm developed by John F. Canny in 1986 for detecting edges in images. It is one of the most widely used and rigorously defined edge detection methods in computer vision, designed to satisfy three formal criteria: low error rate, accurate localization, and single response per edge. The optimal filter is derived using the calculus of variations and can be approximated by the first derivative of a Gaussian.

## Key Concepts

- **Three criteria for edge detection**: (1) low error rate — detect as many real edges as possible, (2) accurate localization — detected edge points should be at the center of the true edge, (3) single response — each edge should be marked only once, and noise should not create false edges
- **Five-stage pipeline**: Gaussian smoothing → gradient computation → non-maximum suppression → double thresholding → hysteresis edge tracking
- **Gaussian smoothing**: Convolves image with a Gaussian kernel to suppress noise before gradient computation; kernel size controls the noise-sensitivity vs. localization tradeoff
- **Gradient computation**: Uses operators (Sobel, Prewitt, Roberts Cross) to compute horizontal (Gx) and vertical (Gy) derivatives; gradient magnitude G = sqrt(Gx² + Gy²) and direction Θ = atan2(Gy, Gx)
- **Gradient direction quantization**: Edge directions are rounded to four discrete angles — 0°, 45°, 90°, 135° — for non-maximum suppression
- **Non-maximum suppression (NMS)**: Edge thinning technique — for each pixel, compare its gradient magnitude to the two neighbors along the gradient direction; suppress (set to 0) if not a local maximum
- **Double thresholding**: Classifies remaining edge pixels as strong (above high threshold), weak (between high and low thresholds), or suppressed (below low threshold)
- **Hysteresis edge tracking**: Weak edge pixels are kept only if connected (8-connectivity) to a strong edge pixel via blob analysis; this eliminates isolated noise responses
- **Optimal filter**: Canny's derivation produces a sum of four exponential terms, approximated in practice by the first derivative of a Gaussian
- **Sigma (σ) parameter**: Controls the Gaussian kernel width — larger σ smooths more noise but reduces edge localization accuracy

## Commands and Syntax

**OpenCV (Python)**:
```python
import cv2
edges = cv2.Canny(image, low_threshold, high_threshold)
```

**Gaussian filter kernel formula** (size (2k+1)×(2k+1)):
```
H[i,j] = (1 / 2πσ²) * exp(-((i-(k+1))² + (j-(k+1))²) / 2σ²)
```

**Example 5×5 Gaussian kernel (σ=2)**:
```
B = (1/159) * [[2,4,5,4,2], [4,9,12,9,4], [5,12,15,12,5], [4,9,12,9,4], [2,4,5,4,2]] * A
```

**Gradient computation**:
```
G = sqrt(Gx² + Gy²)
Θ = atan2(Gy, Gx)
```

**Otsu's method for automatic threshold selection**: Apply Otsu's method to the NMS gradient magnitude image to determine the high threshold; set low threshold = high threshold / 2.

## Relationships

- **Prerequisite operators**: Sobel, Prewitt, Roberts Cross, and Scharr operators are used in the gradient computation stage; choice affects quality and noise sensitivity
- **Deriche edge detector**: Recursive (IIR) reformulation of Canny's FIR filter — computationally faster for large smoothing kernels, suitable for real-time FPGA/DSP implementations, but can introduce rotational asymmetry bias
- **Scale space theory**: Differential edge detection formulated in scale space (Lindeberg 1998) provides sub-pixel accuracy via second- and third-order derivatives
- **Otsu's method**: Used to automatically determine the high threshold value, replacing manual empirical selection
- **Mathematical morphology**: Post-processing technique (Mallat & Zhong) for further thinning edges to enforce single-response criterion
- **Curvelets**: Alternative to Gaussian filtering — decompose signals into multi-scale components; dropping fine scales reduces noise while preserving edge structure
- **Connected-component labeling (blob analysis)**: Used in the hysteresis step to trace connectivity between weak and strong edge pixels
- **Feature detection pipeline**: Canny feeds into higher-level tasks — corner detection (Harris), blob detection (LoG/DoG), Hough transforms, and feature descriptors (SIFT, SURF)

## Exam-Relevant Points

- The five stages in order: (1) Gaussian smoothing, (2) gradient magnitude/direction, (3) non-maximum suppression, (4) double thresholding, (5) hysteresis edge tracking
- Three design criteria: low error rate, good localization, single response per edge
- Larger Gaussian kernel → more noise suppression but worse edge localization (fundamental tradeoff)
- Non-maximum suppression compares gradient magnitude along the gradient direction, not perpendicular to it
- Double thresholding produces three categories: strong edges, weak edges, and suppressed pixels
- Hysteresis preserves weak edges only when connected to strong edges — this is what distinguishes Canny from simple thresholding approaches
- Gradient direction is quantized to four bins (0°, 45°, 90°, 135°) for NMS neighbor lookup
- The optimal Canny filter is theoretically a sum of four exponentials, practically approximated by the first derivative of a Gaussian
- Known limitations: Gaussian smoothing blurs edges along with noise; fixed global thresholds fail on complex images with varying local contrast; 2×2 gradient estimation is noise-sensitive
- Key improvements: adaptive filtering (edge-aware smoothing weights), Otsu-based automatic thresholding, 5×5 Sobel or Scharr for better gradient estimation, morphological thinning, curvelet-based filtering
- Canny–Deriche variant: IIR recursive implementation with fixed computation time regardless of smoothing amount, but biased toward horizontal/vertical edges
