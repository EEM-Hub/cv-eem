# Exam Results: cv-exam.md

**Date:** 2026-06-22 11:35
**Model:** claude:sonnet
**Score:** 45/50 (90%)

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
- **Q21**: WRONG — What specific constraint was U-Net designed to address in medical imaging?
  - Expected: U-Net was designed to work with very few training images, addressing the chronic scarcity of annotated medical data. It also uses mirror padding and tiling to handle arbitrarily large images.
  - Got: Limited availability of annotated training data
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
- **Q37**: WRONG — What is the reparameterization trick in diffusion models used for?
  - Expected: It allows direct sampling of any timestep's noisy version without sequentially applying noise steps. Because the forward process involves Gaussian noise, the cumulative noise at any timestep can be expressed in closed form, enabling random-access sampling during training.
  - Got: Predicting noise instead of the denoised image
- **Q38**: WRONG — What are the two main approaches to self-supervised learning in vision?
  - Expected: Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
  - Got: Contrastive learning and masked image modeling
- **Q39**: CORRECT — What does transfer learning risk when source and target domains are too different?
- **Q40**: CORRECT — In stereo vision, what is the baseline distance between human eyes (interpupillary distance)?
- **Q41**: CORRECT — What did Julesz's random dot stereograms demonstrate about depth perception?
- **Q42**: WRONG — How many absolute depth cues exist in human vision?
  - Expected: b
  - Got: a
- **Q43**: CORRECT — What masking ratio does MAE (Masked Autoencoder) use for self-supervised pretraining?
- **Q44**: CORRECT — What problem does focal loss (used in RetinaNet) address?
- **Q45**: CORRECT — What is the ICP algorithm used for in point cloud processing?
- **Q46**: WRONG — What are the four equivalent mathematical formalisms for diffusion models?
  - Expected: Score matching (learning the score function), denoising score matching, stochastic differential equations (SDEs), and the variational lower bound (ELBO). These provide different theoretical perspectives on the same generative process.
  - Got: DDPMs, Score-based models, SDEs, and ODEs
- **Q47**: CORRECT — What was the first autonomous vehicle and where was it developed?
- **Q48**: CORRECT — What SAE automation level marks the critical transition where the system handles driving but may request human takeover?
- **Q49**: CORRECT — What property of CNNs is often called "convolution" but is technically cross-correlation?
- **Q50**: CORRECT — What does the Swin Transformer's shifted window mechanism achieve?

## Wrong Answers (Detail)

### Q21: What specific constraint was U-Net designed to address in medical imaging?
- **Expected:** U-Net was designed to work with very few training images, addressing the chronic scarcity of annotated medical data. It also uses mirror padding and tiling to handle arbitrarily large images.
- **Got:** Limited availability of annotated training data
- **Objective:** Medical Imaging

**Model response:**

```
```json
{"answer": "Limited availability of annotated training data", "explanation": "U-Net was specifically designed to address the scarcity of annotated training images in medical imaging, where obtaining expert annotations from clinicians is expensive and time-consuming. The architecture achieves strong performance with very few training samples through its symmetric encoder-decoder structure with skip connections that preserve spatial information, combined with aggressive data augmentation strategies. This allows the network to learn robust segmentation from datasets as small as 30 annotated images, which was a critical constraint in biomedical image analysis where large labeled datasets are rarely available."}
```
```

### Q37: What is the reparameterization trick in diffusion models used for?
- **Expected:** It allows direct sampling of any timestep's noisy version without sequentially applying noise steps. Because the forward process involves Gaussian noise, the cumulative noise at any timestep can be expressed in closed form, enabling random-access sampling during training.
- **Got:** Predicting noise instead of the denoised image
- **Objective:** Generative Models

**Model response:**

