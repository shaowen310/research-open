# Generalised Policy Iteration \(GPI\)

It is quite similar to expectation-maximisation algorithm. Policy iteration consists of two interaction processes, policy-evaluation and policy-improvement.

Policy-evaluation process evaluates the value function based on the current policy.

Policy-improvement process improves the policy by making the policy greedy with respect to the current value function.

$$ \pi(s) := \arg\underset{a}{\max} \ q(s,a)$$ 

The iteration ends when both value function and policy are optimal.

The greedy algorithm is proved to generate a policy that achieves not worse **expected return** than the previous policy achieves with respect to the current value function.

![](../.gitbook/assets/generalised-policy-iteration.png)

## Issues

1. Policy evaluation may not be perfect in some cases \(especially when MC or TD is used and some states are not explored\), GPI may not give the optimal value function and policy.

## References

1. R. S. Sutton and A. G. Barto, Reinforcement learning: An introduction. MIT press, 2018. [Link](https://mitpress.mit.edu/books/reinforcement-learning-second-edition)

