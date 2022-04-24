# TODSum
This repository is the official implementation of [TODSum: Task-Oriented Dialogue Summarization with State Tracking](https://arxiv.org/abs/2110.12680).

## About TODSum
TODSum is a large-scale task-oriented dialogue summarization dataset, which is constructed on the basis of [MultiWOZ](https://arxiv.org/abs/1810.00278), including 9906 task-oriented dialogue examples from 5 domains of {restaurant, hotel, attraction, train, taxi}, and including corresponding summaries and unique dialogue states.
<img width="880" alt="截屏2022-04-24 下午4 18 27" src="https://user-images.githubusercontent.com/56821771/164967095-afdb7b18-0edd-47c6-95c9-acc3e2bde027.png">

## About Factual Consistency Metrics
### Introduction
We propose new state-aware factual consistency metrics to evaluate the factual consistency of key slot-value pairs generated in the summary. Specifically, we use ![](http://latex.codecogs.com/svg.latex?\mathcal{N}(t)) and ![](http://latex.codecogs.com/svg.latex?\mathcal{N}(h)) to denote the number of (domain, intent, slot, value) tuples in the target (golden dialogue state) and hypothesis (generated summary) respectively. 
![](http://latex.codecogs.com/svg.latex?\mathcal{N}({h}\cap{t})) denotes the number of slot tuples exactly matched between generated summary and golden dialogue state. 

We define our **state-aware factual consistency metrics** as follows: 

![](http://latex.codecogs.com/svg.latex?Precision=\mathcal{N}({h}\cap{t})/\mathcal{N}(h))

![](http://latex.codecogs.com/svg.latex?Recall=\mathcal{N}({h}\cap{t})/\mathcal{N}(t))

![](http://latex.codecogs.com/svg.latex?F1={2}\cdot{Precision}\cdot{Recall}/(Precision+Recall))

### Using
```bash
cd consistency/
```
```bash
python calc_consistency.py --dst_path=./test.oracle --summary_path=./test.hpy
```
dst_path: the file path for golden dialog state

summary_path: the file path of the generated summary



## Citation
```
@article{zhao2021todsum,
  title={TODSum: Task-Oriented Dialogue Summarization with State Tracking},
  author={Zhao, Lulu and Zheng, Fujia and He, Keqing and Zeng, Weihao and Lei, Yuejie and Jiang, Huixing and Wu, Wei and Xu, Weiran and Guo, Jun and Meng, Fanyu},
  journal={arXiv preprint arXiv:2110.12680},
  year={2021}
}
```
