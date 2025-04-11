<h1 align="center" style="font-size: 36px;">Markov Decision Process (MDP) in Grid-World </h1>
This project implements key concepts from Reinforcement Learning (RL), specifically focusing on value functions and policies in a simple gridworld environment. 

---

## File Descriptions

| File                                                                                                                                  | Description |
|---------------------------------------------------------------------------------------------------------------------------------------|-------------|
| [grid_world.py](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gridworld-mdp/src/grid_world.py)                | Contains constants, helper functions (`step`, `draw`) and gridworld setup including special state transitions. |
| [grid_world.ipynb.py](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gridworld-mdp/notebooks/grid_world.ipynb) | Computes value functions and optimal policies using Bellman equations, and visualizes results. |


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
- States along the edges tend to have **negative expected returns** due to the high likelihood of hitting grid boundaries and receiving penalties.
- **State A**, while offering an immediate reward of **+10**, has a **lower overall value** because transitions from A lead to **A′**, which increases exposure to negative outcomes.
- This demonstrates the process of **evaluating a fixed, stochastic policy** using the Bellman Expectation Equation.

---
## Policy Evaluation
<p align="center">
  <img src="https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gridworld-mdp/generated_images/figure_3_2.png" width="300">
</p>

- States along the edges tend to have **negative expected returns** due to the high likelihood of hitting grid boundaries and receiving penalties.
- **State A**, while offering an immediate reward of **+10**, has a **lower overall value** because transitions from A lead to **A′**, which increases exposure to negative outcomes.
- This demonstrates the process of **evaluating a fixed, stochastic policy** using the Bellman Expectation Equation.

## Value Iteration
<p align="center">
  <img src="https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gridworld-mdp/generated_images/figure_3_5_policy.png" width="300">
</p>

- Several cells contain **multiple arrows**, indicating that **multiple actions** are equally optimal from those states.
- **State B** ends up with a value **greater than its immediate reward of +5**, thanks to favorable transitions through **B′**.
- This section highlights how **value iteration** improves policy by maximizing expected future rewards at each step.
---
## Conclusion

This simulation provides an intuitive understanding of how agents evaluate and optimize their behavior in a gridworld setting. The visualizations of value functions and optimal policies offer insights into how special rewards, grid boundaries, and state transitions influence decision-making over time.
