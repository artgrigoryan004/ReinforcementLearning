<h1 align="center" style="font-size: 36px;"> Gridworld via Dynamic Programming </h1>

This project implements a simple **Grid World** environment used for testing reinforcement learning (RL) algorithms. It demonstrates how an agent can learn to navigate a grid-based environment using basic RL principles such as rewards, penalties, exploration, and convergence.

---

## File Descriptions

| File                 | Description |
|----------------------|-------------|
| [grid_world.py](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gridworld-dp/src/grid_world.py)    | Contains the core implementation of the Grid World environment and reinforcement learning logic. It defines the environment, rewards, transitions, agent updates, and training mechanism. |
| [grid_world.ipynb](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gridworld-dp/notebooks/grid_world.ipynb) | A Jupyter notebook that provides a step-by-step walkthrough for training the agent in the Grid World environment and visualizing its behavior. Ideal for experimentation and learning. |

---

## Key Classes and Methods

 In `grid_world.py`
#### `GridWorldEnv`
A class representing the grid world environment.

- `__init__(self, grid_size, start_state, terminal_states, walls, rewards)`: Initializes the environment with grid size, terminal states, wall positions, and reward values.
- `get_actions(self, state)`: Returns possible actions from a given state.
- `step(self, state, action)`: Applies an action to a state and returns the next state and corresponding reward.
- `is_terminal(self, state)`: Checks if a state is terminal.

#### `ValueIteration`
A class that implements the value iteration algorithm.

- `__init__(self, env, gamma=0.9, theta=0.001)`: Initializes the value iteration algorithm.
- `run(self)`: Runs the value iteration algorithm to find the optimal value function and policy.
- `get_policy(self)`: Returns the derived optimal policy.

---

## Key Functions 
 In `grid_world.ipynb`

- **`display_values_and_policy()`**: Helper function to visualize the computed value function and policy using matplotlib and seaborn.
- **`run_simulation()`**: Simulates an agent moving through the environment using the optimal policy.
- **`plot_grid_policy()`**: Plots arrows on the grid to indicate the direction of the optimal policy.

---

## Conclusion

This Grid World project provides a solid foundation for understanding core reinforcement learning concepts such as:

- Environment modeling
- Value iteration algorithm
- Policy extraction
- Grid-based visualization
