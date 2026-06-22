---
source: sources/wiki-Pose_estimation.md
source_url: https://en.wikipedia.org/wiki/Pose_estimation
---

## 3D Pose Estimation: Predicting Object Transformations from Images

3D pose estimation is the process of predicting the transformation (rotation and translation) of an object from a reference pose, given an image or 3D scan. It is fundamental to computer vision and robotics, enabling tasks such as CAD model alignment, object identification, grasping, and manipulation. Input can be a single image, stereo pair, or image sequence, and targets range from rigid objects to body parts (heads, hands). Methods are typically class-specific and do not generalize across object types.

## Key Concepts

- **6DoF pose**: The full pose consists of 3D rotation and 3D translation (6 degrees of freedom).
- **POSIT algorithm** (1995, Dementhon & Davis): Estimates 3D pose directly from 3D model points and 2D image points using iterative correction. Works from a single uncalibrated image. Limitation: only works on **non-coplanar** points (fails on flat/planar objects).
- **CAD model registration**: Aligns a 3D CAD model over a photograph by optimizing a distance measure between the projected model and the image, using either perspective or orthogonal projection.
- **Calibrated camera approach**: When the camera is calibrated to a world coordinate system, projection rays are reconstructed from 2D image points, and 3D points are found along these rays using iterative closest point (ICP)-based correspondence.
- **Correspondence problem**: Matching 2D image features to 3D model points is central to all pose estimation methods.
- **Database comparison methods**: Match input images against a pre-computed database of known object poses. Accuracy is limited to poses represented in the database; these *recognize* rather than *determine* pose.
- **Occlusion handling**: The basic ICP-based algorithm does not handle partial occlusion. Extended algorithms assume rigid coupling between contours so that the pose of one contour constrains others.

## Commands and Syntax

**ICP-based pose estimation pseudocode (basic, no occlusion):**
```
(a) Reconstruct projection rays from the image points
(b) Estimate the nearest point of each projection ray to a point on the 3D contour
(c) Estimate the pose of the contour with the use of this correspondence set
(d) goto (b)
```

**Extended algorithm (handles occlusion via rigidly coupled contours):**
```
(a) Reconstruct projection rays from the image points
(b) For each projection ray R:
     (c) For each 3D contour:
          (c1) Estimate nearest point P1 of ray R to contour
          (c2) if first contour, choose P1 as P
          (c3) else if dist(P1, R) < dist(P, R), update P = P1
(d) Use (P, R) as correspondence set
(e) Estimate pose with this correspondence set
(f) Transform contours, goto (b)
```

**Notable software libraries:**
- **posest** — GPL C/C++ library for 6DoF pose from 3D-2D correspondences
- **diffgeom2pose** — Matlab solver using only two 3D-2D correspondences with directions
- **MINUS** — C++ for relative pose estimation across three views
- **NVIDIA FoundationPose** — Deep learning foundation model for 6DoF pose estimation and tracking, supports both model-based and model-free setups

## Relationships

- **Camera calibration (resectioning)**: Calibrated approaches require known camera intrinsics/extrinsics; relates directly to camera resectioning.
- **Iterative Closest Point (ICP)**: The core algorithmic framework for correspondence-based pose estimation.
- **Correspondence problem**: Fundamental prerequisite — establishing which 2D features map to which 3D model points.
- **Homography**: Related geometric transformation; homography estimation is a simpler special case for planar objects.
- **Articulated body pose estimation**: Extends 3D pose estimation to multi-joint bodies (human pose).
- **Gesture recognition / 3D object recognition**: Downstream applications that consume pose estimates.
- **Stereo vision**: Provides depth information that simplifies the 2D-to-3D recovery problem.
- **Trifocal tensor**: Multi-view geometry concept relevant to three-view relative pose estimation.
- **SIFT features**: Scale-invariant features used as correspondences with attributed directions in some solvers.

## Exam-Relevant Points

- POSIT works from a **single uncalibrated image** but requires an approximate 3D model and **non-coplanar points**.
- 6DoF = 3 rotation + 3 translation parameters.
- The ICP-based approach iteratively refines correspondences between **projection rays** and **3D contour points**.
- Calibrated vs. uncalibrated camera approaches differ in whether camera parameters relative to a world coordinate system are known.
- Database comparison methods **recognize** pose (limited to stored examples) rather than **determine** it analytically.
- Occlusion handling requires the assumption that contours are **rigidly coupled**.
- Both **perspective** and **orthogonal projection** models can be used depending on the pose representation.
- Modern deep learning approaches (e.g., FoundationPose) support both **model-based** and **model-free** 6DoF estimation.
- The distance measure optimized in CAD registration is computed between the photographed object and the 3D model projection at a given pose.
