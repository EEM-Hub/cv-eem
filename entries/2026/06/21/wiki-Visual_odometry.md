---
source: sources/wiki-Visual_odometry.md
source_url: https://en.wikipedia.org/wiki/Visual_odometry
---

## Visual Odometry and Egomotion Estimation

Visual odometry (VO) is the process of determining the position and orientation of a robot or camera-equipped system by analyzing sequential camera images of its environment. It overcomes limitations of traditional wheel-based odometry — such as wheel slip on non-smooth surfaces and cumulative drift errors — by using visual information to estimate distance traveled. VO is applicable to any locomotion type (wheeled, legged, aerial) and is foundational in autonomous robotics, augmented reality, and planetary exploration (notably the Mars Exploration Rovers).

## Key Concepts

- **Visual Odometry (VO)**: Estimates camera/robot pose changes from sequential images, replacing or supplementing mechanical odometry (wheel encoders).
- **Traditional odometry limitations**: Wheel slip, non-uniform surfaces, and cumulative error make encoder-based odometry increasingly unreliable over time.
- **Monocular VO**: Uses a single camera; cannot directly recover absolute scale.
- **Stereo VO**: Uses two cameras in a stereo configuration; provides depth and scale information, reducing error.
- **Visual-Inertial Odometry (VIO)**: Fuses camera data with an inertial measurement unit (IMU); widely used in commercial quadcopters for GPS-denied localization.
- **Feature-based methods**: Extract and track interest points (features) across frames to estimate motion; traditional approach.
- **Direct (appearance-based) methods**: Use pixel intensities directly rather than extracting features; examples include LSD-SLAM and semi-dense VO.
- **Hybrid methods**: Combine feature-based and direct approaches.
- **Visiodometry**: Uses phase correlation to estimate planar roto-translations between images, avoiding explicit feature extraction.
- **Optical flow**: The vector field describing apparent motion of features between frames; constructed using methods like Lucas-Kanade.
- **Focus of expansion**: The point in the optical flow field from which features diverge, indicating the direction of camera motion.
- **Egomotion**: The 3D motion of a camera within a rigid environment; closely related to VO but emphasizes the camera's own motion estimation.

## Commands and Syntax

No software commands per se, but the standard VO pipeline consists of these algorithmic stages:

1. **Acquire input images** — from single, stereo, or omnidirectional cameras
2. **Image correction** — lens distortion removal and preprocessing
3. **Feature detection and matching** — extract interest points, establish correspondence between frames via:
   - Feature extraction + correlation (not long-term tracking), or
   - Optical flow construction (Lucas-Kanade method)
4. **Outlier removal** — check flow field vectors for tracking errors
5. **Camera motion estimation** — from the optical flow, using either:
   - **Kalman filter** for state estimate maintenance, or
   - **Geometric minimization** of reprojection error between adjacent images (via mathematical optimization or random sampling, e.g., RANSAC)
6. **Trackpoint repopulation** — periodically add new features to maintain image coverage

## Relationships

- **Odometry / Dead Reckoning**: VO is the vision-based analog of traditional mechanical odometry; both estimate incremental pose changes but VO avoids wheel-slip errors.
- **Optical Flow**: Core intermediate representation in VO pipelines; connects to Lucas-Kanade and other flow estimation methods.
- **SLAM (Simultaneous Localization and Mapping)**: VO provides the motion estimation front-end; SLAM adds map building and loop closure for globally consistent trajectories.
- **Feature Detection / Extraction**: VO depends on corner detectors (Harris, FAST, ORB) and descriptors (SIFT, SURF, BRIEF) for feature-based approaches.
- **IMU / Sensor Fusion**: VIO fuses visual and inertial data, improving robustness in texture-poor or high-dynamic environments.
- **Perspective-n-Point (PnP)**: Used within VO to estimate camera pose from 2D-3D point correspondences.
- **Structure from Motion (SfM)**: Offline multi-view reconstruction that shares algorithmic foundations with VO but processes all images globally rather than sequentially.
- **Kalman Filter / State Estimation**: Used as one approach to maintaining pose estimates within the VO pipeline.

## Exam-Relevant Points

- VO estimates pose from **sequential images** and works with **any locomotion type**, unlike wheel encoders.
- **Stereo VO** provides depth and scale; **monocular VO** suffers from scale ambiguity.
- The two main method families are **feature-based** (extract and match keypoints) and **direct** (minimize photometric error on pixel intensities).
- The VO pipeline has six canonical stages: image acquisition, correction, feature detection/matching, outlier removal, motion estimation, and trackpoint repopulation.
- **Motion estimation** can use either a **Kalman filter** or **reprojection error minimization** (geometric optimization or RANSAC).
- **VIO** adds an IMU to VO, critical for GPS-denied environments (e.g., indoor drones).
- **Egomotion** is the 3D motion of the camera itself; estimated from the **focus of expansion** in the optical flow field.
- The **Lucas-Kanade method** is the standard algorithm for constructing the optical flow field in VO.
- **Phase correlation** (visiodometry) is an alternative that estimates planar roto-translations without feature extraction.
- VO was validated on the **Mars Exploration Rovers** (Maimone et al., 2007), a landmark application demonstrating real-world robustness.
- All VO methods suffer from **drift** over time since they estimate incremental motion; loop closure or global optimization (as in SLAM) is needed for long-term consistency.
