# Transformer Quick Guide

## Multi-head attention

<figure><img src="../../.gitbook/assets/multihead_attention (1).png" alt=""><figcaption></figcaption></figure>

The features of the input sequence are extracted using linear layers.

The input shapes are&#x20;

`[batch_size, from_seq_length, features]`,

`[batch_size, to_seq_length, features]`.

`features` is embedding dimension

`features = num_attention_heads * size_per_head`&#x20;

The extracted features are

`Q` 's shape is `[batch_size, num_attention_heads, from_seq_length, size_per_head]`

`K` 's shape is `[batch_size, num_attention_heads, to_seq_length, size_per_head]`

`V` 's shape is `[batch_size, num_attention_heads, to_seq_length, size_per_head]`

We may use one linear layer with an output feature size of `3*num_attention_heads*size_per_head` to replace the three separate linear layers indicated in the diagram.

The output's shape is `[batch_size, from_seq_length, features]`.

To illustrate the shape

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

Source: [https://vaclavkosar.com/ml/cross-attention-in-transformer-architecture](https://vaclavkosar.com/ml/cross-attention-in-transformer-architecture)

In the Transformer model, `Q` is produced by the decoder embedding, `K` and `V` are produced by the encoder embedding.

Implementation

```python
query = attn.to_q(hidden_states)
query = attn.head_to_batch_dim(query)

encoder_hidden_states = encoder_hidden_states if encoder_hidden_states is not None else hidden_states
key = attn.to_k(encoder_hidden_states)
value = attn.to_v(encoder_hidden_states)
key = attn.head_to_batch_dim(key)
value = attn.head_to_batch_dim(value)

attention_probs = attn.get_attention_scores(query, key, attention_mask)
hidden_states = torch.bmm(attention_probs, value)
```

There is non-linear transformation (`softmax`) to compute attention probabilities.

The mask is created by setting the negative infinity value to disabled units before the `softmax`.

### Self-attention

From and to sequences are the same.

## Transformer

### Full architecture

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Source: Attention is all you need.



### Encoder-only

Uses unmasked multi-head attention.

### Decoder-only

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption><p>Decoder-only Transformer Architecture</p></figcaption></figure>

Source: [https://ai.stackexchange.com/questions/40179/how-does-the-decoder-only-transformer-architecture-work](https://ai.stackexchange.com/questions/40179/how-does-the-decoder-only-transformer-architecture-work)

Uses masked multi-head attention.

