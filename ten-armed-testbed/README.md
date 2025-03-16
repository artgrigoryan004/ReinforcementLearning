<h1 align="center" style="font-size: 36px;">K-Armed Bandit Problem </h1>
This project models the K-armed bandit problem with different action selection strategies, producing visualizations of average rewards and optimal action choices over time.

### **Action-Selection Methods:**
- **[Epsilon-Greedy](#epsilon-greedy)**: With probability epsilon, choose a random action; otherwise, choose the action with the highest estimated value.
- **Sample-Average**: Use sample averages to update estimated action values.
- **[Optimistic Initial Values](#optimistic-initial-values-vs-realistic-initial-values)**: Initialize action values optimistically to encourage early exploration.
- **[Upper-Confidence-Bound (UCB)](#upper-confidence-bound-ucb)**: Selects actions considering both estimated value and uncertainty.
- **[Gradient Bandit Algorithm (GBA)](#gradient-bandit-algorithm-gba)**: Uses preference-based action selection with probability updates.

---
<h2 align="center"><strong>File Descriptions</strong></h2>

1. [**bandit.py**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/ten-armed-testbed/src/bandit.py) file defines the `Bandit` class, which represents a k-armed bandit problem with various action-selection strategies. It provides the foundation for implementing and experimenting with different learning algorithms.

### **Key Methods:**
- `initialize()` Initializes the bandit's parameters, including the action values, estimated action values, and action selection counts.

- `act()` Selects an action based on the chosen action-selection method (`ε`-greedy, UCB, gradient-based, or greedy).

- `step(action)` Takes an action, calculates the reward, and updates the estimated action values based on the selected method.



2. [**ten_armed_testbed.ipynb**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/ten-armed-testbed/notebooks/ten_armed_testbed.ipynb) Jupyter notebook simulates the behavior of different bandit algorithms applied to a **10-armed bandit problem**. It runs multiple experiments to measure the performance of various action-selection strategies over time. The notebook allows for evaluating **optimal action selection** and **reward accumulation** across different algorithms.

### **Key Functions:**
- `simulate(runs, times, bandits)` Runs multiple simulations for different bandit problems, calculating the optimal action count and average reward over time.

- The notebook visualizes the impact of different selection strategies.

---

<h2 id="epsilon-greedy" align="center"><strong>ε-Greedy</strong></h2>

  - Analyzes different values of `ε` for balancing **exploration vs exploitation**.
  - Demonstrates the trade-offs between excessive exploration and early exploitation.
<p align="center">
  <img src="https://raw.githubusercontent.com/MariHovhannisyan/ReinforcementLearning/master/ten-armed-testbed/generated_images/figure_2_2.png" width="300">
</p>

* `ε = 0.10`: More exploration, helping find better actions early but impacting long-term results.
* `ε = 0.01`: Better long-term performance with a good mix of exploration and exploitation.
* `ε = 0.00`: Poor performance due to no exploration

### Best Strategy:

* `ε = 0.01` gives the best results in this case, balancing exploration and exploitation for higher rewards over time.  
However, this doesn't mean that the lower `ε` always leads to better results. The optimal value of `ε` depends on the problem and environment, and other settings may lead to different outcomes.
---
<h2 id="optimistic-initial-values-vs-realistic-initial-values" align="center"><strong>Optimistic Initial Values vs Realistic Initial Values</strong></h2>

This approach influences the exploration strategy by initializing action-value estimates optimistically, rather than starting with realistic estimates. By setting action values higher than expected, the agent is encouraged to explore more, as all actions appear initially promising.

<p align="center">
  <img src="https://raw.githubusercontent.com/MariHovhannisyan/ReinforcementLearning/master/ten-armed-testbed/generated_images/figure_2_3.png" width="300">
</p>

This simulation compares two strategies to evaluate how often the agent selects the optimal action:

* `(ε = 0, Q₁ = 5)` A greedy strategy with optimistic initial values.
* `(ε = 0.1, Q₁ = 0)` An `ε`-greedy strategy with realistic initial values.

In this case, optimistic initialization worked better because the environment is stationary.

- **Early Exploration**: High initial values made the agent explore more actions.
- **Quick Convergence**: The agent stuck to the best action once found, maximizing rewards.
- **Unnecessary Exploration**: The `ε`-greedy method kept exploring after finding the best action, causing losses.

---
<h2 id="upper-confidence-bound-ucb" align="center"><strong>Upper-Confidence-Bound (UCB)</strong></h2>

**UCB** improves exploration-exploitation balance by selecting actions with the highest potential return while considering uncertainty in estimates.

<p align="center">
  <img src="https://raw.githubusercontent.com/MariHovhannisyan/ReinforcementLearning/master/ten-armed-testbed/generated_images/figure_2_4.png" width="300">
</p>


The Upper Confidence Bound (UCB) method prioritizes exploring under-explored actions based on an uncertainty term (c = 2). As the agent learns and becomes more confident in its choices, exploration naturally decreases, and it focuses on the most rewarding action.

- Uses UCB with \( c = 2 \) and the sample-average method.
- Implements `ε`-greedy with `ε = 0.1`, also using the sample-average method.

The UCB strategy outperforms epsilon-greedy by directing exploration towards actions that haven't been tried as much, resulting in higher overall rewards.

---
<h2 id="gradient-bandit-algorithm-gba" align="center"><strong>Gradient Bandit Algorithm (GBA)</strong></h2>

GBA uses **preference-based action selection**, updating preferences based on rewards received.

<p align="center">
  <img src="https://raw.githubusercontent.com/MariHovhannisyan/ReinforcementLearning/master/ten-armed-testbed/generated_images/figure_2_5.png" width="300">
</p>

  - **Bandit Configurations:**
  - **Bandit 1**: GBA with `α = 0.1`, baseline reward enabled, true expected reward of 4.
  - **Bandit 2**: GBA with `α = 0.1`, baseline reward disabled, true expected reward of 4.
  - **Bandit 3**: GBA with `α = 0.4`, baseline reward enabled, true expected reward of 4.
  - **Bandit 4**: GBA with `α = 0.4`, baseline reward disabled, true expected reward of 4.

- A higher learning rate (`α = 0.4`) leads to **quicker learning**.
- The **baseline reward** helps **stabilize** learning, improving performance by reducing variance.

---
<h2 align="center"><strong>Conclusion</strong></h2>

- **No single method is universally optimal**—the performance of action selection strategies depends heavily on the environment and the specific problem structure.
- **Upper-Confidence-Bound (UCB)** is particularly effective when accounting for uncertainty in action selection.
- **Gradient-based methods** are well-suited for **non-stationary environments** where rewards may change over time.
- **Exploration** plays a crucial role in maximizing long-term rewards, and different strategies offer various approaches to achieving an effective balance between exploration and exploitation.