```
```json
{"answer": "Predicting noise instead of the denoised image", "explanation": "The reparameterization trick in diffusion models reformulates the model to predict the noise that was added during the forward diffusion process, rather than directly predicting the clean image. This is mathematically equivalent to predicting the mean of the reverse process but provides better training stability and gradient flow. By predicting the noise ε that was added to create the noisy image xₜ from the clean image x₀, the model can be trained more effectively across different noise levels, which is fundamental to the success of modern diffusion models like DDPM."}
```
```

### Q38: What are the two main approaches to self-supervised learning in vision?
- **Expected:** Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
- **Got:** Contrastive learning and masked image modeling
- **Objective:** Self-Supervised Learning

**Model response:**

```
```json
{"answer": "Contrastive learning and masked image modeling", "explanation": "The two main approaches to self-supervised learning in vision are contrastive learning and masked image modeling. Contrastive learning (e.g., SimCLR, MoCo) learns representations by maximizing agreement between differently augmented views of the same image while contrasting them against other images. Masked image modeling (e.g., MAE, BEiT) learns by predicting missing or masked portions of an image, inspired by masked language modeling in NLP. Both approaches enable models to learn powerful visual representations from unlabeled data by creating pretext tasks that require understanding image structure and semantics."}
```
```

### Q42: How many absolute depth cues exist in human vision?
- a) 2
- b) 3 **<--**
- c) 5
- d) 7
- **Expected:** b
- **Got:** a
- **Objective:** Depth Estimation

**Model response:**

```
```json
{"answer": "a", "explanation": "Human vision has 2 absolute depth cues: accommodation (the focusing of the eye's lens) and convergence (the inward rotation of both eyes when fixating on nearby objects). These are called oculomotor or physiological cues because they involve muscular adjustments of the eyes that provide direct information about object distance. Unlike relative depth cues (such as occlusion, linear perspective, or texture gradient) which only indicate which objects are closer or farther relative to each other, absolute cues can provide metric information about the actual distance to an object, though this information is only reliable at relatively close distances (typically within a few meters)."}
```
```

### Q46: What are the four equivalent mathematical formalisms for diffusion models?
- **Expected:** Score matching (learning the score function), denoising score matching, stochastic differential equations (SDEs), and the variational lower bound (ELBO). These provide different theoretical perspectives on the same generative process.
- **Got:** DDPMs, Score-based models, SDEs, and ODEs
- **Objective:** Generative Models

**Model response:**

```
```json
{"answer": "DDPMs, Score-based models, SDEs, and ODEs", "explanation": "The four equivalent mathematical formalisms for diffusion models are: (1) Denoising Diffusion Probabilistic Models (DDPMs) which use discrete-time Markov chains, (2) Score-based generative models which learn the gradient of the log-density, (3) Stochastic Differential Equations (SDEs) which provide a continuous-time formulation, and (4) Ordinary Differential Equations (ODEs) via the probability flow formulation. These perspectives were unified by Song et al., showing they describe the same generative process through different mathematical lenses, enabling flexible sampling and training strategies."}
```
```


## By Objective

- **Medical Imaging**: 0/1 (0%) **WEAK AREA**
- **Depth Estimation**: 0/1 (0%) **WEAK AREA**
- **Self-Supervised Learning**: 1/2 (50%)
- **Generative Models**: 4/6 (66%)
- **Optical Flow**: 2/2 (100%)
- **Edge Detection**: 3/3 (100%)
- **Feature Detection**: 7/7 (100%)
- **Deep Learning Architectures**: 6/6 (100%)
- **Attention and Transformers**: 3/3 (100%)
- **Segmentation**: 2/2 (100%)
- **Object Detection**: 4/4 (100%)
- **3D Vision**: 3/3 (100%)
- **SLAM and Visual Odometry**: 2/2 (100%)
- **Pose Estimation**: 1/1 (100%)
- **Training Techniques**: 1/1 (100%)
- **Transfer Learning**: 1/1 (100%)
- **Stereo Vision**: 2/2 (100%)
- **Autonomous Driving**: 2/2 (100%)
- **CNNs**: 1/1 (100%)
