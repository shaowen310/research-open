# Temporal-Difference Learning

## TD Prediction

TD learning is a combination of MC ideas and DP ideas.

Recall constant-$$\alpha$$ MC

$$ V(S_t) := V(S_t) + \alpha(G_t - V(S_t))$$

TD replaces $$G_t$$ using DP ideas

$$ V(S_t) := V(S_t) + \alpha (R_{t+1} + \gamma V(S_{t+1}) - V(S_t))$$

Initialisation: initialise $$V(s)$$ arbitrarily for all s except $$V(s_{terminal})=0$$



## References

1. R. S. Sutton and A. G. Barto, Reinforcement learning: An introduction. MIT press, 2018. [Link](https://mitpress.mit.edu/books/reinforcement-learning-second-edition)

