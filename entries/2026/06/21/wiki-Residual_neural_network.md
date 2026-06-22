---
source: sources/wiki-Residual_neural_network.md
source_url: https://en.wikipedia.org/wiki/Residual_neural_network
---

## Residual Neural Networks (ResNet): Architecture and Skip Connections

Residual Neural Networks (ResNets) are a deep learning architecture where layers learn residual functions with reference to their inputs, using skip connections of the form x → f(x) + x. Developed by Kaiming He et al. in 2015, ResNet won the ImageNet Large Scale Visual Recognition Challenge (ILSVRC 2015) and solved the degradation problem that prevented training of very deep networks. The residual connection motif has become foundational across deep learning, appearing in transformers (BERT, GPT), AlphaGo Zero, AlphaStar, and AlphaFold.

## Key Concepts

- **Residual connection**: the mapping x → f(x) + x, where f is an arbitrary neural network module — the network learns the *residual* (difference from identity) rather than the full transformation
- **Degradation problem**: stacking more layers in plain networks (e.g., VGGNet) paradoxically *increased* training error; not caused by vanishing gradients but by the optimizer's inability to learn identity mappings in parameterized layers
- **Skip connection / shortcut connection**: performs an identity mapping that adds the block's input directly to its output, enabling signal propagation across arbitrary depth
- **Projection connection**: when input and output dimensions differ (n ≠ m), a learned linear projection P(x) = Mx replaces the identity skip, where M is an m×n matrix trained via backpropagation
- **Vanishing gradient mitigation**: the gradient of loss w.r.t. a shallow layer always includes a direct additive term from deeper layers (∂E/∂x_ℓ includes ∂E/∂x_L), preventing gradient from vanishing entirely
- **Forward signal propagation**: x_L = x_ℓ + Σ F(x_i) for i=ℓ to L-1, meaning any deep layer always has a direct signal path from any shallower layer
- **Variance stabilization**: replacing x + f(x) with x/L + f(x), where L is total residual layers, stabilizes layer input variance
- **LSTM connection**: LSTM memory cells (c_{t+1} = c_t + F(x_t)) function as generalized residual connections; highway networks are LSTMs unfolded in time applied to feedforward nets; ResNet is equivalent to an open-gated highway network

## Residual Block Variants

- **Basic block**: two sequential 3×3 convolutional layers + residual connection; input and output dimensions are equal
- **Bottleneck block**: three convolutional layers (1×1 for dimension reduction → 3×3 convolution → 1×1 for dimension restoration) + residual connection; used in ResNet-50, ResNet-101, and ResNet-152
- **Pre-activation block**: applies activation/normalization *before* the residual function: x_{ℓ+1} = F(φ(x_ℓ)) + x_ℓ; reduces non-identity mappings between blocks; used to train 200–1000+ layer models; consistently outperforms post-activation variants; adopted by GPT-2 and subsequent transformers as "pre-normalization"

## Commands and Syntax

No CLI commands — this is an architecture description. Key architectural specifications:

| Model | Block Type | Depth | Notes |
|-------|-----------|-------|-------|
| ResNet-18 | Basic | 18 layers | Simplest standard variant |
| ResNet-50 | Bottleneck | 50 layers | Uses 1×1 conv for dimension reduction |
| ResNet-101 | Bottleneck | 101 layers | Deeper variant |
| ResNet-152 | Bottleneck | 152 layers | Deepest in original paper |
| Pre-act ResNet-200 | Pre-activation | 200 layers | 3 weeks on 8 GPUs (2016) |

## Relationships

- **Transformers**: all transformer architectures (BERT, GPT, Vision Transformers) use residual connections; very deep transformers cannot train without them; GPT-2 adopted pre-activation (pre-norm) residual blocks
- **LSTM / Highway Networks**: LSTM cell state is a generalized residual connection; highway networks applied LSTM-unfolded-in-time to feedforward nets; ResNet = open-gated highway network
- **VGGNet / AlexNet**: predecessors that demonstrated the degradation problem (VGG-19 at 19 layers, AlexNet at 8 layers)
- **DenseNet** (2016): extends skip connections so every layer connects to every subsequent layer
- **ResNeXt** (2017): combines Inception modules with ResNet
- **Squeeze-and-Excitation Networks** (2018): adds channel attention (SE modules) to ResNet; won ILSVRC 2017
- **Wide Residual Networks** (2016): more channels + fewer layers improves performance and GPU efficiency
- **Stochastic depth / DropPath**: regularization that randomly drops layers, letting signal flow through skip connections; used in Vision Transformers
- **Biological neural networks**: 2023 Science paper found "multilayer shortcuts" resembling skip connections in fruit fly larva connectome

## Exam-Relevant Points

- ResNet won ILSVRC 2015; developed by Kaiming He, Xiangyu Zhang, Shaoqing Ren, Jian Sun (Microsoft Research)
- The core formula is x → f(x) + x (identity shortcut) or x → F(x) + P(x) (projection shortcut when dimensions differ)
- The degradation problem is NOT the vanishing gradient problem — degradation is addressed by residual connections enabling identity mappings; vanishing gradients are addressed by normalization
- Bottleneck blocks (1×1 → 3×3 → 1×1) are used in ResNet-50/101/152; basic blocks (3×3 → 3×3) in shallower variants
- Pre-activation places BN/ReLU *before* the weight layers, not after — this is the design adopted by modern transformers as "pre-normalization"
- Gradient through residual blocks always has an additive identity term, preventing complete vanishing
- ResNet is mathematically equivalent to an open-gated highway network
- Prior art: skip connections date to Rosenblatt (1961), Lang & Witbrock (1988); LSTM residual connection dates to Hochreiter & Schmidhuber (1997)
- State of the art before ResNet was ~20-30 layers (2014); ResNet pushed to 152 layers in the original paper and 1000+ with pre-activation blocks
