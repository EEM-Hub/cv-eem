---
source: sources/wiki-Simultaneous_localization_and_mapping.md
source_url: https://en.wikipedia.org/wiki/Simultaneous_localization_and_mapping
---

## Simultaneous Localization and Mapping (SLAM)

SLAM is the computational problem of constructing or updating a map of an unknown environment while simultaneously tracking an agent's position within it. It is a foundational technique in robotics, autonomous vehicles, AR/VR, and other domains where an agent must navigate without prior map knowledge. The problem is inherently circular — you need a map to localize and a location to map — but several approximate algorithms solve it in tractable time.

## Key Concepts

- **Core problem**: Jointly estimate agent state x_t and environment map m_t from a sequence of control inputs u_t and sensor observations o_t, all treated probabilistically.
- **Probabilistic formulation**: Compute the posterior P(m_{t+1}, x_{t+1} | o_{1:t+1}, u_{1:t}) using Bayes' rule for sequential updates, alternating pose and map estimation (EM-like).
- **Map representations**:
  - **Topological maps** capture connectivity/topology rather than geometry; used to enforce global consistency.
  - **Occupancy grid maps** discretize space into cells assumed statistically independent, marking occupied vs. free.
  - **Landmark-based maps** track uniquely identifiable features (Wi-Fi APs, visual features, beacons).
- **Sensor models**: Divide into **landmark-based** (identify discrete features) and **raw-data** (model observation likelihood directly as function of location).
- **Loop closure**: Recognizing a previously visited location and correcting accumulated drift. Often uses bag-of-words over SIFT features to detect revisits.
- **Active SLAM**: Combines mapping with exploration planning — deciding where to move next to maximize information gain (entropy reduction).
- **SLAM with DATMO**: Extension handling dynamic/moving objects (vehicles, pedestrians) alongside static map building.
- **Collaborative SLAM**: Multiple robots or users combine sensor data to jointly build maps (demonstrated in 2021 DARPA Subterranean Challenge).

## Algorithms and Methods

- **EKF SLAM**: Uses Extended Kalman Filter; feature-based with maximum likelihood data association. Was the dominant method in 1990s-2000s. Limited by Gaussian noise assumption — linearization fails under high uncertainty.
- **FastSLAM**: Particle filter-based; replaced EKF SLAM as the preferred method. Uses Rao-Blackwellized particle filter to factor the problem.
- **GraphSLAM**: Builds a factor graph of observation interdependencies; solves via sparse optimization over the full trajectory. Exploits sparsity of the information matrix.
- **Particle filters / Monte Carlo Localization**: Sample-based posterior estimation; handles non-Gaussian distributions.
- **Covariance intersection**: Conservative approximation avoiding statistical independence assumptions; scales to large environments.
- **Bundle adjustment / MAP estimation**: Joint optimization of poses and landmarks from image data; used in commercial systems (Google ARCore). Computes most likely explanation rather than full posterior.
- **Set-membership / interval methods**: Use interval constraint propagation to bound robot pose and map; provide guaranteed enclosures rather than probabilistic estimates.

## Sensor Modalities

| Sensor Type | Characteristics |
|-------------|----------------|
| **Lidar** (2D/3D) | Dense point clouds; enables direct alignment via ICP/registration; high accuracy |
| **Cameras** (monocular/stereo) | Visual SLAM (VSLAM) using features like SIFT/ORB; ubiquitous but sensitive to lighting |
| **Sonar** | Used in underwater SLAM; lower resolution |
| **Radar** | Works in vision/GPS-denied environments |
| **Tactile** | Extremely sparse; requires strong priors |
| **Acoustic** (microphone arrays) | Maps sound source positions; susceptible to reverberation |
| **Wi-Fi** | Signal strength-based; coarse localization |
| **IMU** (inertial) | Shoe-mounted for pedestrian SLAM; drift-prone alone |
| **GPS** | When available, dominates inference and reduces SLAM to localization-only |

## Relationships

- **Kalman filters / Particle filters**: Core estimation algorithms underlying SLAM implementations.
- **Bayes' rule / Recursive Bayesian estimation**: Mathematical foundation for sequential state updates.
- **Computer vision (SIFT, ORB, OpenCV)**: Provides visual features for VSLAM and loop closure.
- **Robot Operating System (ROS)**: Primary open-source framework hosting SLAM implementations.
- **Point Cloud Library (PCL)**: Used with lidar SLAM for 3D map representation.
- **Odometry / Visual odometry**: Provides motion estimates that feed the kinematics model P(x_t | x_{t-1}).
- **Structure from Motion (SfM)**: Closely related offline problem; SLAM is the online/real-time counterpart.
- **Bundle adjustment**: Offline optimization technique adapted for real-time SLAM (e.g., in ARCore).
- **Occupancy grids / Robotic mapping**: Map representation methods tightly coupled with SLAM output.

## Exam-Relevant Points

- SLAM jointly estimates **both** agent pose and environment map — neither is known a priori.
- The mathematical formulation is a **posterior probability** over pose and map given all observations and controls.
- **EKF SLAM** assumes Gaussian noise and fails under high uncertainty due to linearization errors.
- **GraphSLAM** exploits **sparsity** in the information matrix via factor graphs.
- **Loop closure** is critical for correcting accumulated drift; commonly uses **bag-of-words over SIFT features**.
- Modern self-driving cars often simplify SLAM to **localization-only** by using pre-collected HD maps.
- **Active SLAM** uses **entropy** to decide where to explore next.
- The acronym SLAM was coined in **1995**; foundational spatial uncertainty work by Smith and Cheeseman was in **1986**.
- **Stanley** (2005 DARPA Grand Challenge winner) and **Junior** used SLAM as part of their autonomous driving systems.
- Consumer applications include **robot vacuums** and **VR headsets** (Meta Quest 2, PICO 4) for inside-out tracking.
- **Audiovisual SLAM** fuses camera and microphone array data, compensating for each modality's weaknesses (narrow FOV vs. reverberation).
- MAP estimators compute the **most likely** pose/map explanation, not the full posterior distribution.
