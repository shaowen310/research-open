# Monte Carlo Methods

## Introduction

Monte Carlo methods **estimate value functions** and **determine optimal policies** by **sample sequences of states, actions and rewards** from the agent's interaction with the environment. It uses the average of the sample returns of a state as the estimation of the expected return of the state. It does **not** require knowledge of the **environment's dynamics** which include the complete probability distributions of all possible transitions.

### Notations and definitions

visit to $$s$$ : The occurrence of state $$s$$ in an episode

## Estimation of the State-value Function

### Assumptions

A policy $$\pi$$ is given and fixed

### First-visit MC method and every-visit MC method

Generate episodes following the policy $$\pi$$. A sample sequence of states, actions and rewards

$$ S_0, A_0, R_1, S_1, A_1, R_2, ..., S_{T-1}, A_{T-1}, R_T  (, S_T)$$

First-visit MC method estimates $$v_\pi(s)$$ as the **average** of the **returns following first visits** to $$s$$. \(Only the return following the first visit to $$s$$ in each episode will be used to calculate the estimation of $$v_\pi(s)$$.\)

Every-visit MC method estimates $$v_\pi(s)$$ as the **average** of the **returns following all visits** to $$s$$.

#### Calculation of the return

Starting from one timestamp before the timestamp of the terminal state and going backwards, and update $$G$$ by

$$ G := \gamma G + R_{t+1}$$

$$G$$ is the sample return of the state at $$t$$.

#### Incremental update of the estimation

Initialise $$v_\pi(s)$$ as zero

$$ v_\pi(s) := v_\pi(s) + \alpha(G - v_\pi(s))$$

where $$\alpha$$ is a constant step-size parameter

Note that for first-visit MC method, $$\alpha = 1/n$$ and $$n$$ is the number of first visits to $$s$$ so far \(therefore $$\alpha$$ is not a constant\)

## Estimation of the Action-value Function

The idea is similar to the MC estimation of the state-value function.

### Issue

Many state–action pairs may never be visited.

#### Solution

Consider only policies that are stochastic with a nonzero probability of selecting all actions in each state.

## References

1. R. S. Sutton and A. G. Barto, Reinforcement learning: An introduction. MIT press, 2018. [Link](https://mitpress.mit.edu/books/reinforcement-learning-second-edition)
2. The University of Edinburgh School of Informatics, Reinforcement learning lecture slides, TD. [Link](http://www.inf.ed.ac.uk/teaching/courses/rl/slides/4rllect10.pdf)

