# Reinforcement Learning Grid World
This project utilizes reinforcement learning (RL) to solve a navigational task within a defined environment, specifically, a "Lawnmower Grid World". The environment consists of 16 states with a goal to maximize collected rewards while avoiding penalties.The primary tasks involve moving from the initial state at the top-left corner of the grid to the goal state at the bottom-right corner, collecting batteries (positive rewards) and avoiding pebbles (negative rewards).

<img src="https://github.com/SejalKankriya/reinforcement-learning-grid-world/assets/43418191/0e18c01d-10d8-4188-99ec-d9866ebd963f" width="50%" height="50%">

## Environment Setup

  * **States:** The states are defined as tuples representing the row and column indices on a 4x4 grid, ranging from (0, 0) to (3, 3).
  * **Actions:** Four possible actions include moving Up, Down, Right, and Left.
  * **Rewards:** Rocks represent negative rewards (-5, -6), batteries positive rewards (+5, +6), and the goal state offers the highest reward (+10).
  * **Objective:** Navigate through the grid to reach the goal state at (3, 3) by maximizing the total rewards.

## Vizualization

The environment visualization uses Matplotlib to depict the 4x4 grid where:

  * Grid cells are color-coded to differentiate between positive (warmer) and negative (cooler) rewards.
  * The goal state is highlighted in red, and the lawnmower's current position is marked appropriately on the grid.

<img width="500" alt="Screenshot 2024-04-11 at 9 20 05 PM" src="https://github.com/SejalKankriya/reinforcement-learning-grid-world/assets/43418191/c70e7e28-e5b2-4ef8-9cd3-b2bfa4ec39a0">

## Algorithms Implemented

### SARSA (State-Action-Reward-State-Action)

  * **Approach:** On-policy learning algorithm where the agent learns from the action taken based on the current policy.
  * **Update Formula:** Q(s, a) = Q(s, a) + α (r + γ * Q(s', a') - Q(s, a)), with parameters for learning rate (α), reward (r), discount factor (γ), and Q-values of the current and next state-action pairs.
  * **Features:** Employs a direct method from actual experiences with a balance between exploration and exploitation.

### Q-Learning
  * **Approach:** Off-policy algorithm that learns the optimal policy indirectly using the greedy method.
  * **Update Formula:** Q(s, a) = Q(s, a) + α * (r + γ * max(Q(s', a')) - Q(s, a)).
  * **Features:** It tends to overestimate Q-values due to its maximization step but is robust in large state spaces.


The project showcases the application of SARSA and Q-Learning to a simple yet illustrative RL problem, emphasizing the importance of hyperparameter tuning and algorithm selection based on the specific characteristics of the environment and task objectives.
