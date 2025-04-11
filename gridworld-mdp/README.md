<h1 align="center" style="font-size: 36px;">Markov Decision Process (MDP) in Grid-World </h1>
This project implements key concepts from Reinforcement Learning (RL), specifically focusing on value functions and policies in a simple gridworld environment. The code is inspired by examples from Sutton & Barto’s *Reinforcement Learning: An Introduction* and visually demonstrates how values and policies evolve in Markov Decision Processes (MDPs).

---

## File Descriptions

| File                 | Description |
|----------------------|-------------|
| `[grid_world.py]()`  | Contains constants, helper functions (`step`, `draw`) and gridworld setup including special state transitions. |
| `[grid_world.ipynb].py` | Computes value functions and optimal policies using Bellman equations, and visualizes results. |


---

## Key Methods and Functions

### 1. `step(state, action)`
- Simulates one step in the gridworld.
- Handles special cases for state A and B (jumps to A′ and B′ with positive rewards).
- Handles off-grid penalties (-1) and standard moves (0 reward).

### 2. `draw(grid, is_policy=False)`
- Visualizes the grid:
  - If `is_policy=False`: shows state-value function.
  - If `is_policy=True`: shows arrows for best actions from each state.
- Marks special states (A, A′, B, B′).

### 3. Value Iteration Algorithms
- **Policy Evaluation**: Evaluates a uniform random policy (equal probability for all actions).
- **Optimal Value Iteration**: Iteratively improves state values using the Bellman optimality equation until convergence.
- **Policy Extraction**: Derives the optimal policy based on the final optimal state values.

---

## Conclusion

This simulation provides an intuitive understanding of how agents evaluate and optimize their behavior in a gridworld setting. The visualizations of value functions and optimal policies offer insights into how special rewards, grid boundaries, and state transitions influence decision-making over time.
