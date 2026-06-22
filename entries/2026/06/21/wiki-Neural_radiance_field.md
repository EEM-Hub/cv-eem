---
source: sources/wiki-Neural_radiance_field.md
source_url: https://en.wikipedia.org/wiki/Neural_radiance_field
---

## Neural Radiance Fields (NeRF) — 3D Scene Reconstruction from 2D Images

Neural Radiance Fields (NeRF) are a neural network-based technique for reconstructing 3D scene representations from collections of 2D photographs. Introduced in 2020 (Mildenhall et al., ECCV 2020), a NeRF encodes a scene as a continuous volumetric radiance field parameterized by a deep neural network. Given spatial coordinates (x, y, z) and viewing direction (θ, Φ), the network predicts volume density and view-dependent emitted radiance, which are composited into images via classical volume rendering. The method enables novel view synthesis, geometry extraction, and reflectance estimation.

## Key Concepts

- **Core representation**: An MLP maps 5D input (3D position + 2D viewing direction) to volume density σ and RGB color c. Density is view-independent; color is view-dependent (captures specular effects).
- **Per-scene optimization**: A NeRF must be retrained for every new scene — it is not a generalizable model out of the box.
- **Differentiable rendering pipeline**: Camera rays are marched through the scene, points are sampled, the MLP is queried, and classical volume rendering produces pixel colors. The entire pipeline is differentiable, enabling end-to-end gradient descent against ground-truth images.
- **Data requirements**: Standard 2D images with known camera poses (obtained via SfM/COLMAP, SLAM, GPS, or IMU). No specialized cameras needed.
- **Spectral bias**: Raw MLPs struggle with high-frequency detail. Fourier feature mapping (positional encoding) lifts low-dimensional inputs into a higher-dimensional space, enabling the network to learn sharp details.
- **Plenoxels disproved the necessity of the MLP**: The differentiable volume rendering pipeline — not the neural network itself — is the critical component. Direct optimization of voxel coefficients matches NeRF quality in orders-of-magnitude less time.
- **Gaussian splatting** is a successor/competitor that represents scenes as sparse 3D Gaussians rather than a volumetric field, achieving faster rendering and often higher fidelity.

## Key Variations

| Variant | Year | Key Innovation |
|---------|------|----------------|
| **Fourier Feature Mapping** | 2020 | Positional encoding overcomes spectral bias for high-frequency detail |
| **BARF** (Bundle-Adjusting NeRF) | 2021 | Jointly optimizes camera poses and radiance field using dynamic low-pass filter (coarse-to-fine) |
| **mip-NeRF** | 2021 | Anti-aliasing across scales by casting conical frustums instead of single rays; fits Gaussians to frustum sections |
| **Learned Initializations** | 2021 | Meta-learning assigns initial MLP weights for fast convergence; enables few-shot (even single-image) reconstruction |
| **NeRF-W** (NeRF in the Wild) | 2021 | Three separate MLPs for static scene, appearance embedding (lighting), and transient embedding (moving objects); trains on uncontrolled photo collections |
| **NeRV** (Relighting) | 2021 | MLP outputs surface normals, material params, visibility — enables relighting without retraining |
| **PlenOctrees** | 2021 | Bakes NeRF into an octree with spherical radiance; 3000× faster rendering (real-time) |
| **SNeRG** | 2021 | Sparse voxel grid with lightweight MLP for view-dependent residuals; outperforms PlenOctrees |
| **Instant NGP** (Nvidia) | 2022 | Multi-resolution hash encoding with O(1) lookups + GPU parallelism; real-time *training* |
| **Plenoxels** | 2022 | No neural network at all — direct SGD on sparse voxel coefficients; proves MLP is not essential |
| **3D Gaussian Splatting** | 2023 | Sparse 3D Gaussians optimized via SGD; real-time rendering, often surpasses NeRF fidelity |

## Commands and Syntax

No standard CLI; key frameworks and tools:
- **Nerfstudio** (Tancik et al., SIGGRAPH 2023): Modular open-source framework for NeRF development and experimentation.
- **COLMAP**: Standard SfM tool used upstream to estimate camera poses from image collections.
- **Instant-NGP** (Nvidia): Reference implementation for hash-encoded instant training.

Typical pipeline:
1. Capture images from multiple viewpoints
2. Run SfM (e.g., COLMAP) to extract camera intrinsics/extrinsics
3. Train NeRF model on images + poses
4. Query trained model for novel view synthesis or geometry extraction (e.g., marching cubes for mesh)

## Relationships

- **Structure from Motion (SfM)**: Upstream dependency — provides camera poses needed for training
- **SLAM**: Alternative/complementary method for obtaining camera poses in real-time
- **Volume rendering**: Classical technique that NeRF's rendering pipeline is built upon
- **Ray marching**: The sampling strategy used to query points along camera rays
- **Gaussian splatting**: Competing/successor technique using explicit point-based representation instead of implicit volumetric field
- **Photogrammetry**: Traditional non-neural 3D reconstruction; more geometrically accurate but fails on reflective/transparent surfaces where NeRF succeeds
- **Generative AI**: NeRF combined with diffusion/instruction-following models enables text-guided 3D scene editing
- **Neural fields**: NeRF is a specific instance of the broader neural field paradigm (coordinate-based neural representations)

## Exam-Relevant Points

- NeRF input is 5D: **(x, y, z, θ, Φ)** → output is **(RGB color, volume density σ)**. Density is view-independent; color is view-dependent.
- NeRF requires **retraining per scene** — it is not a single generalizable model.
- **Positional/Fourier encoding** is essential to overcome spectral bias and capture high-frequency details.
- **BARF** solves the imperfect camera pose problem by jointly optimizing poses and the radiance field.
- **mip-NeRF** replaces single rays with conical frustums for **multi-scale anti-aliasing**.
- **Plenoxels proved the MLP is not essential** — the differentiable rendering pipeline is the key component.
- **Gaussian splatting** is the primary modern alternative: explicit representation, faster training and rendering, often higher quality.
- Real-time rendering methods: PlenOctrees (3000× speedup via octree), SNeRG (sparse voxel grid), Instant NGP (hash encoding for real-time *training*).
- NeRF **excels over photogrammetry** on reflective and transparent objects but does **not inherently produce dimensionally accurate geometry**.
- Applications span content creation, medical imaging (3D CT from sparse X-rays), robotics (transparent object manipulation), and VR/AR.
- Key conferences: ECCV (original paper), CVPR, ICCV, SIGGRAPH, NeurIPS.
