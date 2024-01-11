# transformers implementation

## GPT2Model

hidden\_states = output\[0]

```python
self.h = nn.ModuleList([GPT2Block(config, layer_idx=i) for i in range(config.num_hidden_layers)])


query = self.q_attn(hidden_states)
self.q_attn = Conv1D(self.embed_dim, self.embed_dim)

```
