# Exam Results: cv-exam.md

**Date:** 2026-06-22 12:19
**Model:** claude:haiku
**Score:** 42/50 (84%)

## Per-Question Results

- **Q1**: CORRECT — What is the aperture problem in optical flow estimation?
- **Q2**: WRONG — Which optical flow method produces a dense flow field using a global smoothness constraint?
  - Expected: c
  - Got: I'll search the belief database for information about optical flow methods and their characteristics
- **Q3**: CORRECT — What year was the Canny edge detector's optimal filter shown to approximate a Gaussian?
- **Q4**: CORRECT — How many stages are in the Canny edge detection pipeline?
- **Q5**: CORRECT — What does non-maximum suppression achieve in edge detection?
- **Q6**: CORRECT — In the Harris corner detector, what does the response function R avoid computing explicitly?
- **Q7**: CORRECT — What property does the Harris detector have that SIFT extends?
- **Q8**: CORRECT — How many dimensions does a SIFT descriptor have?
- **Q9**: CORRECT — What does SIFT use to approximate the scale-normalized Laplacian of Gaussian?
- **Q10**: CORRECT — What is the standard SIFT distance ratio test threshold for rejecting ambiguous matches?
- **Q11**: CORRECT — In the Hough transform for line detection, what curve does a point in image space map to in parameter space?
- **Q12**: CORRECT — Why does the Hough transform use (rho, theta) parameterization instead of (m, b) slope-intercept form?
- **Q13**: CORRECT — What is the key architectural innovation in ResNet?
- **Q14**: CORRECT — What problem does ResNet's skip connection solve that is distinct from vanishing gradients?
- **Q15**: CORRECT — What was the first CNN architecture deployed commercially, processing checks in US banks?
- **Q16**: CORRECT — What event in 2012 triggered the deep learning revolution in computer vision?
- **Q17**: CORRECT — How does a Vision Transformer (ViT) handle images differently from CNNs?
- **Q18**: CORRECT — What is the computational complexity of standard self-attention with respect to sequence length?
- **Q19**: CORRECT — How does Flash Attention reduce the memory complexity of attention?
- **Q20**: CORRECT — What does U-Net add over a standard fully convolutional encoder-decoder?
- **Q21**: WRONG — What specific constraint was U-Net designed to address in medical imaging?
  - Expected: U-Net was designed to work with very few training images, addressing the chronic scarcity of annotated medical data. It also uses mirror padding and tiling to handle arbitrarily large images.
  - Got: scarce labeled data / limited training images
- **Q22**: CORRECT — What are the three levels of image segmentation in the modern hierarchy?
- **Q23**: CORRECT — What mathematical quantity does Otsu's thresholding method maximize?
- **Q24**: WRONG — What is IoU (Intersection over Union) used for in object detection?
  - Expected: IoU measures the overlap between a predicted bounding box and a ground truth box by dividing the area of intersection by the area of their union. The standard threshold for a correct detection is IoU >= 0.5.
  - Got: IoU (Intersection over Union) is a metric used to measure the spatial overlap between predicted and ground-truth bounding boxes in object detection. It is computed as the area of overlap divided by the area of their union, and serves as the foundation for evaluation: detections with IoU above a threshold (typically 0.5) are classified as true positives, and this discretized signal feeds into precision-recall curves and ultimately mean Average Precision (mAP) for evaluating detector performance.
- **Q25**: CORRECT — What did DETR eliminate from the object detection pipeline?
- **Q26**: CORRECT — What is the key difference between two-stage and one-stage object detectors?
- **Q27**: CORRECT — What does a GAN's optimal discriminator minimize in terms of divergence?
- **Q28**: CORRECT — Why is a GAN called an implicit generative model?
- **Q29**: CORRECT — What is the fundamental speed-quality tradeoff between GANs and diffusion models?
- **Q30**: CORRECT — What did the Plenoxels paper prove about neural radiance fields?
- **Q31**: CORRECT — What fundamental limitation does NeRF have that limits its practical deployment?
- **Q32**: CORRECT — What does SLAM estimate jointly that distinguishes it from visual odometry?
- **Q33**: CORRECT — What mechanism corrects accumulated drift in visual odometry?
- **Q34**: CORRECT — How many degrees of freedom does a full 3D pose have?
- **Q35**: CORRECT — What is the key difference between a VAE's latent space and a standard autoencoder's?
- **Q36**: WRONG — What does batch normalization do differently at inference time compared to training?
  - Expected: During training, batch normalization uses per-batch statistics (mean and variance). At inference, it uses running population statistics accumulated during training, since individual test samples may not form meaningful batches.
  - Got: Perfect! I have found relevant beliefs about batch normalization's behavior at inference vs training
