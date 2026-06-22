---
source: sources/wiki-Stereo_vision.md
source_url: https://en.wikipedia.org/wiki/Stereo_vision
---

## Stereopsis: Binocular Depth Perception

Stereopsis is the visual sensation that objects occupy different positions in depth — stronger than the flat depth cues provided by 2D perspective. Two mechanisms produce it: **binocular depth vision** (processing disparity between two eyes separated by ~6.5 cm) and **motion vision** (processing optical flow when the observer moves). In vision research, "stereopsis" typically refers to the binocular mechanism. It comes in two qualities — fine stereopsis (shape/object recognition) and coarse stereopsis (spatial localization) — each served by distinct neural pathways.

## Key Concepts

- **Binocular disparity**: The difference in visual direction between the two eyes for a given point in space. This is the fundamental input for stereoscopic depth.
- **Horizontal disparity**: The horizontal component of binocular disparity, caused by the ~6.5 cm inter-ocular distance. Sufficient on its own to evoke depth (Wheatstone, 1838).
- **Horopter**: A circle through both eyes and the fixation point. Points on it project to corresponding retinal locations (zero disparity). Perceived as a "screen" on which the visual world is projected.
- **Crossed (negative) disparity**: Object is closer than the horopter — left-eye direction appears right of right-eye direction on the perceptual screen.
- **Parallel (positive) disparity**: Object is farther than the horopter — directions appear side-by-side in the expected order.
- **Fine stereopsis (patent stereopsis)**: Observer can judge the magnitude of depth — perceived depth increases linearly with small disparities. Processed by the parvocellular (parvo) pathway through inferior temporal cortex ("what" pathway). Handles fine detail, color, slow changes.
- **Coarse stereopsis (qualitative stereopsis)**: Observer can judge relative order (nearer/farther) but not magnitude. Processed by the magnocellular (magno) pathway through posterior parietal cortex ("where"/"how" pathway). Handles motion, contrast, rapid changes.
- **Random dot stereogram (Julesz, 1971)**: Proves depth perception precedes form perception — each eye sees only random dots, but binocular viewing reveals a shape in depth.
- **Correspondence problem**: When multiple possible pairings exist between left/right visual directions, the brain must select the correct match. The visual system prefers surfaces (globality principle) and minimal-depth interpretations.
- **Binocular ghost images**: In the double-nail illusion, the brain selects incorrect correspondences, causing objects to appear at phantom locations (C and D) instead of their real positions (A and B).
- **Pulfrich illusion**: A dark filter over one eye delays neural signals, causing a pendulum swinging in a flat arc to appear to move in an elliptical path in depth — demonstrates the simultaneity requirement.

## Commands and Syntax

Not applicable (this is a perceptual science topic, not a software/configuration domain). However, relevant experimental methods include:

- **Stereoscope viewing**: Present separate left/right images to each eye to control disparity.
- **Random dot stereogram construction**: Shift a region of random dots horizontally between left and right images to embed a hidden shape at a controlled disparity.
- **Vergence control techniques**:
  - Brief/unexpected stimulus presentation (prevents reflexive eye movements)
  - Vernier line alignment (each eye sees a hairline the other doesn't; must align to confirm correct fixation)
  - Eye movement registration during experiments

## Relationships

- **Binocular disparity** is closely related to **motion parallax** — both produce depth from angular differences, but disparity uses two viewpoints simultaneously while parallax uses sequential viewpoints during observer motion. They may share the same neural processing system (magno/coarse pathway).
- **Epipolar geometry** provides the geometric framework for understanding correspondence constraints between two viewpoints — directly relevant to both biological and **computer stereo vision**.
- **Vergence eye movements** position the horopter so objects of interest fall within the stereopsis zone; this links stereopsis to **oculomotor control**.
- **Object recognition** depends on fine stereopsis (parvo pathway), while **spatial navigation/localization** depends on coarse stereopsis (magno pathway) — connecting to the broader "what" vs. "where" dual-stream model of visual processing.
- **Depth perception** is the broader category; stereopsis is one cue among many (perspective, occlusion, texture gradients, accommodation, motion parallax).
- **Binocular summation** is a separate benefit of binocular vision (improved visual quality) distinct from stereopsis.

## Exam-Relevant Points

- Stereopsis requires **horizontal disparity** — Wheatstone proved this in 1838 using line stereograms viewed in a stereoscope.
- The **horopter** is the locus of zero disparity; crossed disparity = nearer, parallel disparity = farther.
- **Fine stereopsis**: magnitude judgment, small disparities, linear depth-disparity relationship, parvo pathway, inferior temporal cortex ("what").
- **Coarse stereopsis**: order-only judgment, larger disparities, magno pathway, posterior parietal cortex ("where"/"how").
- Julesz's **random dot stereograms** proved that stereoscopic depth is computed **before** form recognition — no monocular shape cues needed.
- Conditions for stereopsis: (1) horizontal disparity, (2) matching edges of same contrast polarity, (3) approximate temporal simultaneity, (4) proper vergence alignment.
- Color and brightness do **not** need to match between eyes — stereopsis works even with opposite colors (no color mixing occurs; binocular rivalry alternation instead).
- Barlow, Blakemore & Pettigrew (1967) discovered **disparity-tuned neurons** in cat visual cortex — the neural basis of stereopsis. Poggio later found V2 neurons responding to random-dot stereogram depth in monkeys.
- The two stereopsis systems (fine/coarse) can function partly independently — loss of fine stereopsis does not necessarily eliminate coarse stereopsis.
- Practical benefits: threading needles, catching fast balls, pouring liquids, surgical precision, aircraft piloting. For driving, stereopsis helps only at intermediate distances; crash risk in elderly correlates more with glare and visual field loss than stereoacuity.
