---
source: https://en.wikipedia.org/wiki/Vision_transformer
fetched: 2026-06-21
---

Machine learning model for vision processing For other uses, see [Vit](./Vit). [![](//upload.wikimedia.org/wikipedia/commons/thumb/9/93/Vision_Transformer.png/250px-Vision_Transformer.png)](./File:Vision_Transformer.png)The architecture of vision transformer. An input image is divided into patches, each of which is linearly mapped through a patch embedding layer, before entering a standard Transformer encoder. 
| Part of a series on |
| --- |
| Machine learninganddata mining |
| ParadigmsSupervised learningUnsupervised learningSemi-supervised learningSelf-supervised learningReinforcement learningMeta-learningOnline learningBatch learningCurriculum learningRule-based learningNeuro-symbolic AINeuromorphic engineeringQuantum machine learning |
| ProblemsClassificationGenerative modelingRegressionClusteringDimensionality reductionDensity estimationAnomaly detectionData cleaningAutoMLAssociation rulesSemantic analysisStructured predictionFeature engineeringFeature learningLearning to rankGrammar inductionOntology learningMultimodal learning |
| Supervised learning(classification•regression)Apprenticeship learningDecision treesEnsemblesBaggingBoostingRandom forestk-NNLinear regressionNaive BayesArtificial neural networksLogistic regressionPerceptronRelevance vector machine (RVM)Support vector machine (SVM) |
| ClusteringBIRCHCUREHierarchicalk-meansFuzzyExpectation–maximization (EM)DBSCANOPTICSMean shift |
| Dimensionality reductionFactor analysisCCAICALDANMFPCAPGDt-SNESDL |
| Structured predictionGraphical modelsBayes netConditional random fieldHidden Markov |
| Anomaly detectionRANSACk-NNLocal outlier factorIsolation forest |
| Neural networksAutoencoderDeep learningFeedforward neural networkRecurrent neural networkLSTMGRUESNreservoir computingBoltzmann machineRestrictedGANDiffusion modelSOMConvolutional neural networkU-NetLeNetAlexNetDeepDreamNeural fieldNeural radiance fieldPhysics-informed neural networksTransformerVisionMambaSpiking neural networkMemtransistorElectrochemical RAM(ECRAM) |
| Reinforcement learningQ-learningPolicy gradientSARSATemporal difference (TD)Multi-agentSelf-play |
| Learning with humansActive learningCrowdsourcingHuman-in-the-loopMechanistic interpretabilityRLHF |
| Model diagnosticsCoefficient of determinationConfusion matrixLearning curveROC curve |
| Mathematical foundationsKernel machinesBias–variance tradeoffComputational learning theoryEmpirical risk minimizationOccam learningPAC learningStatistical learningVC theoryTopological deep learning |
| Journals and conferencesAAAICVPRECCVECML PKDDEMNLPICCVNeurIPSICMLICLRIJCAIMLJMLR |
| Related articlesGlossary of artificial intelligenceList of datasets for machine-learning researchList of datasets in computer vision and image processingOutline of machine learning |
| vte |

 

A **vision transformer** (**ViT**) is a [transformer](./Transformer_(machine_learning_model)) designed for [computer vision](./Computer_vision).[[1]](./Vision_transformer#cite_note-Dosovitskiy-2021-1) A ViT decomposes an input image into a series of patches (rather than text into [tokens](./Byte_pair_encoding)), serializes each patch into a vector, and maps it to a smaller dimension with a single [matrix multiplication](./Matrix_multiplication). These vector [embeddings](./Latent_space) are then processed by a [transformer encoder](./BERT_(language_model)) as if they were token embeddings.

 

ViTs were designed as alternatives to [convolutional neural networks](./Convolutional_neural_network) (CNNs) in computer vision applications. They have different inductive biases, training stability, and data efficiency.[[2]](./Vision_transformer#cite_note-Raghu-2021-2) Compared to CNNs, ViTs are less data efficient, but have higher capacity. Some of the largest modern computer vision models are ViTs, such as one with 22B parameters.[[3]](./Vision_transformer#cite_note-3)[[4]](./Vision_transformer#cite_note-4)

 

Subsequent to its publication, many variants were proposed, with hybrid architectures with both features of ViTs and CNNs.[[5]](./Vision_transformer#cite_note-Koresh2025-5) ViTs have found application in [image recognition](./Image_recognition), [image segmentation](./Image_segmentation), [weather prediction](./Weather_forecasting), and [autonomous driving](./Autonomous_driving).[[6]](./Vision_transformer#cite_note-Han-2023-6)[[7]](./Vision_transformer#cite_note-Khan-2022-7)

 

## History

 

Transformers were introduced in *[Attention Is All You Need](./Attention_Is_All_You_Need)* (2017),[[8]](./Vision_transformer#cite_note-8) and have found widespread use in [natural language processing](./Natural_language_processing). A 2019 paper[[9]](./Vision_transformer#cite_note-9) applied ideas from the Transformer to computer vision. Specifically, they started with a [ResNet](./Residual_neural_network), a standard [convolutional neural network](./Convolutional_neural_network) used for computer vision, and replaced all convolutional kernels by the self-attention mechanism found in a Transformer. It resulted in superior performance. However, it is not a Vision Transformer.

 

In 2020, an [encoder-only transformer](./Transformer_(deep_learning_architecture)#encoder-only) was adapted for computer vision, yielding the ViT, which reached state of the art in image classification, overcoming the previous dominance of CNN.[[1]](./Vision_transformer#cite_note-Dosovitskiy-2021-1) The masked autoencoder (2022) extended ViT to work with unsupervised training. The vision transformer and the masked autoencoder, in turn, stimulated new developments in convolutional neural networks.[[10]](./Vision_transformer#cite_note-10)[[11]](./Vision_transformer#cite_note-11)

 

Subsequently, there was cross-fertilization between the previous CNN approach and the ViT approach.

 

In 2021, some important variants of the Vision Transformers were proposed. These variants are mainly intended to be more efficient, more accurate or better suited to a specific domain. Two studies [[12]](./Vision_transformer#cite_note-12)[[13]](./Vision_transformer#cite_note-Xiao-2021-13) improved efficiency and robustness of ViT by adding a CNN as a preprocessor. The Swin Transformer[[14]](./Vision_transformer#cite_note-Liu-2021-14) achieved state-of-the-art results on some object detection datasets such as [COCO](./COCO_(dataset)), by using convolution-like sliding windows of attention mechanism, and the [pyramid](./Pyramid_(image_processing)) process in classical computer vision.

 

## Overview

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/7/77/Vision_Transformer.svg/250px-Vision_Transformer.svg.png)](./File:Vision_Transformer.svg)Vision Transformer architecture, showing the encoder-only Transformer blocks inside 

The basic architecture, used by the original 2020 paper,[[1]](./Vision_transformer#cite_note-Dosovitskiy-2021-1) is as follows. In summary, it is a [BERT](./BERT_(language_model))-like encoder-only Transformer.

 

The input image is of type       R   H × ×  W × ×  C     {\displaystyle \mathbb {R} ^{H\times W\times C}}  ![{\displaystyle \mathbb {R} ^{H\times W\times C}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/017d01e20d272f34402165cca04b85e2b6cb1a62), where     H , W , C   {\displaystyle H,W,C}  ![{\displaystyle H,W,C}](https://wikimedia.org/api/rest_v1/media/math/render/svg/a10911864a60086f2640770826615f2db8121e52) are height, width, channel ([RGB](./RGB_color_model)). It is then split into square-shaped patches of type       R   P × ×  P × ×  C     {\displaystyle \mathbb {R} ^{P\times P\times C}}  ![{\displaystyle \mathbb {R} ^{P\times P\times C}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/835f68256918970235469055ba93b6a622da7ea9).

 

For each patch, the patch is pushed through a linear operator, to obtain a vector ("patch embedding"). The position of the patch is also transformed into a vector by "position encoding" (the paper tried no embedding, 1D embedding, 2D embedding, and relative embedding: 1D was adopted).[[a]](./Vision_transformer#cite_note-15)[[1]](./Vision_transformer#cite_note-Dosovitskiy-2021-1): §D.4  The two vectors are added, then pushed through several Transformer encoders.

 

The attention mechanism in a ViT repeatedly transforms representation vectors of image patches, incorporating more and more semantic relations between image patches in an image. This is analogous to how in natural language processing, as representation vectors flow through a transformer, they incorporate more and more semantic relations between words, from syntax to semantics.

 

The above architecture turns an image into a sequence of vector representations. To use these for downstream applications, an additional head needs to be trained to interpret them.

 

For example, to use it for classification, one can add a shallow MLP on top of it that outputs a probability distribution over classes. The original paper uses a linear-[GeLU](./Activation_function)-linear-softmax network.[[1]](./Vision_transformer#cite_note-Dosovitskiy-2021-1)

 

## Variants

 

### Original ViT

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/3/3e/Vision_Transformer.gif/500px-Vision_Transformer.gif)](./File:Vision_Transformer.gif)Animation of ViT. The 0th token is the special `<CLS>`. The other 9 patches are projected by a linear layer before being fed into the Transformer encoder as input tokens 1 to 9. 

The original ViT was an encoder-only Transformer supervise-trained to predict the image label from the patches of the image. As in the case of [BERT](./BERT_(language_model)), it uses a special token `<CLS>` in the input side, and the corresponding output vector is used as the only input of the final output MLP head. The special token is an architectural hack to allow the model to compress all information relevant for predicting the image label into one vector.[[1]](./Vision_transformer#cite_note-Dosovitskiy-2021-1)

 

Transformers found their initial applications in [natural language processing](./Natural_language_processing) tasks, as demonstrated by [language models](./Language_models) such as [BERT](./BERT_(language_model)) and [GPT-3](./GPT-3). By contrast the typical image processing system uses a [convolutional neural network](./Convolutional_neural_network) (CNN). Well-known projects include Xception, [ResNet](./Residual_neural_network), [EfficientNet](./EfficientNet),[[15]](./Vision_transformer#cite_note-16) [DenseNet](./DenseNet),[[16]](./Vision_transformer#cite_note-17) and [Inception](./Inceptionv3).[[17]](./Vision_transformer#cite_note-Sarkar-2021-18)

 

Transformers measure the relationships between pairs of input tokens (words in the case of text strings), termed [attention](./Attention_(machine_learning)). The cost is quadratic in the number of tokens. For images, the basic unit of analysis is the [pixel](./Pixel). However, computing relationships for every pixel pair in a typical image is prohibitive in terms of memory and computation. Instead, ViT computes relationships among pixels in various small sections of the image (e.g., 16x16 pixels), at a drastically reduced cost. The sections (with positional embeddings) are placed in a sequence. The embeddings are learnable vectors. Each section is arranged into a linear sequence and multiplied by the embedding matrix. The result, with the position embedding is fed to the transformer.[[17]](./Vision_transformer#cite_note-Sarkar-2021-18)

 

### Architectural improvements

 

#### Pooling

 Main article: [Pooling layer](./Pooling_layer) 

After the ViT processes an image, it produces some embedding vectors. These must be converted to a single class probability prediction by some kind of network. In the original ViT and Masked Autoencoder, they used a dummy `[CLS]` token, in emulation of the [BERT](./BERT_(language_model)) language model. The output at `[CLS]` is the classification token, which is then processed by a [LayerNorm](./LayerNorm)-feedforward-softmax module into a probability distribution.

 

**Global average pooling (GAP)** does not use the dummy token, but simply takes the average of all output tokens as the classification token. It was mentioned in the original ViT as being equally good.[[1]](./Vision_transformer#cite_note-Dosovitskiy-2021-1)

 

**Multihead attention pooling (MAP)** applies a [multiheaded attention block](./Attention_(machine_learning)) to pooling. Specifically, it takes as input a list of vectors      x  1   ,  x  2   , … …  ,  x  n     {\displaystyle x_{1},x_{2},\dots ,x_{n}}  ![{\displaystyle x_{1},x_{2},\dots ,x_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75c2d357bc1b965979bf171b5ba3bac0f68961c2), which might be thought of as the output vectors of a layer of a ViT. The output from MAP is      M u l t i h e a d e d A t t e n t i o n  ( Q , V , V )   {\displaystyle \mathrm {MultiheadedAttention} (Q,V,V)}  ![{\displaystyle \mathrm {MultiheadedAttention} (Q,V,V)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/43ef54eba0ded90d4d9dec580f65fdb73d634df9), where     q   {\displaystyle q}  ![{\displaystyle q}](https://wikimedia.org/api/rest_v1/media/math/render/svg/06809d64fa7c817ffc7e323f85997f783dbdf71d) is a trainable query vector, and     V   {\displaystyle V}  ![{\displaystyle V}](https://wikimedia.org/api/rest_v1/media/math/render/svg/af0f6064540e84211d0ffe4dac72098adfa52845) is the matrix with rows being      x  1   ,  x  2   , … …  ,  x  n     {\displaystyle x_{1},x_{2},\dots ,x_{n}}  ![{\displaystyle x_{1},x_{2},\dots ,x_{n}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/75c2d357bc1b965979bf171b5ba3bac0f68961c2).[[18]](./Vision_transformer#cite_note-Zhai-2022-19) This was first proposed in the **Set Transformer** architecture.[[19]](./Vision_transformer#cite_note-20)

 

Later papers demonstrated that GAP and MAP both perform better than BERT-like pooling.[[18]](./Vision_transformer#cite_note-Zhai-2022-19)[[20]](./Vision_transformer#cite_note-21) A variant of MAP was proposed as **class attention**, which applies MAP, then feedforward, then MAP again.[[21]](./Vision_transformer#cite_note-22)

 

**Re-attention** was proposed to allow training deep ViT. It changes the multiheaded attention module.[[22]](./Vision_transformer#cite_note-23)

 

### Masked Autoencoder

 [![](//upload.wikimedia.org/wikipedia/commons/thumb/6/6c/Masked_Autoencoder.svg/250px-Masked_Autoencoder.svg.png)](./File:Masked_Autoencoder.svg)Masked Autoencoder architecture 

The **Masked Autoencoder**[[23]](./Vision_transformer#cite_note-24) took inspiration from [denoising autoencoders](./Denoising_autoencoder) and context encoders.[[24]](./Vision_transformer#cite_note-25) It has two ViTs put end-to-end. The first one ("encoder") takes in image patches with positional encoding, and outputs vectors representing each patch. The second one (called "decoder", even though it is still an encoder-only Transformer) takes in vectors with positional encoding and outputs image patches again.

 

#### Training

 

During training, input images (224px x 224 px in the original implementation) are split along a designated number of lines on each axis, producing image patches.[[25]](./Vision_transformer#cite_note-Swin_Transformer_2111-26) A certain percentage of patches are selected to be masked out by mask tokens, while all others are retained in the image. The network is tasked with reconstructing the image from the remaining unmasked patches. Mask tokens in the original implementation are learnable [vector quantities](./Vector_space).[[25]](./Vision_transformer#cite_note-Swin_Transformer_2111-26) A [linear projection](./Projection_(linear_algebra)) with positional embeddings is then applied to the vector of unmasked patches. Experiments varying mask ratio on networks trained on the [ImageNet-1K](./ImageNet) dataset found 75% mask ratios[[25]](./Vision_transformer#cite_note-Swin_Transformer_2111-26) achieved high performance on both finetuning and linear-probing of the encoder's [latent space](./Latent_space). The MAE processes only unmasked patches during training, increasing the efficiency of data processing in the encoder and lowering the memory usage of the [transformer](./Transformer_(deep_learning_architecture)).[[25]](./Vision_transformer#cite_note-Swin_Transformer_2111-26)

 

A less computationally-intensive ViT is used for the decoder in the original implementation of the MAE. Masked patches are added back to the output of the encoder block as mask tokens and both are fed into the decoder. A reconstruction loss is computed for the masked patches to assess network performance.

 

#### Prediction

 

In prediction, the decoder architecture is discarded entirely. The input image is split into patches by the same algorithm as in training, but no patches are masked out. A linear projection with a positional embedding is applied to each patch, and the resulting embedding vector representations of each patch are fed to the encoder.

 

#### Uses and Derivatives

 

Several derivatives of the original MAE have been explored. The MAE has been applied for self-supervised pretraining in medical contexts, including for chest X-ray interpretation.[[26]](./Vision_transformer#cite_note-27) Derivatives of the MAE have been applied in this context to better serve as pretraining in medical contexts.

 Medically Supervised MAE[[27]](./Vision_transformer#cite_note-28) Medically Supervised MAE seeks to address the application of MAE's high mask ratios when applied to medical lesion datasets and uses a [supervised training](./Supervised_learning) set to create local attention maps for medical images in order to constrain which patches are masked out. Medically Supervised MAE achieved state-of-the-art performance as of Jan. 2025 on the classification of medical lesions on the Messidor-2, BTMD, HAM10000, DeepLesion, and ChestXRay2017 datasets[[28]](./Vision_transformer#cite_note-29) [Gray Level Co-occurrence Matrix MAE](./Co-occurrence_matrix) (GLCM-MAE)[[29]](./Vision_transformer#cite_note-30) GCLM-MAE uses GCLM to extract texture information from images in order to preserve texture information. It addresses an issue in which a classic MAE oversmooths images, causing a loss of granular detail that may be important in medical contexts. GLCM-MAE achieves state-of-the-art performance on the identification of gallbladder cancer, breast cancer imaged from ultrasound, pneumonia imaged from X-rays, and COVID-19 imaged from computed tomography as of Jul. 2025. Region-aware MAE,[[30]](./Vision_transformer#cite_note-31) R-MAER-MAE replaces patch-generating step in the original MAE with an algorithm for assigning individual pixels to regions of interest in an image, which are masked out together. The region encoding architecture is standalone, but can be combined with the MAE for region reconstruction. Siamese MAEs (SiamMAE)[[31]](./Vision_transformer#cite_note-32) SiamMAE is a network designed to apply MAEs to video data. Samples two frames from a video (compared to one in the original MAE), and labels them as "past" and "future." The network masks out a majority of the patches (~95%) in the future frame, leaves the past frame untouched, and passes both through the MAE encoder block. The decoder architecture is replaced with attention blocks that map patches from the past frame to the future frame for reconstruction. SiamMAE achieves competitive performance against larger models on segmentation and propagation in videos. 

A similar architecture was BERT ViT (BEiT), published concurrently.[[32]](./Vision_transformer#cite_note-33)

 

### DINO

 

Like the Masked Autoencoder, the **DINO** (self-**di**stillation with **no** labels) method is a way to train a ViT by [self-supervision](./Self-supervised_learning).[[33]](./Vision_transformer#cite_note-Caron-2021-34) DINO is a form of teacher-student [self-distillation](./Knowledge_distillation). In DINO, the student is the model itself, and the teacher is an exponential average of the student's past states. The method is similar to previous works like momentum contrast[[34]](./Vision_transformer#cite_note-35) and bootstrap your own latent (BYOL).[[35]](./Vision_transformer#cite_note-36)

 

The loss function used in DINO is the [cross-entropy loss](./Cross-entropy) between the output of the teacher network (     f   θ θ   t  ′      {\displaystyle f_{\theta '_{t}}}  ![{\displaystyle f_{\theta '_{t}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c9c4800f11ac3e8b0bc5e5c729b4a30c54bc051a)) and the output of the student network (     f   θ θ   t       {\displaystyle f_{\theta _{t}}}  ![{\displaystyle f_{\theta _{t}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/c318a229bd62aef30d84225fc981ec2f2a1c496e)). The teacher network is an exponentially decaying average of the student network's past parameters:      θ θ   t  ′  = α α   θ θ   t   + α α  ( 1 − −  α α  )  θ θ   t − −  1   + ⋯ ⋯    {\displaystyle \theta '_{t}=\alpha \theta _{t}+\alpha (1-\alpha )\theta _{t-1}+\cdots }  ![{\displaystyle \theta '_{t}=\alpha \theta _{t}+\alpha (1-\alpha )\theta _{t-1}+\cdots }](https://wikimedia.org/api/rest_v1/media/math/render/svg/20a526772c4624f3f26df65368674ce21cff1336). The inputs to the networks are two different crops of the same image, represented as     T ( x )   {\displaystyle T(x)}  ![{\displaystyle T(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/1171c29b4c2b5575f50a4ea9313f90448a2cbe05) and      T ′  ( x )   {\displaystyle T'(x)}  ![{\displaystyle T'(x)}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d956b8bccfd575bf67c0dce07c8665fa69a3a510), where     x   {\displaystyle x}  ![{\displaystyle x}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87f9e315fd7e2ba406057a97300593c4802b53e4) is the original image. The loss function is written as    L (  f   θ θ   t  ′    ( T ( x ) ) ,  f   θ θ   t     (  T ′  ( x ) ) )   {\displaystyle L(f_{\theta '_{t}}(T(x)),f_{\theta _{t}}(T'(x)))}  ![{\displaystyle L(f_{\theta '_{t}}(T(x)),f_{\theta _{t}}(T'(x)))}](https://wikimedia.org/api/rest_v1/media/math/render/svg/563065bb63d8cd83357887e6fbb3d2492a166363)One issue is that the network can "collapse" by always outputting the same value (    y   {\displaystyle y}  ![{\displaystyle y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b8a6208ec717213d4317e666f1ae872e00620a0d)), regardless of the input. To prevent this collapse, DINO employs two strategies:

 
- **Sharpening**: The teacher network's output is sharpened using a softmax function with a lower temperature. This makes the teacher more "confident" in its predictions, forcing the student to learn more meaningful representations to match the teacher's sharpened output.
- **Centering**: The teacher network's output is centered by averaging it with its previous outputs. This prevents the teacher from becoming biased towards any particular output value, encouraging the student to learn a more diverse set of features.

 

In January 2024, [Meta AI](./Meta_AI) Research released an updated version called DINOv2[[36]](./Vision_transformer#cite_note-37) with improvements in architecture, loss function, and optimization technique. It was trained on a larger and more diverse dataset. The features learned by DINOv2 were more [transferable](./Transfer_learning), meaning it had better performance in downstream tasks.

 

In August 2025, Meta AI Research released DINOv3, an update to DINOv2. It introduced image-text alignment like [CLIP](./Contrastive_Language-Image_Pre-training). It scaled up the model to 7B parameters and the training dataset to 1.7B images (obtained by diversity-sampling an initial dataset with 17B images). Architecturally, it introduced two improvements: Gram anchoring and axial RoPE ([Rotary Positional Embeddings](./Rotary_positional_embedding)) with jittering. Gram anchoring applies teacher-student self-distillation for the [Gram matrix](./Gram_matrix) between the feature vectors of the patches of an image. It avoids the previously observed problem of degradation of dense feature maps: While performance on global tasks (like classification) continued to improve, performance on dense tasks (like segmentation) would peak early and then decline, with feature maps becoming noisy. Axial RoPE makes the model more robust to varying image resolutions, scales, and aspect ratios.[[37]](./Vision_transformer#cite_note-38)[[38]](./Vision_transformer#cite_note-39)

 

### Swin Transformer

 

The **Swin Transformer** ("**S**hifted **win**dows")[[14]](./Vision_transformer#cite_note-Liu-2021-14) took inspiration from standard CNNs:

 
- Instead of performing self-attention over the entire sequence of tokens, one for each patch, it performs "shifted window based" self-attention, which means only performing attention over square-shaped blocks of patches. One block of patches is analogous to the receptive field of one convolution.
- After every few attention blocks, there is a "merge layer", which merges neighboring 2x2 tokens into a single token. This is analogous to [pooling](./Pooling_layer) (by 2x2 convolution kernels, with stride 2). Merging means concatenation followed by multiplication with a matrix.

 

It is improved by Swin Transformer V2,[[39]](./Vision_transformer#cite_note-40) which modifies upon the ViT by a different attention mechanism[[14]](./Vision_transformer#cite_note-Liu-2021-14): Figure 1 :

 
- [LayerNorm](./LayerNorm) immediately after each attention and feedforward layer ("res-post-norm");
- scaled cosine attention to replace the original dot product attention;
- log-spaced continuous [relative position bias](./Transformer_(machine_learning_model)#Alternative_positional_encodings), which allows [transfer learning](./Transfer_learning) across different window resolutions.

 

### TimeSformer

 

The **TimeSformer**[[40]](./Vision_transformer#cite_note-41) was designed for video understanding tasks, and it applied a factorized self-attention, similar to the factorized convolution kernels found in the [Inception](./Inceptionv3) CNN architecture.[[41]](./Vision_transformer#cite_note-42) Schematically, it divides a video into frames, and each frame into a square grid of patches (same as ViT). Let each patch coordinate be denoted by     x , y , t   {\displaystyle x,y,t}  ![{\displaystyle x,y,t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/77a04fe169d6625eedb4e4db82339863f01f5ef9), denoting horizontal, vertical, and time.

 
- A space attention layer is a self-attention layer where each query patch      q  x , y , t     {\displaystyle q_{x,y,t}}  ![{\displaystyle q_{x,y,t}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/87ca5e2c2a1149aeca6dc82604aaec7edd0e8a75) attends to only the key and value patches      k   x ′  ,  y ′  ,  t ′    ,  v   x ′  ,  y ′  ,  t ′      {\displaystyle k_{x',y',t'},v_{x',y',t'}}  ![{\displaystyle k_{x',y',t'},v_{x',y',t'}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/83e32beda6e54ce888f1dcc2bede309170e399bb) such that     t =  t ′    {\displaystyle t=t'}  ![{\displaystyle t=t'}](https://wikimedia.org/api/rest_v1/media/math/render/svg/7052c148f3b151bda60fb3f2ccbd693fac915a11).
- A time attention layer is where the requirement is      x ′  = x ,  y ′  = y   {\displaystyle x'=x,y'=y}  ![{\displaystyle x'=x,y'=y}](https://wikimedia.org/api/rest_v1/media/math/render/svg/b128f599e21a101878defb185a56988d73cdc471) instead.

 

The TimeSformer also considered other attention layer designs, such as the "height attention layer" where the requirement is      x ′  = x ,  t ′  = t   {\displaystyle x'=x,t'=t}  ![{\displaystyle x'=x,t'=t}](https://wikimedia.org/api/rest_v1/media/math/render/svg/d5b6b981f519d36dbd667fc7d3418eef3daac5e5). However, they found empirically that the best design interleaves one space attention layer and one time attention layer.

 

### ViT-VQGAN

 

In **ViT-VQGAN**,[[42]](./Vision_transformer#cite_note-43) there are two ViT encoders and a discriminator. One encodes 8x8 patches of an image into a list of vectors, one for each patch. The vectors can only come from a discrete set of "codebook", as in [vector quantization](./Vector_quantization). Another encodes the quantized vectors back to image patches. The training objective attempts to make the reconstruction image (the output image) faithful to the input image. The discriminator (usually a convolutional network, but other networks are allowed) attempts to decide if an image is an original real image, or a reconstructed image by the ViT.

 

The idea is essentially the same as vector quantized variational autoencoder (VQVAE) plus [generative adversarial network](./Generative_adversarial_network) (GAN).

 

After such a ViT-VQGAN is trained, it can be used to code an arbitrary image into a list of symbols, and code an arbitrary list of symbols into an image. The list of symbols can be used to train into a standard autoregressive transformer (like GPT), for autoregressively generating an image. Further, one can take a list of caption-image pairs, convert the images into strings of symbols, and train a standard GPT-style transformer. Then at test time, one can just give an image caption, and have it autoregressively generate the image. This is the structure of Google Parti.[[43]](./Vision_transformer#cite_note-44)

 

### Others

 

Other examples include the visual transformer,[[44]](./Vision_transformer#cite_note-45) CoAtNet,[[45]](./Vision_transformer#cite_note-46) CvT,[[46]](./Vision_transformer#cite_note-47) the data-efficient ViT (DeiT),[[47]](./Vision_transformer#cite_note-48) etc.

 

In the Transformer in Transformer architecture, each layer applies a vision Transformer layer on each image patch embedding, add back the resulting tokens to the embedding, then applies another vision Transformer layer.[[48]](./Vision_transformer#cite_note-49)

 

## Comparison with CNNs

 

Typically, ViT uses patch sizes larger than standard CNN kernels (3x3 to 7x7). ViT is more sensitive to the choice of the optimizer, [hyperparameters](./Hyperparameter_(machine_learning)), and network depth. Preprocessing with a layer of smaller-size, overlapping (stride < size) convolutional filters helps with performance and stability.[[13]](./Vision_transformer#cite_note-Xiao-2021-13)

 

This different behavior seems to derive from the different [inductive biases](./Inductive_bias) they possess:

 
- CNN applies the same set of filters for processing the entire image. This allows them to be more data efficient and less sensitive to local perturbations.[[2]](./Vision_transformer#cite_note-Raghu-2021-2)
- ViT applies self-attention, allowing them to easily capture long-range relationships between patches.[[49]](./Vision_transformer#cite_note-Gross2025-LLViT-50) They also require more data to train, but they can ingest more training data compared to CNN, which might not improve after training on a large enough training dataset. ViT also appears more robust to input image distortions such as adversarial patches or permutations.[[50]](./Vision_transformer#cite_note-51)

 

## Applications

 

ViT have been used in many computer vision tasks with excellent results and in some cases even state-of-the-art, such as in [image classification](./Image_classification), [object detection](./Object_detection), video [deepfake](./Deepfake) detection,[[51]](./Vision_transformer#cite_note-52) [image segmentation](./Image_segmentation),[[52]](./Vision_transformer#cite_note-53) [anomaly detection](./Anomaly_detection), [image synthesis](./Image_synthesis), [cluster analysis](./Cluster_analysis), [autonomous driving](./Autonomous_driving).[[6]](./Vision_transformer#cite_note-Han-2023-6)[[7]](./Vision_transformer#cite_note-Khan-2022-7)

 

ViT had been used for image generation as backbones for [GAN](./Generative_adversarial_network)[[53]](./Vision_transformer#cite_note-54) and for [diffusion models](./Diffusion_model) (diffusion transformer, or DiT).[[54]](./Vision_transformer#cite_note-55)

 

DINO[[33]](./Vision_transformer#cite_note-Caron-2021-34) has been demonstrated to learn useful representations for clustering images and exploring morphological profiles on biological datasets, such as images generated with the [Cell Painting](./Cell_Painting) assay.[[55]](./Vision_transformer#cite_note-56)

 

In 2024, a 113 billion-parameter ViT model was designed (the largest ViT to date) for [weather and climate prediction](./Weather_forecasting), and trained on the [Frontier supercomputer](./Frontier_(supercomputer)) with a throughput of 1.6 [exaFLOPs](./Floating_point_operations_per_second).[[56]](./Vision_transformer#cite_note-57)

 

## See also

 
- [Transformer (machine learning model)](./Transformer_(machine_learning_model))
- [Convolutional neural network](./Convolutional_neural_network)
- [Attention (machine learning)](./Attention_(machine_learning))
- [Perceiver](./Perceiver)
- [Deep learning](./Deep_learning)
- [PyTorch](./PyTorch)
- [TensorFlow](./TensorFlow)

 

## Notes

  
1. [↑](./Vision_transformer#cite_ref-15) All positional embeddings in Dosovitskiy *et al.* (2021) all performed better than no embedding. They were not very different from each other, though 1D has a slight advantage in score.

 

## References

  
1. [1](./Vision_transformer#cite_ref-Dosovitskiy-2021_1-0) [2](./Vision_transformer#cite_ref-Dosovitskiy-2021_1-1) [3](./Vision_transformer#cite_ref-Dosovitskiy-2021_1-2) [4](./Vision_transformer#cite_ref-Dosovitskiy-2021_1-3) [5](./Vision_transformer#cite_ref-Dosovitskiy-2021_1-4) [6](./Vision_transformer#cite_ref-Dosovitskiy-2021_1-5) [7](./Vision_transformer#cite_ref-Dosovitskiy-2021_1-6) Dosovitskiy, Alexey; Beyer, Lucas; Kolesnikov, Alexander; Weissenborn, Dirk; Zhai, Xiaohua; Unterthiner, Thomas; Dehghani, Mostafa; Minderer, Matthias; Heigold, Georg; Gelly, Sylvain; Uszkoreit, Jakob (2021-06-03). "An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale". [arXiv](./ArXiv_(identifier)):[2010.11929](https://arxiv.org/abs/2010.11929) [[cs.CV](https://arxiv.org/archive/cs.CV)].
2. [1](./Vision_transformer#cite_ref-Raghu-2021_2-0) [2](./Vision_transformer#cite_ref-Raghu-2021_2-1) Raghu, Maithra; Unterthiner, Thomas; Kornblith, Simon; Zhang, Chiyuan; Dosovitskiy, Alexey (2021-08-19). "Do Vision Transformers See Like Convolutional Neural Networks?". [arXiv](./ArXiv_(identifier)):[2108.08810](https://arxiv.org/abs/2108.08810) [[cs.CV](https://arxiv.org/archive/cs.CV)].
3. [↑](./Vision_transformer#cite_ref-3) Dehghani, Mostafa; Djolonga, Josip; Mustafa, Basil; Padlewski, Piotr; Heek, Jonathan; Gilmer, Justin; Steiner, Andreas; Caron, Mathilde; Geirhos, Robert (2023-02-10), *Scaling Vision Transformers to 22 Billion Parameters*, [arXiv](./ArXiv_(identifier)):[2302.05442](https://arxiv.org/abs/2302.05442)
4. [↑](./Vision_transformer#cite_ref-4) ["Scaling vision transformers to 22 billion parameters"](https://research.google/blog/scaling-vision-transformers-to-22-billion-parameters/). *research.google*. Retrieved 2024-08-07.
5. [↑](./Vision_transformer#cite_ref-Koresh2025_5-0) Koresh, Ella; Gross, Ronit D.; Meir, Yuval; Tzach, Yarden; Halevi, Tal; Kanter, Ido (2025). ["Unified CNNs and transformers underlying learning mechanism reveals multi-head attention modus vivendi"](https://www.sciencedirect.com/science/article/pii/S0378437125001815). *Physica A: Statistical Mechanics and Its Applications*. **666** 130529. [arXiv](./ArXiv_(identifier)):[2501.12900](https://arxiv.org/abs/2501.12900). [Bibcode](./Bibcode_(identifier)):[2025PhyA..66630529K](https://ui.adsabs.harvard.edu/abs/2025PhyA..66630529K). [doi](./Doi_(identifier)):[10.1016/j.physa.2025.130529](https://doi.org/10.1016%2Fj.physa.2025.130529). [ISSN](./ISSN_(identifier)) [0378-4371](https://search.worldcat.org/issn/0378-4371).
6. [1](./Vision_transformer#cite_ref-Han-2023_6-0) [2](./Vision_transformer#cite_ref-Han-2023_6-1) Han, Kai; Wang, Yunhe; Chen, Hanting; Chen, Xinghao; Guo, Jianyuan; Liu, Zhenhua; Tang, Yehui; Xiao, An; Xu, Chunjing; Xu, Yixing; Yang, Zhaohui; Zhang, Yiman; Tao, Dacheng (2023-01-01). "A Survey on Vision Transformer". *IEEE Transactions on Pattern Analysis and Machine Intelligence*. **45** (1): 87–110. [arXiv](./ArXiv_(identifier)):[2012.12556](https://arxiv.org/abs/2012.12556). [Bibcode](./Bibcode_(identifier)):[2023ITPAM..45...87H](https://ui.adsabs.harvard.edu/abs/2023ITPAM..45...87H). [doi](./Doi_(identifier)):[10.1109/TPAMI.2022.3152247](https://doi.org/10.1109%2FTPAMI.2022.3152247). [ISSN](./ISSN_(identifier)) [0162-8828](https://search.worldcat.org/issn/0162-8828). [PMID](./PMID_(identifier)) [35180075](https://pubmed.ncbi.nlm.nih.gov/35180075).
7. [1](./Vision_transformer#cite_ref-Khan-2022_7-0) [2](./Vision_transformer#cite_ref-Khan-2022_7-1) Khan, Salman; Naseer, Muzammal; Hayat, Munawar; Zamir, Syed Waqas; Khan, Fahad Shahbaz; Shah, Mubarak (2022-09-13). "Transformers in Vision: A Survey". *ACM Comput. Surv*. **54** (10s): 200:1–200:41. [arXiv](./ArXiv_(identifier)):[2101.01169](https://arxiv.org/abs/2101.01169). [doi](./Doi_(identifier)):[10.1145/3505244](https://doi.org/10.1145%2F3505244). [ISSN](./ISSN_(identifier)) [0360-0300](https://search.worldcat.org/issn/0360-0300).
8. [↑](./Vision_transformer#cite_ref-8) [Vaswani, Ashish](./Ashish_Vaswani); Shazeer, Noam; Parmar, Niki; Uszkoreit, Jakob; Jones, Llion; [Gomez, Aidan N](./Aidan_Gomez); Kaiser, Łukasz; Polosukhin, Illia (2017). ["Attention is All you Need"](https://proceedings.neurips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf) (PDF). *Advances in Neural Information Processing Systems*. **30**. Curran Associates, Inc.
9. [↑](./Vision_transformer#cite_ref-9) Ramachandran, Prajit; Parmar, Niki; Vaswani, Ashish; Bello, Irwan; Levskaya, Anselm; Shlens, Jon (2019). ["Stand-Alone Self-Attention in Vision Models"](https://proceedings.neurips.cc/paper/2019/hash/3416a75f4cea9109507cacd8e2f2aefc-Abstract.html). *Advances in Neural Information Processing Systems*. **32**. Curran Associates, Inc. [arXiv](./ArXiv_(identifier)):[1906.05909](https://arxiv.org/abs/1906.05909).
10. [↑](./Vision_transformer#cite_ref-10) Liu, Zhuang; Mao, Hanzi; Wu, Chao-Yuan; Feichtenhofer, Christoph; Darrell, Trevor; Xie, Saining (2022). ["A ConvNet for the 2020s"](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_A_ConvNet_for_the_2020s_CVPR_2022_paper.html): 11976–11986. [arXiv](./ArXiv_(identifier)):[2201.03545](https://arxiv.org/abs/2201.03545). `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
11. [↑](./Vision_transformer#cite_ref-11) Woo, Sanghyun; Debnath, Shoubhik; Hu, Ronghang; Chen, Xinlei; Liu, Zhuang; Kweon, In So; Xie, Saining (2023). ["ConvNeXt V2: Co-Designing and Scaling ConvNets With Masked Autoencoders"](https://openaccess.thecvf.com/content/CVPR2023/html/Woo_ConvNeXt_V2_Co-Designing_and_Scaling_ConvNets_With_Masked_Autoencoders_CVPR_2023_paper.html): 16133–16142. [arXiv](./ArXiv_(identifier)):[2301.00808](https://arxiv.org/abs/2301.00808). `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
12. [↑](./Vision_transformer#cite_ref-12) Wu, Bichen; Xu, Chenfeng; Dai, Xiaoliang; Wan, Alvin; Zhang, Peizhao; Yan, Zhicheng; Masayoshi, Tomizuka; Gonzalez, Joseph; Keutzer, Kurt; Vajda, Peter (2020). "Visual Transformers: Token-based Image Representation and Processing for Computer Vision". [arXiv](./ArXiv_(identifier)):[2006.03677](https://arxiv.org/abs/2006.03677) [[cs.CV](https://arxiv.org/archive/cs.CV)].
13. [1](./Vision_transformer#cite_ref-Xiao-2021_13-0) [2](./Vision_transformer#cite_ref-Xiao-2021_13-1) Xiao, Tete; Singh, Mannat; Mintun, Eric; Darrell, Trevor; Dollár, Piotr; Girshick, Ross (2021-06-28). "Early Convolutions Help Transformers See Better". [arXiv](./ArXiv_(identifier)):[2106.14881](https://arxiv.org/abs/2106.14881) [[cs.CV](https://arxiv.org/archive/cs.CV)].
14. [1](./Vision_transformer#cite_ref-Liu-2021_14-0) [2](./Vision_transformer#cite_ref-Liu-2021_14-1) [3](./Vision_transformer#cite_ref-Liu-2021_14-2) Liu, Ze; Lin, Yutong; Cao, Yue; Hu, Han; Wei, Yixuan; Zhang, Zheng; Lin, Stephen; Guo, Baining (2021-03-25). "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows". [arXiv](./ArXiv_(identifier)):[2103.14030](https://arxiv.org/abs/2103.14030) [[cs.CV](https://arxiv.org/archive/cs.CV)].
15. [↑](./Vision_transformer#cite_ref-16) Tan, Mingxing; Le, Quoc (23 June 2021). ["EfficientNetV2: Smaller Models and Faster Training"](https://proceedings.mlr.press/v139/tan21a/tan21a.pdf) (PDF). *Proceedings of the 38th International Conference on Machine Learning (PMLR)*. **139**: 10096–10106. [arXiv](./ArXiv_(identifier)):[2104.00298](https://arxiv.org/abs/2104.00298). Retrieved 31 October 2023.
16. [↑](./Vision_transformer#cite_ref-17) Huang, Gao; Liu, Zhuang; van der Maaten, Laurens; Q. Weinberger, Kilian (28 Jan 2018). "Densely Connected Convolutional Networks". [arXiv](./ArXiv_(identifier)):[1608.06993](https://arxiv.org/abs/1608.06993) [[cs.CV](https://arxiv.org/archive/cs.CV)].
17. [1](./Vision_transformer#cite_ref-Sarkar-2021_18-0) [2](./Vision_transformer#cite_ref-Sarkar-2021_18-1) Sarkar, Arjun (2021-05-20). ["Are Transformers better than CNN's at Image Recognition?"](https://web.archive.org/web/20220511082728/https://towardsdatascience.com/are-transformers-better-than-cnns-at-image-recognition-ced60ccc7c8). *Medium*. Archived from [the original](https://towardsdatascience.com/are-transformers-better-than-cnns-at-image-recognition-ced60ccc7c8) on 2022-05-11. Retrieved 2021-07-11.
18. [1](./Vision_transformer#cite_ref-Zhai-2022_19-0) [2](./Vision_transformer#cite_ref-Zhai-2022_19-1) Zhai, Xiaohua; Kolesnikov, Alexander; Houlsby, Neil; Beyer, Lucas (June 2022). ["Scaling Vision Transformers"](https://dx.doi.org/10.1109/cvpr52688.2022.01179). *2022 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*. IEEE. pp. 1204–1213. [arXiv](./ArXiv_(identifier)):[2106.04560](https://arxiv.org/abs/2106.04560). [doi](./Doi_(identifier)):[10.1109/cvpr52688.2022.01179](https://doi.org/10.1109%2Fcvpr52688.2022.01179). [ISBN](./ISBN_(identifier)) [978-1-6654-6946-3](./Special:BookSources/978-1-6654-6946-3).
19. [↑](./Vision_transformer#cite_ref-20) Lee, Juho; Lee, Yoonho; Kim, Jungtaek; Kosiorek, Adam; Choi, Seungjin; Teh, Yee Whye (2019-05-24). ["Set Transformer: A Framework for Attention-based Permutation-Invariant Neural Networks"](https://proceedings.mlr.press/v97/lee19d.html). *Proceedings of the 36th International Conference on Machine Learning*. PMLR: 3744–3753. [arXiv](./ArXiv_(identifier)):[1810.00825](https://arxiv.org/abs/1810.00825).
20. [↑](./Vision_transformer#cite_ref-21) Karamcheti, Siddharth; Nair, Suraj; Chen, Annie S.; Kollar, Thomas; Finn, Chelsea; Sadigh, Dorsa; [Liang, Percy](./Percy_Liang) (2023-02-24), *Language-Driven Representation Learning for Robotics*, [arXiv](./ArXiv_(identifier)):[2302.12766](https://arxiv.org/abs/2302.12766)
21. [↑](./Vision_transformer#cite_ref-22) Touvron, Hugo; Cord, Matthieu; Sablayrolles, Alexandre; Synnaeve, Gabriel; Jégou, Hervé (2021). ["Going Deeper With Image Transformers"](https://openaccess.thecvf.com/content/ICCV2021/html/Touvron_Going_Deeper_With_Image_Transformers_ICCV_2021_paper.html): 32–42. [arXiv](./ArXiv_(identifier)):[2103.17239](https://arxiv.org/abs/2103.17239). `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
22. [↑](./Vision_transformer#cite_ref-23) Zhou, Daquan; Kang, Bingyi; Jin, Xiaojie; Yang, Linjie; Lian, Xiaochen; Jiang, Zihang; Hou, Qibin; Feng, Jiashi (2021-04-19), *DeepViT: Towards Deeper Vision Transformer*, [arXiv](./ArXiv_(identifier)):[2103.11886](https://arxiv.org/abs/2103.11886)
23. [↑](./Vision_transformer#cite_ref-24) He, Kaiming; Chen, Xinlei; Xie, Saining; Li, Yanghao; Dollár, Piotr; Girshick, Ross (2021). "Masked Autoencoders Are Scalable Vision Learners". [arXiv](./ArXiv_(identifier)):[2111.06377](https://arxiv.org/abs/2111.06377) [[cs.CV](https://arxiv.org/archive/cs.CV)].
24. [↑](./Vision_transformer#cite_ref-25) Pathak, Deepak; Krahenbuhl, Philipp; Donahue, Jeff; Darrell, Trevor; Efros, Alexei A. (June 2016). "Context Encoders: Feature Learning by Inpainting". *2016 IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*. IEEE. pp. 2536–2544. [arXiv](./ArXiv_(identifier)):[1604.07379](https://arxiv.org/abs/1604.07379). [doi](./Doi_(identifier)):[10.1109/CVPR.2016.278](https://doi.org/10.1109%2FCVPR.2016.278). [ISBN](./ISBN_(identifier)) [978-1-4673-8851-1](./Special:BookSources/978-1-4673-8851-1).
25. [1](./Vision_transformer#cite_ref-Swin_Transformer_2111_26-0) [2](./Vision_transformer#cite_ref-Swin_Transformer_2111_26-1) [3](./Vision_transformer#cite_ref-Swin_Transformer_2111_26-2) [4](./Vision_transformer#cite_ref-Swin_Transformer_2111_26-3) Liu, Ze; Lin, Yutong; Cao, Yue; Hu, Han; Wei, Yixuan; Zhang, Zheng; Lin, Stephen; Guo, Baining (2021). "Swin Transformer: Hierarchical Vision Transformer using Shifted Windows". [arXiv](./ArXiv_(identifier)):[2111.06377](https://arxiv.org/abs/2111.06377) [[cs.CV](https://arxiv.org/archive/cs.CV)].
26. [↑](./Vision_transformer#cite_ref-27) Zhou, Lei; Liu, Huidong; Bae, Joseph; He, Junjun; Samaras, Dimitris; Prasanna, Prateek (2022). "Self Pre-Training with Masked Autoencoders for Medical Image Classification and Segmentation". [arXiv](./ArXiv_(identifier)):[2203.05573](https://arxiv.org/abs/2203.05573) [[eess.IV](https://arxiv.org/archive/eess.IV)].
27. [↑](./Vision_transformer#cite_ref-28) Chen, Rui; Yang, Xiaotong; Li, Yue; Peng, Guocheng; Zhu, Qiuyue; Zhang, Zhenyu; Jiang, Hong (2024). "Deep learning-based model for automatic detection and grading of meibomian gland dysfunction from infrared images". *Applied Soft Computing*. **164** 112905. [doi](./Doi_(identifier)):[10.1016/j.asoc.2024.112905](https://doi.org/10.1016%2Fj.asoc.2024.112905) (inactive 17 October 2025).`{{cite journal}}`:  CS1 maint: DOI inactive as of October 2025 ([link](./Category:CS1_maint:_DOI_inactive_as_of_October_2025))
28. [↑](./Vision_transformer#cite_ref-29) Chen, Rui; Yang, Xiaotong; Li, Yue; Peng, Guocheng; Zhu, Qiuyue; Zhang, Zhenyu; Jiang, Hong (2024). "Deep learning-based model for automatic detection and grading of meibomian gland dysfunction from infrared images". *Applied Soft Computing*. **164** 112905. [arXiv](./ArXiv_(identifier)):[2507.10869](https://arxiv.org/abs/2507.10869).
29. [↑](./Vision_transformer#cite_ref-30) Madan, Chetan; Satia, Aarjav; Basu, Soumen; Gupta, Pankaj; Dutta, Usha; Arora, Chetan (2025). "Focus on Texture: Rethinking Pre-training in Masked Autoencoders for Medical Image Classification". [arXiv](./ArXiv_(identifier)):[2507.10869](https://arxiv.org/abs/2507.10869) [[eess.IV](https://arxiv.org/archive/eess.IV)].
30. [↑](./Vision_transformer#cite_ref-31) Nguyen, Duy Kien; Li, Yanghao; Aggarwal, Vaibhav; Oswald, Martin R.; Kirillov, Alexander; Snoek, Cees G. M.; Chen, Xinlei (2024). ["R-MAE: Regions Meet Masked Autoencoders"](https://openreview.net/pdf?id=ba84RDHFnz) (PDF). *OpenReview.net*. International Conference on Learning Representations.
31. [↑](./Vision_transformer#cite_ref-32) Gupta, Agrim; Wu, Jiajun; Deng, Jia; Fei-Fei, Li (2023). "Siamese Masked Autoencoders". [arXiv](./ArXiv_(identifier)):[2305.14344](https://arxiv.org/abs/2305.14344) [[cs.CV](https://arxiv.org/archive/cs.CV)].
32. [↑](./Vision_transformer#cite_ref-33) Bao, Hangbo; Dong, Li; Piao, Songhao; Wei, Furu (2021-10-06). ["BEiT: BERT Pre-Training of Image Transformers"](https://openreview.net/forum?id=p-BhZSz59o4). *International Conference on Learning Representations*. [arXiv](./ArXiv_(identifier)):[2106.08254](https://arxiv.org/abs/2106.08254).
33. [1](./Vision_transformer#cite_ref-Caron-2021_34-0) [2](./Vision_transformer#cite_ref-Caron-2021_34-1) Caron, Mathilde; Touvron, Hugo; Misra, Ishan; Jegou, Herve; Mairal, Julien; Bojanowski, Piotr; Joulin, Armand (October 2021). ["Emerging Properties in Self-Supervised Vision Transformers"](https://dx.doi.org/10.1109/iccv48922.2021.00951). *2021 IEEE/CVF International Conference on Computer Vision (ICCV)*. IEEE. pp. 9630–9640. [arXiv](./ArXiv_(identifier)):[2104.14294](https://arxiv.org/abs/2104.14294). [doi](./Doi_(identifier)):[10.1109/iccv48922.2021.00951](https://doi.org/10.1109%2Ficcv48922.2021.00951). [ISBN](./ISBN_(identifier)) [978-1-6654-2812-5](./Special:BookSources/978-1-6654-2812-5).
34. [↑](./Vision_transformer#cite_ref-35) He, Kaiming; Fan, Haoqi; Wu, Yuxin; Xie, Saining; Girshick, Ross (2020). ["Momentum Contrast for Unsupervised Visual Representation Learning"](https://openaccess.thecvf.com/content_CVPR_2020/html/He_Momentum_Contrast_for_Unsupervised_Visual_Representation_Learning_CVPR_2020_paper.html): 9729–9738. [arXiv](./ArXiv_(identifier)):[1911.05722](https://arxiv.org/abs/1911.05722). `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
35. [↑](./Vision_transformer#cite_ref-36) Grill, Jean-Bastien; Strub, Florian; Altché, Florent; Tallec, Corentin; Richemond, Pierre; Buchatskaya, Elena; Doersch, Carl; Avila Pires, Bernardo; Guo, Zhaohan; Gheshlaghi Azar, Mohammad; Piot, Bilal; kavukcuoglu, koray; Munos, Remi; Valko, Michal (2020). ["Bootstrap Your Own Latent - A New Approach to Self-Supervised Learning"](https://proceedings.neurips.cc/paper/2020/hash/f3ada80d5c4ee70142b17b8192b2958e-Abstract.html). *Advances in Neural Information Processing Systems*. **33**. Curran Associates, Inc.: 21271–21284.
36. [↑](./Vision_transformer#cite_ref-37) Oquab, Maxime; Darcet, Timothée; Moutakanni, Théo; Vo, Huy; Szafraniec, Marc; Khalidov, Vasil; Fernandez, Pierre; Haziza, Daniel; Massa, Francisco (2023-04-14). "DINOv2: Learning Robust Visual Features without Supervision". [arXiv](./ArXiv_(identifier)):[2304.07193](https://arxiv.org/abs/2304.07193) [[cs.CV](https://arxiv.org/archive/cs.CV)].
37. [↑](./Vision_transformer#cite_ref-38) ["DINOv3: Self-supervised learning for vision at unprecedented scale"](https://ai.meta.com/blog/dinov3-self-supervised-vision-model/). *ai.meta.com*. [Archived](https://web.archive.org/web/20250814224844/https://ai.meta.com/blog/dinov3-self-supervised-vision-model/) from the original on 2025-08-14. Retrieved 2025-08-16.
38. [↑](./Vision_transformer#cite_ref-39) Siméoni, Oriane; Vo, Huy V.; Seitzer, Maximilian; Baldassarre, Federico; Oquab, Maxime; Jose, Cijo; Khalidov, Vasil; Szafraniec, Marc; Yi, Seungeun; Ramamonjisoa, Michaël; Massa, Francisco; Haziza, Daniel; Wehrstedt, Luca; Wang, Jianyuan; Darcet, Timothée; Moutakanni, Théo; Sentana, Leonel; Roberts, Claire; Vedaldi, Andrea; Tolan, Jamie; Brandt, John; Couprie, Camille; Mairal, Julien; Jégou, Hervé; Labatut, Patrick; Bojanowski, Piotr (2025). "DINOv3". [arXiv](./ArXiv_(identifier)):[2508.10104](https://arxiv.org/abs/2508.10104) [[cs.CV](https://arxiv.org/archive/cs.CV)].
39. [↑](./Vision_transformer#cite_ref-40) Liu, Ze; Hu, Han; Lin, Yutong; Yao, Zhuliang; Xie, Zhenda; Wei, Yixuan; Ning, Jia; Cao, Yue; Zhang, Zheng; Dong, Li; Wei, Furu; Guo, Baining (2022). ["Swin Transformer V2: Scaling Up Capacity and Resolution"](https://openaccess.thecvf.com/content/CVPR2022/html/Liu_Swin_Transformer_V2_Scaling_Up_Capacity_and_Resolution_CVPR_2022_paper.html). Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition. pp. 12009–12019.
40. [↑](./Vision_transformer#cite_ref-41) Bertasius, Gedas; Wang, Heng; Torresani, Lorenzo (2021-02-09). "Is Space-Time Attention All You Need for Video Understanding?". [arXiv](./ArXiv_(identifier)):[2102.05095](https://arxiv.org/abs/2102.05095) [[cs.CV](https://arxiv.org/archive/cs.CV)].
41. [↑](./Vision_transformer#cite_ref-42) Szegedy, Christian; Vanhoucke, Vincent; Ioffe, Sergey; Shlens, Jon; Wojna, Zbigniew (2016). ["Rethinking the Inception Architecture for Computer Vision"](https://www.cv-foundation.org/openaccess/content_cvpr_2016/html/Szegedy_Rethinking_the_Inception_CVPR_2016_paper.html): 2818–2826. [arXiv](./ArXiv_(identifier)):[1512.00567](https://arxiv.org/abs/1512.00567). `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
42. [↑](./Vision_transformer#cite_ref-43) Yu, Jiahui; Li, Xin; Koh, Jing Yu; Zhang, Han; Pang, Ruoming; Qin, James; Ku, Alexander; Xu, Yuanzhong; Baldridge, Jason; Wu, Yonghui (2021). "Vector-quantized Image Modeling with Improved VQGAN". [arXiv](./ArXiv_(identifier)):[2110.04627](https://arxiv.org/abs/2110.04627) [[cs.CV](https://arxiv.org/archive/cs.CV)].
43. [↑](./Vision_transformer#cite_ref-44) ["Parti: Pathways Autoregressive Text-to-Image Model"](https://sites.research.google/parti/). *sites.research.google*. Retrieved 2023-11-03.
44. [↑](./Vision_transformer#cite_ref-45) Wu, Bichen; Xu, Chenfeng; Dai, Xiaoliang; Wan, Alvin; Zhang, Peizhao; Yan, Zhicheng; Tomizuka, Masayoshi; Gonzalez, Joseph; Keutzer, Kurt (2020-11-19), *Visual Transformers: Token-based Image Representation and Processing for Computer Vision*, [arXiv](./ArXiv_(identifier)):[2006.03677](https://arxiv.org/abs/2006.03677)
45. [↑](./Vision_transformer#cite_ref-46) Dai, Zihang; Liu, Hanxiao; Le, Quoc V.; Tan, Mingxing (2021-06-09). "CoAtNet: Marrying Convolution and Attention for All Data Sizes". [arXiv](./ArXiv_(identifier)):[2106.04803](https://arxiv.org/abs/2106.04803) [[cs.CV](https://arxiv.org/archive/cs.CV)].
46. [↑](./Vision_transformer#cite_ref-47) Wu, Haiping; Xiao, Bin; Codella, Noel; Liu, Mengchen; Dai, Xiyang; Yuan, Lu; Zhang, Lei (2021-03-29). "CvT: Introducing Convolutions to Vision Transformers". [arXiv](./ArXiv_(identifier)):[2103.15808](https://arxiv.org/abs/2103.15808) [[cs.CV](https://arxiv.org/archive/cs.CV)].
47. [↑](./Vision_transformer#cite_ref-48) Touvron, Hugo; Cord, Matthieu; Jégou, Hervé (2022). "DeiT III: Revenge of the ViT". In Avidan, Shai; Brostow, Gabriel; Cissé, Moustapha; Farinella, Giovanni Maria; Hassner, Tal (eds.). *Computer Vision – ECCV 2022*. Lecture Notes in Computer Science. Vol. 13684. Cham: Springer Nature Switzerland. pp. 516–533. [arXiv](./ArXiv_(identifier)):[2204.07118](https://arxiv.org/abs/2204.07118). [doi](./Doi_(identifier)):[10.1007/978-3-031-20053-3_30](https://doi.org/10.1007%2F978-3-031-20053-3_30). [ISBN](./ISBN_(identifier)) [978-3-031-20053-3](./Special:BookSources/978-3-031-20053-3).
48. [↑](./Vision_transformer#cite_ref-49) Han, Kai; Xiao, An; Wu, Enhua; Guo, Jianyuan; XU, Chunjing; Wang, Yunhe (2021). ["Transformer in Transformer"](https://proceedings.neurips.cc/paper/2021/hash/854d9fca60b4bd07f9bb215d59ef5561-Abstract.html). *Advances in Neural Information Processing Systems*. **34**. Curran Associates, Inc.: 15908–15919.
49. [↑](./Vision_transformer#cite_ref-Gross2025-LLViT_50-0) Gross, Ronit D.; Halevi, Tal; Koresh, Ella; Tzach, Yarden; Kanter, Ido (2025). ["Low-latency vision transformers via large-scale multi-head attention"](https://www.sciencedirect.com/science/article/pii/S037843712500487X). *Physica A: Statistical Mechanics and Its Applications*. **675** 130835. [arXiv](./ArXiv_(identifier)):[2506.23832](https://arxiv.org/abs/2506.23832). [Bibcode](./Bibcode_(identifier)):[2025PhyA..67530835G](https://ui.adsabs.harvard.edu/abs/2025PhyA..67530835G). [doi](./Doi_(identifier)):[10.1016/j.physa.2025.130835](https://doi.org/10.1016%2Fj.physa.2025.130835). [ISSN](./ISSN_(identifier)) [0378-4371](https://search.worldcat.org/issn/0378-4371).
50. [↑](./Vision_transformer#cite_ref-51) Naseer, Muzammal; Ranasinghe, Kanchana; Khan, Salman; Hayat, Munawar; Khan, Fahad Shahbaz; [Yang, Ming-Hsuan](./Ming-Hsuan_Yang) (2021-05-21). "Intriguing Properties of Vision Transformers". [arXiv](./ArXiv_(identifier)):[2105.10497](https://arxiv.org/abs/2105.10497) [[cs.CV](https://arxiv.org/archive/cs.CV)].
51. [↑](./Vision_transformer#cite_ref-52) Coccomini, Davide; Messina, Nicola; Gennaro, Claudio; Falchi, Fabrizio (2022). "Combining Efficient *Net* and Vision Transformers for Video Deepfake Detection". *Image Analysis and Processing – ICIAP 2022*. Lecture Notes in Computer Science. Vol. 13233. pp. 219–229. [arXiv](./ArXiv_(identifier)):[2107.02612](https://arxiv.org/abs/2107.02612). [doi](./Doi_(identifier)):[10.1007/978-3-031-06433-3_19](https://doi.org/10.1007%2F978-3-031-06433-3_19). [ISBN](./ISBN_(identifier)) [978-3-031-06432-6](./Special:BookSources/978-3-031-06432-6). [S2CID](./S2CID_(identifier)) [235742764](https://api.semanticscholar.org/CorpusID:235742764).
52. [↑](./Vision_transformer#cite_ref-53) Kirillov, Alexander; Mintun, Eric; Ravi, Nikhila; Mao, Hanzi; Rolland, Chloe; Gustafson, Laura; Xiao, Tete; Whitehead, Spencer; Berg, Alexander C.; Lo, Wan-Yen; Dollar, Piotr; Girshick, Ross (2023). ["Segment Anything"](https://openaccess.thecvf.com/content/ICCV2023/html/Kirillov_Segment_Anything_ICCV_2023_paper.html): 4015–4026. `{{cite journal}}`: Cite journal requires `|journal=` ([help](./Help:CS1_errors#missing_periodical))
53. [↑](./Vision_transformer#cite_ref-54) Jiang, Yifan; Chang, Shiyu; Wang, Zhangyang (2021). ["TransGAN: Two Pure Transformers Can Make One Strong GAN, and That Can Scale Up"](https://proceedings.neurips.cc/paper_files/paper/2021/hash/7c220a2091c26a7f5e9f1cfb099511e3-Abstract.html). *Advances in Neural Information Processing Systems*. **34**. Curran Associates, Inc.: 14745–14758. [arXiv](./ArXiv_(identifier)):[2102.07074](https://arxiv.org/abs/2102.07074).
54. [↑](./Vision_transformer#cite_ref-55) Peebles, William; Xie, Saining (March 2023). "Scalable Diffusion Models with Transformers". [arXiv](./ArXiv_(identifier)):[2212.09748v2](https://arxiv.org/abs/2212.09748v2) [[cs.CV](https://arxiv.org/archive/cs.CV)].
55. [↑](./Vision_transformer#cite_ref-56) Doron, Michael; Moutakanni, Théo; Chen, Zitong S.; Moshkov, Nikita; Caron, Mathilde; Touvron, Hugo; Bojanowski, Piotr; Pernice, Wolfgang M.; Caicedo, Juan C. (2023-06-18). "Unbiased single-cell morphology with self-supervised vision transformers". [bioRxiv](./BioRxiv_(identifier)) [10.1101/2023.06.16.545359](https://doi.org/10.1101%2F2023.06.16.545359).
56. [↑](./Vision_transformer#cite_ref-57) Wang, Xiao; Liu, Siyan; Tsaris, Aristeidis; Choi, Jong-Youl; Aji, Ashwin; Fan, Ming; Zhang, Wei; Yin, Junqi; Ashfaq, Moetasim; Lu, Dan; Balaprakash, Prasanna (2024). "ORBIT: Oak Ridge Base Foundation Model for Earth System Predictability". [arXiv](./ArXiv_(identifier)):[2404.14712](https://arxiv.org/abs/2404.14712) [[physics.ao-ph](https://arxiv.org/archive/physics.ao-ph)].

 

## Further reading

 
- Zhang, Aston; Lipton, Zachary; Li, Mu; Smola, Alexander J. (2024). ["11.8. Transformers for Vision"](https://d2l.ai/chapter_attention-mechanisms-and-transformers/vision-transformer.html). *Dive into deep learning*. Cambridge New York Port Melbourne New Delhi Singapore: Cambridge University Press. [ISBN](./ISBN_(identifier)) [978-1-009-38943-3](./Special:BookSources/978-1-009-38943-3).
- Steiner, Andreas; Kolesnikov, Alexander; Zhai, Xiaohua; Wightman, Ross; Uszkoreit, Jakob; Beyer, Lucas (June 18, 2021). "How to train your ViT? Data, Augmentation, and Regularization in Vision Transformers". [arXiv](./ArXiv_(identifier)):[2106.10270](https://arxiv.org/abs/2106.10270) [[cs.CV](https://arxiv.org/archive/cs.CV)].

 
| vteGenerative AI |
| --- |
| Concepts | AutoencoderDeep learningFine-tuningFoundation modelGenerative adversarial networkGenerative pre-trained transformerLarge language modelModel Context ProtocolNeural networkPrompt engineeringReinforcement learning from human feedbackRetrieval-augmented generationSelf-supervised learningStochastic parrotSynthetic dataTop-p samplingTransformerVariational autoencoderVibe codingVision transformerWord embedding |
| Models | TextAmazon NovaCharacter.aiClaudeCommandDeepSeekDoubaoErnieEXAONEGeminiGemmaGLMGPTChatGPTGrokIBM GraniteKimiMAIMicrosoft CopilotMistralMiniMaxMuse SparkNemotronPerplexitySolarPoeHKChatQwenTencent HyXiaomi MiMoYou.comImageAdobe FireflyFluxGPT ImageIdeogramMidjourneyNano BananaRecraftSeedreamStable DiffusionVideoDream MachineGenieworld modelHailuo AIKling AILTXRunway GenSeedanceSoraVeoSpeech15.aiElevenGemini SpeechMiniMax SpeechMusicEleven MusicEndelMiniMax MusicRiffusionSunoUdio | Text | Amazon NovaCharacter.aiClaudeCommandDeepSeekDoubaoErnieEXAONEGeminiGemmaGLMGPTChatGPTGrokIBM GraniteKimiMAIMicrosoft CopilotMistralMiniMaxMuse SparkNemotronPerplexitySolarPoeHKChatQwenTencent HyXiaomi MiMoYou.com | Image | Adobe FireflyFluxGPT ImageIdeogramMidjourneyNano BananaRecraftSeedreamStable Diffusion | Video | Dream MachineGenieworld modelHailuo AIKling AILTXRunway GenSeedanceSoraVeo | Speech | 15.aiElevenGemini SpeechMiniMax Speech | Music | Eleven MusicEndelMiniMax MusicRiffusionSunoUdio |
| Text | Amazon NovaCharacter.aiClaudeCommandDeepSeekDoubaoErnieEXAONEGeminiGemmaGLMGPTChatGPTGrokIBM GraniteKimiMAIMicrosoft CopilotMistralMiniMaxMuse SparkNemotronPerplexitySolarPoeHKChatQwenTencent HyXiaomi MiMoYou.com |
| Image | Adobe FireflyFluxGPT ImageIdeogramMidjourneyNano BananaRecraftSeedreamStable Diffusion |
| Video | Dream MachineGenieworld modelHailuo AIKling AILTXRunway GenSeedanceSoraVeo |
| Speech | 15.aiElevenGemini SpeechMiniMax Speech |
| Music | Eleven MusicEndelMiniMax MusicRiffusionSunoUdio |
| Products | Coding toolsClaude CodeCodexCursorDevin AIGitHub CopilotGoogle AntigravityReplitAgentsAutoGPTChatGPT agentClaude CoworkGemini SparkManusMiniMax AgentOpenClaw | Coding tools | Claude CodeCodexCursorDevin AIGitHub CopilotGoogle AntigravityReplit | Agents | AutoGPTChatGPT agentClaude CoworkGemini SparkManusMiniMax AgentOpenClaw |
| Coding tools | Claude CodeCodexCursorDevin AIGitHub CopilotGoogle AntigravityReplit |
| Agents | AutoGPTChatGPT agentClaude CoworkGemini SparkManusMiniMax AgentOpenClaw |
| Applications | DeepfakeaudioSlopslopaganda |
| Companies | Aleph AlphaAnthropicAnysphereBaichuanCanvaCognition AICohereContextual AIDeepSeekDeepLEleutherAIElevenLabsGoogleAIDeepMindHeyGenHugging FaceInflection AIKuaishouLightricksLovableLuma LabsMeta AIMeta Superintelligence LabsMicrosoft AIMiniMaxMistral AIMoonshot AIOpenAIPerplexity AIRunwaySafe SuperintelligenceSakana AISalesforceScale AISoundHound AISpaceXAIStability AIStepFunSynthesiaThinking Machines LabUpstageXiaomiZ.ai |
| Controversies | Generative AI pornographyDeepfake pornographyon Grokof Taylor SwiftPause Giant AI ExperimentsRemoval of Sam Altman from OpenAIStatement on AI RiskTay (chatbot)Théâtre D'opéra SpatialVoiceverse NFT plagiarism |
| CategoryCommons |

 
| vteArtificial intelligence(AI) |
| --- |
| HistorytimelineGlossaryCompaniesProjectsList of open-source AI software |
| Concepts | Automated reasoningParameterHyperparameterLoss functionsRegressionBias–variance tradeoffDouble descentOverfittingClusteringGradient descentSGDQuasi-Newton methodConjugate gradient methodBackpropagationAttentionConvolutionNormalizationBatchnormActivationSoftmaxSigmoidRectifierGatingWeight initializationRegularizationDatasetsAugmentationPrompt engineeringReinforcement learningQ-learningSARSAImitationPolicy gradientDiffusionLatent diffusion modelAutoregressionAdversaryRAGUncanny valleyRLHFSelf-supervised learningReflectionRecursive self-improvementHallucinationWord embeddingVibe codingSymbolic AINeuro-symbolic AI |
| Applications | Automated theorem provingMachine learningIn-context learningArtificial neural networkDeep learningLanguage modelLargeNMTReasoningModel Context ProtocolIntelligent agentAI agentArtificial human companionHumanity's Last ExamLethal autonomous weapons (LAWs)Generative AIWeak AIHypotheticalArtificial general intelligence (AGI)Artificial superintelligence (ASI)Agent2Agent protocol |
| Implementations | Audio–visualAlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasisTextList of large language modelsProject DebaterIBM WatsonIBM WatsonxDecisionalAlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot controlReasoning systemsDeductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systemsCognitive architecturesACT-RSoarCLARIONLIDAOpenCogKnowledge basesConceptNetWikidataDBpediaYAGO | Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis | Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx | Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control | Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems | Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog | Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| Audio–visual | AlexNetWaveNetHuman image synthesisHWROCRComputer visionSpeech synthesis15.aiElevenLabsSpeech recognitionWhisperFacial recognitionAlphaFoldText-to-image modelsAuroraDALL-EFireflyFluxGPT ImageIdeogramImagenMidjourneyRecraftStable DiffusionText-to-video modelsDream MachineRunway GenHailuo AIKlingSoraSeedanceVeoMusic generationRiffusionSunoUdioWorld modelsGenieOasis |
| Text | List of large language modelsProject DebaterIBM WatsonIBM Watsonx |
| Decisional | AlphaGoAlphaZeroOpenAI FiveSelf-driving carMuZeroAction selectionAutoGPTRobot control |
| Reasoning systems | Deductive classifiersExpert systemsInference enginesKnowledge-based systemsLogic programsProcedural reasoning systemsSemantic reasonersRule-based systems |
| Cognitive architectures | ACT-RSoarCLARIONLIDAOpenCog |
| Knowledge bases | ConceptNetWikidataDBpediaYAGO |
| People | Alan TuringWarren Sturgis McCullochWalter PittsJohn von NeumannChristopher D. ManningClaude ShannonShun'ichi AmariKunihiko FukushimaTakeo KanadeMarvin MinskyJohn McCarthyNathaniel RochesterAllen NewellCliff ShawHerbert A. SimonOliver SelfridgeFrank RosenblattBernard WidrowJoseph WeizenbaumSeymour PapertSeppo LinnainmaaPaul WerbosGeoffrey HintonJohn HopfieldJürgen SchmidhuberYann LeCunYoshua BengioLotfi A. ZadehStephen GrossbergAlex GravesJames GoodnightAndrew NgFei-Fei LiAlex KrizhevskyIlya SutskeverOriol VinyalsQuoc V. LeIan GoodfellowDemis HassabisDavid SilverAndrej KarpathyAshish VaswaniNoam ShazeerAidan GomezJohn SchulmanMustafa SuleymanJan LeikeDaniel KokotajloFrançois Chollet |
| Neural network architectures | Neural Turing machineDifferentiable neural computerTransformerVision transformer (ViT)Recurrent neural network (RNN)Long short-term memory (LSTM)Gated recurrent unit (GRU)Echo state networkMultilayer perceptron (MLP)Convolutional neural network (CNN)Residual neural network (RNN)Highway networkMambaAutoencoderVariational autoencoder (VAE)Generative adversarial network (GAN)Graph neural network (GNN) |
| Political | AI Cold WarAI safety(Alignment)AI takeoverElectionsEthics of AIEUAI ActNationalismPrecautionary principleRegulation of AIUSVirtual politicianPropaganda |
| Social and economic | AI boomAI bubbleAI data centerAI effectAI literacyAI slopAI veganismAI winterAnthropomorphismArms raceCompetitionEnvironmental impactExplainable AIGenerative engine optimizationIn architectureIn educationIn fictionIn healthcareChatbot psychosisIn marketingIn video gamesIn visual artMilitary applicationsAI warfareWorkplace impact |
| Category |