<h1 align="center" style="font-size: 36px;">Tic-Tac-Toe with Reinforcement Learning</h1>
This project implements a Tic-Tac-Toe game using Reinforcement Learning (RL). It trains RL agents to play the game, allows human players to compete against RL agents, and saves trained policies for future use.

<h2 align="center"><strong>File Descriptions</strong></h2>

- [**tic_tac_toe.py**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/Tic_tac_toe/tic_tac_toe.py): Contains the main game logic, training routines, and functions for playing the game either against the RL agent or another human player. This script manages the overall flow of the game, including agent training and playing.
  
- [**state.py**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/Tic_tac_toe/state.py): Responsible for generating and managing all possible board states in the Tic-Tac-Toe game. It handles the representation of the game state, including checking for win conditions, draws, and available moves.

- [**player.py**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/Tic_tac_toe/player.py): Defines two classes: `RLPlayer` and `HumanPlayer`. The `RLPlayer` class handles the Reinforcement Learning agent's decision-making and training processes, while the `HumanPlayer` class allows a human player to interact with the game.

- [**judge.py**](https://github.com/MariHovhannisyan/ReinforcementLearning/blob/master/Tic_tac_toe/judge.py): Manages the rules and flow of the game between two players. It ensures that the game follows the correct rules, determines the winner, and updates the game state accordingly.


<h2 align="center"><strong>How It Works</strong></h2>

1. **Game Setup**: 
   - The game starts with a 3x3 board, and each player is assigned either X or O.

2. **Player Interaction**:
   - The board is represented by the following positions: `q, w, e, a, s, d, z, x, c`.  
   - A human player makes a move by choosing a spot on the board.  
   - The RL agent selects its move based on its trained strategy.

3. **Game Flow**:
   - The game alternates between players until one wins or the board is full (a draw).

4. **Training the RL Agent**:
   - The RL agent learns by playing games. It improves its strategy after each game.

5. **Game End:**
   - The game ends when there’s a winner or a draw. The result is shown, and the agent may update its strategy if it’s being trained(after each game, the agent uses the result (win, loss, or draw) to update its strategy). 


