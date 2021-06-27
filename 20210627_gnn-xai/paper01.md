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
- 近年のGNNのXAI手法はGNN Explainer, PG Explainer, PGM Explainerなどが有る
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
- GNNの亜種 : GCN, GAT, GIN
- GNNのXAIの紹介
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
- Q1 : サブグラフの重要度が分かるとなぜ嬉しいのか
- A1-1 : サブグラフのうち、複雑なネットワークを構成する単純な要素をモチーフといい、多くドメインでグラフ全体の機能を決定する可能性が有るから(例:分子)
- A1-2 : サブグラフは人間にとって直感的で分かりやすいから
- Q2 : 既存手法の問題点は？
- A2-1 : 現状、個々の入力サンプルに対する説明を直接提供できない(例:XGNNは入力に依存しない)
- A2-2 : 現状、ノード/エッジの重要度しか計算できない(計算後に結合可能ならサブグラフを作れるが、必ずしも結合可能なことは保証されない)
- A2-3 : 現状、入力に対するノード/エッジの説明は可能だが、ノード/エッジ相互の説明はできない
- 式(1)は問題の定式化 : 「訓練済みモデルf」と「入力グラフG」と「Gのサブグラフ集合」をスコアリング関数に入力し、説明を生成する(全探索)
- 全探索は効率的でないのでMCTSを用いる
    - `visiting count`と`reward`を記録して検索空間を減らしていく
    - プルーニングアクションにドメイン知識を組み込んで良い    
- スコアリング関数にはShapley値を用いる
    - `reward`はスコアリング関数設計に依存するので注意
    - 「サブグラフを入力する」という方法では、異なる構造のグラフ間の比較がうまくできない
    - 大域的なShapley値の計算コストが高いので、サブグラフ周辺のみを用いて近似計算する
    - ノード毎の隣接ノード数は異なる為、ターゲットノード数を固定せずにMCサンプリングする
- graph classification以外のタスクにも適用可能
    - node classification, link prediction, ...
- GNNをブラックボックスとみなしているので、GCN, GAT, GIN, Line-GNN等、様々なGNNモデルに適用可能

# 4 Experimental Studies
- データセット : MUTAG/BBBP/Graph-SST2/BA-2Motifs/BA-Shape
- モデル : GCN/GAT/GIN
- XAI : SubgraphX/MCTS GNN/GNNExplainer/PGExplainer
    - MCTS GNN : サブグラフを入力した時の出力をスコアリング関数にする(Shapley値を計算しない)
- Figures
    - Fig2 : Graph-SST2 + GAT
    - Fig3 : BA-2Motifs + GCN, 上は正予測、下は誤予測
    - Fig4 : MUTAG + GIN, 2つの正しい予測の説明
    - Fig5 : Fidelity-Sparsityカーブ
    - Fig6 : BA-Shape + GCN
- 定量的実験 : Fidelity-Sparsityカーブ(Figure 5)
- 定性的実験 : 時間コスト比較(Table 2)
- プルーニングアクション :  Low2high(高Fidelity)とHigh2low(低コスト)

# 5 Conclusions
- 既存のGNNのXAI手法はエッジやノードの重要性を説明するが、サブグラフの重要性を説明した方が人間にわかりやすい
- SubgraphXという、サブグラフを使って説明する手法を提案した
- サブグラフのShapley値を計算する
- サブグラフはMCTSで探索し、aggregationの範囲内のみShapley値を計算する
- 受容可能なTime complexityを保ちながらGNNの説明性を獲得できた

# Appendix
- Appendix.A : データセットとGNNモデル
    - データセット
        - MUTAG
        - BBBP
        - Graph-SST2
        - BA-2Motifs
        - BA-Shape
    - GNNモデル
        - GCN
        - GIN
        - GAT
- Appendix.B : Graph Classification Model
    - Fig.7 : BBBP, MUTAG
    - Fig.8 : Graph-SST2
- Appendix.C : Node Classification Model
    - Fig.9 : BA-Shapeの説明を可視化