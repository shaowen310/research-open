# Monte Carlo Methods

## Introduction

Monte Carlo methods **estimate value functions** and **determine optimal policies** by **sample sequences of state, actions and rewards** from the agent's interaction with the environment. It does **not** require knowledge of the **environment's dynamics** which include the complete probability distributions of all possible transitions.

### Notations and definitions

visit to $$s$$ : The occurrence of state $$s$$ in an episode

## Estimation of the State-Value Function

### Assumptions

A policy $$\pi$$ is given and fixed

### First-visit MC method and every-visit MC method

Generate episodes following the policy $$\pi$$.

First-visit MC method estimates $$v_\pi(s)$$ as the average of the returns **following first visits** to $$s$$. \(Only the return following the first visit to $$s$$ in each episode will be used to calculate the estimation of $$v_\pi(s)$$.\)

Every-visit MC method estimates $$v_\pi(s)$$ as the average of the returns **following all visits** to $$s$$.



## References

1. R. S. Sutton and A. G. Barto, Reinforcement learning: An introduction. MIT press, 2018. [Link](https://mitpress.mit.edu/books/reinforcement-learning-second-edition)

