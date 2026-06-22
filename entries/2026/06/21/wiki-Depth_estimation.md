---
source: sources/wiki-Depth_estimation.md
source_url: https://en.wikipedia.org/wiki/Depth_estimation
---

## Depth Perception: Visual Cues for 3D Scene Understanding

Depth perception is the visual system's ability to perceive distance to objects, enabling three-dimensional understanding of the world. It relies on two broad categories of cues — monocular (single-eye) and binocular (two-eye) — each exploiting different optical, geometric, and physiological phenomena. This topic is foundational to computer vision, where algorithmic analogs of these biological cues drive stereo vision, monocular depth estimation, and 3D reconstruction.

## Key Concepts

- **Monocular cues** provide depth information from a single viewpoint; **binocular cues** require two viewpoints with known geometry
- **Motion parallax**: relative apparent motion of objects at different distances during observer movement; provides absolute depth if observer velocity/direction is known
- **Depth from optical expansion**: approaching objects produce expanding retinal projections; enables time-to-contact (TTC) estimation
- **Kinetic depth effect**: 3D structure recovered from 2D motion of projected features (structure from motion)
- **Linear perspective**: parallel lines converge at vanishing points; enables relative depth reconstruction
- **Relative size**: objects subtending larger visual angles appear closer; requires same-class assumption
- **Familiar size**: combining known object size with visual angle yields absolute depth
- **Aerial perspective**: atmospheric scattering reduces contrast and shifts color toward blue at distance (rendered as "distance fog" in CG)
- **Accommodation**: ciliary muscle adjustment changes lens focal length; effective only below ~2 meters
- **Occlusion (interposition)**: nearer surfaces partially block farther ones; provides depth ordering but not metric depth
- **Texture gradient**: surface texture detail diminishes with distance
- **Defocus blur**: out-of-focus regions signal depth difference from the focal plane; some spiders use this as a primary depth cue
- **Elevation**: objects closer to the horizon line appear farther away
- **Stereopsis (binocular disparity)**: triangulation from two slightly offset retinal images; disparity magnitude inversely relates to distance
- **Convergence**: angle between eye axes when fixating; effective below ~10 meters
- **Shadow stereopsis**: differential shadow patterns between eyes contribute to stereoscopic depth
- **Only three cues provide absolute distance**: convergence, accommodation, and familiar size; all others are relative

## Commands and Syntax

No commands per se, but the following algorithmic correspondences to biological cues are critical in CV:

- **Stereo matching** — computational analog of stereopsis: rectify image pair, compute disparity map, triangulate depth
- **Structure from Motion (SfM)** — analog of kinetic depth effect and motion parallax: recover 3D from 2D feature tracks across frames
- **Monocular depth estimation** — learned models exploit perspective, texture gradient, relative size, occlusion, and defocus blur
- **Vanishing point detection** — extracts perspective geometry for camera calibration and scene layout
- **Optical flow / time-to-contact** — analog of depth from optical expansion
- **Depth from defocus** — algorithms estimate depth from varying blur across the image

## Relationships

- **Stereo vision systems** directly implement binocular disparity (stereopsis) and require calibrated camera geometry (epipolar geometry, rectification)
- **Monocular depth estimation** (deep learning) implicitly learns most monocular cues listed here — perspective, occlusion, texture gradient, relative/familiar size, aerial perspective
- **Structure from Motion** and **visual odometry** exploit motion parallax computationally
- **Object detection and segmentation** leverage occlusion reasoning for layered scene understanding
- **Rendering and graphics** (aerial perspective as distance fog, perspective projection, depth of field) are inverse problems to depth perception
- **Time-to-contact** estimation connects to autonomous driving and collision avoidance
- **Evolutionary theories** (Newton-Muller-Gudden law, eye-forelimb hypothesis) explain why different species have different visual architectures — relevant to understanding what cues are available in bio-inspired vision systems

## Exam-Relevant Points

- **Monocular vs. binocular distinction**: monocular cues work from a single image; binocular cues require a stereo pair — this maps directly to monocular depth estimation vs. stereo vision in CV
- **Only convergence, accommodation, and familiar size give absolute depth**; all other cues are relative — critical for understanding why scale ambiguity exists in monocular and even some stereo systems
- **Accommodation is effective only below ~2 meters**; convergence below ~10 meters — these limits motivate the use of other cues at longer ranges
- **Stereopsis requires overlapping fields of view** — the binocular field overlap determines the usable stereo region; analogous to stereo camera baseline and field-of-view trade-offs
- **Kinetic depth effect** is the perceptual basis for Structure from Motion — 3D structure recoverable from 2D projected motion
- **Occlusion provides ordinal depth only** (relative ranking), not metric depth — important constraint in occlusion-based reasoning
- **Aerial perspective / atmospheric scattering** causes contrast reduction and blue shift at distance — relevant to outdoor scene understanding and dehazing algorithms
- **Defocus blur as depth cue** is the basis for depth-from-defocus algorithms and is exploited by some biological systems (jumping spiders)
- **Texture gradient** encodes surface orientation and distance — a cue that shape-from-texture algorithms attempt to recover
- **The predator-prey eye placement hypothesis** (frontal eyes for depth, lateral for panoramic view) is an oversimplification — the eye-forelimb hypothesis and counterexamples (crocodiles, dolphins, squirrels) show the relationship is more complex
