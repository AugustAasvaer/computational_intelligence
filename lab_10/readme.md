# Lab 10 solution

Reinforcement Agent implementation

Uses Q-learning to learn the best policy. Two agents are defined and trained against each other. After training, you can play agains the agents youself. The agents are simulated playing 1000 games agents that play random, legal moves. After the simulation the result are plotted. The Q-learning agent works fairly well. Tweaking the reward decay, eploration rate, etc. before training might also find better numbers for these values. The Q-table after playing 10000 games has about 4-5000 positions. This means that the agent will still occationally find itself in unknown positions even after all the training, seen as there are about 19000 possible positions in tic tac toe.

## References

https://towardsdatascience.com/reinforcement-learning-implement-tictactoe-189582bea542: Used for inspiration of implementing the Q-learning algortihm