- **Q37**: CORRECT — What is the reparameterization trick in diffusion models used for?
- **Q38**: WRONG — What are the two main approaches to self-supervised learning in vision?
  - Expected: Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
  - Got: Let me try searching directly in the belief database using the exam tool capabilities:

{"tool": "se
- **Q39**: CORRECT — What does transfer learning risk when source and target domains are too different?
- **Q40**: CORRECT — In stereo vision, what is the baseline distance between human eyes (interpupillary distance)?
- **Q41**: CORRECT — What did Julesz's random dot stereograms demonstrate about depth perception?
- **Q42**: CORRECT — How many absolute depth cues exist in human vision?
- **Q43**: CORRECT — What masking ratio does MAE (Masked Autoencoder) use for self-supervised pretraining?
- **Q44**: CORRECT — What problem does focal loss (used in RetinaNet) address?
- **Q45**: WRONG — What is the ICP algorithm used for in point cloud processing?
  - Expected: Iterative Closest Point (ICP) aligns two point clouds by iteratively finding closest-point correspondences and computing the rigid transformation (rotation + translation) that minimizes their distance. It converges to a local minimum, so a good initial alignment is needed.
  - Got: Let me try searching the beliefs database directly using the correct tool format:

```json
{"tool":
- **Q46**: CORRECT — What are the four equivalent mathematical formalisms for diffusion models?
- **Q47**: WRONG — What was the first autonomous vehicle and where was it developed?
  - Expected: b
  - Got: I'll search the belief database for information about the first autonomous vehicle and its origins.
- **Q48**: CORRECT — What SAE automation level marks the critical transition where the system handles driving but may request human takeover?
- **Q49**: CORRECT — What property of CNNs is often called "convolution" but is technically cross-correlation?
- **Q50**: WRONG — What does the Swin Transformer's shifted window mechanism achieve?
  - Expected: Swin Transformer computes self-attention within local windows and shifts the window partitioning between layers to enable cross-window connections. This gives linear computational complexity with respect to image size (instead of quadratic) while maintaining the ability to model long-range dependencies across layers.
  - Got: Reduces computational complexity of attention from O(n²) to O(n) by restricting self-attention to local windows instead of global, enabling efficient vision transformers for dense prediction tasks

## Wrong Answers (Detail)

### Q2: Which optical flow method produces a dense flow field using a global smoothness constraint?
- a) Lucas-Kanade
- b) RAFT
- c) Horn-Schunck **<--**
- d) Farneback
- **Expected:** c
- **Got:** I'll search the belief database for information about optical flow methods and their characteristics
- **Objective:** Optical Flow

**Model response:**

```

```

### Q21: What specific constraint was U-Net designed to address in medical imaging?
- **Expected:** U-Net was designed to work with very few training images, addressing the chronic scarcity of annotated medical data. It also uses mirror padding and tiling to handle arbitrarily large images.
- **Got:** scarce labeled data / limited training images
- **Objective:** Medical Imaging

**Model response:**

```
U-Net was specifically designed to address the constraint of scarce labeled training data in medical imaging. The belief database confirms that U-Net was designed to yield precise segmentation with very few labeled training images—a critical advantage in biomedical imaging where manual segmentation remains the gold standard but labeled data is extremely scarce. This few-shot learning capability was a key architectural innovation that made U-Net particularly valuable for medical imaging applications.
```

### Q24: What is IoU (Intersection over Union) used for in object detection?
- **Expected:** IoU measures the overlap between a predicted bounding box and a ground truth box by dividing the area of intersection by the area of their union. The standard threshold for a correct detection is IoU >= 0.5.
- **Got:** IoU (Intersection over Union) is a metric used to measure the spatial overlap between predicted and ground-truth bounding boxes in object detection. It is computed as the area of overlap divided by the area of their union, and serves as the foundation for evaluation: detections with IoU above a threshold (typically 0.5) are classified as true positives, and this discretized signal feeds into precision-recall curves and ultimately mean Average Precision (mAP) for evaluating detector performance.
- **Objective:** Object Detection

**Model response:**

```
The belief database confirms that IoU quantifies spatial overlap between bounding boxes and is the first layer in object detection's evaluation pipeline. It thresholds detections into true/false positives, which then roll up into per-class Average Precision metrics and finally mean Average Precision across all classes. This standardized IoU-to-AP-to-mAP pipeline became the invariant measurement framework against which successive generations of detection architectures could be objectively evaluated.
```

### Q36: What does batch normalization do differently at inference time compared to training?
- **Expected:** During training, batch normalization uses per-batch statistics (mean and variance). At inference, it uses running population statistics accumulated during training, since individual test samples may not form meaningful batches.
- **Got:** Perfect! I have found relevant beliefs about batch normalization's behavior at inference vs training
- **Objective:** Training Techniques

**Model response:**

```

```

### Q38: What are the two main approaches to self-supervised learning in vision?
- **Expected:** Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
- **Got:** Let me try searching directly in the belief database using the exam tool capabilities:

{"tool": "se
- **Objective:** Self-Supervised Learning

**Model response:**

```

```

### Q45: What is the ICP algorithm used for in point cloud processing?
- **Expected:** Iterative Closest Point (ICP) aligns two point clouds by iteratively finding closest-point correspondences and computing the rigid transformation (rotation + translation) that minimizes their distance. It converges to a local minimum, so a good initial alignment is needed.
- **Got:** Let me try searching the beliefs database directly using the correct tool format:

```json
{"tool":
- **Objective:** 3D Vision

**Model response:**

```

```

### Q47: What was the first autonomous vehicle and where was it developed?
- a) Navlab at Carnegie Mellon
- b) Stanford Cart at Stanford **<--**
- c) DARPA Grand Challenge entry
- d) Waymo prototype at Google
- **Expected:** b
- **Got:** I'll search the belief database for information about the first autonomous vehicle and its origins.
- **Objective:** Autonomous Driving

