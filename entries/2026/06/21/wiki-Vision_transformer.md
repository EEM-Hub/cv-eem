---
source: sources/wiki-Vision_transformer.md
source_url: https://en.wikipedia.org/wiki/Vision_transformer
---

## Vision Transformer (ViT) Architecture and Variants

The Vision Transformer (ViT) adapts the transformer architecture from NLP to computer vision by decomposing images into fixed-size patches, projecting them into embeddings, and processing them through a standard transformer encoder. Introduced in 2020, ViTs challenged the dominance of CNNs in image classification and have since spawned numerous variants for tasks including segmentation, video understanding, and medical imaging.

## Key Concepts

- **Patch embedding**: An input image (H x W x C) is split into fixed-size square patches (P x P x C), each linearly projected into a vector. Positional encodings are added before feeding into the transformer encoder.
- **Encoder-only architecture**: ViT uses a BERT-like encoder-only transformer, not the full encoder-decoder structure.
- **`<CLS>` token**: A special classification token prepended to the patch sequence; its output vector is fed to the classification head (MLP). This is an architectural hack borrowed from BERT.
- **Inductive bias difference**: ViTs lack the built-in spatial locality and translation equivariance of CNNs. They are less data-efficient but have higher model capacity.
- **Quadratic cost mitigation**: Self-attention is computed over patches (e.g., 16x16 pixels) rather than individual pixels, drastically reducing the O(n^2) cost.
- **Pooling strategies**: Three approaches for converting output embeddings to classification — CLS token pooling (original), Global Average Pooling (GAP), and Multihead Attention Pooling (MAP). GAP and MAP outperform CLS pooling.
- **Masked Autoencoder (MAE)**: Self-supervised ViT training by masking 75% of patches and reconstructing them. Only unmasked patches are processed by the encoder, improving efficiency. Decoder is discarded at inference.
- **DINO**: Self-supervised teacher-student self-distillation. Teacher is an exponential moving average of the student. Uses sharpening (low-temperature softmax) and centering to prevent representation collapse.
- **DINOv2/v3**: Successive improvements — DINOv2 improved transferability; DINOv3 (Aug 2025) added image-text alignment (like CLIP), scaled to 7B parameters/1.7B images, introduced Gram anchoring (fixes dense feature map degradation) and axial RoPE with jittering.
- **Swin Transformer**: Uses shifted-window self-attention (local, not global) with hierarchical merging layers (analogous to CNN pooling). Achieved SOTA on object detection (COCO).
- **TimeSformer**: Factorized attention for video — alternates spatial attention (within one frame) and temporal attention (same patch across frames).
- **ViT-VQGAN**: Combines ViT with vector quantization and adversarial training for image tokenization. Enables autoregressive image generation (basis of Google Parti).

## Commands and Syntax

No CLI commands — this is a model architecture topic. Key architectural parameters:

- **Input**: Image of shape R^(H x W x C)
- **Patches**: Split into P x P x C patches; typical patch sizes are 16x16 or 32x32 (larger than CNN kernels of 3x3 to 7x7)
- **Position encoding**: 1D learned embeddings (adopted over 2D or relative alternatives)
- **Classification head**: Linear -> GeLU -> Linear -> Softmax
- **MAE mask ratio**: 75% optimal for ImageNet-1K (both fine-tuning and linear probing)
- **SiamMAE mask ratio**: ~95% for video frame prediction
- **Swin merge operation**: Concatenate 2x2 neighboring tokens, then multiply by a matrix (analogous to 2x2 pooling with stride 2)

## Relationships

- **Transformers (NLP origin)**: ViT directly adapts the encoder-only transformer from "Attention Is All You Need" (2017) and BERT
- **CNNs**: ViTs were designed as alternatives to CNNs (ResNet, EfficientNet, etc.); hybrid architectures combine both (e.g., CNN preprocessor + ViT, Swin Transformer's local windows)
- **BERT**: ViT mirrors BERT's architecture — encoder-only, CLS token, masked pretraining (MAE parallels masked language modeling)
- **CLIP**: DINOv3 incorporates image-text alignment similar to CLIP's contrastive learning
- **GANs/VAEs**: ViT-VQGAN combines ViT with VQVAE and GAN discriminators for image generation
- **Self-supervised learning**: MAE and DINO are the two primary self-supervised paradigms for ViTs
- **Knowledge distillation**: DINO is a self-distillation method; DeiT uses distillation from CNN teachers
- **Image generation**: ViT-VQGAN enables autoregressive generation (Google Parti)

## Exam-Relevant Points

- ViTs split images into **patches** (not pixels) to make self-attention computationally feasible
- The original ViT is an **encoder-only** transformer (like BERT), not encoder-decoder
- ViTs are **less data-efficient** than CNNs but have **higher capacity** — largest models reach 22B parameters
- **1D positional embeddings** were adopted over 2D or relative alternatives in the original paper
- MAE uses **75% masking** and processes **only unmasked patches** during training (efficiency gain)
- MAE discards the decoder entirely at inference time
- DINO prevents collapse through **sharpening** (low-temperature softmax) and **centering** (running average of outputs)
- DINO's teacher network is an **exponential moving average** of the student — not a separate model
- Swin Transformer uses **local shifted-window attention** (not global), making it more CNN-like and efficient for dense prediction tasks like object detection
- GAP and MAP pooling **outperform** the original CLS token approach
- TimeSformer uses **factorized space-time attention** — alternating spatial and temporal attention layers
- DINOv3 solved the problem where **dense task performance degraded** even as global task performance improved, via **Gram anchoring**
- Cross-fertilization: ViT and MAE **stimulated new CNN developments** (ConvNeXt etc.)
- Swin Transformer achieved SOTA on **COCO object detection**, not just classification
- ViT-VQGAN tokenizes images into discrete symbols, enabling **autoregressive image generation** via standard GPT-style transformers
