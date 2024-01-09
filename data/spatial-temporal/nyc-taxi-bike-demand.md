---
description: 'Paper: https://arxiv.org/pdf/2012.08080.pdf'
---

# NYC Taxi/Bike Demand

## Task definition

Station-level demand prediction.



For station-less transportation, we partition a region into grids and use clustering techniques to discover virtual stations.

We have four subtasks: taxi demand, taxi dropoff, bike demand, and bike dropoff.

### Task 1: graph completion

Given a graph $$G=(V,E)$$

Stations correspond to $$V$$ in the study region.

We have $$N$$ nodes in $$G$$.

At timestamp t the graph $$G$$ has a feature matrix $$X_t \in R^{N \times d}$$, where $$d$$ is the input feature dimension.

Given graph signals of $$\tau$$ steps, we aim at obtaining an adjacency matrix $$A \in R^{N \times N}$$ to complete the definition of $$G$$.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Task 2: transportation demand prediction

At time step t, given the graph G and P steps historical graph signals, we intend to obtain a mapping function F2 to forecast the next Q steps graph signals.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Example adjacency matrix

```
array([[1.        , 0.16438753, 0.        , 0.        , 0.        ],
       [0.16438753, 1.        , 0.        , 0.10269756, 0.        ],
       [0.        , 0.        , 1.        , 0.        , 0.72590021],
       [0.        , 0.10269756, 0.        , 1.        , 0.        ],
       [0.        , 0.        , 0.72590021, 0.        , 1.        ]])
```

The matrix determines the aggregation manner of nodes themselves and their neighbors in graph convolution.

It embeds the temporal correlation between node pairs.





