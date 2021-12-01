# Papers

## \[LM-BFF] Making Pre-trained Language Models Better Few-shot Learners

{% embed url="https://arxiv.org/abs/2012.15723" %}

### Motivation

GPT-3 achieves few-shot performance solely by leveraging a natural-language prompt and a few task demonstrations as input context.

### Contribution

LM-BFF, a suit of simple and complementary techniques for **fine-tuning language models on** **a small number of annotated examples**.

1. Pipeline for automating prompt template generation.
2. Fine-tuning with demonstrations: dynamically and selectively incorporating demonstrations into each context.

### Task Definition

Prompt template generation: automatic template generation from a fixed set of label words.

Fine-tuning: sampling similar demonstrations

### Code

[https://github.com/princeton-nlp/LM-BFF](https://github.com/princeton-nlp/LM-BFF)

#### Create conda environment

```
conda create --name lmbff python=3.8

conda install pytorch==1.6.0 torchvision==0.7.0 cudatoolkit=10.2 -c pytorch
conda install -c conda-forge transformers=3.5.1
conda install -c conda-forge sentence-transformers
conda install pandas
```

####
