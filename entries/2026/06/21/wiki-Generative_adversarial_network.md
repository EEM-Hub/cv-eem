---
source: sources/wiki-Generative_adversarial_network.md
source_url: https://en.wikipedia.org/wiki/Generative_adversarial_network
---

## Generative Adversarial Networks (GANs)

GANs are a class of deep learning frameworks where two neural networks — a generator and a discriminator — compete in a zero-sum game. Introduced by Ian Goodfellow et al. in 2014, the generator learns to produce synthetic data matching the statistics of a training set, while the discriminator learns to distinguish real data from generated data. Originally proposed for unsupervised learning, GANs have been applied across supervised, semi-supervised, and reinforcement learning settings.

## Key Concepts

- **Two-player zero-sum game**: The generator minimizes and the discriminator maximizes the same objective function L(G, D).
- **Generator**: Maps from a latent space (random noise, typically Gaussian or uniform) to the data space via a learned function G. In image generation, typically a deconvolutional neural network.
- **Discriminator**: Classifies inputs as real (from training data) or fake (from generator). In image generation, typically a convolutional neural network. Outputs a value in [0, 1].
- **Indirect training**: The generator is not trained to minimize distance to specific images but to fool the discriminator, enabling unsupervised learning.
- **Implicit generative model**: GANs do not explicitly model the likelihood function, unlike flow-based models or VAEs. They cannot find the latent variable for a given sample.
- **Pushforward measure**: In practice, the generator distribution is implemented as a pushforward — sample z from a simple distribution, then apply G(z).
- **Reparameterization trick**: The decomposition of the generator distribution into a simple prior composed with a learned mapping; independently developed alongside VAEs by Kingma & Welling.
- **Jensen-Shannon divergence**: The optimal discriminator effectively computes the JS divergence between the real and generated distributions. The objective at optimal D* equals 2·D_JS(μ_ref; μ_G) − 2·ln2.
- **Optimal discriminator**: For any fixed generator, the optimal discriminator is deterministic: D*(x) = dμ_ref / d(μ_ref + μ_G), the Radon-Nikodym derivative.
- **Asymptotic consistency**: Since neural networks are universal approximators, GANs are asymptotically consistent.
- **Single-pass generation**: Unlike autoregressive models (WaveNet, PixelRNN), GANs generate a complete sample in one forward pass.

## Commands and Syntax

The GAN objective function:

```
L(G, D) = E_{x ~ μ_ref}[ln D(x)] + E_{z ~ μ_Z}[ln(1 - D(G(z)))]
```

Training procedure:
1. Train discriminator on real samples from training set until acceptable accuracy
2. Seed generator with random input sampled from latent space (e.g., multivariate normal)
3. Generator produces candidates; discriminator evaluates them
4. Apply independent backpropagation to both networks alternately
5. Generator improves sample quality; discriminator improves detection

Minimax formulation:

```
min_G max_D L(G, D)
```

## Relationships

- **Variational Autoencoders (VAEs)**: Share the reparameterization trick; VAEs explicitly model likelihood while GANs do not. VAEs may not be proven universal approximators.
- **Flow-based generative models**: Explicit generative models that provide invertible mappings, unlike GANs.
- **Autoregressive models** (WaveNet, PixelRNN): Require multiple sequential passes vs. GAN's single-pass generation.
- **Boltzmann machines**: Restrict function types used by the network; GANs have no such restriction.
- **Diffusion models**: Alternative deep generative framework (listed alongside GANs in neural network taxonomy).
- **Game theory**: GAN training is formalized as a minimax game; equilibrium analysis uses Nash equilibrium concepts and the minimax theorem.
- **Convolutional neural networks**: Used as discriminator architecture for image tasks.
- **Deconvolutional neural networks**: Used as generator architecture for image tasks.

## Exam-Relevant Points

- GANs were introduced by **Ian Goodfellow et al. in June 2014**.
- The GAN game is a **zero-sum game** between generator (minimizes) and discriminator (maximizes).
- The optimal discriminator computes the **Jensen-Shannon divergence** between real and generated distributions.
- GANs are **implicit generative models** — they do not explicitly model likelihood and cannot invert (find latent code for a given sample).
- The generator uses a **pushforward measure**: sample from simple distribution, transform through learned function G.
- The **minimax theorem** applies only when strategy sets are finitely spanned; in general GANs, different equilibrium concepts (generator-first, discriminator-first, Nash) may not agree.
- For the **original GAN game**, all three equilibrium types exist and are equal.
- GANs are **asymptotically consistent** due to the universal approximation theorem for neural networks.
- Key advantage over autoregressive models: **single-pass generation** of complete samples.
- Key advantage over Boltzmann machines: **no restriction on function type** in the network.
- The reparameterization trick was independently developed for GANs and for VAEs (Kingma & Welling, Rezende et al.).
- GANs apply to **unsupervised, semi-supervised, supervised, and reinforcement learning**.
- The discriminator's optimal strategy is always **deterministic** (proven via Jensen's inequality).
