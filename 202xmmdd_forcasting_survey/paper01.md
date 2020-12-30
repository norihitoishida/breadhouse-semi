# 概要

|Topic|Description|
|---|---|
|タイトル|Forecasting: theory and practice|
|日付|2020/12/04|
|著者|F Petropoulos, et al.|
|所属|University of Bath, et al.|
|リンク|[arXiv:2012.03854 [stat.AP]](https://arxiv.org/abs/2012.03854)|
|概要|時系列予測の歴史、理論、実践的アプローチのまとめ。|
|備考|[著者による](https://twitter.com/fotpetr/status/1332025434867904514)と、この分野で初めての`encyclopedic-type`のアプローチらしい。|


# 目次
- [1 Introduction](#1-Introduction)
- [2 Theory](#2-Theory)
- [3 Practice](#3-Practice)
    - 3.1 Data collection
    - 3.2 Data preprocessing
    - 3.3 Data augmentation
    - 3.4 Data analysis
- [4 Forecasting: benefits, practices, value, and limitations](#4-Forecasting:-benefits,-practices,-value,-and-limitations)
    - 4.1 Model selection
    - 4.2 Training
    - 4.3 Hyper-parameter selection
- [Appendix A List of acronyms](#Appendix-A-List-of-acronyms)
    - 5.1 Requirement encoding
    - 5.2 Formal Verification
    - 5.3 Test-based Verification
- [Appendix B Software](#Appendix-B-Software)
    - 6.1 Integration
    - 6.2 Monitoring
    - 6.3 Updating
- [Appendix C Data sets](#Appendix-C-Data-sets)
    - 7.1 Ethics
    - 7.2 End users’ trust
    - 7.3 Security

# 1 Introduction
- MLモデルの本番投入に関する包括的なレポートが少ない！
- 本論文の主なContributionは、フェーズごとの課題をまとめた事
- 構成
    - MLモデルのデプロイのワークフロー(セクション2)
    - ワークフローのフェーズ毎の課題(セクション3〜6)
    - フェーズに横断的な課題(セクション7)
    - それらの課題の潜在的な解決策(セクション8)

# 2 Theory
- [Ashmore+(2019)](https://arxiv.org/abs/1905.04223)に準拠して、MLモデルのデプロイのワークフローを示す。

|フェーズ|説明|
|---|---|
|データ管理 (Data management)|収集, 前処理, 拡張, 分析|
|モデル学習 (Model learning|モデル選択, 学習, ハイパラ調整|
|モデル検証 (Model verification)|機能とパフォーマンスの確認|
|デプロイ (Model deployment)|統合, 監視, 更新|

![ml-life-cycle](https://github.com/norihitoishida/breadhouse-semi/blob/main/20201206_ml-deploying/img/ml-life-cycle.png "ml-life-cycle")


# 3 Practice
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


# 4 Forecasting: benefits, practices, value, and limitations
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

# Appendix A List of acronyms

# Appendix B Software

# Appendix C Data sets