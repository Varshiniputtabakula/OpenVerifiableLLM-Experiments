# OpenVerifiableLLM Experiments

A simple framework to analyze and interpret divergence in model training.

![Divergence Framework](framework.png)

## Overview

This repository explores how small variations during training affect model behavior and reproducibility.

The goal is to understand how training trajectories evolve under different conditions and to distinguish between expected variation and meaningful inconsistencies.

---

## Key Contributions

- Comparison of deterministic vs stochastic training
- Tracking divergence across training steps
- Classification of divergence patterns:
  - Stable
  - Gradual Drift
  - Fluctuating
  - Explosive
- Simple decision framework for interpreting divergence
- Analysis of reproducibility and training sensitivity

---

## Reproducibility and Sensitivity Analysis

In addition to divergence tracking, this work explores how reproducibility breaks down under small changes:

- Sensitivity to random seeds and stochasticity  
- Impact of data ordering and minor data variations  
- Effect of small perturbations in model parameters  

These experiments show that even small changes can lead to different training trajectories, highlighting the need for more nuanced verification beyond exact matching.

---

## Key Observations

- Deterministic runs remain stable across training  
- Stochastic runs show structured but non-monotonic divergence  
- Optimizer choice significantly affects divergence behavior  
- Small perturbations can compound over time  

These observations suggest that divergence is not random and should be interpreted based on behavior rather than strict numerical matching.

---

## Key Insight

Not all divergence means failure.

Different divergence behaviors reflect different underlying causes, so verification systems should consider training dynamics rather than relying only on exact numerical matching.

---

## Motivation

In systems like OpenVerifiableLLM, ensuring reproducibility is critical.

This work helps define what kinds of variation are acceptable and what might indicate deeper issues. It also highlights that any intervention (such as watermarking) should preserve natural training behavior rather than introduce unintended changes in learning dynamics.