**Model response:**

```

```

### Q50: What does the Swin Transformer's shifted window mechanism achieve?
- **Expected:** Swin Transformer computes self-attention within local windows and shifts the window partitioning between layers to enable cross-window connections. This gives linear computational complexity with respect to image size (instead of quadratic) while maintaining the ability to model long-range dependencies across layers.
- **Got:** Reduces computational complexity of attention from O(n²) to O(n) by restricting self-attention to local windows instead of global, enabling efficient vision transformers for dense prediction tasks
- **Objective:** Attention and Transformers

**Model response:**

```
The Swin Transformer's shifted-window mechanism addresses the quadratic computational bottleneck of standard self-attention by restricting attention computation to local spatial windows rather than computing it globally across the entire image. This scope restriction, combined with hierarchical merging layers that concatenate 2×2 neighboring tokens (analogous to CNN pooling), achieves state-of-the-art results on dense prediction tasks like object detection (COCO) while maintaining computational tractability. The mechanism represents a complementary architectural solution to ViT's approach: while ViT sacrifices spatial resolution for global attention scope through patch tokenization, Swin sacrifices global scope for local resolution, making it more suitable for tasks requiring fine-grained spatial information.
```


## By Objective

- **Medical Imaging**: 0/1 (0%) **WEAK AREA**
- **Training Techniques**: 0/1 (0%) **WEAK AREA**
- **Optical Flow**: 1/2 (50%)
- **Self-Supervised Learning**: 1/2 (50%)
- **Autonomous Driving**: 1/2 (50%)
- **Attention and Transformers**: 2/3 (66%)
- **3D Vision**: 2/3 (66%)
- **Object Detection**: 3/4 (75%)
- **Edge Detection**: 3/3 (100%)
- **Feature Detection**: 7/7 (100%)
- **Deep Learning Architectures**: 6/6 (100%)
- **Segmentation**: 2/2 (100%)
- **Generative Models**: 6/6 (100%)
- **SLAM and Visual Odometry**: 2/2 (100%)
- **Pose Estimation**: 1/1 (100%)
- **Transfer Learning**: 1/1 (100%)
- **Stereo Vision**: 2/2 (100%)
- **Depth Estimation**: 1/1 (100%)
- **CNNs**: 1/1 (100%)
