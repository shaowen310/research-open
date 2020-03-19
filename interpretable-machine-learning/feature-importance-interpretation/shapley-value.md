# Shapley Value

Try to measure how each feature affects the prediction power of a model. 

Suppose $$v$$ is the evaluation function of a model's prediction power. Feature subsets $$S \subseteq F$$, where $$F$$ is the set of all features. $$f_S$$ is the model trained with features in set $$S$$. Shapley value of a feature $$i$$ is defined as

$$
\phi_i = \sum{S \subseteq F \setminus i} \frac{|S|!(|F|-|S|-1)!}{|F|!}(v(f_{S \cup {i} })-v(f_{S}))
$$





