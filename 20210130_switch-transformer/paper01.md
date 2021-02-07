# 概要

|Topic|Description|
|---|---|
|タイトル|Switch Transformers: Scaling to Trillion Parameter Models with Simple and Efficient Sparsity|
|日付|2021/01/11|
|著者|W Fedus, B Zoph, N Shazeer|
|所属|Google Brain|
|リンク|[arXiv:2101.03961 [cs.LG]](https://arxiv.org/abs/2101.03961)|
|概要|TransformerのMixture of Expertsモデル|
|備考||

***

# 目次

- [1 Introduction](#1-Introduction)
- [2 Switch Transformer](#2-Switch-Transformer)
    - 2.1 Simplifying Sparse Routing
        - 2.1.1 Mixture of Expert Routing
        - 2.1.2 Switch Routing: Rethinking Mixture-of-Experts
    - 2.2 Efficient Sparse Routing 
        - 2.2.1 Distributed Switch Implementation
        - 2.2.2 A Differentiable Load Balancing Loss
    - 2.3 Putting It All Together: The Switch Transformer 
    - 2.4 Improved Training and Fine-Tuning Techniques 
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

# 1 Introduction
# 2 Switch Transformer
# 3 Scaling Properties
# 4 Downstream Results
# 5 Designing Models with Data, Model, and Expert-Parallelism
# 6 Related Work
# 7 Discussion
# 8 Future Work
# 9 Conclusion
# Appendix


