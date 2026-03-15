# Reinforcement Learning Coin-Collection Game (Linear Q-Learning)

This project demonstrates how a **reinforcement learning agent can learn to play a custom game environment** using **Linear Q-Learning with a neural network approximator**.

The project includes:

- A **custom 2D game environment built with Pygame**
- A **custom environment**
- A **Linear Q-Learning model implemented in PyTorch**
- A **state representation for decision making**
- A **training pipeline with experience replay**
- A **trained AI agent that can autonomously play the game**
- A **real-time visualized AI agent**

The goal of the game is for the player (or AI agent) to **collect coins while avoiding an enemy** within a time limit.  
This project highlights the ability to combine **machine learning, simulation environments, and game development** to build intelligent agents.

---

# Demo

The trained agent can autonomously play the game using a learned policy.  
During gameplay the agent learns to:

- Move toward coins
- Avoid the enemy
- Maximize score within the time limit

The repository includes a **visual demo mode** where the trained model plays the game.

---

# Game Overview

The environment consists of:

- **Player** – controlled either by a human or the AI agent
- **Coins** – increase the score when collected
- **Enemy** – moves to intercept the player
- **Timer** – limits how long the player has to collect coins

Two game modes are available:

## Graphical Mode

- Full Pygame rendering
- Used for demonstrations and visualization

## Fast Training Mode

- No graphics
- Runs significantly faster
- Designed for efficient reinforcement learning training

---

# Reinforcement Learning Approach

The AI agent uses **Deep Q-Learning with a linear neural network** to estimate Q-values for each possible action.

## State Representation

The environment is converted into a **17-dimensional state vector** including:

- Danger detection in four directions
- Relative position of the coin
- Relative position of the enemy
- Collision checks with nearby objects

Example signals in the state vector:

- Enemy within danger range (up/down/left/right)
- Coin position relative to the player
- Enemy position relative to the player

---

## Action Space

The agent can choose from four actions:

```
[UP, DOWN, LEFT, RIGHT]
```

The neural network predicts the **Q-value** for each action, and the agent selects the highest value.

---

## Model Architecture

The Q-network is implemented in **PyTorch**.

```
Input Layer:   17 features
Hidden Layer:  2000 neurons
Output Layer:  4 actions
```

The model approximates the Q-function:

```
Q(state, action)
```

which estimates the expected reward for taking an action in a given state.

---

## Training Strategy

The agent is trained using standard **Deep Q-Learning techniques**.

### Experience Replay

- Past experiences are stored in a replay buffer
- Random batches are sampled to stabilize training

### Short-Term Learning

- Immediate training after each step

### Long-Term Memory

- Periodic training on batches from the replay buffer

### Epsilon-Greedy Exploration

- Early training uses random actions
- Over time the agent shifts toward model predictions

---

# Project Structure

```
project/
│
├── game_4_agent.py        # Pygame game environment
├── model.py               # Neural network and Q-learning trainer
├── agent_trainer.py       # Training loop for the AI agent
├── agent_player.py        # Runs a trained agent
├── SpriteSheetReader.py   # Utility for sprite sheet loading
├── model.pth              # Saved trained model
```

---

# Training the Agent

To train a new model:

```
python agent_trainer.py
```

During training the script will:

- Play games autonomously
- Train the neural network
- Plot scores over time
- Save the best performing model

---

# Running the Trained Agent

To watch the trained AI play the game:

```
python agent_player.py
```

This loads the saved `model.pth` file and runs the visual demo.

---

# Technologies Used

- **Python**
- **PyTorch** (neural network implementation)
- **Pygame** (game environment)
- **NumPy**
- **Matplotlib** (training visualization)

---

# Key Concepts Demonstrated

This project demonstrates several important machine learning and AI concepts:

- Reinforcement Learning
- Q-Learning
- Neural Network Function Approximation
- Experience Replay
- Epsilon-Greedy Exploration
- Custom Game Environment Design
