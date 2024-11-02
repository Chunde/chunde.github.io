---
layout: page
title: Model-Based deep Learning for Reinforcement Learning
description: First project in reinforcement learning
img: assets/img/deep_q_learning.jpeg
importance: 3
category: Research
---

## Deep Q-Learning (DQL) Research
Deep Q-Learning (DQL) is a temporal difference method used to estimate an action-value function. Rather than estimating real-valued predictions for every possible state-action pair, I proposed an alternative approach involving learning a probabilistic model of the transition function. Specifically, I employed a convolutional network trained on 4-tuples: state, action, reward, and next state.
## Model-Based Approach
Instead of directly learning an action-value function, this network predicts the next state and reward based on a given state-action input. This model-based approach enables integration of planning, reducing the amount of real-world data required, although it demands greater computational resources during training.
## Inspiration and Exploration
Google's DeepMind achievement with Atari sparked my interest in this area. Initially, my knowledge of reinforcement learning was limited. To gain a deeper understanding of DQN:
* I studied and debugged Pac-Man code to grasp its core principles.
* I explored the source code of DeepMind's Atari framework and successfully replicated their results on the "Breakout" game, as described in their Nature paper.
* After training the DQN network for approximately 12 million steps, I achieved expected outcomes.
Experimentation and Optimization
I also experimented with transferring parameters from a trained network to a new game to accelerate training. This approach provided valuable insights into optimizing training processes across tasks.

## Demo: Training a Pac-Man Agent

<iframe width="720" height="480" src="https://www.youtube.com/embed/r3pb-ZDEKVg?si=XFCLh7yszaAjbx53" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Training a Atlantis Agent

<iframe width="720" height="480" src="https://www.youtube.com/embed/8GKjSAr-lwI?si=gsSSS__7VGsTQ2vr" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>