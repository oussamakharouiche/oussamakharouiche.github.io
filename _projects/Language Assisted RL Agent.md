---
layout: project # Use the new project layout
title: "Language Assisted RL Agent"
rank: 1
---

## Problem Addressed  
Traditional Reinforcement Learning (RL) agents excel at optimizing reward signals but lack the ability to interpret and act on high-level **natural language instructions**. This limits their adaptability in real-world scenarios where tasks are often defined through human commands. Our project bridges this gap by integrating **natural language understanding (NLU)** with RL, enabling agents to execute complex textual directives in structured environments.  

---

## Solution Developed  
We designed a **language-guided RL agent** that translates textual instructions into actionable policies within a grid environment. Key components include:  
- **Environment Design**:  
  - A customizable grid world (built with `Gymnasium`) where the agent navigates to corners.  
  - **Observation Space**: Combines agent position (coordinates), BERT text embeddings of instructions, and optionally grid images.  
  - **Reward Structure**: Penalizes step count (-1 per step) and rewards goal completion (+60).  
- **Language Integration**:  
  - **BERT Embeddings**: Process textual instructions (e.g., *“Go to the upper-right corner”*) into semantic representations.  
  - **Dual Fine-Tuning Strategies**:  
    - **Classification Fine-Tuning**: Trained BERT on a sequence classification task to cluster embeddings by goal labels, improving intra-class similarity.  
    - **Contrastive Learning**: Enhanced distinction between ambiguous instructions (e.g., *“top-left” vs. “bottom-left”*) by pushing dissimilar commands apart in the embedding space.   
- **RL Architecture**:  
  - **Proximal Policy Optimization (PPO)** with two distinct architectures:  
    - **Multi-Input Network**: Fuses agent coordinates and BERT text embeddings to guide policy decisions.  
    - **Visual Attention Pathway**: Uses CNNs to process grid images and cross-attention mechanisms to align visual features with language embeddings, enabling spatial reasoning.  

---

## Technologies Used 
- **Core Frameworks**: Python, PyTorch, Gymnasium.  
- **Language Models**: BERT for text embeddings, fine-tuned with **classification** and **contrastive learning**. 
- **RL Algorithms**: Proximal Policy Optimization (PPO) with custom multi-input networks.


---

## Future Work  
- **Inverse Reinforcement Learning (IRL)**: Implement methods inspired by **Inverse Reinforcement Learning with Natural Language Goals**.
- **Multi-Goal Instructions**: Expand the agent’s capability to handle **complex instructions with multiple interdependent goals** (e.g., *“Collect the key, open the door, then reach the exit”*).
 

---

## Bibliography  
1. [**Proximal Policy Optimization Algorithms**](https://arxiv.org/abs/1707.06347).  
2. [**BabyAI: A Platform to Study Grounded Language Learning**](https://arxiv.org/abs/1810.08272).  
3. [**Inverse Reinforcement Learning with Natural Language Goals**](https://arxiv.org/abs/2008.06924).  

---

🔗 **Links**  
- [GitHub Repository](https://github.com/oussamakharouiche/Language-Assisted-RL-Agent-)  
- [Project Poster](https://drive.google.com/file/d/1Hvc0dEbmnYoxHY1DKkbc9BzlMoopHPkK/view?usp=sharing)  

