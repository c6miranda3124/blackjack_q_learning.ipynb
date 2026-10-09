# Blackjack Q-Learning

A reinforcement learning project that explores how an AI agent can learn to play Blackjack through trial and error.

## Project Overview

I chose Blackjack because every game has a clear outcome: a win, loss, or draw. This makes it a good environment for experimenting with reinforcement learning, since the agent can use the results of each game to improve its decisions.

The goal of this project was to train an AI agent using **Q-learning** to determine when to hit or stand in Blackjack and compare its performance against simpler playing strategies.

## How It Works

The project uses Q-learning, a reinforcement learning algorithm that allows an agent to learn from its experiences.

The agent makes decisions based on three pieces of information:

- The player's current hand value
- The dealer's visible card
- Whether the player has a usable ace

The agent can choose between two actions: **Hit** or **Stand**.

After each game, it receives a reward:

- **+1** for winning
- **0** for a draw
- **-1** for losing

During training, the agent explores different actions and updates its Q-values based on the rewards it receives. Over time, it learns which decisions are more effective in different situations.

## Implementation

Using a provided Blackjack environment and starter code, I implemented the Q-learning algorithm and training process in Python.

The agent was trained over **500,000 games**, using an epsilon-greedy strategy to balance exploring new actions with choosing actions it had already learned.

After training, I evaluated the agent over 10,000 games and compared it against three other strategies:

1. Randomly hitting or standing
2. Standing when the player's hand reaches 17 or higher
3. Standing when the player's hand reaches 18 or higher

The project also includes visualizations comparing the strategies and showing the agent's training progress.

## Results

Each strategy was evaluated over 10,000 Blackjack games.

| Strategy | Win Rate | Average Reward |
|---|---:|---:|
| Random | 28.89% | -0.3816 |
| Stand on 17+ | 41.15% | -0.0738 |
| Stand on 18+ | 40.37% | -0.1047 |
| **Q-Learning** | **42.43%** | **-0.0615** |

The Q-learning agent achieved the highest win rate and average reward among the four strategies tested.

Although the improvement over the fixed strategies was relatively small, the results showed how reinforcement learning could be used to develop a playing strategy through experience rather than relying entirely on predetermined rules.

## Challenges and What I Learned

One of the biggest challenges was understanding how Q-learning works and how the agent improves its decisions through repeated training.

I also wanted to make sure the agent wasn't simply memorizing its training experiences. To evaluate this, I tested the learned strategy on separate games and compared its performance against other strategies.

This project gave me hands-on experience with reinforcement learning and helped me better understand how to train, evaluate, and experiment with AI models.

## Technologies Used

- **Python** — Q-learning implementation and training
- **Jupyter Notebook** — Development and experimentation
- **Gymnasium** — Blackjack environment
- **NumPy** — Numerical operations
- **Matplotlib** — Results and training visualizations

## Running the Project

1. Download or clone this repository.
2. Install the required Python packages:

   `pip install numpy==1.26.4 gymnasium==0.29.1 matplotlib==3.8.4`

3. Open `Blackjack_Q_Learning_CLEAN_FIXED.ipynb` in Jupyter Notebook.
4. Run the cells in order to train the agent, evaluate its performance, and generate the visualizations.

Training is configured for 500,000 games. For a quicker test, the training and evaluation episode counts can be reduced in the notebook.

## Future Improvements

One possible improvement would be to expand the Blackjack environment to include additional information, such as cards visible from other players or previously played cards.

This could allow the agent to explore more advanced strategies and provide opportunities for further experimentation with reinforcement learning.
