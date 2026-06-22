# Exam Results: cv-exam.md

**Date:** 2026-06-22 11:21
**Model:** claude:sonnet
**Score:** 48/50 (96%)

## Per-Question Results

- **Q1**: CORRECT — What is the aperture problem in optical flow estimation?
- **Q2**: CORRECT — Which optical flow method produces a dense flow field using a global smoothness constraint?
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
- **Q21**: CORRECT — What specific constraint was U-Net designed to address in medical imaging?
- **Q22**: CORRECT — What are the three levels of image segmentation in the modern hierarchy?
- **Q23**: CORRECT — What mathematical quantity does Otsu's thresholding method maximize?
- **Q24**: CORRECT — What is IoU (Intersection over Union) used for in object detection?
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
- **Q36**: CORRECT — What does batch normalization do differently at inference time compared to training?
- **Q37**: CORRECT — What is the reparameterization trick in diffusion models used for?
- **Q38**: WRONG — What are the two main approaches to self-supervised learning in vision?
  - Expected: Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
  - Got: Pixel-space masked reconstruction (e.g., MAE) and representation-space self-distillation (e.g., DINO)
- **Q39**: CORRECT — What does transfer learning risk when source and target domains are too different?
- **Q40**: CORRECT — In stereo vision, what is the baseline distance between human eyes (interpupillary distance)?
- **Q41**: CORRECT — What did Julesz's random dot stereograms demonstrate about depth perception?
- **Q42**: CORRECT — How many absolute depth cues exist in human vision?
- **Q43**: CORRECT — What masking ratio does MAE (Masked Autoencoder) use for self-supervised pretraining?
- **Q44**: CORRECT — What problem does focal loss (used in RetinaNet) address?
- **Q45**: CORRECT — What is the ICP algorithm used for in point cloud processing?
- **Q46**: CORRECT — What are the four equivalent mathematical formalisms for diffusion models?
- **Q47**: CORRECT — What was the first autonomous vehicle and where was it developed?
- **Q48**: CORRECT — What SAE automation level marks the critical transition where the system handles driving but may request human takeover?
- **Q49**: CORRECT — What property of CNNs is often called "convolution" but is technically cross-correlation?
- **Q50**: WRONG — What does the Swin Transformer's shifted window mechanism achieve?
  - Expected: Swin Transformer computes self-attention within local windows and shifts the window partitioning between layers to enable cross-window connections. This gives linear computational complexity with respect to image size (instead of quadratic) while maintaining the ability to model long-range dependencies across layers.
  - Got: Addresses the O(n²) attention bottleneck by restricting computation to local spatial windows

## Wrong Answers (Detail)

### Q38: What are the two main approaches to self-supervised learning in vision?
- **Expected:** Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
- **Got:** Pixel-space masked reconstruction (e.g., MAE) and representation-space self-distillation (e.g., DINO)
- **Objective:** Self-Supervised Learning

**Model response:**

```
```json
{"answer": "Pixel-space masked reconstruction (e.g., MAE) and representation-space self-distillation (e.g., DINO)", "explanation": "Self-supervised vision learning spans two fundamentally different paradigms based on their learning objectives. The first approach is pixel-space masked reconstruction (exemplified by MAE), which masks a large portion of image patches (e.g., 75%) and trains the model to reconstruct the missing pixels from the visible context. The second approach is representation-space self-distillation (exemplified by DINO), which uses an exponential moving average teacher network with techniques like sharpening and centering to learn representations through agreement between different augmented views of the same image. These two paradigms differ in whether they operate at the data level (reconstructing raw pixels) or the representation level (matching learned feature representations), providing complementary strategies for self-supervised pretraining of vision transformers."}
```
```

### Q50: What does the Swin Transformer's shifted window mechanism achieve?
- **Expected:** Swin Transformer computes self-attention within local windows and shifts the window partitioning between layers to enable cross-window connections. This gives linear computational complexity with respect to image size (instead of quadratic) while maintaining the ability to model long-range dependencies across layers.
- **Got:** Addresses the O(n²) attention bottleneck by restricting computation to local spatial windows
- **Objective:** Attention and Transformers

**Model response:**

```
```json
{"answer": "Addresses the O(n²) attention bottleneck by restricting computation to local spatial windows", "explanation": "The Swin Transformer's shifted-window mechanism restricts self-attention to local spatial windows rather than computing global attention across the entire image. This architectural choice directly addresses the quadratic computational bottleneck inherent in standard self-attention, making transformers tractable for high-resolution vision tasks. By limiting attention scope to local windows and using hierarchical merging layers (analogous to CNN pooling), Swin achieves state-of-the-art performance on tasks like COCO object detection while maintaining computational efficiency. This represents a complementary strategy to ViT's approach: where ViT reduces sequence length through coarse patch tokenization to enable global attention, Swin sacrifices global scope for finer resolution through local windowing."}
```
```


## By Objective

- **Self-Supervised Learning**: 1/2 (50%)
- **Attention and Transformers**: 2/3 (66%)
- **Optical Flow**: 2/2 (100%)
- **Edge Detection**: 3/3 (100%)
- **Feature Detection**: 7/7 (100%)
- **Deep Learning Architectures**: 6/6 (100%)
- **Medical Imaging**: 1/1 (100%)
- **Segmentation**: 2/2 (100%)
- **Object Detection**: 4/4 (100%)
- **Generative Models**: 6/6 (100%)
- **3D Vision**: 3/3 (100%)
- **SLAM and Visual Odometry**: 2/2 (100%)
- **Pose Estimation**: 1/1 (100%)
- **Training Techniques**: 1/1 (100%)
- **Transfer Learning**: 1/1 (100%)
- **Stereo Vision**: 2/2 (100%)
- **Depth Estimation**: 1/1 (100%)
- **Autonomous Driving**: 2/2 (100%)
- **CNNs**: 1/1 (100%)
