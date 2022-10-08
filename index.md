---
layout: default
---

## Abstract

Meta-learning has been recognized as an effective remedy for solving the cold-start problem in the recommendation domain.
Traditional models assume that the testing samples are always distributionally aligned with the training ones.
However, in the cold start setting, we can only observe a small number of users and items, which, in practice, may fail to represent the newly arrived (testing) sample distributions, and thus lead to lowed recommendation performance.
For alleviating this problem, in this paper, we propose a robust meta recommender framework to address the distribution shift problem. \\
In specific, we argue that the distribution shift may exist on both of the user- and item-levels, and in order to remove them simultaneously, we design a novel distributionally robust model by hierarchically reweighing the training samples.
Generally speaking, the sample weights are leveraged to tune the training distribution, and we minimize the worst-case loss by searching the weights on a unit ball, which is expected to improve the robustness of the learned model. \\
Theoretically, we analyze the convergence rate and demonstrate the generalization capability of our framework.
Empirically, we conduct extensive experiments based on different meta recommender models and real-world datasets to verify the generality and effectiveness of our framework.
For benefiting the research community and promoting this direction, we have released our code at this page.

## Requirements

numpy==1.22.4 \\
PyYAML==6.0 \\
scikit_learn==1.1.2 \\
torch==1.11.0

## Quick Start

You can run a sample with quick start in any datasets in `1 overall_and_ablation` dictionary. \\
For example, you can use the following commands after installing the required packages. 
    
    python quick_start.py
    
## Running the model

You can run the models with commands in the following forms.

    
    python run.py MeLU hiddenDim1 32 hiddenDim2 32 localLr 0.1 lr 0.1 gamma 0.99 batchSize 20 epoch 200 userNum 20000 
    
The first parameter is the model name, and then following hyper-parameters.

## Hyper-parameters

You can find the full hyper-parameter form in [Google Drive](https://docs.google.com/spreadsheets/d/14vrGx10EcPnU3tBYhZXKGvanL7o2pnDG/edit?usp=sharing&ouid=105504424352348994104&rtpof=true&sd=true). 
