---
source: sources/wiki-Semantic_segmentation.md
source_url: https://en.wikipedia.org/wiki/Semantic_segmentation
---

## Image Segmentation: Methods, Types, and Applications

Image segmentation is the process of partitioning a digital image into multiple segments (sets of pixels), where each pixel is assigned a label such that pixels sharing a label have common characteristics (color, intensity, texture). The goal is to transform an image into a representation that is more meaningful and easier to analyze — locating objects, boundaries, and regions. The result is either a complete covering of the image by labeled regions, or a set of extracted contours.

## Key Concepts

- **Definition**: Assigning a label to every pixel so that same-label pixels share visual characteristics; adjacent regions differ significantly in those characteristics
- **Three types of segmentation**:
  - **Semantic segmentation** — classifies every pixel by category (e.g., all "person" pixels get one label, all "background" another); does not distinguish instances
  - **Instance segmentation** — identifies each distinct object instance separately (e.g., person 1 vs. person 2)
  - **Panoptic segmentation** — combines both: every pixel gets a class label AND an instance ID
- **Two broad technique classes**: classical computer vision approaches and AI/deep-learning-based techniques
- **Thresholding** — simplest method; converts grayscale to binary using a clip-level. Key challenge is selecting the threshold. Methods include Otsu's method (maximum variance), maximum entropy, balanced histogram thresholding, and k-means clustering
- **K-means clustering** — iteratively assigns pixels to K clusters by minimizing distance (color, intensity, texture, location). Guaranteed to converge but not guaranteed optimal. K-means++ improves initialization
- **Mean Shift** — partitions into an unknown number of clusters (no need to specify K a priori)
- **Histogram-based methods** — single-pass efficiency; peaks and valleys in the histogram locate clusters. Can be applied recursively for finer segmentation. Weakness: identifying significant peaks/valleys can be difficult
- **Edge detection** — detects region boundaries via intensity discontinuities. Produces disconnected edges that must be closed for full segmentation. Related concept: spatial-taxons (hierarchical figure-ground decomposition)
- **Region growing** — starts from seed pixels, iteratively adds neighbors that satisfy a similarity criterion. Variants:
  - Seeded: requires initial seed points; results depend on seed placement
  - Unseeded: no explicit seeds; creates new regions when delta exceeds threshold T
  - Statistical Region Merging (SRM): builds 4-connected pixel graph, sorts edges by intensity difference, merges via statistical predicate
  - Lambda-connected: connectivity degree based on pixel intensity paths
- **Compression-based methods** — optimal segmentation minimizes coding length; models boundary smoothness (Huffman-coded chain codes) and texture (multivariate normal entropy). Uses agglomerative clustering
- **Dual clustering** — combines histogram analysis, cluster compactness, and border gradients across brightness space and image space
- **Isolated point detection** — uses the Laplacian operator (second derivative); a point is isolated if |R(x,y)| >= T
- **Motion-based segmentation** — exploits frame-to-frame differences to isolate moving objects; interactive segmentation uses robotic poking to induce motion

## Commands and Syntax

- **Laplacian operator** (discrete form):
  `∇²f(x,y) = f(x+1,y) + f(x-1,y) + f(x,y+1) + f(x,y-1) - 4f(x,y)`
- **K-means algorithm**:
  1. Initialize K cluster centers (random or K-means++)
  2. Assign each pixel to nearest cluster center
  3. Recompute centers as cluster averages
  4. Repeat until convergence
- **Isolated point detection threshold function**:
  `g(x,y) = 1 if |R(x,y)| >= T, else 0`
- **Dual clustering measure**: `M_DC = G / (k × L)` where G = mean border gradient, k = brightness difference, L = total border length; maximize over all thresholds T

## Relationships

- **Edge detection** provides boundaries that feed into segmentation; segmentation and edge detection are complementary
- **Clustering** (k-means, mean shift) connects segmentation to unsupervised learning and data mining
- **Thresholding** is foundational — Otsu's method, histogram methods, and region growing all depend on threshold selection
- **Medical imaging** is the dominant application domain — CT, MRI, volume rendering, 3D reconstruction via marching cubes
- **Object detection, face recognition, pedestrian detection** all build on segmentation as a preprocessing step
- **Deep learning** architectures are increasingly used for nuclei instance segmentation in digital pathology (whole slide images)
- **Panoptic segmentation** unifies semantic and instance segmentation into a single framework
- **Minimum Description Length (MDL)** principle connects compression-based segmentation and edge partitioning methods

## Exam-Relevant Points

- **Semantic vs. instance vs. panoptic**: know the precise definitions and differences — semantic assigns class labels only, instance separates individual objects, panoptic does both
- **Otsu's method** maximizes inter-class variance for automatic threshold selection
- **K-means** is guaranteed to converge but NOT guaranteed to find the global optimum
- **Mean Shift** does not require specifying K in advance (unlike K-means)
- **Histogram-based methods** are the most efficient (single pass through pixels)
- **Region growing** results are sensitive to seed placement and noise
- **Laplacian** is the operator used for isolated point detection (second derivative)
- **Compression-based segmentation** uses the principle that optimal segmentation minimizes coding length; multivariate normal has maximum entropy among distributions with given mean and covariance
- **Edge detection** produces disconnected edges — additional processing needed to close contours for segmentation
- **SRM** uses 4-connectedness and sorts edges by intensity difference in a priority queue
- **Lambda-connected segmentation** computes connectivity degree along pixel paths
- **3D reconstruction** from segmented image stacks uses algorithms like marching cubes
