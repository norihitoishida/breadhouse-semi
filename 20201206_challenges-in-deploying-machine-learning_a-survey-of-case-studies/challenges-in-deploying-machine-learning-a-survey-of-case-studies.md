# 概要

|Topic|Description|
|---|---|
|タイトル|Challenges in Deploying Machine Learning: a Survey of Case Studies|
|日付|2020/11/18|
|著者|A Paleyes, RG Urma, ND Lawrence|
|所属|Department of Computer Science University of Cambridge, Cambridge Spark|
|リンク|[arXiv:2011.09926 [cs.LG]](https://arxiv.org/abs/2011.09926)|
|概要|MLモデルの実運用の際のプラクティス。|
|備考|[The ML-Retrospectives, Surveys & Meta-Analyses Workshop, NeurIPS 2020](https://ml-retrospectives.github.io/neurips2020/)|


# 目次
- [1 Introduction](#1-Introduction)
- [2 Machine Learning Deployment Workflow](#2-Machine-Learning-Deployment-Workflow)
- [3 Data Management](#3-Data-Management)
    - 3.1 Data collection
    - 3.2 Data preprocessing
    - 3.3 Data augmentation
    - 3.4 Data analysis
- [4 Model Learning](#4-Model-Learning)
    - 4.1 Model selection
    - 4.2 Training
    - 4.3 Hyper-parameter selection
- [5 Model Verification](#5-Model-Verification)
    - 5.1 Requirement encoding
    - 5.2 Formal Verification
    - 5.3 Test-based Verification
- [6 Model Deployment](#6-Model-Deployment)
    - 6.1 Integration
    - 6.2 Monitoring
    - 6.3 Updating
- [7 Cross-cutting aspects](#7-Cross-cutting-aspects)
    - 7.1 Ethics
    - 7.2 End users’ trust
    - 7.3 Security
- [8 Discussion of potential solutions](#8-Discussion-of-potential-solutions)
    - 8.1 Tools and services
    - 8.2 Holistic approaches
- [9 Further Work](#9-Further-Work)
- [10 Conclusion](#10-Conclusion)

# 1 Introduction
- MLモデルの本番投入に関する包括的なレポートが少ない！
- 本論文の主なContributionは、フェーズごとの課題をまとめた事
- 構成
    - MLモデルのデプロイのワークフロー(セクション2)
    - ワークフローのフェーズ毎の課題(セクション3〜6)
    - フェーズに横断的な課題(セクション7)
    - それらの課題の潜在的な解決策(セクション8)

# 2 Machine Learning Deployment Workflow
- [Ashmore+(2019)](https://arxiv.org/abs/1905.04223)に準拠して、MLモデルのデプロイのワークフローを示す。

|フェーズ|説明|
|---|---|
|データ管理 (Data management)|収集, 前処理, データ拡張, 分析|
|モデル学習 (Model learning|モデル選択, 学習, ハイパラ調整|
|モデル検証 (Model verification)|機能とパフォーマンスの確認|
|デプロイ (Model deployment)|インフラとの統合, モデルの監視と更新|

![ml-life-cycle](https://github.com/norihitoishida/breadhouse-semi/blob/main/20201206_challenges-in-deploying-machine-learning_a-survey-of-case-studies/img/ml-life-cycle.png "ml-life-cycle")

- 各フェーズの課題一覧

- 〜ここにTable1を追加〜


# 3 Data Management


# 4 Model Learning


# 5 Model Verification


# 6 Model Deployment


# 7 Cross-cutting aspects


# 8 Discussion of potential solutions


# 9 Further Work
- このサーベイでやらなかった事
    - 非技術的な課題
    - 産業分野の比較分析
    - セクション8.1で簡単に紹介したツールの詳細な説明と比較

# 10 Conclusion
- MLモデルを本番環境にデプロイする際に、データ管理、学習、検証、デプロイの各フェーズで発生しうる課題を示した
- フェーズを横断的な課題(倫理やセキュリティ)を示した
- MLの実務応用で得られた経験は共有されにくい傾向があるので、可能なら公開しよう！