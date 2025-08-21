# SAE-ception: Iteratively Using Sparse Autoencoders as a Training Signal

This repository contains the official code and experimental setup for the paper **SAE-ception**. Our work explores whether post-hoc interpretability tools can be repurposed as a training signal to build models that are more interpretable by design.

We introduce **SAE-ception**, a method that iteratively incorporates features extracted by a sparse autoencoder (SAE) as auxiliary targets in the training loop.

## Abstract

> We explore whether post-hoc interpretability tools can be repurposed as a training signal to build models that are more interpretable by design. We introduce *SAE-ception*, a method that iteratively incorporates features extracted by a sparse autoencoder (SAE) as auxiliary targets in the training loop. Across three distinct settings --- an MLP on MNIST, a vision transformer (ViT-H) on CIFAR-10, and ConvNeXt-V2 on ImageNet-1k --- our method led to substantial gains in feature clustering and separability of the learned SAE features. The effect on monosemanticity and task performance, however, is context-dependent. On the simpler MLP, the approach is a clear success, improving not only the SAE's feature quality but also the base model's final task accuracy by over 2.5%. On the ViT-H, SAE-ception doubles the monosemanticity of the SAE (MI-CSI) after a single cycle with only a 0.1% drop in task accuracy. While the gains in feature cluster separability persist on ConvNeXt-V2, monosemanticity metrics remained largely stagnant --- MI-CSI shifted from a baseline of 0.28 to 0.31. We conclude that SAE-ception is a low-cost method that reliably enhances features for post-hoc analysis, making it a valuable tool for practitioners, while its ability to improve the base model's representations depends on the specific architecture and task. Determining the conditions under which it can consistently improve a base model's internal monosemanticity remains a key direction for future exploration.

## Repository Structure

This repository is organized into three main folders, each corresponding to a distinct experiment conducted in the paper.

    DIGIT-MNIST/: An MLP model trained on the MNIST dataset.

    CIFAR-10/: A Vision Transformer (ViT-H) model trained on the CIFAR-10 dataset.

    ImageNet1K/: A ConvNeXt-V2 model trained on the ImageNet-1k dataset.

### Experiment Contents

Each experiment folder contains the code and scripts for running the SAE-ception methodology. The core components in each directory are:

- Model Adaptation: Scripts to prepare and adapt the base model for the SAE-ception training loop.

- SAE Training: Code to train the sparse autoencoder on the features extracted from the base model.

- Feature Sharpening: Implementation of the iterative process where SAE features are used as auxiliary targets to retrain the base model.

- Metrics & Interpretation: Notebooks and scripts for evaluating the results, including:

    - Interpretability and feature clustering metrics.
    - Base model and linear probe accuracy measurements.
