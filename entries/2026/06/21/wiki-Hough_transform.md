---
source: sources/wiki-Hough_transform.md
source_url: https://en.wikipedia.org/wiki/Hough_transform
---

## Hough Transform for Shape Detection

The Hough transform is a feature extraction technique that detects imperfect instances of geometric shapes (lines, circles, ellipses, arbitrary shapes) in images through a voting procedure in parameter space. Edge points vote for shape candidates in an accumulator array; peaks in the accumulator correspond to detected shapes. Mathematically equivalent to the Radon transform, it was patented by Paul Hough in 1962, modernized by Duda and Hart (1972) with the rho-theta parameterization, and popularized by Ballard (1981) for arbitrary shapes.

## Key Concepts

- **Voting procedure**: Each edge pixel casts votes for all shape parameter combinations it could belong to; shapes appear as peaks (local maxima) in the accumulator space.
- **Parameter space (Hough space)**: A quantized space whose dimensions equal the number of shape parameters — 2D for lines (r, θ), 3D for circles (a, b, r), 3D for planes (θ, φ, ρ).
- **Hesse normal form for lines**: `r = x·cos(θ) + y·sin(θ)` where r is perpendicular distance from origin to line, θ is angle of that perpendicular. Avoids the unbounded slope problem of y = mx + b.
- **Sinusoidal duality**: A single image point maps to a sinusoidal curve in (r, θ) space; collinear points produce sinusoids that intersect at the same (r, θ) — converting collinear-point detection to concurrent-curve detection.
- **Accumulator array**: Discretized matrix over parameter space; each cell accumulates votes. Bin with highest value = most-supported shape instance.
- **Probabilistic interpretation**: The Hough transform performs approximate naive Bayes inference — uniform prior over shape space, independent pixel evidence (log-likelihoods add), peak detection = maximum likelihood estimation. Ignoring negative evidence enables detection of partially occluded shapes.
- **Gradient direction optimization** (O'Gorman & Clowes): Using the edge gradient direction constrains θ to ~45° arc instead of full 180°, reducing computation and spurious votes.
- **Kernel-based Hough Transform (KHT)**: Votes on clusters of approximately collinear pixels using oriented elliptical-Gaussian kernels; achieves real-time performance on large images (e.g., 1280×960).
- **3DKHT for plane detection**: Extends KHT to unorganized point clouds with O(n log n) cost; uses trivariate Gaussian kernels on co-planar clusters in spherical (θ, φ, ρ) accumulator. Orders of magnitude faster than RANSAC/RHT.
- **Generalized Hough Transform**: For shapes without analytic parameterization — uses a precomputed look-up table (R-table) so features vote for position, orientation, and scale of arbitrary template shapes.

## Commands and Syntax

**Line detection (rho-theta parameterization):**
```
r = x·cos(θ) + y·sin(θ)
```
- Accumulator dimensions: quantized r (distance) × quantized θ (angle)
- For each edge pixel (x, y): sweep θ over range, compute r, increment accumulator[r][θ]
- Extract lines from local maxima in accumulator

**Circle detection:**
```
(i - a)² + (j - b)² = r²
```
- Known radius: 2D accumulator (a, b) for center
- Unknown radius: 3D accumulator (a, b, r)
- For each edge point (i, j): increment cells satisfying circle equation
- Find local maxima → detected circles

**Plane detection (3D point clouds):**
- Explicit form: `z = aₓx + aᵧy + d` → 3D accumulator (aₓ, aᵧ, d) — works well for near-horizontal planes (e.g., airborne lidar)
- Normal-vector form: parameterize by spherical normal (θ, φ) and distance ρ — general orientation, each point votes for sinusoidal surface

**Cylinder detection (point clouds):**
- Two-step: (1) find cylinder orientation, (2) find position and radius

## Relationships

- **Edge detection** (Canny, Sobel, etc.) is typically a prerequisite — provides the edge map that feeds into the Hough transform
- **Radon transform**: Mathematically identical in 2D; Hough is the image-analysis application of Radon
- **RANSAC**: Competing approach for shape fitting in point clouds; Hough is deterministic while RANSAC is probabilistic/randomized
- **Randomized Hough Transform (RHT)**: Stochastic variant that samples point subsets rather than exhaustively voting
- **Generalized Hough Transform** (Ballard 1981): Extension for non-analytic shapes using R-tables; links to template matching
- **Feature detection pipeline**: Sits between edge detection (upstream) and shape-based object recognition (downstream)
- **Blob/corner detection**: Alternative feature detection approaches (LoG, DoG, Harris) that detect different primitives
- **Naive Bayes / Maximum Likelihood Estimation**: The probabilistic framework underpinning the accumulator voting logic

## Exam-Relevant Points

- The rho-theta parameterization `r = x·cos(θ) + y·sin(θ)` solves the unbounded-slope problem of y = mx + b for vertical lines
- Each image point maps to a **sinusoid** in Hough space; collinear points produce sinusoids that **intersect** at the same (r, θ)
- Accumulator dimensionality equals the number of shape parameters: 2 for lines, 3 for circles (with unknown radius), 3 for planes
- The Hough transform handles **noise, gaps, and partial occlusion** because it accumulates evidence globally — this is its primary advantage over local edge-linking methods
- Gradient direction can reduce the voting range from 180° to ~45°, improving both speed and accuracy
- For circles with **known radius**: 2D accumulator; **unknown radius**: 3D accumulator (more expensive)
- The Hough transform is mathematically equivalent to the **Radon transform**
- Probabilistic interpretation: uniform prior + naive Bayes (independent pixel evidence) + MLE (peak detection); ignoring negative evidence enables partial-occlusion robustness
- KHT achieves real-time by voting on **clusters** rather than individual pixels
- 3DKHT for plane detection in point clouds runs in **O(n log n)** — much faster than RANSAC/RHT
- The **Generalized Hough Transform** uses an **R-table** (look-up table) to detect arbitrary non-analytic shapes
- Key limitation: high-dimensional parameter spaces cause memory and computation explosion — mitigation strategies include gradient constraints, coarse-to-fine search, and multi-stage cascaded transforms
- Hough transform returns **infinite lines** (no endpoint information) — a post-processing step is needed to determine which image segments correspond to detected lines
