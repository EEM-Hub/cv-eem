# Exam Results: cv-exam.md

**Date:** 2026-06-22 10:52
**Model:** claude:opus
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
  - Got: Contrastive learning and masked image modeling
- **Q39**: CORRECT — What does transfer learning risk when source and target domains are too different?
- **Q40**: CORRECT — In stereo vision, what is the baseline distance between human eyes (interpupillary distance)?
- **Q41**: CORRECT — What did Julesz's random dot stereograms demonstrate about depth perception?
- **Q42**: WRONG — How many absolute depth cues exist in human vision?
  - Expected: b
  - Got: d
- **Q43**: CORRECT — What masking ratio does MAE (Masked Autoencoder) use for self-supervised pretraining?
- **Q44**: CORRECT — What problem does focal loss (used in RetinaNet) address?
- **Q45**: CORRECT — What is the ICP algorithm used for in point cloud processing?
- **Q46**: CORRECT — What are the four equivalent mathematical formalisms for diffusion models?
- **Q47**: CORRECT — What was the first autonomous vehicle and where was it developed?
- **Q48**: CORRECT — What SAE automation level marks the critical transition where the system handles driving but may request human takeover?
- **Q49**: CORRECT — What property of CNNs is often called "convolution" but is technically cross-correlation?
- **Q50**: CORRECT — What does the Swin Transformer's shifted window mechanism achieve?

## Wrong Answers (Detail)

### Q38: What are the two main approaches to self-supervised learning in vision?
- **Expected:** Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
- **Got:** Contrastive learning and masked image modeling
- **Objective:** Self-Supervised Learning

**Model response:**

```
{"answer": "Contrastive learning and masked image modeling", "explanation": "The two main approaches to self-supervised learning in computer vision are contrastive learning and masked image modeling (MIM). Contrastive learning methods (e.g., SimCLR, MoCo, BYOL, DINO) learn representations by pulling together different augmented views of the same image while pushing apart views of different images in an embedding space. Masked image modeling methods (e.g., MAE, BEiT, SimMIM) follow the masked language modeling paradigm from NLP: they mask random patches of an input image and train the model to reconstruct the missing content, either in pixel space or in a learned token space. Contrastive methods dominated the earlier wave of self-supervised vision research, while masked image modeling gained prominence after the success of Vision Transformers, drawing a direct parallel to BERT-style pretraining. Some taxonomies also frame these as 'joint-embedding' vs. 'generative' approaches, but contrastive learning and masked image modeling remain the most widely recognized categorization of the two paradigms."}
```

### Q42: How many absolute depth cues exist in human vision?
- a) 2
- b) 3 **<--**
- c) 5
- d) 7
- **Expected:** b
- **Got:** d
- **Objective:** Depth Estimation

**Model response:**

```
{"answer": "d", "explanation": "There are 7 absolute (or 'oculomotor' and 'pictorial') depth cues that provide information about the actual distance of objects in human vision. These are: accommodation (lens shape change for focusing), convergence (inward rotation of the eyes), familiar size (known object size used to judge distance), absolute motion parallax, aerial perspective (haze/color shift with distance), height in the visual field (objects higher in the field appear farther), and texture gradient (texture density increases with distance). Some taxonomies group these slightly differently, but the commonly cited count in vision science textbooks is 7 absolute depth cues, distinguishing them from relative depth cues (which only indicate which of two objects is nearer, not how far away either one is)."}
```


## By Objective

- **Depth Estimation**: 0/1 (0%) **WEAK AREA**
- **Self-Supervised Learning**: 1/2 (50%)
- **Optical Flow**: 2/2 (100%)
- **Edge Detection**: 3/3 (100%)
- **Feature Detection**: 7/7 (100%)
- **Deep Learning Architectures**: 6/6 (100%)
- **Attention and Transformers**: 3/3 (100%)
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
- **Autonomous Driving**: 2/2 (100%)
- **CNNs**: 1/1 (100%)
