# GCN_res-CS-v2
This is an improvement of the  [(GCN_res + 8 layers)](https://github.com/ytchx1999/ogbn_arxiv_GCN_res)  model, using the C&amp;S method. **This is the v2 version(adjust parameters).**

### ogbn-arxiv

+ Check out the model：[(GCN_res + 8 layers)](https://github.com/ytchx1999/ogbn_arxiv_GCN_res)

+ Check out the C&S method：[C&S](https://arxiv.org/abs/2010.13993)

#### Improvement Strategy：

+ add C&S method

#### Environmental Requirements

+ pytorch == 1.8.1
+ pytorch_geometric == 1.6.3
+ ogb == 1.3.0

#### Experiment Setup：

The model is 8 layers, 10 runs which conclude 500 epochs.

```bash
python gcn_res_cs.py
```

#### Detailed Hyperparameter:

```bash
num_layers = 8
hidden_dim = 128
dropout = 0.5
lr = 0.01
runs = 10
epochs = 500
alpha = 0.2
beta = 0.7
num_correction_layers = 50
correction_alpha = 0.7
num_smoothing_layers = 50
smoothing_alpha = 0.7
scale = 1.
A1 = 'DAD'
A2 = 'DAD'
```

#### Result:

```bash
All runs:
Highest Train: 98.23 ± 0.02
Highest Valid: 74.45 ± 0.11
  Final Train: 98.23 ± 0.02
   Final Test: 73.13 ± 0.17
```

| Model            | Test Accuracy   | Valid Accuracy  | Parameters | Hardware          |
| ---------------- | --------------- | --------------- | ---------- | ----------------- |
| GCN_res + C&S_v2 | 0.7313 ± 0.0017 | 0.7445 ± 0.0011 | 155824     | Tesla V100 (32GB) |

