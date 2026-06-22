# Exam Results: cv-exam.md

**Date:** 2026-06-22 12:09
**Model:** claude:haiku
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
- **Q10**: WRONG — What is the standard SIFT distance ratio test threshold for rejecting ambiguous matches?
  - Expected: c
  - Got: b
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
- **Q37**: WRONG — What is the reparameterization trick in diffusion models used for?
  - Expected: It allows direct sampling of any timestep's noisy version without sequentially applying noise steps. Because the forward process involves Gaussian noise, the cumulative noise at any timestep can be expressed in closed form, enabling random-access sampling during training.
  - Got: To enable stable gradient-based training and efficient sampling by reformulating the reverse diffusion process to predict noise rather than directly predicting the posterior mean.
- **Q38**: WRONG — What are the two main approaches to self-supervised learning in vision?
  - Expected: Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
  - Got: Contrastive learning and masked image modeling (generative prediction)
- **Q39**: CORRECT — What does transfer learning risk when source and target domains are too different?
- **Q40**: CORRECT — In stereo vision, what is the baseline distance between human eyes (interpupillary distance)?
- **Q41**: CORRECT — What did Julesz's random dot stereograms demonstrate about depth perception?
- **Q42**: WRONG — How many absolute depth cues exist in human vision?
  - Expected: b
  - Got: c
- **Q43**: CORRECT — What masking ratio does MAE (Masked Autoencoder) use for self-supervised pretraining?
- **Q44**: CORRECT — What problem does focal loss (used in RetinaNet) address?
- **Q45**: CORRECT — What is the ICP algorithm used for in point cloud processing?
- **Q46**: WRONG — What are the four equivalent mathematical formalisms for diffusion models?
  - Expected: Score matching (learning the score function), denoising score matching, stochastic differential equations (SDEs), and the variational lower bound (ELBO). These provide different theoretical perspectives on the same generative process.
  - Got: Denoising Diffusion Probabilistic Models (DDPM), Score-based generative models, Stochastic Differential Equations (SDEs), and Probability Flow ODE
- **Q47**: CORRECT — What was the first autonomous vehicle and where was it developed?
- **Q48**: CORRECT — What SAE automation level marks the critical transition where the system handles driving but may request human takeover?
- **Q49**: CORRECT — What property of CNNs is often called "convolution" but is technically cross-correlation?
- **Q50**: CORRECT — What does the Swin Transformer's shifted window mechanism achieve?

## Wrong Answers (Detail)

### Q10: What is the standard SIFT distance ratio test threshold for rejecting ambiguous matches?
- a) 0.6
- b) 0.7
- c) 0.8 **<--**
- d) 0.9
- **Expected:** c
- **Got:** b
- **Objective:** Feature Detection

**Model response:**

```
```json
{"answer": "b) 0.7", "explanation": "The standard SIFT distance ratio test threshold, introduced by David Lowe, uses 0.7 as the accepted value for rejecting ambiguous matches. This test compares the distance to the nearest neighbor feature with the distance to the second-nearest neighbor; if the ratio of these distances exceeds 0.7, the match is rejected as ambiguous. While Lowe's original paper mentioned values around 0.8, 0.7 has become the de facto standard threshold used across most SIFT implementations and computer vision libraries due to its empirical effectiveness at filtering false positives while retaining valid matches."}
```
```

### Q37: What is the reparameterization trick in diffusion models used for?
- **Expected:** It allows direct sampling of any timestep's noisy version without sequentially applying noise steps. Because the forward process involves Gaussian noise, the cumulative noise at any timestep can be expressed in closed form, enabling random-access sampling during training.
- **Got:** To enable stable gradient-based training and efficient sampling by reformulating the reverse diffusion process to predict noise rather than directly predicting the posterior mean.
- **Objective:** Generative Models

**Model response:**

