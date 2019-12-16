**Methodology**: We implement [Q-learning](https://en.wikipedia.org/wiki/Q-learning) from scratch with optional epsilon-greedy training, and ensemble modeling. The agent learns to play either first or second against a random player.

**Observations**: When teaching the agent to play in a single session, the agent learns fairly variant behaviors for starting a game as the first player and would suggest that 1) there are either several equally optimal first moves or 2) learning against a random player teaches the agent different behaviors, reinforcing the winning behaviors randomly. This led to implementing an ensemble approach to see if the agent could consistently find the most optimal first move. Several ensembles settled on a first move at the center of the board, which is known to be an acceptable first move according to known [strategy](https://en.wikipedia.org/wiki/Tic-tac-toe#Strategy). However, playing the opening move in a corner gives the opponent more chances to make a mistake. Even so either move does not make a difference between perfect players. I, personally, lost more often when the agent opened with a corner move but found it hard, if not impossible, to win when playing the opening move at all. I found that implementing random choices via epsilon led to poor training of the agent.

**Drawbacks**: The main drawback of this approach in general is that all states must be stored in memory. It's interesting that the number of unique states (when the agent must learn to play first or second) is 8,533. Given the seemingly small total action space at each step, it's easy to see how much one would need to save to memory to teach an agent a much more complex game.

![tictacwhoagif](https://media.giphy.com/media/hRBtq1lRaxWWQ60sex/giphy.gif)

**Next**: 
* Compare these results to that of deep Q-learning.
* Train two agents at the same time against each other.
