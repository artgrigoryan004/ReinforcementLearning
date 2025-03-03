<h1 align="center" style="font-size: 36px;">K-Armed Bandit Problem </h1>
This project models the K-armed bandit problem with different action selection strategies, producing visualizations of average rewards and optimal action choices over time

<h2 align="center"><strong>File Descriptions</strong></h2>

1. [**bandit.py**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/ten-armed-testbed/src/bandit.py)  file defines the `Bandit` class, which represents a k-armed bandit problem with various action-selection strategies. It provides the foundation for implementing and experimenting with different learning algorithms, such as the epsilon-greedy algorithm, sample-average method, and gradient bandit algorithm.

### Key Methods:
- `initialize()`
  Initializes the bandit's parameters, including the action values, estimated action values, and action selection counts.

- `act()`
  Selects an action based on the chosen action-selection method (epsilon-greedy or greedy).

- `step(action)`
  Takes an action, calculates the reward, and updates the estimated action values based on the selected method.

### Action-Selection Methods:
- **Epsilon-Greedy**: With probability epsilon, choose a random action; otherwise, choose the action with the highest estimated value.
- **Sample-Average**: Use sample averages to update estimated action values.
---

2. [**ten_armed_testbed.ipynb**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/ten-armed-testbed/notebooks/ten_armed_testbed.ipynb) Jupyter notebook simulates the behavior of different bandit algorithms applied to a 10-armed bandit problem. It runs multiple experiments to measure the performance of a bandit algorithm over time. The notebook allows for the evaluation of the optimal action selection strategy and the rewards achieved by an agent during exploration and exploitation.

### Key Functions:
- `simulate(runs, times, bandits)`
  Runs multiple simulations for different bandit problems, calculating the optimal action count and average reward over time.

- The notebook plots and saves the reward distribution and optimal action selection rate as figures to help visualize the performance of the agent.

### Approach:
- Simulates experiments using different values for the exploration parameter (epsilon) in an epsilon-greedy strategy.
- Tracks the average reward and the percentage of optimal actions chosen by the agent at each time step.
- Results are visualized through various plots.

---
<h2 align="center"><strong>Results</strong></h2>

![Figure 2.2](https://raw.githubusercontent.com/MariHovhannisyan/ReinforcementLearning/master/ten-armed-testbed/generated_images/figure_2_2.png)

* `ε = 0.10`: More exploration, helping find better actions early but impacting long-term results.
* `ε = 0.01`: Better long-term performance with a good mix of exploration and exploitation.
* `ε = 0.00`: Poor performance due to no exploration

### Best Strategy:

* `ε = 0.01` gives the best results in this case, balancing exploration and exploitation for higher rewards over time.  
However, this doesn't mean that the lower `ε` always leads to better results. The optimal value of `ε` depends on the problem and environment, and other settings may lead to different outcomes.

