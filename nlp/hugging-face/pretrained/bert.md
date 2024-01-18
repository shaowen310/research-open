# BERT

Source code [https://github.com/huggingface/transformers/blob/master/src/transformers/models/bert/modeling\_bert.py](https://github.com/huggingface/transformers/blob/master/src/transformers/models/bert/modeling\_bert.py)

## Load Model

General procedure

```
tokenizer = BertTokenizer.from_pretrained('bert-base-cased')
config = BertConfig.from_pretrained("bert-base-cased")
model = BertLMHeadModel.from_pretrained('bert-base-cased', config=config)
```

Still don't know how `trainer_state.json` is saved.
