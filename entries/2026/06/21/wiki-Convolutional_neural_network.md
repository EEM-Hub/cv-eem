---
source: sources/wiki-Convolutional_neural_network.md
source_url: https://en.wikipedia.org/wiki/Convolutional_neural_network
---

## Convolutional Neural Networks (CNNs): Architecture, Operations, and Applications

Convolutional neural networks are a class of feedforward neural networks that learn spatial features through filter/kernel optimization rather than full connectivity. They are the foundational architecture for deep learning-based computer vision and image processing, though increasingly supplemented or replaced by transformers in some tasks. CNNs achieve parameter efficiency through weight sharing across spatial locations, enabling deeper networks that avoid vanishing/exploding gradient problems inherent in fully connected architectures.

## Key Concepts

- **Core principle**: CNNs replace full connectivity with local receptive fields and shared weights — a 100x100 image needs 10,000 weights per neuron in a fully connected layer but only 25 weights per 5x5 convolutional kernel
- **Shift/space invariance**: Shared-weight convolution kernels slide along input features, producing translation-equivariant feature maps; however, most CNNs are **not** truly translation-invariant due to downsampling operations
- **Convolution vs. correlation**: Modern CNN implementations actually perform correlation and call it convolution — mathematically equivalent for learned weights since weight reversal doesn't affect the final learned function
- **Input tensor shape**: (batch) x (height) x (width) x (channels); output after convolution is a feature map with shape (batch) x (map height) x (map width) x (map channels)
- **Biological inspiration**: Architecture mirrors the visual cortex — simple cells respond to edges in small receptive fields, complex cells have larger fields insensitive to exact edge position (Hubel & Wiesel, 1950s-60s)
- **Regularization through architecture**: Weight sharing inherently regularizes, reducing overfitting compared to fully connected networks; additional techniques include weight decay, dropout, skip connections
- **Higher-layer features** are extracted from progressively wider context windows compared to lower layers

## Layer Types

- **Convolutional layers**: Apply learned kernels (dot product / Frobenius inner product) across input, typically with ReLU activation; each neuron processes only its receptive field
- **Depthwise separable convolution**: Spatial convolution applied independently per channel (depthwise), followed by 1x1 convolution (pointwise) — reduces computation
- **Pooling layers**: Reduce spatial dimensions by combining neuron clusters; **max pooling** (takes maximum value) and **average pooling** (takes mean) are most common; local pooling uses small tiles (e.g., 2x2), global pooling acts on entire feature map
- **Fully connected layers**: Traditional MLP layers connecting every neuron; typically at the end for classification after flattening
- **Deconvolutional layers** (transpose convolution): Reverse of convolution — multiplication by the transpose matrix; used in image generators; prone to checkerboard artifacts (fix: upscale-then-convolve)
- **Unpooling layers**: Expand spatial dimensions (e.g., 2x2 unpooling copies each entry into a 2x2 block)

## Receptive Field

- Each neuron in a convolutional layer receives input from a restricted area of the previous layer
- Effective receptive field grows with network depth as convolutions compound
- **Dilated/atrous convolution**: Expands receptive field without increasing parameters by interleaving visible and blind regions; can use multiple dilation ratios in a single layer for variable receptive field size

## Commands and Syntax

Typical CNN layer specification (PyTorch-style pseudocode):
```python
# Convolutional layer
nn.Conv2d(in_channels, out_channels, kernel_size=5, stride=1, padding=0)

# Depthwise separable convolution
nn.Conv2d(in_channels, in_channels, kernel_size=3, groups=in_channels)  # depthwise
nn.Conv2d(in_channels, out_channels, kernel_size=1)  # pointwise

# Pooling
nn.MaxPool2d(kernel_size=2, stride=2)
nn.AvgPool2d(kernel_size=2, stride=2)

# Transpose convolution (deconvolution)
nn.ConvTranspose2d(in_channels, out_channels, kernel_size=2, stride=2)
```

## Relationships

- **Feedforward neural networks**: CNNs are a specialized subtype with local connectivity and weight sharing
- **Transformers / Vision Transformers (ViT)**: Increasingly replacing CNNs in some vision tasks; CNNs retain advantages for smaller datasets and when inductive bias for spatial locality is beneficial
- **Backpropagation**: Primary training method for CNNs since LeCun et al. (1989)
- **GPU computing**: CNNs' practical breakthrough depended on GPU acceleration (first GPU CNN implementation: Chellapilla et al., 2006; AlexNet on GPU: 2012)
- **Image segmentation (U-Net, FCN)**: Use encoder-decoder architectures with deconvolutional/upsampling layers
- **Landmark architectures**: LeNet (1995) → AlexNet (2012) → deeper networks; each advanced the field through architectural innovations

## Historical Timeline

| Year | Milestone |
|------|-----------|
| 1969 | Fukushima introduces multilayer feature detection + ReLU activation |
| 1980 | Neocognitron — first trainable CNN architecture (S-layers + C-layers) |
| 1987 | TDNN (Waibel) — first CNN with weight sharing + gradient descent training |
| 1988 | Zhang et al. — shift-invariant neural network trained with backprop |
| 1989 | LeCun et al. — backprop-trained CNN for handwritten digit recognition |
| 1990 | Max pooling introduced (Yamaguchi et al.) |
| 1995 | LeNet-5 — 7-layer CNN for check reading, deployed in US banks |
| 2006 | First GPU-implemented CNN (4x faster than CPU) |
| 2012 | AlexNet — GPU-trained deep CNN wins ImageNet, triggers deep learning revolution |

## Exam-Relevant Points

- A CNN's parameter efficiency comes from **weight sharing** — the same filter is applied across all spatial locations, drastically reducing parameters vs. fully connected layers
- **Max pooling** selects the maximum value in a region; **average pooling** computes the mean — max pooling is more commonly used in modern architectures
- CNNs produce **translation-equivariant** feature maps but are generally **not translation-invariant** due to downsampling
- The **receptive field** grows deeper in the network; dilated convolutions expand it without adding parameters
- **Depthwise separable convolution** = depthwise (per-channel spatial) + pointwise (1x1 cross-channel) — used to reduce computational cost
- **Deconvolution** (transpose convolution) is the transpose of a convolutional layer's matrix and can produce **checkerboard artifacts**
- LeNet-5 (1995) processed 32x32 pixel images; scaling to higher resolution required more layers and compute
- The neocognitron (1980) introduced the two fundamental layer types: convolutional (S-layer) and downsampling/pooling (C-layer)
- CNNs require **less preprocessing** than traditional image classification — filters are learned automatically rather than hand-engineered
- Applications span: image/video recognition, image classification, image segmentation, medical imaging, NLP, recommender systems, brain-computer interfaces, financial time series
