---
layout: project # Use the new project layout
title: "Proximal Policy Optimization Algorithms implementation"
---

**This project is a PPO paper implementation using Gymnasium environments, PyTorch, and Wandb for metrics visualization.**

---

## Overview
In this project, I implement PPO, a state-of-the-art policy gradient algorithm, from scratch in PyTorch. The goal is to train agents on classic control tasks provided by Gymnasium (e.g., CartPole-v1, LunarLander-v3). Key highlights:

- **Policy and Value Networks:** Separate and unified actor (policy) and critic (value) networks built with PyTorch.
- **Clipped Surrogate Objective:** Implementation of PPO’s clipped loss function for stable updates.
- **Advantage Estimation:** Generalized Advantage Estimation (GAE) for variance reduction.
- **Logging & Visualization:** Track training metrics (reward, loss) via Wandb.

---

## Features

- **Training Loop:** mini-batch updates, learning rate scheduling.
- **Checkpointing:** Save and load model weights for reproducibility.
- **Wandb Integration:** Visualize reward curves, loss components, and learning rate.
- **Configurable Hyperparameters:** Easily adjust learning rate, clip ratio, batch size, and more.

---

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/oussamakharouiche/PPO-Implementation.git
   cd PPO-Implementation
   ```
2. Create a virtual environment and install dependencies:
   ```bash
   python3 -m venv ppo
   source ppo/bin/activate
   pip install -r requirements.txt
   ```

---

## Bibliography

1. Create config file if not found
2. Train the ppo agent:
   ```bash
   python3 ppo.py --config-path ./configs/cartpole_config.yaml
   ```
3. evaluate the agent:
   ```bash
   python3 evaluate.py --config-path ./configs/cartpole_config.yaml
   ```

---

## 📈 Results

| Environment     | Avg. Reward | Std. Dev |
| --------------- | ----------- | -------- |
| CartPole-v1     | 500.0       | 0.0      |
| LunarLander-v3  | 240.5       | 15.2     |

*Note: Results may vary based on random seed and hyperparameters.*  

---

## Bibliography 
1. [**Proximal Policy Optimization Algorithms**](https://arxiv.org/abs/1707.06347).

---

🔗 **Links**  
- [GitHub Repository](https://github.com/oussamakharouiche/PPO-Implementation#)

