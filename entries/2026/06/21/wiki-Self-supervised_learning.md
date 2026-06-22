---
source: sources/wiki-Self-supervised_learning.md
source_url: https://en.wikipedia.org/wiki/Self-supervised_learning
---

## Self-Supervised Learning (SSL) in Machine Learning

Self-supervised learning is a machine learning paradigm where models generate their own supervisory signals from unlabeled data, rather than relying on human-annotated labels. It sits between supervised and unsupervised learning: it pursues classification-like objectives but derives training signal from the structure of the data itself. SSL has become foundational for large-scale pretraining in vision, language, and audio.

## Key Concepts

- **Core idea**: The model creates its own labels by exploiting inherent structure, correlations, or metadata within the input data — no external annotation required.
- **Two-step training**: (1) Solve a pretext task using pseudo-labels to initialize model parameters; (2) Fine-tune on the actual downstream task using supervised or unsupervised learning.
- **Pseudo-labels**: Model-generated labels assigned to unlabeled data based on the model's own predictions. Also used for adapting to concept drift in dynamic environments.
- **Pretext tasks**: Auxiliary tasks designed so that solving them forces the model to learn useful feature representations (e.g., predicting rotation, filling masked patches).
- **Data augmentation**: Input is transformed (noise, cropping, rotation) to create related sample pairs that serve as implicit supervision.

### Four major SSL types:

- **Autoassociative SSL**: Train the model to reconstruct its own input (autoencoders). Encoder maps to latent space; decoder reconstructs. Loss = reconstruction error (e.g., MSE).
- **Contrastive SSL**: Uses both positive and negative example pairs. Loss minimizes distance between positive pairs and maximizes distance between negative pairs. Examples: CLIP, InfoNCE.
- **Non-contrastive SSL (NCSSL)**: Uses only positive examples. Avoids trivial collapse through architectural tricks (asymmetric predictor, stop-gradient on target branch). Examples: BYOL, DirectPred.
- **Joint-Embedding Predictive Architectures (JEPA)**: Operates in latent space rather than pixel space. Predicts masked latent representations from visible context. Avoids pixel-level noise to focus on semantic structure. Introduced by Yann LeCun (2022) as a path toward autonomous machine intelligence. Includes the concept of a "world model."

## Commands and Syntax

No CLI commands — this is a conceptual topic. Key mathematical formulation:

- **InfoNCE loss**: L_N = -E_X[log(f_k(x_{t+k}, c_t) / Σ_{x_j ∈ X} f_k(x_j, c_t))]
  - One positive sample from p(x_{t+k} | c_t), N-1 negative samples from proposal distribution p(x_{t+k})
  - Based on Noise Contrastive Estimation (NCE)

- **Autoencoder reconstruction loss**: Typically mean squared error between input and reconstructed output.

## Relationships

- **vs. Supervised learning**: SSL generates its own labels; supervised learning requires explicit human-annotated labels. SSL is a form of pretraining that often precedes supervised fine-tuning.
- **vs. Unsupervised learning**: Both avoid labels, but SSL creates explicit supervisory signal from data structure, while unsupervised learning discovers inherent data structures (clustering, density estimation).
- **vs. Semi-supervised learning**: Semi-supervised uses a small amount of labeled data plus unlabeled data. SSL uses no labels at all during pretraining.
- **Transfer learning**: SSL pretrained models are frequently used as feature extractors for downstream tasks via transfer learning.
- **Reinforcement learning**: SSL can create abstract compressed state representations in RL settings.
- **Autoencoders**: Autoencoder training is inherently self-supervised, but modern SSL jargon often refers specifically to pretext-task-based setups.
- **Contrastive learning → CLIP**: Bridges vision and language by jointly training image and text encoders with contrastive objectives.
- **JEPA → World models**: LeCun's architecture connects SSL to autonomous reasoning and planning.

## Exam-Relevant Points

- SSL uses the data itself to generate supervisory signals — no external labels needed.
- The two-step process: pretext task with pseudo-labels → downstream task with supervised/unsupervised learning.
- **Contrastive vs. non-contrastive**: Contrastive uses positive AND negative pairs; non-contrastive uses ONLY positive pairs but requires architectural asymmetry to avoid collapse.
- **JEPA operates in latent space**, not pixel space — this distinguishes it from autoencoders.
- **InfoNCE** is the key loss function for contrastive learning — know the structure (one positive, N-1 negatives, softmax-style ratio).
- **Barlow Twins and VICReg** are joint-embedding methods that enforce covariance constraints without negative sampling.
- Key real-world systems: wav2vec (speech, Facebook), BERT (search queries, Google), GPT-3 (language, OpenAI), BYOL (ImageNet, non-contrastive).
- Pseudo-labels serve dual purpose: SSL pretraining AND concept drift adaptation.
- SSL sits between supervised and unsupervised: has a classification-like objective but doesn't use external labels.
- Deep CCA is the foundational technique behind joint-embedding architectures.
