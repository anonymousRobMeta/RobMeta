---
layout: default
---

## Meta Recommendation with Robustness Improvement


## Quick Start

### Step 1: Download the project

First of all, download our project `RobMeta.zip` from [Google Drive](https://drive.google.com/file/d/1Uh72K-T7oU4--wlaDRneeUIKnKHhvBtA/view?usp=sharing) and unzip the file. The file includes both codes and datasets.

### Step 2: Create the running environment

Create `Python 3.8` enviroment and install the packages that the project requires.
- numpy==1.22.3
- PyYAML==6.0 
- scikit_learn==1.1.2 
- torch==1.11.0

You can install the packages with the following command.

```
    pip install -r requirements.txt
```

### Step 3: Run the project

Choose a dataset to run (e.g. MovieLens-1M) with the following command.

```
    cd movielens-1m
```

Choose a model (e.g. MeLU) to run with the following command.

```
    python run.py MeLU hiddenDim1 32 hiddenDim2 32 localLr 0.1 lr 0.1 gamma 0.99 batchSize 20 epoch 200 userNum 20000
```

You can also use `quick_start.py` to run the project conveniently.

```
    python quick_start.py
```

You can also change the hyper-parameters as you want. The necessary hyper-parameters for each model have been recorded in the `hyperParam` dictionary.

### Step 4: Check the performance

The performance will be saved in `performance.csv`. The first column is the name of models. The second column is the number of testing sets (with different β). The third to the sixth columns are metrices `NDCG@10, Recall@10, Precision@10, F1@10` in order.


## 5 Hyper-parameters search range

We tune hyper-parameters according to the following table.

| Hyper-parameter     | Explanation | Range |
| ------------------- | ---------------------------------------------------- | ------------------- |
| taskWeightLr | user weights lr | \{0.00001, 0.0001, 0.001, 0.005, 0.01, 0.05, 0.1\} |
| sampleWeightLr | interaction weights lr | \{0.00001, 0.0001, 0.001, 0.005, 0.01, 0.05, 0.1\} |
| localLr     | adapt lr | \{0.001, 0.01, 0.05, 0.1\} |
| lr   | model lr |  \{0.001, 0.01, 0.05, 0.1\} |
| batchSize | batch size |  \{20, 100, 200, 400\} |
| gamma | learning rate decay | \{0.95, 0.97, 0.99\} |
| hiddenDim1 | hidden layer1 dim | \{16, 32, 64, 128\} |
| hiddenDim2 | hidden layer2 dim | \{16, 32, 64, 128\} |
| indHiddenDim | index embedding dim | \{16, 32, 64, 128\} |

As different base models have different hyper-paramerters to tune, you can view the details in the corresponding model files.
