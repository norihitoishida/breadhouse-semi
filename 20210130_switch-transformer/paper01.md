# 概要

|Topic|Description|
|---|---|
|タイトル|Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity|
|日付|2021/01/11|
|著者|W Fedus, B Zoph, N Shazeer|
|所属|Google Brain|
|リンク|[arXiv:2101.03961 [cs.LG]](https://arxiv.org/abs/2101.03961)|
|概要|TransformerのMixture of Expertsモデル|
|備考|[サンプルコード](https://github.com/tensorflow/mesh/blob/master/mesh_tensorflow/transformer/moe.py)|

***

# 目次
- [ABSTRACT](#ABSTRACT)
- [1 Introduction](#1-Introduction)
- [2 Switch Transformer](#2-Switch-Transformer)
    - [2.1 Simplifying Sparse Routing](##2.1-Simplifying-Sparse-Routing)
        - 2.1.1 Mixture of Expert Routing
        - 2.1.2 Switch Routing: Rethinking Mixture-of-Experts
    - [2.2 Efficient Sparse Routing ](##2.2-Efficient-Sparse-Routing)
        - 2.2.1 Distributed Switch Implementation
        - 2.2.2 A Differentiable Load Balancing Loss
    - [2.3 Putting It All Together: The Switch Transformer](##2.3-Putting-It-All-Together:-The-Switch-Transformer)
    - [2.4 Improved Training and Fine-Tuning Techniques](##2.4-Improved-Training-and-Fine-Tuning-Techniques)
        - 2.4.1 Selective precision with large sparse models
        - 2.4.2 Smaller parameter initialization for stability
        - 2.4.3 Regularizing large sparse models
- [3 Scaling Properties](#3-Scaling-Properties)
    - 3.1 Scaling Results on a Step-Basis 
    - 3.2 Scaling Results on a Time-Basis 
    - 3.3 Scaling Versus a Larger Dense Model 
- [4 Downstream Results](#4-Downstream-Results)
    - 4.1 Fine-Tuning 
    - 4.2 Distillation 
    - 4.3 Multilingual Learning
- [5 Designing Models with Data, Model, and Expert-Parallelism](#5-Designing-Models-with-Data,-Model,-and-Expert-Parallelism)
    - 5.1 Data Parallelism
    - 5.2 Model Parallelism
    - 5.3 Model and Data Parallelism
    - 5.4 Expert and Data Parallelism
    - 5.5 Expert, Model and Data Parallelism
    - 5.6 Towards Trillion Parameter Models
- [6 Related Work](#6-Related-Work)
- [7 Discussion](#7-Discussion)
- [8 Future Work](#8-Future-Work)
- [9 Conclusion](#9-Conclusion)
- [Appendix](#Appendix)
    - A Switch for Attention
    - B Preventing Token Dropping with No-Token-Left-Behind
    - C Encouraging Exploration Across Experts
    - D Switch Transformers in Lower Compute Regimes
    - E Relation of Upstream to Downstream Model Performance 
    - F Pseudo Code for Switch Transformers 

# ABSTRACT
- 通常のdeep learningではモデルの全てのパラメータが使われる。
- 一方、Mixture of Experts (MoE)モデルは入力ごとに異なる部分のパラメータが使われる。
- MoEは推論時の計算コストを抑えられるメリットがある。
- しかし`複雑さ`・`通信コスト`・`学習の不安定さ`等の課題があった。
- 本論文では`Switch Transformer`という枠組みを提案しこれらに対処した。
- `T5-Base`, `T5-Large`をベースにしたアーキテクチャで、pre-trainingが7倍速くなった。
- 多言語モデルでも上手くいった。
- `C4`データセットを使って`T5-XXL`が4倍速くなった。(どういう意味？)

# 1 Introduction

**背景**



**貢献**



# 2 Switch Transformer

## 2.1 Simplifying Sparse Routing

**2.1.1 Mixture of Expert Routing**


**2.1.2 : Switch Routing: Rethinking Mixture-of-Experts**


## 2.2 Efficient Sparse Routing 


**2.2.1 Distributed Switch Implementation**

**2.2.2 A Differentiable Load Balancing Loss**



## 2.3 Putting It All Together: The Switch Transformer





## 2.4 Improved Training and Fine-Tuning Techniques





**2.4.1 Selective precision with large sparse models**

**2.4.2 Smaller parameter initialization for stability**


**2.4.3 Regularizing large sparse models**

# 3 Scaling Properties
# 4 Downstream Results
# 5 Designing Models with Data, Model, and Expert-Parallelism
# 6 Related Work


# 7 Discussion
- FAQ

|No.|疑問|回答|
|---|---|---|
|1|パフォーマンスが良いのはパラメータが多いからでは？||
|2|計算資源が乏しい環境で使える？||
|3|||
|4|モデルは縮小可能？||
|5|||
|6|なぜ今までスパースモデルが広く使われていなかった？|理由1 : デンスモデルで十分だったから。(そしてハードウェアがそれ用に進化したから)<br>理由2 : モデルの複雑さ・通信コスト・学習の不安定さ、などの課題があったから。|


# 8 Future Work

|No.|トピック|詳細|
|---|---|---|
|1|学習の安定性向上||
|2|||
|3|スケーリング||
|4|||
|5|||
|6|モダリティ|NLP以外のモダリティや、モダリティをまたがるモデルの開発。|



# 9 Conclusion
- Switch Transformersはスケーラブルで効果的なNLPモデル。
- MoEを簡素化して学習を安定させた。
- 同等サイズのデンスモデルよりサンプル効率を向上させた。
- デンスモデル(T5)と比較して、学習速度を大幅に改善した。
- pre-training、Fine-tuning、マルチタスクトレーニング、様々なタスクで優れている。


# Appendix

- A: Switch for Attention




- B: Preventing Token Dropping with No-Token-Left-Behind



- C: Encouraging Exploration Across Experts


- D: Switch Transformers in Lower Compute Regimes
    - Switch Transformersはスケールが小さい場合も有効に機能します。
    - Expertsが2, 4, 8個でも(同じFLOPのモデルと比較して)性能は向上します。
    - 1コアあたり1expertをオススメします。


- E: Relation of Upstream to Downstream Model Performance


- F: Pseudo Code for Switch Transformers
    - 割愛。元論文にTensorflow2のコード有り。
