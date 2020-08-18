# Monte Carlo Methods

## Introduction

Monte Carlo methods **estimate value functions** and **determine optimal policies** by **sample sequences of states, actions and rewards** from the agent's interaction with the environment. It uses the average of the sample returns of a state as the estimation of the expected return of the state. It does **not** require knowledge of the **environment's dynamics** which include the complete probability distributions of all possible transitions.

### Notations and definitions

visit to $$s$$ : The occurrence of state $$s$$ in an episode

## Estimation of the State-Value Function

### Assumptions

A policy $$\pi$$ is given and fixed

### First-visit MC method and every-visit MC method

Generate episodes following the policy $$\pi$$. A sample sequence of states, actions and rewards

$$ S_0, A_0, R_1, S_1, A_1, R_2, ..., S_{T-1}, A_{T-1}, R_T  (, S_T)$$

First-visit MC method estimates $$v_\pi(s)$$ as the average of the returns **following first visits** to $$s$$. \(Only the return following the first visit to $$s$$ in each episode will be used to calculate the estimation of $$v_\pi(s)$$.\)

Every-visit MC method estimates $$v_\pi(s)$$ as the average of the returns **following all visits** to $$s$$.

#### Calculation of the return

Starting from one timestamp before the timestamp of the terminal state and going backwards, and update $$G$$ by

$$ G = \gamma G + R_{t+1}$$



## References

1. R. S. Sutton and A. G. Barto, Reinforcement learning: An introduction. MIT press, 2018. [Link](https://mitpress.mit.edu/books/reinforcement-learning-second-edition)

