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
    - NNは1940年代に提案されました。
    - 実用化され始めたのは1980年代後半のLeNetからです。
    - モダンなDNNが登場したのは2010年代初頭、AlexNet以降です。
    - 2010年代前半におけるDNNの成功の要因は主に3点あります。
    1. 大量のデータが有ること
    1. ハードウェアの進化
    1. フレームワークの発達
    - AlexNetがImageNetコンテスト2012で優勝した際、GPUで計算を行っていました。
    - 以降、多くのDNNがGPU上で稼働しています。
- E. Applications of DNN
    - 様々なドメインでDNNを用いたアプリケーションが使用されています。
    - 画像/動画(画像分類/物体検知/セグメンテーション/行動認識)
    - 音声/言語(音声認識/音声生成/翻訳)
    - 医療(ゲノム処理/画像診断)
    - ゲーム(Atari/碁)
    - ロボティクス(把持/計画/視覚ナビゲーション/ドローン制御/自動運転)
    - 他
        - 金融(取引/リスクアセスメント)
        - インフラ(安全性向上/トラフィック向上)
        - 天気予報/イベント検知
- F. Embedded versus Cloud
    - 学習には大量のデータと計算リソースが必要です。通常クラウドで行われます。
    - 推論はエッジでも行われます。例を示します。
        - 通信遅延のリスクが高い場合
        - 通信がセキュリティ上のリスクになる場合
    - エッジ機器にはエネルギー消費/計算量/メモリ量の制限があります。
 
# 3 OVERVIEW OF DNNS

# 4 DNN DEVELOPMENT RESOURCES

# 5 HARDWARE FOR DNN PROCESSING
# 6 NEAR-DATA PROCESSING
# 7 CO-DESIGN OF DNN MODELS AND HARDWARE
# 8 BENCHMARKING METRICS FOR DNN EVALUATION AND COMPARISON
# 9 SUMMARY
- DNNは様々な分野で成果を出してるけど計算量も大きいので