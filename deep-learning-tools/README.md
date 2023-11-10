# Deep Learning Tools

## Set random number for reproducibility

Python

```
random.seed(seed)
```

Numpy

```
np.random.seed(seed)
```

PyTorch

```
torch.manual_seed(seed)
if n_gpu > 0:
    torch.cuda.manual_seed_all(seed)
```

