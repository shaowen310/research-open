# PyTorch Data

## DataLoader

## Sampler

Note:

Neither `sampler` nor `batch_sampler` is compatible with iterable-style datasets, since such datasets have no notion of a key or an index.

`RandomSampler(replacement=False)` behaves the same as `DataLoader(shuffle=True)` &#x20;

&#x20;DistributedSampler is used for multi-GPU.



