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
- DNNは様々なタスクで優れた結果を残していますが、計算が複雑です。
- 現在、主にGPUを用いて処理が行われています。
- 本論文では、DNN、DNN用ハードウェアアーキテクチャ、効率化の手法等を紹介します。

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
- 基礎的なFFN, 内部メモリを持つRNN, 畳み込み処理を行うCNN等があります。
- Dropout:接続を切ることで計算量を減らす手法。
- Weight sharing:層間で重みを共有しメモリ量を減らす手法。
- A. Convolutional Neural Networks (CNNs)
    - 本論文では画像分類に焦点を当てます。
    - 画像処理で一般的なDNNはCNNです。CNNは深いレイヤを持ちます。
    - 高次元の畳み込みを行い、抽象化された情報を保持するfeature mapを生成します。
    - 活性化にはシンプルで高速なReLU(及びその亜種)が用いられることが多いです。
    - 音声認識タスクではmaxoutが効果的です。
    - プーリングを行う事で移動や歪みに対して安定します。
    - Batch Normalization(BN)はレイヤ間の入力分布を正規化する事で高速化・安定化を図ります。
    - BNの多くはConv層とFC層の間で行われます。
    - BN以前の安定化手法としてlocal response normalization(LRN)がありますが、現在はあまり使われていません。
- B. Popular DNN Models
    - 著名なDNNモデルを紹介します。
    - それぞれのレイヤ数/タイプ/形状(フィルタやチャネル情報)/接続を理解することで、ハードウェアレベルの効率化の為に重要です。
    - MACs = 積和演算数
        - LeNet(1989)
            - Input:28x28x1
            - Layer:Conv2, FC2
            - Filter:5x5, 6,16
            - Pooling:mean, 2x2
            - Act:sigmoid
            - Weight:60k
            - MACs:341k
        - AlexNet(2012)
            - Input:28x28x1
            - Layer:Conv5, FC3
            - Filter:3×3\~11×11, 96\~384
            - Channel:3\~256
            - Pooling:max, 3x3
            - Act:ReLU
            - Weight:61M
            - MACs:724M
            - Note:GPU, LRN, Parallel
        - Overfeat(2013)
            - Input:231×231x3
            - Layer:Conv5, FC3
            - Filter:5x5, 6,16
            - Weight:146M
            - MACs:2.8G
        - VGG-16(2014)
            - Input:224×224x3
            - Layer:Conv13, FC3
            - Filter:3x3
            - Pooling:mean, 2x2
            - Weight:138M
            - MACs:15.5G
        - GoogLeNet(2014)
            - Filter:1x1 \~ 5x5, 
            - Pooling:max, 3x3
            - Note:BN, Parallel
        - ResNet(2015)
            - Weight:60M(ResNet-152)
            - MACs:11.3G(ResNet-152)
            - Note:Skip Connect

# 4 DNN DEVELOPMENT RESOURCES
- DNNの高速な開発を支える、豊富な開発リソースを紹介します。
- A. Frameworks
    - Caffe, Tensorflow, Torch, Theano, MXNet, CNTK
    - Keras
    - cuDNN
- B. Models
    - 様々なpre-trainedモデルが公開されている。
- C. Popular Datasets for Classification
    - MNIST:28x28x1, 10クラス, Train60k, Test10k
    - CIFAR-10:32x32x3, 10クラス, Train50k, Test10k
    - ImageNet:256×256x3, 1000クラス, Train1.3M, Test100k
- D. Datasets for Other Tasks
    - PASCAL VOC:CV(detection), 20クラス
    - COCO:CV(detection/segmentation/recognition), 91カテゴリ
    - Google Open Images:CV, 6000カテゴリ
    - Youtube dataset:CV(video), 4800クラス
    - Google AudioSet:Audio, 632イベント
# 5 HARDWARE FOR DNN PROCESSING
- モダンなハードウェアプラットフォームはDNN専用の処理を備えています。
- DNNの処理は積和演算(MAC)なので並列化が容易です。2種類の並列化パラダイムを紹介します。
    - Temporal architectures
        - ALUは相互に通信しない
        - SIMD, SIMT : 単一命令でマルチデータ/マルチスレッド処理
        - CPU, GPU
        - 変換を行い乗算回数を減らす事で高速化
    - Spatial architectures
        - ALUは個別のコントロールを持ち、相互に通信してデータフローを形成する
        - ASIC, FPGA
        - メモリを再利用することで省エネ化
![Parallel paradigms](./img/p1-fig17-alus.png)
- A. Accelerate Kernel Computation on CPU and GPU Platforms
    - ConvもFCも行列演算に帰着できます。ConvはToeplitz行列の形に変換する事で行列演算に変換できますが、Toeplitz行列は冗長なため、ストレージが非効率になるかメモリアクセスパターンが複雑になります。
    - 行列演算用のソフトウェアが公開されています。
        - CPU:OpenBLAS, Intel MKL
        - GPU:cuBRAS, cuDNN
    - 行列演算は離散フーリエ変換のアダマール積で表現できます。
    - FFTを用いることで計算量を大幅に削減できますが、必要なストレージ容量が大きくなる等のデメリットもあります。
- B. Energy-Efficient Dataflow for Accelerators
# 6 NEAR-DATA PROCESSING
- A. DRAM
- B. SRAM
- C. Non-volatile Resistive Memories
- D. Sensors
# 7 CO-DESIGN OF DNN MODELS AND HARDWARE
- A. Reduce Precision
- B. Reduce Number of Operations and Model Size
# 8 BENCHMARKING METRICS FOR DNN EVALUATION AND COMPARISON
- A. Metrics for DNN Models
- B. Metrics for DNN Hardware
# 9 SUMMARY
- DNNは様々な分野で成果を出してるけど計算量も大きいので