# Computer Vision Exam

## Q1: What is the aperture problem in optical flow estimation?
- a) The camera lens aperture is too small to capture motion
- b) One equation with two unknowns makes local flow underdetermined
- c) The field of view is too narrow to observe full object motion
- d) Optical sensors cannot distinguish brightness from color changes
Answer: b
Objective: Optical Flow

## Q2: Which optical flow method produces a dense flow field using a global smoothness constraint?
- a) Lucas-Kanade
- b) RAFT
- c) Horn-Schunck
- d) Farneback
Answer: c
Objective: Optical Flow

## Q3: What year was the Canny edge detector's optimal filter shown to approximate a Gaussian?
Answer: Canny derived his optimal filter analytically and showed it closely approximates the first derivative of a Gaussian. The original paper was published in 1986.
Objective: Edge Detection

## Q4: How many stages are in the Canny edge detection pipeline?
- a) 3
- b) 4
- c) 5
- d) 6
Answer: c
Objective: Edge Detection

## Q5: What does non-maximum suppression achieve in edge detection?
Answer: It thins edges to single-pixel width by suppressing pixels that are not local maxima along the gradient direction.
Objective: Edge Detection

## Q6: In the Harris corner detector, what does the response function R avoid computing explicitly?
- a) The image gradient
- b) The Gaussian smoothing kernel
- c) The eigenvalues of the structure tensor
- d) The Hessian matrix
Answer: c
Objective: Feature Detection

## Q7: What property does the Harris detector have that SIFT extends?
Answer: Harris is invariant to rotation and illumination changes but not to scale. SIFT extends this by adding scale invariance through a multi-scale DoG approach.
Objective: Feature Detection

## Q8: How many dimensions does a SIFT descriptor have?
- a) 64
- b) 128
- c) 256
- d) 512
Answer: b
Objective: Feature Detection

## Q9: What does SIFT use to approximate the scale-normalized Laplacian of Gaussian?
- a) Gabor filters
- b) Difference of Gaussians (DoG)
- c) Hessian matrix
- d) Steerable pyramids
Answer: b
Objective: Feature Detection

## Q10: What is the standard SIFT distance ratio test threshold for rejecting ambiguous matches?
- a) 0.6
- b) 0.7
- c) 0.8
- d) 0.9
Answer: c
Objective: Feature Detection

## Q11: In the Hough transform for line detection, what curve does a point in image space map to in parameter space?
- a) A circle
- b) A parabola
- c) A sinusoid
- d) A straight line
Answer: c
Objective: Feature Detection

## Q12: Why does the Hough transform use (rho, theta) parameterization instead of (m, b) slope-intercept form?
Answer: The slope-intercept form has unbounded parameters for vertical lines (infinite slope). The (rho, theta) normal parameterization avoids this by representing all lines with bounded parameters.
Objective: Feature Detection

## Q13: What is the key architectural innovation in ResNet?
- a) Batch normalization after every layer
- b) Skip connections that add input identity to layer output
- c) Depthwise separable convolutions
- d) Dilated convolutions for larger receptive fields
Answer: b
Objective: Deep Learning Architectures

## Q14: What problem does ResNet's skip connection solve that is distinct from vanishing gradients?
Answer: The degradation problem — deeper networks have higher training error than shallower ones even without vanishing gradients. Skip connections ensure the gradient always has an additive identity component, making it easier to learn identity mappings.
Objective: Deep Learning Architectures

## Q15: What was the first CNN architecture deployed commercially, processing checks in US banks?
- a) AlexNet
- b) VGGNet
- c) LeNet-5
- d) GoogLeNet
Answer: c
Objective: Deep Learning Architectures

## Q16: What event in 2012 triggered the deep learning revolution in computer vision?
Answer: AlexNet's victory in the ImageNet Large Scale Visual Recognition Challenge (ILSVRC), achieving significantly lower error rates than previous methods using a deep CNN trained on GPUs.
Objective: Deep Learning Architectures

## Q17: How does a Vision Transformer (ViT) handle images differently from CNNs?
- a) It processes raw pixels with self-attention
- b) It splits images into patches and treats them as token sequences
- c) It uses depthwise separable convolutions
- d) It applies attention only to downsampled feature maps
Answer: b
Objective: Deep Learning Architectures

## Q18: What is the computational complexity of standard self-attention with respect to sequence length?
- a) O(n)
- b) O(n log n)
- c) O(n²)
- d) O(n³)
Answer: c
Objective: Attention and Transformers

