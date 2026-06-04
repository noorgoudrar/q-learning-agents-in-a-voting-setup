# Applied Economic Analysis
# Overconfidence of Q-Learning Agents in Noisy Signals in a Voting Environment

This project analyzes the intersection of behavioral economics and algorithmic learning by operationalizing the voter overconfidence framework established by **Kartal and Tyran (2022)** into reinforcement learning systems.

### 1. Extension of the Kartal & Tyran Framework
The original framework by Kartal and Tyran demonstrates that human voters overestimating the accuracy of their information acts as a structural multiplier for fake news. Their model assumes human heterogeneity in cognitive abilities to discern truth from noise. 

This implementation extends their setup to autonomous Q-learning agents, replacing human cognitive variance with automated reinforcement loops. The objective is to determine if algorithmic agents, driven purely by reward maximization, can naturally self-calibrate to informational neutrality or if they inherently develop overconfidence when exposed to noisy environments.

### 2. Model
An agent receives a noisy news signal $s_i \in \{\alpha, \beta\}$ regarding an unknown state of the world $S \in \{A, B\}$, with an objective signal precision $q_i$. 

Following the extension, we introduce a parameter $\lambda$ acting as a multiplier on the agent's perceived precision:
$$\pi(q_i) = \lambda \times q_i$$

The system evaluates three structural behaviors based on the value of $\lambda$:
*   **$\lambda > 1$ (Overconfidence):** The agent overvalues the accuracy of the signal.
*   **$\lambda = 1$ (Neutrality):** The agent perfectly calibrates its subjective belief to objective reality.
*   **$\lambda < 1$ (Underconfidence):** The agent undervalues its signal precision.

### 3. Simulation Setup & Mechanics
The codebase simulates two distinct operational environments across different penalty vectors:
*   **Revealed Signal Quality ($q_i$ revealed):** The agent receives explicit feedback on its signal precision after each voting episode to adjust its choices.
*   **Hidden Signal Quality ($q_i$ hidden):** The agent remains "blind" to $q_i$, observing only the raw signal $s_i$, forcing it to dynamically form an internal belief ($\hat{q}_i$) regarding its quality.

To counteract the empirical tendency of optimization algorithms to default to overconfidence, the model introduces a social cost/error penalty. This penalizes the agent specifically when an overconfidence-induced action results in an incorrect vote, mirroring the real-world negative externalities of algorithmic misinformation propagation.
