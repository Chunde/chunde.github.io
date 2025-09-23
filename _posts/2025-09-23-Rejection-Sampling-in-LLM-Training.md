---
layout: post
title: Rejection Sampling
date: 2025-09-23 23:37:40
description: A method for generating high-quality samples by filtering model outputs against quality criteria
tags: LLM training sampling reinforcement-learning alignment
tabs: true
---

Rejection sampling is a technique used in large language model (LLM) training, particularly in reinforcement learning from human feedback (RLHF) and related alignment methods. It serves as a simple but effective approach to generate high-quality training data by selectively accepting or rejecting samples based on predefined criteria.

## Core Concept

The process involves:
1. **Generating multiple candidate responses** from the LLM for a given prompt
2. **Evaluating each candidate** against a quality metric (typically using a reward model or human raters)
3. **Rejecting low-quality samples** and **accepting only the best candidates** for training

Mathematically, if we have a reward function $$R(x)$$ that scores sample quality, rejection sampling selects samples where $$R(x) > \tau$$ for some threshold $$\tau$$.

## Applications in LLM Training

### Reward Modeling
In RLHF Phase 2, rejection sampling helps create high-quality demonstration data by filtering out poor responses, ensuring the policy model learns from only the best examples.

### Data Augmentation
By generating diverse candidates and selecting the highest-quality ones, rejection sampling creates additional training data that aligns better with human preferences.

### Quality Control
During inference or data generation, rejection sampling acts as a filter to ensure only acceptable outputs are used or presented.

## Advantages and Limitations

**Advantages:**
- Simple to implement and understand
- Requires no gradient computations
- Can be highly effective when the reward model is accurate

**Limitations:**
- Computationally expensive (requires generating multiple candidates)
- Sample inefficient (many generations are discarded)
- Performance depends heavily on the quality of the reward function

Rejection sampling represents a fundamental building block in modern LLM alignment pipelines, often serving as a baseline for more sophisticated sampling techniques like proximal policy optimization (PPO) or best-of-n sampling.