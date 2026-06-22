---
source: sources/wiki-Image_registration.md
source_url: https://en.wikipedia.org/wiki/Image_registration
---

## Image Registration in Computer Vision

Image registration is the process of transforming different sets of data into a single coordinate system so they can be compared or integrated. The data may come from multiple photographs, different sensors, different times, depths, or viewpoints. It is fundamental to computer vision, medical imaging, military automatic target recognition, satellite imagery analysis, astrophotography, and panoramic image creation.

## Key Concepts

- **Image registration** aligns multiple datasets into one coordinate system to enable comparison or integration
- **Target/fixed/sensed image**: the reference image that remains stationary; **moving/source image(s)**: the image(s) transformed to align with the target
- **Intensity-based methods**: compare intensity patterns between images using correlation metrics; operate on entire images or sub-images
- **Feature-based methods**: find correspondences between distinct image features (points, lines, contours), then compute a geometric transformation from those correspondences
- **Affine transformations**: global transforms including rotation, scaling, translation, and shearing — cannot model local geometric differences
- **Nonrigid/elastic transformations**: locally warp the target image to align with the reference; include radial basis functions (thin-plate splines, multiquadrics), viscous fluid models, and diffeomorphisms
- **Parametric models**: transformation described by a fixed number of parameters dictated by the model; **non-parametric models**: allow arbitrary per-element displacement
- **Diffeomorphisms**: smooth, invertible, topology-preserving transformations generated via flows; central to Computational Anatomy and LDDMM methods
- **Phase correlation**: frequency-domain method resilient to noise and occlusions; uses FFT for fast cross-correlation; a single peak in the output indicates relative translation
- **Log-polar coordinates**: used to extend phase correlation to determine rotation and scaling differences
- **Single-modality registration**: aligns images from the same scanner/sensor type
- **Multi-modality registration**: aligns images from different scanner types (e.g., CT/MRI, PET/CT, ultrasound/CT)
- **Similarity measures**: cross-correlation, mutual information, sum of squared intensity differences, ratio image uniformity — mutual information is most popular for multi-modality registration
- **Uncertainty** in registration is a significant concern, especially in remote sensing (where pixels may represent kilometers) and medical diagnostics

## Commands and Syntax

No specific CLI commands are described in this source. Key software tools and libraries referenced:

- **SPM** (Statistical Parametric Mapping) — implements warp-field estimation and application
- **AIR** — another program for warp-field operations
- **MRI Studio** / **MRICloud.org** — generate diffeomorphic coordinate transformations
- **elastix** — toolbox for rigid and nonrigid image registration
- **niftyreg** — near real-time rigid, affine (block matching), and nonrigid registration (free-form deformation)
- **MATLAB Image Processing Toolbox** — functions for registering multimodal MRI images and general image registration
- **RANSAC** — iterative algorithm for robust estimation of transformation parameters when control points exceed the minimum required

## Relationships

- **Computational Anatomy / LDDMM**: provides the mathematical framework (geodesic flows of diffeomorphisms) for large-deformation registration
- **Correspondence problem**: feature-based registration must solve this to match features across images
- **Phase correlation / FFT**: frequency-domain approach to registration, contrasted with spatial-domain methods
- **Medical imaging**: primary consumer of multi-modality and nonrigid registration (CT, MRI, PET, ultrasound fusion)
- **Remote sensing / georeferencing**: registration aligns satellite imagery to ground-truth coordinates
- **Astrophotography**: image stacking uses registration to improve signal-to-noise ratio
- **Panoramic image creation**: registration is essential for stitching images together
- **Change detection**: requires confident registration with uncertainty quantification
- **Point set registration / spatial normalization**: related geometric alignment problems
- **Talairach atlas**: neuroimaging standard that nonrigid registration maps patient data onto

## Exam-Relevant Points

- Know the distinction between **intensity-based** (correlation metrics on pixel values) and **feature-based** (geometric correspondence of distinct points/lines) registration methods
- **Affine transformations** are global (rotation, scaling, translation, shearing); **nonrigid transformations** handle local deformations
- **Mutual information** is the preferred similarity measure for **multi-modality** registration; **cross-correlation** and **SSD** are used for **same-modality** registration
- **Phase correlation** works in the frequency domain, is noise-resilient, and uses FFT for performance; extend to rotation/scaling via **log-polar coordinates**
- **RANSAC** is used to robustly estimate transformation parameters from over-determined control point sets
- **Diffeomorphisms** preserve topology (1-to-1 and onto); composed via function composition, not addition; generated via flows (LDDMM)
- **Rigid image registration** in radiation therapy uses 6 degrees of freedom (3 translation + 3 rotation)
- Medical imaging commonly requires **nonrigid registration** to handle breathing, anatomical changes, and inter-subject variability — except for structures with low anatomical variability (e.g., inner ear) where **rigid registration** preserves geometry
- Automation levels range from manual to fully automatic; semi-automatic methods still require user verification
- Uncertainty quantification in registration is critical but computationally expensive; in remote sensing, registration error can translate to kilometers of spatial error
