# 概要

|Topic|Description|
|---|---|
|タイトル|On Explainability of Graph Neural Networks via Subgraph Explorations|
|日付|2021/05/31|
|著者|Hao Yuan, Haiyang Yu, Jie Wang, Kang Li, Shuiwang Ji|
|リンク|[arXiv:2102.05152 [cs.LG]](https://arxiv.org/abs/2102.05152)|
|概要|GNNのXAI|
|備考|Accepted by ICML 2021|


# 目次
- [0 Abstract](#0-Abstract)
- [1 Introduction](#1-Introduction)
- [2 Rekated Work](#2-Rekated-Work)
- [3 The Proposed SubgraphX](#3-The-Proposed-SubgraphX)
- [4 Experimental Studies](#4-Experimental-Studies)
- [5 Conclusions](#5-Conclusions)
- [Appendix](#Appendix)

# 0 Abstract
- 基本的にGNNはブラックボックス
- 既存のGNNのXAI手法はサブストラクチャを無視している
- SubgraphXという、サブグラフを使って説明する手法を提案する
- これは明示的・直接的なサブグラフによるGNNを説明としては初めての試み
- トレーニング済みのGNNにグラフを入力した際、モンテカルロ木探索でShapley値の大きいサブグラフを探索する
- Shapley値を使うことでサブグラフの形状に依存せず比較できる
- Shapley値を近似計算する(aggregationの範囲内でのみ計算)ことで計算を効率化する
- 安価なコストで説明性を得られる事を実験で確認した


# 1 Introduction
- GNNはグラフデータを直接扱えるがブラックボックスモデル
- 近年様々なDeep learningモデルに対するXAI研究が進んでいる
- しかし、画像・テキスト・テーブル等のモデルのグリッド性を仮定するXAI手法はGNNに適用できない
- 近年のGNN専用XAI手法は以下のものが有る
    - GNN Explainer
    - PG Explainer
    - PGM Explainer
- これらは単一のノードやエッジの重要性に焦点を当てている(サブグラフを考慮していない)
- 今回の提案手法SubgraphXは、サブグラフの重要性を計算可能
- GNNの処理はAggregate/Combinate/Readoutの3段階
    - Aggregate : 隣接するノードを集約する
    - Combinate : 更新する
    - Readout : node featuresを集約する
- Aggregate処理は「異なるサブグラフ間の相互作用の計算」と解釈できる
- Aggregateする範囲内だけでShapley値を計算する(全体で計算しない)
- 定性的/定量的実験を行い、安価なコストで説明性を得られる事を確認した

# 2 Rekated Work
- GNNの亜種 : GCN, GAT, GIN, 
- GNNのXAI
    - gradients/features-based(勾配/特徴)
        - SA, CAM, Guided BP
        - 画像の説明手法によく使われている
        - 単純で効率的だがグラフデータの特性を組み込めない
    - decomposition(分解)
        - LRP, Excitation BP, GNN-LRP 
        - Back-Propで予測を入力空間まで分解する
    - surrogate(代理モデル)
        - 単純で解釈可能なモデルを代理モデルに使う
    - generationbased(生成)
        - XGNN
        - 特定の予測を最大化するようなグラフパターンを生成する
    - perturbation-based(摂動)
        - GNNExplainer, PGExplainer, GraphMask
        - 入力featureに摂動を乗せて予測の変化を監視し、影響を測る
        - GNNExplainer : ソフトマスクを使って予測の変化前後の相互情報量を最大化
        - PGExplainer : エッジの重要度を計算、ソフトマスクではなくリパラトリックで近似
        - GraphMask : PGExplainerを全てのレイヤのエッジに適用する

# 3 The Proposed SubgraphX
- 
- 
- 
- 
- 
- 
- 

# 4 Experimental Studies
- 
- 
- 
- 
- 
- 
- 

# 5 Conclusions
- 
- 
- 
- 
- 
- 
- 

# Appendix
- Appendix.A 
- Appendix.B 
- Appendix.C 