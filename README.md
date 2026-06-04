# Qlearning Voter Model
# Overconfidence of Q-Learning Agents in Noisy Signals in a Voting Environment

This repository contains the replication code and simulations for the Applied Economic Analysis project (ECO131237). It extends the theoretical framework of **Kartal and Tyran (2022)** to reinforcement learning agents.

For a complete breakdown of the theoretical model and economic interpretation, please refer to the verbatim file: `AEA_Assignment_VFinal.pdf`[cite: 1].

## Project Overview

This study analyzes how the confidence level ($\lambda$) of a Q-learning agent evolves when exposed to noisy information signals. We test whether an algorithm can autonomously achieve informational neutrality or if it naturally converges toward overconfidence to maximize its rewards.

### Core Model
The agent's subjective perception of its signal precision $q_i$ is modeled as:
$$\pi(q_i) = \lambda \times q_i$$

*   **$\lambda > 1$**: Overconfident behavior.
*   **$\lambda = 1$**: Neutral behavior.
*   **$\lambda < 1$**: Underconfident behavior.