## Q19: How does Flash Attention reduce the memory complexity of attention?
Answer: Flash Attention uses a tiling strategy that computes attention block-by-block, keeping intermediate results in fast SRAM rather than writing the full attention matrix to HBM. This achieves linear memory complexity instead of quadratic.
Objective: Attention and Transformers

## Q20: What does U-Net add over a standard fully convolutional encoder-decoder?
- a) Dilated convolutions
- b) Batch normalization
- c) Skip connections concatenating encoder features to decoder
- d) Attention gates
Answer: c
Objective: Deep Learning Architectures

## Q21: What specific constraint was U-Net designed to address in medical imaging?
Answer: U-Net was designed to work with very few training images, addressing the chronic scarcity of annotated medical data. It also uses mirror padding and tiling to handle arbitrarily large images.
Objective: Medical Imaging

## Q22: What are the three levels of image segmentation in the modern hierarchy?
Answer: Semantic segmentation (assigns a class label to every pixel), instance segmentation (distinguishes individual object instances), and panoptic segmentation (combines both semantic and instance segmentation for a complete scene parse).
Objective: Segmentation

## Q23: What mathematical quantity does Otsu's thresholding method maximize?
- a) Entropy
- b) Inter-class variance
- c) Signal-to-noise ratio
- d) Gradient magnitude
Answer: b
Objective: Segmentation

## Q24: What is IoU (Intersection over Union) used for in object detection?
Answer: IoU measures the overlap between a predicted bounding box and a ground truth box by dividing the area of intersection by the area of their union. The standard threshold for a correct detection is IoU >= 0.5.
Objective: Object Detection

## Q25: What did DETR eliminate from the object detection pipeline?
- a) Convolutional backbones
- b) Non-maximum suppression and anchor boxes
- c) Feature pyramid networks
- d) Region proposal networks only
Answer: b
Objective: Object Detection

## Q26: What is the key difference between two-stage and one-stage object detectors?
Answer: Two-stage detectors (like R-CNN family) first generate region proposals then classify each region. One-stage detectors (like YOLO) perform detection as a single regression problem, predicting bounding boxes and class probabilities directly from the full image in one pass, trading some accuracy for real-time speed.
Objective: Object Detection

## Q27: What does a GAN's optimal discriminator minimize in terms of divergence?
- a) KL divergence
- b) Wasserstein distance
- c) Jensen-Shannon divergence
- d) Total variation distance
Answer: c
Objective: Generative Models

## Q28: Why is a GAN called an implicit generative model?
Answer: A GAN can generate samples but cannot compute the probability density of a given input — there is no tractable way to invert the generator to obtain likelihoods. This contrasts with explicit models like VAEs that model the density directly.
Objective: Generative Models

## Q29: What is the fundamental speed-quality tradeoff between GANs and diffusion models?
Answer: GANs generate samples in a single forward pass (fast but can suffer mode collapse), while diffusion models generate through iterative denoising over many steps (slower but produce higher quality and more diverse samples with stable training).
Objective: Generative Models

## Q30: What did the Plenoxels paper prove about neural radiance fields?
Answer: Plenoxels demonstrated that the MLP (neural network) component is not essential for NeRF-quality novel view synthesis — a sparse voxel grid with spherical harmonics can achieve comparable results, proving that the representation matters more than the network architecture.
Objective: 3D Vision

## Q31: What fundamental limitation does NeRF have that limits its practical deployment?
- a) It can only render at low resolution
- b) It requires per-scene retraining
- c) It cannot handle reflective surfaces
- d) It needs depth sensors as input
Answer: b
Objective: 3D Vision

## Q32: What does SLAM estimate jointly that distinguishes it from visual odometry?
Answer: SLAM jointly estimates the camera pose AND builds a map of the environment. Visual odometry only estimates camera motion (pose) incrementally without maintaining a global map, which is why VO inherently drifts over time.
Objective: SLAM and Visual Odometry

## Q33: What mechanism corrects accumulated drift in visual odometry?
- a) Kalman filtering
- b) Bundle adjustment
- c) Loop closure detection
- d) IMU sensor fusion
Answer: c
Objective: SLAM and Visual Odometry

## Q34: How many degrees of freedom does a full 3D pose have?
- a) 3
- b) 4
- c) 6
- d) 9
Answer: c
Objective: Pose Estimation

