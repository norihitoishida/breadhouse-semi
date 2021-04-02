# Information

|Topic|Description|
|---|---|
|タイトル|Efficient Processing of Deep Neural Networks: A Tutorial and Survey|
|日付|2017/03/27|
|著者|V Sze, YH Chen, TJ Yang, JS Emer|
|所属||
|リンク|[arXiv:1703.09039 [cs.CV]](https://arxiv.org/abs/1703.09039)|
|概要|DNN用ハードウェア・アーキテクチャのチュートリアル|
|備考|Published in: Proceedings of the IEEE ( Volume: 105, Issue: 12, Dec. 2017)|

***

# Table of contents
- [1 INTRODUCTION](#1-INTRODUCTION)
- [2 BACKGROUND ON DEEP NEURAL NETWORKS](#2-BACKGROUND-ON-DEEP-NEURAL-NETWORKS)
    - A. Artificial Intelligence and DNNs
    - B. Neural Networks and Deep Neural Networks (DNNs)
    - C. Inference versus Training
    - D. Development History
    - E. Applications of DNN
    - F. Embedded versus Cloud
- [3 OVERVIEW OF DNNS](#3-OVERVIEW-OF-DNNS)
    - A. Convolutional Neural Networks (CNNs)
    - B. Popular DNN Models
- [4 DNN DEVELOPMENT RESOURCES](#4-DNN-DEVELOPMENT-RESOURCES)
    - A. Frameworks
    - B. Models
    - C. Popular Datasets for Classification
    - D. Datasets for Other Tasks
- [5 HARDWARE FOR DNN PROCESSING](#5-HARDWARE-FOR-DNN-PROCESSING)
    - A. Accelerate Kernel Computation on CPU and GPU Platforms
    - B. Energy-Efficient Dataflow for Accelerators
- [6 NEAR-DATA PROCESSING](#6-NEAR-DATA-PROCESSING)
    - A. DRAM
    - B. SRAM
    - C. Non-volatile Resistive Memories
    - D. Sensors
- [7 CO-DESIGN OF DNN MODELS AND HARDWARE](#7-CO-DESIGN-OF-DNN-MODELS-AND-HARDWARE)
    - A. Reduce Precision
    - B. Reduce Number of Operations and Model Size
- [8 BENCHMARKING METRICS FOR DNN EVALUATION AND COMPARISON](#8-BENCHMARKING-METRICS-FOR-DNN-EVALUATION-AND-COMPARISON)
    - A. Metrics for DNN Models
    - B. Metrics for DNN Hardware
- [9 SUMMARY](#9-SUMMARY)


# 1 INTRODUCTION

# 2 BACKGROUND ON DEEP NEURAL NETWORKS
- 本セクションではAIの文脈におけるDNNの位置づけ、開発の動機、歴史等を説明します。
- A. Artificial Intelligence and DNNs
    - DNNはAIの1分野で、脳の活動を模倣して考案されたモデルです。
    - 脳の活動を元に考えられた他にモデルとしてSpiking computing等があります。
- B. Neural Networks and Deep Neural Networks (DNNs)
    - DNNは線型結合と活性化による非線形変換を多重に行います。
    - 中間層の数は1000を超える場合があります。
    - 浅いNNに比べて、複雑で抽象的な特徴量を学習できます。
    - 例えば画像をDNNに入力すると、線やエッジ等の特徴量を認識し解釈できます。
    - この様な特徴から、様々な分野で優れた成績を残しています。
- C. Inference versus Training
    - DNNは学習フェーズと推論フェーズがあります。
    - 学習では、ロスを最小化するように重みが勾配法で更新されます。
    - Backpropagationを用いる事で効率的に勾配を計算できます。
    - メモリを保持する大量のストレージ領域が必要です。
    - また、Backpropagation時は高い精度が必要です。
    - よって、(後のセクションで紹介する)精度を下げて計算量を抑える手法は推論時に使います。
    - 学習の効率化と安定性向上の為に様々な手法が用いられます。(Batch Normalization, Fine tuning等)
    - この論文では学習時ではなく推論時の効率化に焦点を当てます。
- D. Development History
- E. Applications of DNN
- F. Embedded versus Cloud

# 3 OVERVIEW OF DNNS

# 4 DNN DEVELOPMENT RESOURCES

# 5 HARDWARE FOR DNN PROCESSING
# 6 NEAR-DATA PROCESSING
# 7 CO-DESIGN OF DNN MODELS AND HARDWARE
# 8 BENCHMARKING METRICS FOR DNN EVALUATION AND COMPARISON
# 9 SUMMARY
- DNNは様々な分野で成果を出してるけど計算量も大きいので