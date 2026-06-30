# TaxiRL: Enhancing SARSA with Prioritized Sweeping and Reward Shaping

Reinforcement Learning course project that investigates how different planning and reward design techniques affect the performance of a SARSA agent in the Taxi-v4 environment.

## Authors

- Gal Moyal
- Eden Furman

---

## Project Overview

This project is based on the Gymnasium Taxi-v4 environment, where an agent must:

1. Navigate to the passenger.
2. Pick up the passenger.
3. Navigate to the destination.
4. Successfully drop off the passenger.

The objective is to compare different learning approaches and analyze how planning mechanisms, generalization, exploration strategies, and reward shaping influence learning speed and final policy quality.

---

## Environment

- Environment: Gymnasium Taxi-v4
- Grid Size: 5×5
- Actions:
  - Move North
  - Move South
  - Move East
  - Move West
  - Pickup
  - Dropoff

---

## Algorithms

The project implements and compares:

- SARSA
- SARSA + Prioritized Sweeping
- SARSA + Kernel Generalization
- SARSA + Prioritized Sweeping + Kernel

---

## Main Experiments

### 1. SARSA vs Prioritized Sweeping

Comparison of the baseline SARSA agent against SARSA enhanced with Prioritized Sweeping.

Metrics:

- Total Reward
- Episode Length
- Illegal Actions
- Success Rate

---

### 2. Ablation Study

Evaluation of the contribution of each added component:

- Base SARSA
- SARSA + Prioritized Sweeping
- SARSA + Kernel
- SARSA + Prioritized Sweeping + Kernel

---

### 3. Reward Design

Several reward functions were evaluated.

### Base Reward

Default Taxi-v4 reward.

### Sparse Reward

Minimal feedback during training.

### Reward 3

Milestone-based reward shaping.

Several parameter configurations were tested.

### Reward 4

Distance-based reward shaping using Manhattan distance.

Multiple parameter variations were evaluated.

---

### 4. Failure Analysis

Although some reward functions produced promising learning curves, policy evaluation revealed unstable behavior.

The project includes:

- Policy visualization
- GIF generation
- Greedy policy evaluation (ε = 0)
- Q-value analysis
- Local minima investigation

---

### 5. Epsilon Sweep

Comparison of exploration rates:

- ε = 0.01
- ε = 0.05
- ε = 0.1
- ε = 0.2
- ε = 0.4

Studied metrics:

- Success Rate
- Total Reward
- Steps
- Illegal Actions

---

### 6. Planning Steps Sweep

Comparison of different Prioritized Sweeping planning depths:

- n = 1
- n = 3
- n = 5
- n = 10
- n = 20

---

### 7. Investigation of the "Bump" Phenomenon

An additional analysis explaining the temporary increase in illegal actions observed for very small epsilon values during training.

---

## Training Parameters

Default parameters:

| Parameter | Value |
|-----------|------:|
| Alpha | 0.1 |
| Gamma | 0.99 |
| Epsilon | 0.1 |
| Planning Steps | 5 |
| Episodes | 500 |
| Max Steps | 200 |
| Seeds | 42, 123, 777, 999, 2024 |

Kernel parameters:

- β = 4
- c = 0.5

---

## Project Features

- CSV result caching (avoids rerunning expensive experiments)
- Saved trained agents (.pkl)
- Automatic graph generation
- Policy visualization
- GIF generation
- Comprehensive experiment analysis

---

## Main Findings

- Prioritized Sweeping significantly improves sample efficiency and learning speed.
- Kernel generalization mainly improves the early stages of learning but increases computational cost.
- The default Taxi reward achieved the most stable policies.
- Proper reward shaping can improve learning, but poorly designed rewards may create unstable policies and local minima.
- Small epsilon values generally produced the best final policies.

---

## Technologies

- Python
- Gymnasium
- NumPy
- Matplotlib
- Pandas
- Seaborn
- Pillow

---


## Course

Reinforcement Learning

Software Engineering Department

Braude College of Engineering
