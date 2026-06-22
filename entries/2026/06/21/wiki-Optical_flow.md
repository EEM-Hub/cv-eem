---
source: sources/wiki-Optical_flow.md
source_url: https://en.wikipedia.org/wiki/Optical_flow
---

## Optical Flow: Motion Estimation from Visual Scenes

Optical flow (or optic flow) is the pattern of apparent motion of objects, surfaces, and edges in a visual scene caused by relative motion between an observer and the scene. It can also be defined as the distribution of apparent velocities of brightness patterns in an image. The concept originated from WWII research into pilot vision during landing, with James J. Gibson coining the term "optic flow" in 1950. It is foundational to both biological vision systems and computer vision, with applications spanning robotics, video compression, autonomous navigation, and fluid mechanics.

## Key Concepts

- **Brightness constancy constraint**: The assumption that a point's brightness remains constant between frames: I(x,y,t) - I(x+u, y+v, t+1) = 0, where w = (u,v) is the displacement vector
- **Aperture problem**: The brightness constancy constraint alone cannot solve for (u,v) at each pixel — one equation, two unknowns — so additional constraints are needed
- **Regularized models** (global methods): Add a smoothness/regularization constraint, minimizing a cost function with both a data term and a gradient penalty weighted by α. When Ψ(x) = x², this is the **Horn-Schunck method**
- **Parametric models** (local methods): Group pixels into regions and estimate motion parameters per region. The simplest is the **Lucas-Kanade method**, which assumes purely translational motion in rectangular patches
- **Variational approach**: Linearizes the brightness constancy constraint via first-order Taylor expansion: Ix·u + Iy·v + It = 0, making the optimization tractable
- **Coarse-to-fine / multi-scale**: Addresses the limitation that linearization is only valid for small displacements — downsample, solve, then refine at progressively finer scales using image warping
- **Focus of expansion**: The point in the visual field from which optic flow vectors radiate outward during forward motion — indicates direction of travel
- **Cost volumes**: A 4D tensor representing matching costs between all pixel pairs in two feature maps, used in learning-based methods

## Commands and Syntax

No CLI commands per se, but key algorithmic formulations:

- **Linearized optical flow constraint equation**: `Ix·u + Iy·v + It = 0` where Ix, Iy, It are spatial and temporal image derivatives
- **Horn-Schunck energy functional**: E = ∫∫ (Ix·u + Iy·v + It)² + α(|∇u|² + |∇v|²) dx dy — solved via Euler-Lagrange equations discretized and iterated with Gauss-Seidel
- **Lucas-Kanade loss**: Minimizes Σ |I(x+u, y+v, t+1) - I(x,y,t)| over a local rectangular region R
- **Alternative solvers for non-linearized formulations**: Max-flow min-cut, linear programming, belief propagation

## Relationships

- **Motion estimation / video compression (MPEG)**: Optical flow is related to but distinct from block-based motion estimation — optical flow additionally seeks to infer 3D scene structure and observer motion
- **Visual odometry**: Optical flow enables robots and autonomous vehicles to estimate ego-motion from camera input
- **Particle image velocimetry (PIV)**: Optical flow applied to fluid mechanics for non-invasive flow measurement using tracer particles
- **Deep learning architectures**: FlowNet (2015, CNN/U-Net), PWC-Net (cost volumes + warping), RAFT (GRU-based iterative refinement at 1/8 resolution) — each generation trading off accuracy, memory, and resolution handling
- **Self-supervised learning**: Methods like CroCo use cross-view completion pre-training to reduce dependence on synthetic ground-truth datasets (FlyingChairs, FlyingThings3D)
- **Neuromorphic engineering**: Bio-inspired circuits that respond to optical flow, relevant to event cameras and low-power sensors
- **Optical flow sensors**: Hardware implementations (vision chips) used in optical mice, UAV stabilization, and robotics navigation

## Exam-Relevant Points

- The **aperture problem** is the core reason additional constraints (smoothness or parametric) are needed beyond brightness constancy
- **Horn-Schunck** = global/regularized method (dense flow, Ψ(x)=x²); **Lucas-Kanade** = local/parametric method (sparse flow, rectangular patches, translation-only)
- Linearization via Taylor expansion is only valid for **small displacements** — coarse-to-fine pyramids are the standard remedy
- The regularization parameter **α** controls the trade-off between data fidelity and flow smoothness — higher α yields smoother but potentially less accurate flow
- **RAFT** replaced coarse-to-fine pyramids with iterative GRU-based updates at fixed 1/8 resolution, improving fine detail preservation and fast-motion robustness
- Supervised learning models rely on **synthetic datasets** (FlyingChairs, FlyingThings3D) and are evaluated on **MPI Sintel, KITTI, and Spring** benchmarks
- The **domain gap** between synthetic training data and real-world footage remains a key challenge for learning-based methods
- Optical flow differs from simple motion vectors: it also encodes information about **3D scene structure** and **observer vs. object motion** ambiguity
- **James J. Gibson** (1947/1950) is the foundational figure; the concept has roots in Euclid's Optics and Helmholtz's motion parallax
