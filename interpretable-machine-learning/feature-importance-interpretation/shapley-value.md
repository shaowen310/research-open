# Shapley Value

Try to measure how each feature affects the prediction power of a model. 

Suppose $$v$$ is the evaluation function of a model's prediction power. Feature subsets $$S \subseteq F$$, where $$F$$ is the set of all features. $$f_S$$ is the model trained with features in set $$S$$. Shapley value of a feature $$i$$ is defined as

$$
\phi_i = \sum_{S \subseteq F \setminus i} \frac{|S|!(|F|-|S|-1)!}{|F|!}(v(f_{S \cup {i} })-v(f_{S}))
$$

{% hint style="info" %}
About the weight

$$
\frac{|S|!(|F|-|S|-1)!}{|F|!}
$$

It is the inverse of

$$
\frac{|F|!}{|S|!(|F|-|S|-1)!1!}
$$

The inverse is the number of ways to distribute $$|F|$$ different items to three stacks, which have $$|S|$$ , $$|F|-|S|-1$$ , and 1 item respectively.
{% endhint %}

The difficulty of calculating Shapley value directly is to consider all the combinations of $$S \subseteq F  \setminus i$$. There are around $$n!$$ choices, not considering the cost of retraining all these models.

