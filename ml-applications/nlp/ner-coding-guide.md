# NER Coding Guide

## Data format

### CoNLL03

```
-DOCSTART- -X- -X- O

EU NNP B-NP B-ORG
rejects VBZ B-VP O
German JJ B-NP B-MISC
call NN I-NP O
to TO B-VP O
boycott VB I-VP O
British JJ B-NP B-MISC
lamb NN I-NP O
. . O O

Peter NNP B-NP B-PER
Blackburn NNP I-NP I-PER

```

Each word in a sentence is labeled with POS, Chunk and NER tags.

It uses empty line to separate sentences.

## Preprocess

### What is the input for BERT?

3 sequences which are

* input\_ids: id for subword token&#x20;
* attention\_mask: indicates which portion contains valid input, "1" for true, "0" for false
* segment\_id: indicates the segment a token belongs to when the input contains a pair of sentences, "0" for the first sentence, "1" for the second sentence. For NER, use "0" for all tokens.

### What is the output?

* labels: id for labels. Note that if a word is split into several subwords, only the first subword is annotated with the source label, all others are annotated using null label.

### How to locate the subword in the source sentence?

Use 'offset\_mapping'. Each pair indicates the start and end position of a subword relative to the original word.

## Reference

{% embed url="https://colab.research.google.com/github/NielsRogge/Transformers-Tutorials/blob/master/BERT/Custom_Named_Entity_Recognition_with_BERT_only_first_wordpiece.ipynb#scrollTo=f5EHpuB78pIa" %}
Google BERT NER Tutorial
{% endembed %}

