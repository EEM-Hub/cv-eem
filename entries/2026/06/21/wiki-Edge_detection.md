---
source: sources/wiki-Edge_detection.md
source_url: https://en.wikipedia.org/wiki/Edge_detection
---

## Edge Detection Methods in Computer Vision

Edge detection encompasses mathematical methods for identifying curves in digital images where brightness changes sharply or has discontinuities. It is a fundamental tool in image processing, machine vision, and computer vision, used extensively in feature detection and feature extraction. Detected edges ideally correspond to object boundaries, surface markings, depth discontinuities, changes in material properties, or variations in scene illumination.

## Key Concepts

- **Edge definition**: Curves in a digital image where image brightness changes sharply or has discontinuities
- **Edges correspond to**: discontinuities in depth, discontinuities in surface orientation, changes in material properties, and variations in scene illumination
- **Viewpoint-independent edges**: Reflect inherent 3D object properties (surface markings, surface shape) — do not change with viewpoint
- **Viewpoint-dependent edges**: Change as viewpoint changes, reflect scene geometry (e.g., occlusion boundaries)
- **Edge vs. line**: An edge is a boundary between two regions; a line is a thin feature with an edge on each side (lines are detected by ridge detectors, not edge detectors)
- **Edge blur model**: Real edges are not ideal step functions; they are affected by focal blur (depth-of-field/PSF), penumbral blur (shadow from non-zero-radius light), and shading on smooth objects. Modeled as a Gaussian-smoothed step edge (error function) with blur scale parameter sigma
- **Fragmentation**: A common problem where detected edge curves are not connected, have missing segments, or include false edges
- **Two main categories of approaches**:
  - **Search-based**: Compute first-order derivative (gradient magnitude), then search for local directional maxima
  - **Zero-crossing-based**: Compute second-order derivative (Laplacian or nonlinear differential expression), then find zero crossings
- **Non-maximum suppression (NMS)**: Edge points defined as points where gradient magnitude assumes a local maximum in the gradient direction — produces thin edges by definition
- **Hysteresis thresholding**: Uses two thresholds (upper and lower). Upper threshold starts an edge; edge is traced while above lower threshold. Handles the problem of choosing a single threshold and assumes edges are continuous curves
- **Edge thinning**: Post-processing technique to reduce thick edges to one-pixel-wide elements; uses connectivity analysis (typically 8-connectivity) with multi-pass directional removal

## Commands and Syntax

**Central difference gradient filters:**
```
Lx = [-1/2, 0, +1/2]  (vertical kernel)
Ly = [+1/2, 0, -1/2]  (horizontal kernel)
```

**Sobel operator kernels:**
```
        [+1  0  -1]              [+1  +2  +1]
Ly =    [+2  0  -2]      Lx =   [ 0   0   0]
        [+1  0  -1]              [-1  -2  -1]
```

**Gradient magnitude:**
```
|∇L| = sqrt(Lx² + Ly²)
```

**Gradient direction:**
```
θ = atan2(Ly, Lx)
```

**Second-order derivative filters (discrete):**
```
Lxx(x,y) = L(x-1,y) - 2L(x,y) + L(x+1,y)
Lyy(x,y) = L(x,y-1) - 2L(x,y) + L(x,y+1)
Lxy(x,y) = 1/4 * [L(x-1,y-1) - L(x-1,y+1) - L(x+1,y-1) + L(x+1,y+1)]
```

**Differential edge detection (Lindeberg):**
Zero-crossings of: `Lx²·Lxx + 2·Lx·Ly·Lxy + Ly²·Lyy = 0`
with sign condition: `Lx³·Lxxx + 3·Lx²·Ly·Lxxy + 3·Lx·Ly²·Lxyy + Ly³·Lyyy ≤ 0`

**Edge thinning algorithm (8-connectivity):**
1. Multi-pass directional scan (N, S, E, W)
2. Remove a point if: no neighbor in current pass direction, not a line endpoint, isolated, and removal does not disconnect neighbors
3. Repeat passes until desired accuracy

## Relationships

- **Feature detection pipeline**: Edge detection is a subtask of feature detection, alongside corner detection, blob detection, and ridge detection
- **Scale space**: Gaussian pre-smoothing is almost always applied before edge detection; differential edge detection operates on scale-space representations L(x,y;t)
- **Canny edge detector**: Combines Gaussian smoothing, gradient computation, non-maximum suppression, and hysteresis thresholding — still considered state-of-the-art
- **Marr-Hildreth algorithm**: Zero-crossings of Laplacian of Gaussian (LoG) — historically important but produces false edges at gradient minima and poor localization at curved edges
- **Canny-Deriche detector**: Derived from similar criteria as Canny but uses recursive filters instead of Gaussian/exponential filters
- **Hough transform**: Benefits significantly from thinned edges for line/ellipse detection
- **Object recognition**: Sharp, thin edges improve recognition efficiency
- **Noise reduction**: Pre-processing step critical to edge detection quality; higher-dimensional filters (e.g., 7x7 Prewitt) trade resolution for better SNR handling
- **Related 1D problems**: Step detection (spatial discontinuities) and change detection (temporal discontinuities)

## Exam-Relevant Points

- **Canny edge detector criteria**: Detection (find all edges), localization (edges close to true position), minimal response (single response per edge). Optimal filter is sum of four exponentials, well-approximated by first-derivative of Gaussian
- **Sobel vs. Prewitt vs. Roberts Cross**: All are first-order gradient operators with different kernel designs; Sobel uses weighted center row/column for smoothing
- **Search-based = first-order derivatives; zero-crossing-based = second-order derivatives** — know which methods fall in which category
- **Hysteresis thresholding uses TWO thresholds** (upper to start, lower to continue) — distinguishes Canny from simple threshold approaches
- **Non-maximum suppression** produces thin edges (1 pixel wide) without post-processing; gradient direction is rounded to multiples of 45° on discrete grids
- **Marr-Hildreth limitations**: Returns false edges at local gradient minima; poor localization at curved edges — primarily of historical interest
- **Edge blur sources**: Focal blur (depth-of-field), penumbral blur (shadows), smooth-surface shading — not just noise
- **Gaussian smoothing** is the standard pre-processing step for edge detection (noise reduction); the scale parameter must be chosen appropriately
- **Kovalevsky method**: Unique in using color channel differences rather than brightness — can detect edges between pixels of equal brightness but different colors
- **Differential edge detection** (Lindeberg): Achieves sub-pixel accuracy by finding zero-crossings of second-order directional derivative in gradient direction within scale space
- **Extended filters** (e.g., 7x7 Prewitt): Handle low-SNR images at the cost of spatial resolution
