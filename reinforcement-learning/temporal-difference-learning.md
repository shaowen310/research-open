# Temporal Difference \(TD\) Learning

TD learning is a combination of MC ideas and DP ideas.

## TD\(0\)

### Estimation of the State-value Function

Constant-$$\alpha$$ MC for non-stationary problems

$$ V(S_t) := V(S_t) + \alpha(G_t - V(S_t))$$

TD replaces $$G_t$$ using DP ideas

$$ V(S_t) := V(S_t) + \alpha (R_{t+1} + \gamma V(S_{t+1}) - V(S_t))$$

Note:

For both methods, initialise $$V(s)$$ **arbitrarily** for all $$s$$ except $$V(terminal)=0$$ .

Why initialising $$V(s)$$  arbitrarily does not matter?

$$ v_n = (1-\alpha)^n v_0 + [1-(1-\alpha)^n]G$$ if $$G$$ is constant. We observe that $$\lim_{n \to \infty}(1-\alpha)^n = 0$$ . Rigorous proof of convergence is provided [here](https://doi.org/10.1023/A:1022632907294).

#### Convergence

\(Proved\) For any fixed policy $$\pi$$, TD\(0\) has been proved to converge to $$v_\pi$$, in the mean for a constant $$\alpha$$ if it is sufficiently small, and with probability 1 if $$\alpha$$ decreases according to the usual stochastic approximation conditions.

_Convergence rate_

\(Not proved\) In practice, TD methods have usually been found to converge faster than constant-$$\alpha$$ MC methods on stochastic tasks.

#### Batch update

Train completely on a finite amount of data, e.g., train repeatedly on 10 episodes until convergence. Compute updates according to TD or MC, but **only update estimates after each complete pass through the data**.

Notes:

1. $$\alpha$$ should be sufficiently small to achieve convergence.
2. Constant-$$\alpha$$ TD and MC converge to different answers.

#### Optimality of TD\(0\)

_Differences between the optimal values achieved by constant-_$$\alpha$$ _MC and TD_

Illustration see [Stanford University reinforcement learning lecture slides](http://web.stanford.edu/class/cme241/lecture_slides/rich_sutton_slides/11-12-TD.pdf) p24 - p30

Conclusion:

If the process is Markov, TD estimation is expected to produce lower error on future data than MC estimation. MC estimation fits past \(or existing\) data better.

### Sarsa: On-policy TD Control

For each step of episode

Action value evaluation

$$ Q(S_t, A_t) := Q(S_t, A_t) + \alpha[R_{t+1} + \gamma Q(S_{t+1}, A_{t+1}) - Q(S_t, A_t)]$$

Policy improvement

$$\varepsilon$$-greedy selection of the action based on Q

### Q-learning: Off-policy TD Control

For each step of episode

Action value evaluation

$$ Q(S_t, A_t) := Q(S_t, A_t) + \alpha[R_{t+1} + \gamma \max_a Q(S', a) - Q(S_t, A_t)]$$

Policy improvement

$$\varepsilon$$-greedy selection of the action based on Q

Note:

The learned action-value function, Q, directly approximates $$q^*$$, the optimal action-value function, independent of the policy being followed.

## References

1. R. S. Sutton and A. G. Barto, Reinforcement learning: An introduction. MIT press, 2018. [Link](https://mitpress.mit.edu/books/reinforcement-learning-second-edition)
2. Stanford University, cme241 reinforcement learning lecture slides, TD. [Link](http://web.stanford.edu/class/cme241/lecture_slides/rich_sutton_slides/11-12-TD.pdf)

