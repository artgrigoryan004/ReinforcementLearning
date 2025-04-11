# Gambler’s Problem – (Value Iteration)

## Project Description

This project implements the **Gambler’s Problem** using **Dynamic Programming** with **Value Iteration**. The gambler aims to reach a goal amount (e.g., 100 units) starting with some capital, by betting in a way that maximizes the probability of reaching the goal. 

The code simulates value iteration over multiple sweeps, visualizes the value function's convergence, and the final learned policy.

---

## Key Concepts

- **States:** Amount of capital (1 to 99).
- **Actions:** Stake to bet (up to min(capital, goal - capital)).
- **Reward:** +1 only if gambler reaches goal.
- **Transition probability:** Win with probability *p*, lose with *1-p*.
- **Objective:** Maximize probability of reaching goal (value function).

---

## Key Functions & Methods

`value_iteration(p_h, theta = 1e-9, max_sweep = 1000)`
Performs value iteration:
- `p_h`: Probability of the coin landing heads.
- `theta`: Convergence threshold.
- `max_sweeps`: Max number of value function sweeps.

Returns:
- Value function over states.
- Optimal policy.

`plot_value_estimates_over_sweeps(value_history)`
Plots the value function over multiple sweeps to show convergence.

`plot_final_policy(policy)`
Plots the final learned policy (how much to bet at each state).

<p align="center">
  <img src="https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gambler-problem/generated_images/figure_4_3.png" width="500">
</p>

### Top Plot:
- **X-axis:** Capital (state).
- **Y-axis:** Estimated value function.
- **Curves:** Each line represents a sweep of value iteration. The curves converge toward the true value function as sweeps increase.

### Bottom Plot:
- **X-axis:** Capital.
- **Y-axis:** Optimal action (stake).
- **Points:** Show the optimal bet at each capital. A peak indicates where betting large amounts is optimal.

<p align="center">
  <img src="https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/gambler-problem/book_images/Figure_4_3.PNG" width="500">
</p>

### Reference Plot:
- Reproduction of Sutton & Barto’s Figure 4.3.
- Shows expected results for validation and comparison.

---

## Conclusion

This implementation successfully solves the Gambler’s Problem using dynamic programming. Over multiple sweeps:
- The value function converges smoothly.
- The optimal policy learned resembles the official result.
- The code is efficient and visually demonstrates convergence and learned policy.
