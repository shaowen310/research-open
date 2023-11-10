# Deep Learning Tools

## Set random number for reproducibility

Python

```text
random.seed(seed)
```

Numpy

```text
np.random.seed(seed)
```

PyTorch

```text
torch.manual_seed(seed)
if n_gpu > 0:
    torch.cuda.manual_seed_all(seed)
```



