# Befor train

https://github.com/user-attachments/assets/e94f5b69-2b05-4102-8963-06d65e8800a7

# After train

[after.webm](https://github.com/user-attachments/assets/4c518591-edd2-485b-8298-53be6883667e)



<img width="640" height="480" alt="training-curve" src="https://github.com/user-attachments/assets/4ef304c2-13ce-4b5e-817d-48ee78890204" />


# DQN Lunar Lander 🚀

Implementation of a **Deep Q-Network (DQN)** reinforcement learning agent
that learns to land a spacecraft in the **Lunar Lander** environment —
developed as my B.Sc. thesis project in Electrical Engineering
(Control Systems) at Babol Noshirvani University of Technology.

## Overview
The agent learns, entirely through trial and error, to control a lunar
lander and touch down softly on the landing pad. No hand-crafted rules —
the control policy is learned purely from interaction with the environment.

## Environment & Actions
The lander observes its state (position, velocity, angle, angular velocity,
leg contact) and at each step chooses one of 4 discrete actions:
- Do nothing
- Fire left engine
- Fire right engine
- Fire main (bottom) engine

## How It Works
Deep Reinforcement Learning = Reinforcement Learning + Deep Learning.
- The agent interacts with the environment: observes state → takes action →
  receives reward
- A deep neural network approximates the Q-value function Q(s, a)
- **Experience replay:** past transitions are stored in a memory buffer and
  sampled in batches to stabilize training
- **ε-greedy exploration:** the agent starts by exploring randomly (ε = 1.0)
  and gradually exploits learned knowledge (ε decays to 0.01)

## Network Architecture & Hyperparameters
| Component | Value |
|---|---|
| Input | State space (8 features) |
| Hidden layer 1 | Dense 150, ReLU |
| Hidden layer 2 | Dense 120, ReLU |
| Output | Dense 4 (actions), Linear |
| Loss | MSE |
| Optimizer | Adam (lr = 0.001) |
| Discount factor (γ) | 0.99 |
| Batch size | 64 |
| Replay memory | 1,000,000 transitions |
| Exploration (ε) | 1.0 → 0.01 (decay = 0.996) |

## Results
After ~400 training episodes, the average episode reward rises from about
**-450** to a stable **+200 to +300** — the environment is considered
*solved* at 200 points.



## Tech Stack
Python · TensorFlow (Keras) · NumPy · OpenAI Gym (LunarLander-v2)

## How to Run
1. Clone the repository
2. Install dependencies: `pip install -r requirements.txt`
3. Run: `python RUN.py`

## Author

[keihanian.zahra@gmail.com][zahra keihanian]
