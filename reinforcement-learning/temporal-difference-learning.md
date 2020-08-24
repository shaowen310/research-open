# Temporal-Difference Learning

## TD Prediction

TD learning is a combination of MC ideas and DP ideas.

### TD\(0\)

Recall constant-$$\alpha$$ MC

$$ V(S_t) := V(S_t) + \alpha(G_t - V(S_t))$$

TD replaces $$G_t$$ using DP ideas

$$ V(S_t) := V(S_t) + \alpha (R_{t+1} + \gamma V(S_{t+1}) - V(S_t))$$

Initialisation: initialise $$V(s)$$ arbitrarily for all s except $$V(s_{terminal})=0$$

#### Convergence

\(Proven\) For any fixed policy $$\pi$$, TD\(0\) has been proved to converge to $$v_\pi$$, in the mean for a constant $$\alpha$$ if it is sufficiently small, and with probability 1 if $$\alpha$$ decreases according to the usual stochastic approximation conditions.



## References

1. R. S. Sutton and A. G. Barto, Reinforcement learning: An introduction. MIT press, 2018. [Link](https://mitpress.mit.edu/books/reinforcement-learning-second-edition)

