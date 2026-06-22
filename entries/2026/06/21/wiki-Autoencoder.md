---
source: sources/wiki-Autoencoder.md
source_url: https://en.wikipedia.org/wiki/Autoencoder
---

## Autoencoders: Architecture, Training, and Variants

Autoencoders are unsupervised neural networks that learn compressed representations of data by training an encoder to map inputs to a lower-dimensional latent space and a decoder to reconstruct the original input. They are foundational to dimensionality reduction, feature learning, anomaly detection, and generative modeling, with variants (VAE, sparse, denoising, contractive) tailored to specific tasks.

## Key Concepts

- **Encoder-Decoder Architecture**: An encoder function E_φ maps input space X (R^m) to latent/code space Z (R^n); a decoder D_θ maps Z back to X. Typically m > n (undercomplete).
- **Latent Representation**: The intermediate code z = E_φ(x) is called the latent variable, latent vector, or code. It captures a compressed representation of the input.
- **Undercomplete vs. Overcomplete**: Undercomplete autoencoders have dim(Z) < dim(X), forcing compression. Overcomplete autoencoders have dim(Z) ≥ dim(X) and risk learning the identity function unless regularized — though experiments show they can still learn useful features.
- **Loss Function**: L(θ, φ) = E[d(x, D_θ(E_φ(x)))], where d is a reconstruction quality function. Most commonly, d is the L2 (mean squared error) loss.
- **Training**: Optimized via gradient descent to minimize reconstruction loss. The reference distribution is typically the empirical distribution of the training dataset.
- **Unsupervised Learning**: No labels required — the network learns to reconstruct its own input, discovering structure in the data as a byproduct.

## Commands and Syntax

- **One-layer MLP encoder**: E_φ(x) = σ(Wx + b), where σ is an activation function, W is a weight matrix, b is a bias vector.
- **Reconstruction loss (L2)**: L(θ, φ) = (1/N) Σ ||x_i − D_θ(E_φ(x_i))||²
- **Sparse autoencoder with regularization**: min L(θ, φ) + λ · L_sparse(θ, φ), where λ controls sparsity strength.
- **k-sparse function**: f_k(x_1,...,x_n) = (x_1·b_1,...,x_n·b_n), where b_i = 1 if |x_i| is in the top-k activations, 0 otherwise. Backpropagation zeroes gradients for inactive units.
- **KL divergence sparsity loss**: s(ρ, ρ̂) = ρ log(ρ/ρ̂) + (1−ρ) log((1−ρ)/(1−ρ̂))

## Relationships

- **Dimensionality Reduction**: Autoencoders perform a nonlinear generalization of PCA; related to factor analysis, ICA, NMF, and t-SNE.
- **Variational Autoencoders (VAEs)**: Combine autoencoder architecture with variational Bayesian methods; the latent space is a mixture of distributions (not fixed vectors), enabling generative modeling via p_θ(x) = ∫ p_θ(x,z) dz.
- **Sparse Coding / Neuroscience**: Sparse autoencoders are motivated by the sparse coding hypothesis in neuroscience — only a small subset of neurons fire for any given input.
- **Generative Models**: At the limit, an ideal undercomplete autoencoder's decoder can generate realistic samples by feeding arbitrary latent codes. VAEs formalize this capability.
- **Feature Learning**: Learned representations serve as input features for downstream classification, clustering, or regression tasks.
- **Regularization Techniques**: Sparse, denoising, and contractive autoencoders each add different constraints to prevent trivial solutions and encourage useful representations.

## Exam-Relevant Points

- An autoencoder consists of exactly two components: an **encoder** (input → latent code) and a **decoder** (latent code → reconstruction).
- **Undercomplete** = latent dimension < input dimension (forces compression); **overcomplete** = latent dimension ≥ input dimension (needs regularization to avoid identity mapping).
- The standard training objective is **reconstruction loss** (typically MSE/L2), optimized via gradient descent.
- **VAEs** differ fundamentally from standard autoencoders: they model the latent space as probability distributions (not fixed vectors) and belong to variational Bayesian methods.
- **Sparse autoencoders** enforce sparsity via either (a) hard k-sparse top-k selection or (b) soft sparsity regularization loss (KL divergence or L1/L2 penalty). They may have **more** hidden units than inputs.
- Sparsity regularization with KL divergence compares actual activation density ρ_k(x) against a desired sparsity ρ̂_k per layer.
- Applications span: facial recognition, feature detection, anomaly detection, word embeddings, and synthetic data generation.
- Autoencoders are **unsupervised** — they learn from unlabeled data by reconstructing their own input.
- The k-sparse autoencoder's backpropagation rule (zero gradient for inactive units) is a generalization of **ReLU**.