```
```json
{
  "answer": "To enable stable gradient-based training and efficient sampling by reformulating the reverse diffusion process to predict noise rather than directly predicting the posterior mean.",
  "explanation": "The reparameterization trick in diffusion models reformulates the reverse process parameterization from predicting the mean μ(x_t, t) to predicting the noise ε that was added during the forward diffusion step. This is mathematically equivalent but offers several advantages: it yields a simple mean-squared error loss function for training the noise prediction network, provides more numerically stable gradients, and simplifies the sampling procedure. Instead of computing the posterior mean directly, the model predicts ε_θ(x_t, t), and the reverse step is computed as x_{t-1} = (1/√α_t) * x_t - ((1-α_t)/(√(1-ᾱ_t)√α_t)) * ε_θ(x_t, t). This reformulation became standard practice in modern diffusion models like DDPM because it makes both training and sampling more tractable and leads to better empirical results."
}
```
```

### Q38: What are the two main approaches to self-supervised learning in vision?
- **Expected:** Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
- **Got:** Contrastive learning and masked image modeling (generative prediction)
- **Objective:** Self-Supervised Learning

**Model response:**

```
```json
{
  "answer": "Contrastive learning and masked image modeling (generative prediction)",
  "explanation": "The two main approaches to self-supervised learning in vision are (1) contrastive learning, which learns representations by contrasting similar and dissimilar image examples to pull similar representations together and push dissimilar ones apart (exemplified by SimCLR, MoCo, BYOL), and (2) generative or masked prediction approaches, which learn by reconstructing masked or missing portions of images to capture semantic structure (exemplified by Masked Autoencoders, iBOT, MAE). Contrastive methods optimize directly for similarity preservation, while generative methods learn through reconstruction tasks, representing complementary philosophies for discovering useful visual representations without labeled data."
}
```
```

### Q42: How many absolute depth cues exist in human vision?
- a) 2
- b) 3 **<--**
- c) 5
- d) 7
- **Expected:** b
- **Got:** c
- **Objective:** Depth Estimation

**Model response:**

```
```json
{
  "answer": "c) 5",
  "explanation": "Absolute depth cues in human vision provide metric information about actual distance to objects. The five primary absolute depth cues are: (1) binocular disparity (stereopsis), which uses the difference between the two eyes' views; (2) convergence, the inward rotation of the eyes when fixating on nearby objects; (3) accommodation, the lens adjustment for focus that provides distance information; (4) motion parallax, the relative motion of objects at different depths during observer movement; and (5) familiar size, using knowledge of an object's actual size to estimate distance. While some sources distinguish only the three physiological cues (disparity, convergence, accommodation), the more complete classification includes motion-based and knowledge-based cues, making five the most comprehensive answer."
}
```
```

### Q46: What are the four equivalent mathematical formalisms for diffusion models?
- **Expected:** Score matching (learning the score function), denoising score matching, stochastic differential equations (SDEs), and the variational lower bound (ELBO). These provide different theoretical perspectives on the same generative process.
- **Got:** Denoising Diffusion Probabilistic Models (DDPM), Score-based generative models, Stochastic Differential Equations (SDEs), and Probability Flow ODE
- **Objective:** Generative Models

**Model response:**

```
```json
{
  "answer": "Denoising Diffusion Probabilistic Models (DDPM), Score-based generative models, Stochastic Differential Equations (SDEs), and Probability Flow ODE",
  "explanation": "These four formulations are mathematically equivalent ways to parameterize diffusion models. DDPMs predict the noise added at each step, score-based models predict the gradient of the log probability (score function), SDEs provide a continuous-time formulation of the forward and reverse processes, and the Probability Flow ODE offers a deterministic counterpart that generates samples via ODE solving rather than stochastic sampling. All four describe the same underlying generative process but using different parameterizations, allowing practitioners to choose based on computational efficiency, theoretical elegance, or sampling requirements."
}
```
```


## By Objective

- **Depth Estimation**: 0/1 (0%) **WEAK AREA**
- **Self-Supervised Learning**: 1/2 (50%)
- **Generative Models**: 4/6 (66%)
- **Feature Detection**: 6/7 (85%)
- **Optical Flow**: 2/2 (100%)
- **Edge Detection**: 3/3 (100%)
- **Deep Learning Architectures**: 6/6 (100%)
- **Attention and Transformers**: 3/3 (100%)
- **Medical Imaging**: 1/1 (100%)
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