## Q35: What is the key difference between a VAE's latent space and a standard autoencoder's?
- a) VAEs use larger latent dimensions
- b) VAEs learn distributions over latent vectors, not fixed vectors
- c) VAEs use convolutional layers in the encoder
- d) VAEs have skip connections
Answer: b
Objective: Generative Models

## Q36: What does batch normalization do differently at inference time compared to training?
Answer: During training, batch normalization uses per-batch statistics (mean and variance). At inference, it uses running population statistics accumulated during training, since individual test samples may not form meaningful batches.
Objective: Training Techniques

## Q37: What is the reparameterization trick in diffusion models used for?
Answer: It allows direct sampling of any timestep's noisy version without sequentially applying noise steps. Because the forward process involves Gaussian noise, the cumulative noise at any timestep can be expressed in closed form, enabling random-access sampling during training.
Objective: Generative Models

## Q38: What are the two main approaches to self-supervised learning in vision?
Answer: Contrastive methods (which learn by comparing positive pairs against negative pairs) and non-contrastive methods (which use only positive pairs with asymmetric architectures to prevent collapse, like BYOL, Barlow Twins, and VICReg).
Objective: Self-Supervised Learning

## Q39: What does transfer learning risk when source and target domains are too different?
- a) Overfitting
- b) Negative transfer
- c) Mode collapse
- d) Catastrophic forgetting
Answer: b
Objective: Transfer Learning

## Q40: In stereo vision, what is the baseline distance between human eyes (interpupillary distance)?
- a) 4.5 cm
- b) 6.5 cm
- c) 8.5 cm
- d) 10.5 cm
Answer: b
Objective: Stereo Vision

## Q41: What did Julesz's random dot stereograms demonstrate about depth perception?
Answer: They proved that stereoscopic depth perception can occur without monocular form recognition — the brain can extract depth purely from binocular disparity, before any object recognition takes place. This established stereopsis as a pre-attentive computational primitive.
Objective: Stereo Vision

## Q42: How many absolute depth cues exist in human vision?
- a) 2
- b) 3
- c) 5
- d) 7
Answer: b
Objective: Depth Estimation

## Q43: What masking ratio does MAE (Masked Autoencoder) use for self-supervised pretraining?
- a) 25%
- b) 50%
- c) 75%
- d) 90%
Answer: c
Objective: Self-Supervised Learning

## Q44: What problem does focal loss (used in RetinaNet) address?
Answer: Focal loss addresses the extreme class imbalance between foreground and background examples in dense object detection. It down-weights the loss for well-classified (easy) negative examples, focusing training on hard examples.
Objective: Object Detection

## Q45: What is the ICP algorithm used for in point cloud processing?
Answer: Iterative Closest Point (ICP) aligns two point clouds by iteratively finding closest-point correspondences and computing the rigid transformation (rotation + translation) that minimizes their distance. It converges to a local minimum, so a good initial alignment is needed.
Objective: 3D Vision

## Q46: What are the four equivalent mathematical formalisms for diffusion models?
Answer: Score matching (learning the score function), denoising score matching, stochastic differential equations (SDEs), and the variational lower bound (ELBO). These provide different theoretical perspectives on the same generative process.
Objective: Generative Models

## Q47: What was the first autonomous vehicle and where was it developed?
- a) Navlab at Carnegie Mellon
- b) Stanford Cart at Stanford
- c) DARPA Grand Challenge entry
- d) Waymo prototype at Google
Answer: b
Objective: Autonomous Driving

## Q48: What SAE automation level marks the critical transition where the system handles driving but may request human takeover?
- a) Level 2
- b) Level 3
- c) Level 4
- d) Level 5
Answer: b
Objective: Autonomous Driving

## Q49: What property of CNNs is often called "convolution" but is technically cross-correlation?
Answer: The operation called "convolution" in CNNs is actually cross-correlation — the kernel is not flipped before sliding over the input. True convolution requires flipping the kernel. The distinction doesn't matter for learned kernels since the network can learn the flipped version.
Objective: CNNs

## Q50: What does the Swin Transformer's shifted window mechanism achieve?
Answer: Swin Transformer computes self-attention within local windows and shifts the window partitioning between layers to enable cross-window connections. This gives linear computational complexity with respect to image size (instead of quadratic) while maintaining the ability to model long-range dependencies across layers.
Objective: Attention and Transformers
