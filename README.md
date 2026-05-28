# Simplicial Embeddings Improve Sample Efficiency in Actor-Critic Agents

This repository contains the code for the paper:  
**"Simplicial Embeddings Improve Sample Efficiency in Actor-Critic Agents"**  
by *Johan Obando-Ceron**, *Walter Mayor**, *Samuel Lavoie*, *Scott Fujimoto*, *Aaron Courville*, and *Pablo Samuel Castro*  

★ Equal contribution

🎉 Accepted to ICLR 2026 (Main Conference).

*Work conducted at Mila Quebec AI Institute and University of Montreal.*

## 📄 **[Read the Full Paper on arXiv ▶️](https://arxiv.org/pdf/2510.13704.pdf)**

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
    --sim_type sim_actor \
    --sim_dimension 64 \
    --seed 128
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

```bibtex
@article{seo2025fasttd3,
  title={Fasttd3: Simple, fast, and capable reinforcement learning for humanoid control},
  author={Seo, Younggyo and Sferrazza, Carmelo and Geng, Haoran and Nauman, Michal and Yin, Zhao-Heng and Abbeel, Pieter},
  journal={arXiv preprint arXiv:2505.22642},
  year={2025}
}
```

```bibtex
@article{lavoie2022simplicial,
  title={Simplicial embeddings in self-supervised learning and downstream classification},
  author={Lavoie, Samuel and Tsirigotis, Christos and Schwarzer, Max and Vani, Ankit and Noukhovitch, Michael and Kawaguchi, Kenji and Courville, Aaron},
  journal={arXiv preprint arXiv:2204.00616},
  year={2022}
}
```
