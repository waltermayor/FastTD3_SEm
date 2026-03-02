# FastTD3-SEM: Simplicial Embeddings Improve Sample Efficiency in Actor-Critic Agents

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)]
[![arXiv](https://img.shields.io/badge/arXiv-2510.13704-b31b1b.svg)]

Official implementation of:

"Simplicial Embeddings Improve Sample Efficiency in Actor-Critic Agents"

**Authors:**  
Johan Obando-Ceron* (Mila, Université de Montréal),  
Walter Mayor* (Independent Researcher),  
Samuel Lavoie (Mila, Université de Montréal),  
Scott Fujimoto (NYU),  
Aaron Courville (Mila, Université de Montréal, CIFAR),  
Pablo Samuel Castro (Mila)

\* Equal contribution

Paper: https://arxiv.org/abs/2510.13704  

---

## Overview

This repository implements **FastTD3 enhanced with Simplicial Embeddings (SEM)**, 
a lightweight geometric representation module introduced in our paper:

> Simplicial Embeddings Improve Sample Efficiency in Actor-Critic Agents

Simplicial Embeddings introduce a geometric inductive bias by constraining latent
representations to lie on products of simplices. This results in:

- Sparse and structured feature representations
- More stable critic bootstrapping
- Stronger and more informative policy gradients
- Improved sample efficiency
- No degradation in wall-clock training speed

When integrated into FastTD3, SEM consistently improves performance
across high-dimensional humanoid control benchmarks.

---

## 🔁 Relationship to FastTD3

This project builds upon the official FastTD3 implementation:

FastTD3: Simple, Fast, and Capable Reinforcement Learning for Humanoid Control  
https://github.com/younggyoseo/FastTD3 

Specifically:

- We reuse the original training infrastructure.
- We preserve the installation pipeline.
- We extend the actor and critic architectures with Simplicial Embeddings.
- We introduce additional configuration parameters for geometric control.

If you use this repository, please also cite the original FastTD3 work.

---

## ✨ What is New in This Repository?

Compared to the original FastTD3 implementation, we introduce:

- **Simplicial Embeddings (SEM)** module for actor and/or critic networks
- **Geometric latent constraint mechanism**
- **New hyperparameters controlling simplex dimensionality and regularization**
- **Additional logging metrics for representation diagnostics**
- Modified default hyperparameters optimized for SEM

---

## ⚙️ Installation

Clone this repository:

```bash
git clone https://github.com/<your-username>/FastTD3-SEM.git
cd FastTD3-SEM
```

Installation is identical to FastTD3.

Please follow the setup instructions from the original repository:
https://github.com/younggyoseo/FastTD3 

After installation, this repository can be used directly.

---

## 🚀 Running Experiments

Activate the appropriate Conda environment as described in FastTD3.

### Example: HumanoidBench

```bash
python fast_td3/train.py \
    --env_name h1hand-walk-v0 \
    --no_compile \
    --sem_type sim_actor \
    --sem_dimension 64 \
    --seed 1
```

## Citation

If you use this code, please cite:

```bibtex
@article{obando_ceron2025simplicial,
  title   = {Simplicial Embeddings Improve Sample Efficiency in Actor-Critic Agents},
  author  = {Obando-Ceron, Johan and Mayor, Walter and Lavoie, Samuel and Fujimoto, Scott and Courville, Aaron and Castro, Pablo Samuel},
  journal = {arXiv preprint arXiv:2510.13704},
  year    = {2025}
}
```

And please also cite FastTD3:

```bibtex
@article{seo2025fasttd3,
  title={Fasttd3: Simple, fast, and capable reinforcement learning for humanoid control},
  author={Seo, Younggyo and Sferrazza, Carmelo and Geng, Haoran and Nauman, Michal and Yin, Zhao-Heng and Abbeel, Pieter},
  journal={arXiv preprint arXiv:2505.22642},
  year={2025}
}
```
