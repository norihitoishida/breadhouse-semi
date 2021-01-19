# 概要

|Topic|Description|
|---|---|
|タイトル|Opportunities and Challenges in Explainable Artificial Intelligence (XAI): A Survey|
|日付|2020/06/16|
|著者|Arun Das, Paul Rad|
|所属|IEEE|
|リンク|[arXiv:2006.11371 [cs.CV]](https://arxiv.org/abs/2006.11371)|
|概要|XAI(Explainable AI)サーベイ。|
|備考|[参考 : XAI技術の効能をユーザ実験で評価する研究(Hara, 2020)](https://www.slideshare.net/SatoshiHara3/xai-238616601)|


# 目次
- [1 Introduction](#1-Introduction)
- [2 Taxonomies and Organization](#2-Taxonomies-and-Organization)
- [3 Definitions and Preliminaries](#3-Definitions-and-Preliminaries)
- [4 Scope of Explanation](#4-Scope-of-Explanation)
- [5 Differences in the Methodology](#5-Differences-in-the-Methodology)
- [6 Model Usage or Implementation Level](#6-Model-Usage-or-Implementation-Level)
- [7 Evaluation Methodologies, Issues, and Future Directions](#7-Evaluation-Methodologies,-Issues,-and-Future-Directions)
- [8 Conclusion](#8-Conclusion)

# 1 Introduction
- DNNをはじめとするBlack-Box Modelは説明可能性 (Explainability) が低い！
- Explainabilityが低いモデルには以下のような問題が発生しうる。

|問題の種類|どの様な問題が起こるか|
|---|---|
|バイアス・倫理|- StyleGANの学習データに白人の画像が多く, オバマ元大統領の顔を白人に復元<br>- 既存の履歴書で採用AIを学習させたら, 女性というだけで不当に評価を下げてしまった|
|堅牢性|- Adversarial Examples (例 : パンダとテナガザル)<br>- クラウド上で動いているモデルを解析 (例 : DeepPeep)<br>- 悪意を持ってモデルを学習させる (例 : Microsoft Tay)|
|品質保証|- どこまでテストすれば十分かわからない (例 : 自動運転AIでカンガルーの飛出しを検知できなかった)|
|法的リスク|- 商用アカウントをスパム判定で誤BANした際の逸失利益の扱い<br>- PL法違反|

- だからXAI(Explainable AI = 説明可能AI)の研究は大事！
- 本論文ではXAIの様々なアプローチを説明します。

# 2 Taxonomies and Organization
- 本論文では以下の3つの観点から手法を分類します。

|観点|区分|
|---|---|
|Scope (範囲)|Local : データインスタンスごとに説明マップを生成する。<br>Global : データの集合に対して説明マップを生成する。|
|Methodology (方法論)|BackProb : 勾配を用いる。<br>Perturbation : 摂動を用いる。|
|Usage (使用方法)|Intrinsic : モデルに依存する。<br>Post-Hoc : モデルに依存しない。学習済みモデルに適用可能。|

- 本論文の構成は以下の通りです。
    - [セクション3](#3-Definitions-and-Preliminaries) : 用語の定義等の説明。
    - [セクション4](#4-Scope-of-Explanation) : Scopeによる分類の説明。
    - [セクション5](#5-Differences-in-the-Methodology) : Methodologyによる分類の説明。
    - [セクション6](#6-Model-Usage-or-Implementation-Level) : Usageによる分類の説明。
    - [セクション7](#7-Evaluation-Methodologies,-Issues,-and-Future-Directions) : XAIの評価方法の紹介。
    - [セクション8](#8-Conclusion) : まとめと結論。

# 3 Definitions and Preliminaries
- Explainability(説明可能性)やInterpretability(解釈可能性)等、用語の定義が文献によって微妙に違う！
- そこで、本論文では以下のように定義します。

|用語|定義|
|---|---|
|Interpretability (解釈可能性)||
|Interpretation (解釈)|モデルの出力を人間が理解できるように簡略化した表現。|
|Explanation (説明)|入力のfeatureの、出力に与える重要性や出力との関係性を表すメタ情報。|
|White-box||
|Black-box||
|Transparent ()||
|Trustability ()||
|Bias ()||
|Fairness ()||


# 4 Scope of Explanation

# 5 Differences in the Methodology

# 6 Model Usage or Implementation Level

# 7 Evaluation Methodologies, Issues, and Future Directions

# 8 Conclusion
- Table5を乗っける(説明と共に)


