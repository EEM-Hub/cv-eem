---
source: sources/wiki-Diffusion_model.md
source_url: https://en.wikipedia.org/wiki/Diffusion_model
---

## Diffusion Models for Generative Modeling

Diffusion models are a class of latent variable generative models that learn to generate new data by modeling a diffusion process. They work in two phases: a forward process that gradually adds Gaussian noise to data until it becomes pure noise, and a learned reverse process that iteratively denoises random noise back into realistic samples. Originally introduced in 2015 using non-equilibrium thermodynamics, they became practically effective with the DDPM paper (2020) and are now the backbone of major image generation systems like Stable Diffusion and DALL-E.

## Key Concepts

- **Forward diffusion process**: Iteratively adds Gaussian noise to data x₀ over T steps using a fixed noise schedule β₁,...,βT ∈ (0,1), producing increasingly noisy versions x₁,...,xT until xT ≈ N(0,I)
- **Reverse/backward diffusion process**: A neural network learns to undo each noise step, parameterizing p_θ(x_{t-1}|x_t) as a Gaussian with learned mean μ_θ and covariance Σ_θ
- **Noise schedule**: The sequence of β_t values controls how quickly data is corrupted; α_t = 1 - β_t and ᾱ_t = α₁···α_t are cumulative products
- **Reparameterization trick**: x_t can be sampled directly from x₀ in one step: x_t|x₀ ~ N(√ᾱ_t · x₀, σ_t² I), avoiding sequential computation during training
- **DDPM (Denoising Diffusion Probabilistic Model)**: The 2020 formulation that made diffusion models practical, trained via variational inference
- **Score-based formulation**: Equivalent formalism where the model learns the score function ∇_x log p(x) — the gradient of the log probability density
- **Backbone architecture**: The denoising network is typically a U-Net or Transformer
- **Non-equilibrium thermodynamics origin**: The data distribution is "out of equilibrium" and diffuses toward the equilibrium Gaussian N(0,I), analogous to particles diffusing in a potential well V(x) = ½‖x‖²
- **Equivalent formalisms**: Markov chains, denoising diffusion probabilistic models, noise-conditioned score networks, and stochastic differential equations (SDEs)
- **Posterior distribution**: The reverse conditional q(x_{t-1}|x_t, x₀) is tractable and Gaussian with known mean μ̃_t and variance σ̃_t², which serves as the training target

## Commands and Syntax

No CLI commands — this is a mathematical/theoretical topic. Key formulas:

- **Forward step**: x_t = √(1-β_t) · x_{t-1} + √β_t · z_t where z_t ~ N(0,I)
- **Direct sampling**: x_t = √ᾱ_t · x₀ + σ_t · ε where ε ~ N(0,I)
- **Reverse step**: x_{t-1} ~ N(μ_θ(x_t, t), Σ_θ(x_t, t))
- **Posterior mean**: μ̃_t(x_t, x₀) = [√α_t(1-ᾱ_{t-1})x_t + √ᾱ_{t-1}(1-α_t)x₀] / σ_t²
- **Training objective (simplified)**: Predict the noise ε added at each step; loss = ‖ε - ε_θ(x_t, t)‖²
- **Variational bound**: Training uses the ELBO, decomposed into per-timestep KL divergence terms between q(x_{t-1}|x_t,x₀) and p_θ(x_{t-1}|x_t)

## Relationships

- **Variational autoencoders (VAEs)**: Diffusion models can be viewed as a hierarchical VAE with T latent layers, but with a fixed (non-learned) encoder
- **Score matching / Langevin dynamics**: Score-based models learn ∇_x log p(x) and generate via Langevin MCMC; shown equivalent to DDPM
- **Stochastic differential equations**: Continuous-time generalization (Song et al.) unifies DDPM and score-based approaches under a single SDE framework
- **GANs**: Diffusion models achieve comparable or superior image quality without adversarial training instabilities
- **U-Net / Transformer**: Standard backbone architectures for the denoising network
- **Text encoders + cross-attention**: Combined with diffusion for text-conditioned generation (DALL-E, Stable Diffusion)
- **Non-equilibrium thermodynamics**: Theoretical foundation — forward process is physical diffusion, reverse process is learned
- **Gaussian processes**: The full forward trajectory x_{1:T}|x₀ forms a Gaussian process, enabling reparameterization
- **Computer vision tasks**: Primary application domain — image generation, denoising, inpainting, super-resolution, video generation
- **Discrete diffusion models**: Extension of the continuous framework to discrete/categorical data

## Exam-Relevant Points

- The forward process requires **no learning** — it is a fixed Markov chain defined by the noise schedule β_t
- The key reparameterization: x_t can be computed directly from x₀ without iterating through intermediate steps, using x_t = √ᾱ_t · x₀ + σ_t · ε
- The reverse posterior q(x_{t-1}|x_t, x₀) is **tractable** (closed-form Gaussian) — this is what makes training feasible
- DDPM was introduced in **2020** (Ho et al.); the original diffusion model concept dates to **2015** (Sohl-Dickstein et al.)
- The coefficients √(1-β_t) and √β_t in the forward step preserve unit variance: Var(X_t) = I if Var(X₀) = I
- Training uses **variational inference** — maximizing the evidence lower bound (ELBO)
- At convergence, x_T approaches the **standard Gaussian** N(0,I) regardless of the starting distribution (given finite second moment)
- The model learns to predict either: the **noise** ε added at each step, the **clean data** x₀, or the **score** ∇_x log p(x_t)
- Sampling is iterative (T reverse steps) and therefore **slower** than single-pass generators like GANs — this is the main computational drawback
- The connection to **Langevin dynamics**: reverse diffusion combines gradient descent (toward high-density regions) with random noise (to maintain distributional diversity — pure gradient descent collapses everything to the mode)
