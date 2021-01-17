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

***

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
|データ管理 (Data management)|収集, 前処理, 拡張, 分析|
|モデル学習 (Model learning|モデル選択, 学習, ハイパラ調整|
|モデル検証 (Model verification)|機能とパフォーマンスの確認|
|デプロイ (Model deployment)|統合, 監視, 更新|

![ml-life-cycle](https://github.com/norihitoishida/breadhouse-semi/blob/main/20201206_ml-deploying/img/ml-life-cycle.png "ml-life-cycle")


# 3 Data Management
- 品質の良いデータはMLパイプラインに不可欠
- 本セクションでは、データの収集, 前処理, 拡張, 分析, の各ステップそれぞれに関する課題を示す

|ステップ|起こりうる問題|対策の例|
|---|---|---|
|収集|データの場所や構造が明確でないケース|ドメイン知識でカバー|
|前処理|欠損値の補完, データ形式の変換, 表記ゆれの修正等を行うのが大変なケース|ツールで自動化|
|前処理|データが様々な場所に存在するケース|ツールで自動化|
|拡張|膨大な量のデータにラベリングする必要があるケース|教師なし学習|
|拡張|ラベリングにドメイン知識が必要なケース|弱教師あり学習|
|拡張|学習データのばらつきが小さすぎるケース|ドメイン知識でカバー|
|分析|データに潜在的なバイアスや予期しない分布が存在するケース|ツールで可視化|


# 4 Model Learning
- 本セクションでは、モデル選択, 学習, ハイパラ調整, の各ステップそれぞれに関する課題を示す

|ステップ|起こりうる問題|対策の例|
|---|---|---|
|モデル選択|モデルが複雑過ぎて試行錯誤の回数が稼げない|簡単なモデルから試す|
|モデル選択|計算リソースの制限に引っかかる|軽いモデルを試す|
|モデル選択|モデルの解釈性が悪く開発が進まない|解釈性のあるモデルから試す|
|学習|学習に金銭的コストがかかる|軽いモデルを試す|
|学習|学習によって温室効果ガス排出量が増える|軽いモデルを試す|
|ハイパラ調整|ハイパラ調整に時間や金銭的コストが掛かる|HyperbandやBO等の手法を試す|
|ハイパラ調整|ハードウェア依存性がある|適切な条件でHPOする|

# 5 Model Verification
- MLモデルの機能要件や汎化性能を確認する必要がある
- ある指標のパフォーマンスが必ずしもビジネス上の価値につながるとは限らないので注意
- 本セクションでは、要件のエンコード, フォーマル検証, テストベース検証, の各ステップそれぞれに関する課題を示す

|ステップ|確認すべき点|
|---|---|
|要件のエンコード|パフォーマンス指標|
|要件のエンコード|ビジネス価値指標|
|フォーマル検証|機能要件の確認|
|テストベース検証|汎化性能の確認|


# 6 Model Deployment
- 基本的にはDevOpsの原則が適用できるが、ML固有の課題も存在する
- [Dang+(2019)](https://ieeexplore.ieee.org/abstract/document/8802836)ではその研究の方向性のロードマップを示し、AIOpsと名付けている
- 本セクションでは、統合, 監視, 更新, の各ステップそれぞれに関する課題を示す

|ステップ|起こりうる問題|
|---|---|
|統合|通常のDevOpsと相性が悪い場合がある(コードの再利用等)|
|監視|意図しないフィードバックループによる過学習|
|監視|外れ値耐性|
|更新|コンセプトドリフト|
|更新|CD/CIの複雑さ|

# 7 Cross-cutting aspects
- 本セクションでは、フェーズを横断する課題を示す
- 本セクションでは、倫理, 信頼, セキュリティ, に関する課題を示す
- Alan Turing InstituteのAI倫理に関するレポート([Leslie, D. (2019)](https://www.turing.ac.uk/sites/default/files/2019-06/understanding_artificial_intelligence_ethics_and_safety.pdf))
- エンドユーザの信頼を得る方法
    - コミュニケーションを取る
    - 技術的な進歩ではなく、進捗状況を共有する
    - 説明責任のためのメカニズムを確立する
    - プロジェクトの初期段階から関わってもらう
- 敵対的攻撃の例
    - [Microsoft’s Tay (2016)](https://spectrum.ieee.org/tech-talk/artificial-intelligence/machine-learning/in-2016-microsofts-racist-chatbot-revealed-the-dangers-of-online-conversation)
        - Twitter上での会話を通じて学習するチャットボット
        - 悪意有るユーザによって学習され、人種差別等の発言
        - Microsoftは公開を停止しポリコレ版のZoをリリース
        - 政治や宗教などのトピックについて、会話をしないように設計されている
    - [DeepPeep (Jha+, 2020)](https://arxiv.org/abs/2007.15248)
        - クラウド上で実行されているDNNモデルの構造等を解読
        - 順伝播/逆伝播時間, GPU使用率, メモリ使用量を見る
        - ネットワークトポロジ, ブロック, cuBLASカーネル等を推測
    - [Model Inversion Attacks (Fredrikson+, 2015)](https://dl.acm.org/doi/10.1145/2810103.2813677)
        - NNによる顔の分類タスク(ラベルは名前)において、confidence valueの情報を用いて学習データを復元する

|分類|起こりうる問題|
|---|---|
|倫理|プライバシー侵害|
|倫理|学習データに起因するバイアス (例: 性別, 人種)|
|倫理|モデル出力の権利 (例: アート, DeepFake)|
|倫理|モデル出力の恣意的な操作, 悪用 (例: Civil unrest)|
|信頼|解釈可能性が低く使ってもらえない|
|信頼|UX/UIが悪くて使ってもらえない|
|セキュリティ|学習データへの攻撃 (Data poisoning)|
|セキュリティ|モデルの構造や重みを覗き見る (Model stealing)|
|セキュリティ|モデルから学習データを復元 (Model inversion)|


# 8 Discussion of potential solutions
- MLモデルの本番運用をスケーラブルにしたい
- つまり、その恩恵を受ける可能性のあるすべてのビジネスがアクセスできるようにしたい
- そのためには、問題点を理解して、それらに対処するツール, サービス, ベストプラクティスを共有することが重要
- ツールやサービスは便利だが、依存関係の管理などの保守コストが掛かるので注意
- ストレージ, API, モデル監視機能等を持つ, MLプラットフォームのサービスの例
    - [AWS SageMaker](https://aws.amazon.com/jp/sagemaker/)
    - [Microsoft AzureML](https://azure.microsoft.com/ja-jp/free/machine-learning)
    - [Uber Michelangelo](https://eng.uber.com/michelangelo-machine-learning-platform/)
    - [TensorFlow TFX](https://www.tensorflow.org/tfx?hl=ja)
- 弱教師あり学習のツールの例
    - [Snorkel](https://www.snorkel.org/)
    - [Snuba](https://github.com/getsentry/snuba)
    - [cleanlab](https://github.com/cgnorthcutt/cleanlab)
- 開発のベストプラクティスの例
    - [GoogleのML開発ベストプラクティス](https://developers.google.com/machine-learning/guides/rules-of-ml)
    - [TRL4ML](https://arxiv.org/abs/2006.12497): アジャイル開発やスクラム開発に変わるML専用の開発手法
    - [DOA](https://tborchertblog.wordpress.com/2020/02/13/28/): データ指向アーキテクチャで、データの追跡や収集が楽なためMLモデルに向いている

# 9 Further Work
- このサーベイでやらなかった事
    - 非技術的な課題
    - 産業分野の比較分析
    - セクション8.1で簡単に紹介したツールの詳細な説明と比較

# 10 Conclusion
- MLモデルを本番環境にデプロイする際に、データ管理、学習、検証、デプロイの各フェーズで発生しうる課題を示した
- フェーズを横断的な課題(倫理やセキュリティ)を示した
- MLの実務応用で得られた経験は共有されにくい傾向があるので、可能なら公開しよう！