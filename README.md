# README: Procedural Latent Prompt Injection (PLPI)

Official implementation of the paper: **"Overcoming the Semantic Bottleneck for Deterministic Structural Control in Text-to-Image Synthesis"**

## Overview

This repository provides a training-free, zero-shot framework for deterministic structural control in Latent Diffusion Models (LDMs). By bypassing the semantic bottleneck of text encoders, **Procedural Latent Prompts**—structured mathematical tensors—are injected directly into the diffusion latent space.

### Key Contributions

* **Deterministic Control:** Ensures structural properties such as symmetry and alignment without reliance on probabilistic text prompts.
* **Plasticity Window Identification:** Optimizes interventions during the critical phase (timesteps 10–20) when the model is most responsive to control.
* **Hierarchical Injection:** Separates global composition (mid-block injection) from local textures (input-level injection).
* **High Efficiency:** Minimal inference overhead; no auxiliary networks or retraining required.

## Performance

PLPI demonstrates significant improvements over standard stochastic baselines:

* **+19.6%** in structural alignment (CLIP).
* **+12.3%** in diversity and variance regulation.
* Validated across medical, scientific, and artistic domains.

## Architecture

The framework models the diffusion process as a **steerable Stochastic Differential Equation (SDE)**.

### SDE Perturbation Mechanism

The latent state is updated via a linear mixing formula that preserves phase information:

* **xₜ:** Current latent state
* **p:** Procedurally generated geometric prior
* **α:** Injection strength (optimal values empirically determined)

## Pattern Dictionary

The repository provides several non-linguistic, mathematically defined prompts:

1. **Gaussian Foveated Focus:** Central compositional focus using radial basis functions.
2. **Vertical/Axial Symmetry:** Deterministic reflection for anatomical or architectural alignment.
3. **High-Frequency Kernels:** Spatial-frequency priors for micro-textures, e.g., membranes or brickwork.

## Usage & Implementation

The core functionality is provided by the `LatentInjector` class, controlled via a `Latents_callback` that intercepts the denoising loop in real time.

### Operational Guidelines

* **Plasticity Window:** Effective interventions occur between **steps 10–20**.
* **Injection Strength (α):** Values above **0.7** may cause artifacts or unnatural repetitions.
