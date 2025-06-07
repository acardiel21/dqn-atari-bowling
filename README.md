# Deep Q-Network (DQN) Agent for Atari Bowling

This project implements a Deep Q-Network (DQN) reinforcement learning agent to play Atari Bowling using raw pixel inputs. Developed as part of NYU's CS-UA 473: Fundamentals of Machine Learning, the project explores the challenges of sparse rewards, precision timing, and limited exploration in deep RL settings.

---

## Environment
- **Game:** Atari Bowling (via OpenAI Gym)
- **State Space:** Raw pixel frames (84×84 grayscale), stacked over 4 frames
- **Action Space:** Discrete joystick/button combinations

---

## Model Architecture
- **Convolutional Neural Network (CNN):** 3 conv layers + fully connected layers
- **Experience Replay:** Buffer of 100,000 transitions
- **Target Network:** Updated periodically
- **Exploration:** Epsilon-greedy (bug: fixed epsilon = 0.10 in both phases)
- **Training Episodes:** 200 per implementation phase

---

## Iterative Improvements
### Phase 1
- Standard DQN with intended epsilon decay (bug: fixed at 0.10)
- Result: Flat learning curve; average score ~28

### Phase 2
- Tuned hyperparameters: learning rate, batch size, target update freq
- Still constrained by fixed epsilon = 0.10
- Result: Learning curve slope = 0.1288; average score rose to ~34
- Best episodes scored up to 60 points

---

## Challenges Explored
- Sparse reward timing (only scored after ball hits pins)
- Exploration-exploitation tradeoff
- Catastrophic forgetting
- Visual cue learning from raw pixels
- Temporal understanding through frame stacking

---

## Key Takeaways
- Even with limited exploration, proper tuning (learning rate, target updates) enabled meaningful learning
- CNN-based DQNs are viable for precision-timing tasks with pixel inputs
- Reinforcement learning agents struggle with delayed feedback and sparse rewards
- Hyperparameter tuning can partially mitigate exploration issues

---
