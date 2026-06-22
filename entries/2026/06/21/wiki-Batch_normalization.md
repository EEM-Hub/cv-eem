---
source: sources/wiki-Batch_normalization.md
source_url: https://en.wikipedia.org/wiki/Batch_normalization
---

## Batch Normalization in Neural Networks

Batch normalization is a technique introduced by Ioffe and Szegedy (2015) that stabilizes and accelerates neural network training by normalizing each layer's inputs to zero mean and unit variance within each mini-batch, then applying learned scale (γ) and shift (β) parameters to restore representational capacity.

## Key Concepts

- **Internal covariate shift**: The phenomenon where the distribution of inputs to each layer changes during training as preceding layers' parameters update, forcing each layer to continually readjust. Batch norm was originally designed to address this, though recent research disputes this explanation.
- **Normalization step**: For each mini-batch of size *m*, compute per-dimension mean (μ_B) and variance (σ²_B), then normalize each input: x̂ = (x - μ_B) / √(σ²_B + ε), where ε is a small constant for numerical stability.
- **Affine transform**: After normalization, learned parameters γ (scale) and β (shift) are applied: y = γx̂ + β. This restores the network's ability to represent any function the original layer could, making normalization lossless in terms of representational power.
- **Training vs. inference difference**: During training, statistics are computed per mini-batch. During inference, population statistics (running mean/variance accumulated over training) replace batch statistics so output is deterministic and independent of other inputs in a batch.
- **Population variance uses Bessel's correction**: Var[x] = (m/(m-1)) · E_B[σ²_B], applying the unbiased variance estimator.
- **Non-iid concern**: Batch normalization makes items within a batch statistically dependent (no longer iid), which can degrade gradient estimation quality.

## Commands and Syntax

**Forward pass (training):**
1. Compute batch mean: μ_B = (1/m) Σ x_i
2. Compute batch variance: σ²_B = (1/m) Σ (x_i - μ_B)²
3. Normalize: x̂_i = (x_i - μ_B) / √(σ²_B + ε)
4. Scale and shift: y_i = γ · x̂_i + β

**Forward pass (inference):**
- y = γ · (x - E[x]) / √(Var[x] + ε) + β
- Uses accumulated population statistics; reduces to a linear transform.

**Backpropagation:**
- ∂l/∂γ = Σ (∂l/∂y_i) · x̂_i
- ∂l/∂β = Σ (∂l/∂y_i)
- Gradients w.r.t. input x_i involve terms from both the normalized output, the variance, and the mean (three-part chain rule through the batch statistics).

**Typical framework usage (PyTorch):**
```python
nn.BatchNorm2d(num_features)  # for conv layers (normalizes over N, H, W)
nn.BatchNorm1d(num_features)  # for fully connected layers (normalizes over N)
```

## Relationships

- **Residual networks / skip connections**: In very deep networks, batch norm can initially cause gradient explosion; skip connections (as in ResNets) mitigate this.
- **Dropout**: Batch norm provides a regularization effect that can reduce or eliminate the need for dropout.
- **Learning rate**: Networks with batch norm tolerate higher learning rates without vanishing/exploding gradients.
- **Other normalization methods**: Layer Normalization, Instance Normalization, and Group Normalization are alternatives that avoid batch-size dependence — important for small-batch or sequence-model settings.
- **Loss landscape smoothness (Lipschitz continuity)**: Theoretical work shows batch norm bounds gradient magnitudes and loss Hessian curvature, producing a smoother optimization landscape with more predictive gradients.
- **Activation functions**: The BN transform is applied before (or after) the activation function; placement affects training dynamics.

## Exam-Relevant Points

- Batch norm normalizes per-dimension across the mini-batch, not across dimensions within a single sample.
- The learnable parameters are γ (scale) and β (shift) — two parameters per normalized dimension.
- ε is added for numerical stability in the denominator, not for regularization.
- At inference time, batch norm uses **population statistics** (running averages from training), not the current batch's statistics — making inference deterministic.
- The population variance applies Bessel's correction (m/(m-1)).
- At inference, batch norm collapses to a fixed linear transform (no learnable update).
- The original "internal covariate shift" explanation is disputed; the smoothing/Lipschitz explanation has stronger empirical support (VGG-16 experiment with injected noise still showed improvement).
- Batch norm introduces inter-sample dependence within a batch, breaking the iid assumption.
- Batch norm enables higher learning rates, reduces sensitivity to initialization, and acts as a regularizer.
- In convolutional networks, batch norm shares statistics across spatial dimensions (H, W) but computes separately per channel.
