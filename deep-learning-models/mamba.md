# Mamba

## Architecture

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

## Layers

Projection layer: `in_proj`

<pre class="language-python"><code class="lang-python">factory_kwargs = {"device": device, "dtype": dtype}
<strong>self.in_proj = nn.Linear(self.d_model, self.d_inner * 2, bias=bias, **factory_kwargs)
</strong></code></pre>

Convolution layer: `conv1d`

<pre class="language-python"><code class="lang-python"><strong>self.conv1d = nn.Conv1d(
</strong>    in_channels=self.d_inner,
    out_channels=self.d_inner,
    bias=conv_bias,
    kernel_size=d_conv,
    groups=self.d_inner,
    padding=d_conv - 1,
    **factory_kwargs,
)
</code></pre>

Activation layer: `silu`

## States

hidden\_states, conv\_state, ssm\_state

## Sequence transformation

### Conv step

causal\_cov1d\_update

### SSM step

