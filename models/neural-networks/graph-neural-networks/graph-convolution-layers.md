# Graph Convolution Layers

## Notations

| Notation | Definition |
| :--- | :--- |
| $$N$$ | number of nodes in the graph |
| $$F$$ | dimension of the node attributes \(i.e., each node has an attribute in $$\mathbb{R}^F$$ \) |
| $$F'$$ | dimension of the node attributes after a message passing layer |
| $$S$$ | dimension of the edge attributes \(i.e., each edge has an attribute in $$\mathbb{R}^S$$ \) |
| $$A \in {\{0,1\}}^{N \times N}$$ | binary adjacency matrix |
| $$X \in \mathbb{R}^{N \times F}$$ | node attributes matrix |
| $$E \in \mathbb{R}^{N \times N \times S}$$ | edge attributes matrix |
| $$D = \textrm{diag} ( \sum\limits_{j=0} a_{ij})$$ | degree matrix, a diagonal matrix which each entry indicates the number of times an edge terminates at a vertex |
| $$W, V$$ | trainable kernels |
| $$b$$ | trainable bias vector |
| $$\mathcal{N}(i)$$ | the one-hop neighbourhood of node $$i$$ |



## References

