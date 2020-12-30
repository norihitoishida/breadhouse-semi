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
    - 2.1 Introduction to forecasting theory
    - 2.2 Pre-processing data
        - 2.2.1. Unit root tests
        - 2.2.2. Time series decomposition
        - 2.2.3. Anomaly detection and time series forecasting
        - 2.2.4. Exogenous variables and feature engineering
    - 2.3 Statistical and econometric models
        - 2.3.1. Exponential smoothing models
        - 2.3.2. Time-series regression models
        - 2.3.3. Theta method and models
        - 2.3.4. Autoregressive integrated moving average (ARIMA) models
        - 2.3.5. ARCH/GARCH models
        - 2.3.6. Forecasting for multiple seasonal cycles
        - 2.3.7. State-space models
        - 2.3.8. Markov switching models
        - 2.3.9. Threshold models
        - 2.3.10. Peak over the theshold
        - 2.3.11. Forecasting with many variables
        - 2.3.12. Functional time series models
        - 2.3.13. Bayesian forecasting with copulas
        - 2.3.14. Forecasting with DSGE models
        - 2.3.15. Low and high prices in volatility models
        - 2.3.16. Robust estimation and forecasting
        - 2.3.17. Robust equilibrium-correction forecasting devices
        - 2.3.18. Forecasting with data subject to revision
        - 2.3.19. Innovation diffusion models
        - 2.3.20. The natural law of growth in competition
        - 2.3.21. Synchronic and diachronic competition
        - 2.3.22. Estimation and representation of uncertainty
        - 2.3.23. Forecasting under fat tails
    - 2.4 Variable and model selection
        - 2.4.1. Leading indicators and Granger causality
        - 2.4.2. Model complexity
        - 2.4.3. Variable selection
        - 2.4.4. Model selection
        - 2.4.5. Cross-validation for time-series data
    - 2.5 Combining forecasts
        - 2.5.1. Forecast combination: a brief review of statistical approaches
        - 2.5.2. Density forecast combinations
        - 2.5.3. Ensembles and predictive probability post processors
        - 2.5.4. The wisdom of crowds
    - 2.6 Data-driven methods
        - 2.6.1. Forecasting with big data
        - 2.6.2. Forecasting on distributed systems
        - 2.6.3. Agent-based models
        - 2.6.4. Feature-based time series forecasting
        - 2.6.5. Forecasting with bootstrap
        - 2.6.6. Bagging for time series forecasting
        - 2.6.7. Neural networks
        - 2.6.8. Deep probabilistic forecasting models
        - 2.6.9. Machine learning
        - 2.6.10. Machine learning with (very) noisy data
        - 2.6.11. Clustering-based forecasting
        - 2.6.12. Hybrid methods
    - 2.7 Methods for intermittent demands and count data
        - 2.7.1. Parametric methods for intermittent demand forecasting
        - 2.7.2. Non-parametric intermittent demand methods
        - 2.7.3. Classification methods
    - 2.8 Reasoning and mining
        - 2.8.1. Fuzzy logic
        - 2.8.2. Association rule mining
        - 2.8.3. Forecasting with text information
    - 2.9 Forecasting by aggregation
        - 2.9.1. Cross-sectional hierarchical forecasting
        - 2.9.2. Temporal aggregation
        - 2.9.3. Cross-temporal hierarchies
        - 2.9.4. Ecological inference forecasting
    - 2.10 Forecasting with judgment
        - 2.10.1. Judgmental forecasting6
        - 2.10.2. Judgmental adjustments of computer-based forecasts
        - 2.10.3. Judgmental model selection
        - 2.10.4. Panels of experts
        - 2.10.5. Scenarios and judgmental forecasting
        - 2.10.6. Trusting model and expert forecasts
    - 2.11 Evaluation, validation, and calibration
        - 2.11.1. Point, interval, and pHDR forecast error measures
        - 2.11.2. Evaluating probabilistic forecasts
        - 2.11.3. Assessing the reliability of probabilistic forecasts
        - 2.11.4. Statistical tests of forecast performance
    - 2.12 The future of forecasting theory
- [3 Practice](#3-Practice)
    - 3.1 Introduction to forecasting practice
    - 3.2 Operations and supply chain management
        - 3.2.1. Demand management
        - 3.2.2. Forecasting in the supply chain
        - 3.2.3. Forecasting for inventories
        - 3.2.4. Retail sales forecasting
        - 3.2.5. Online retail forecasting
        - 3.2.6. Promotional forecasting
        - 3.2.7. New product forecasting
        - 3.2.8. Spare parts forecasting
        - 3.2.9. Predictive maintenance
        - 3.2.10. Reverse logistics
    - 3.3 Economics and finance
        - 3.3.1. Macroeconomic survey expectations
        - 3.3.2. Forecasting GDP and inflation
        - 3.3.3. Forecasting UK unemployment
        - 3.3.4. Forecasting UK productivity
        - 3.3.5. Fiscal forecasting for government budget surveillance in Europe1
        - 3.3.6. Interest rate prediction with Markov switching models
        - 3.3.7. Term structure interest rates prediction with threshold models
        - 3.3.8. House price forecasting1
        - 3.3.9. Exchange rate forecasting
        - 3.3.10. Financial time series forecasting with range-based volatility models
        - 3.3.11. Copula forecasting with multivariate dependent financial times series
        - 3.3.12. Financial forecasting with neural networks
        - 3.3.13. Forecasting returns to investment style
        - 3.3.14. Forecasting stock returns
        - 3.3.15. Forecasting crashes in stock markets
    - 3.4 Energy
        - 
    - 3.5 Environmental applications
    - 3.6 Social good and demographic forecasting
    - 3.7 Systems and humans
    - 3.8 Other applications
    - 3.9 The future of forecasting practice
- [4 Forecasting: benefits, practices, value, and limitations](#4-Forecasting:-benefits,-practices,-value,-and-limitations)

- [Appendix A List of acronyms](#Appendix-A-List-of-acronyms)

- [Appendix B Software](#Appendix-B-Software)

- [Appendix C Data sets](#Appendix-C-Data-sets)

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
- 略語の一覧
- TODO: ソートして訳を付け、表にする

```
ACC: Ant Colony Clustering
ACD: Autoregressive Conditional Duration
ADIDA: Aggregate–Disaggregate Intermittent Demand Approach
ADL: Autoregressive Distributed Lag
ADMM: Alternating Direction Method of Multipliers
AI: Artificial Intelligence
AIC: Akaike’s Information Criterion
ANACONDA: Analysis of National Causes of Death for Action
ANFIS: Adaptive Neuro-Fuzzy Inference System
ANN: Artificial Neural Network
AO: Additive Outlier
AR: AutoRegressive (model)
ARX: AutoRegressive with eXogenous variables (model)
ARCH: AutoRegressive Conditional Heteroskedasticity
ARMA: AutoRegressive-Moving Average (model)
ARIMA: AutoRegressive Integrated Moving Average (model)
ARIMAX: AutoRegressive Integrated Moving Average with eXogenous variables (model)
B&M: Brick and Mortar
BATS: Box-Cox transform, ARMA errors, Trend, and Seasonal components (model)
BEER: Behavioural Equilibrium Exchange Rate
BEKK: Baba-Engle-Kraft-Kroner GARCH
BEKK-HL: BEKK High Low
BIC: Bayesian Information Criterion
BLAST: Building Loads Analysis and System Thermodynamics
BM: Bass Model
BMC: Bootstrap Model Combination
BPNN: Back-Propagation Neural Network
CARGPR: Conditional AutoRegressive Geometric Process Range (model)
CARR: Conditional AutoRegressive Range (model)
CARRS: Conditional AutoRegressive Rogers and Satchell (model)
CDS: Credit Default Swap
CNN: Convolutional Neural Network
COVID-19: Coronavirus disease 2019
CVAR: Cointegrated Vector AutoRegressive (model)
CAViaR: Conditional AutoRegressive Value At Risk
CL: Cross Learning
CPFR: Collaborative Planning, Forecasting, and Replenishment
CRCD: Competition and Regime Change Diachronic (model)
CRPS: Continuous Ranked Probability Score CSR: Complete Subset Regression
CV: Cross-Validation
DA: Deterministic Annealing
DC: Distribution Centre
DCC: Dynamic Conditional Correlation
DCC-RGARCH: Range GARCH DCC
DFM: Dynamic Factor Model
DGP: Data Generation Process
DJI: Dow Jones Industrial DM: Diebold-Mariano (test)
DSGE: Dynamic Stochastic General Equilibrium
DSHW: Double Seasonal Holt-Winters
DSTCC-CARR: Double Smooth Transition Conditional Correlation CARR
DT: Delay Time
EEG: ElectroEncephaloGram
EGARCH: Exponential GARCH
EH: Expectations Hypothesis
EMD: Empirical Mode Decomposition
ENet: Elastic Net
ENSO: El Nino Southern Oscillation ˜
ERCOT: Electric Reliability Council of Texas
ES: Expected Shortfall
ESP-r: Environmental Systems Performance – research
ESTAR: Exponential STAR ETS: ExponenTial Smoothing (or Error, Trend, Seasonality)
EVT: Extreme Value Theory
EWMA: Exponentially Weighted Moving Average
FAR: Functional AutoRegressive (model)
FASSTER: Forecasting with Additive Switching of Seasonality, Trend and Exogenous Regressors
FCM: Fuzzy C-Means
FIGARCH: Fractionally Integrated GARCH
FIS: Fuzzy Inference System
FFNN: Feed-Forward Neural Network
FFORMA: Feature-based FORecast Model Averaging
FMCG: Fast Moving Consumer Goods
FPCA: Functional Principal Component Analysis
FRB/EDO: Federal Reserve Board’s Estimated, Dynamic, Optimisation-based (model)
FSS: Forecasting Support System
FVA: Forecast Value Added
GARCH: General AutoRegressive Conditional Heteroscedasticity
GARCH-PARK-R: GARCH PARKinson Range
GARCH-TR: GARCH True Range
GB: Givon-Bass
GBM: Generalised Bass Model
GDP: Gross Domestic Product
GGM: Gusseo-Guidolin Model (GGM)
GJR-GARCH: Glosten-Jagannathan-Runkle GARCH
GM: Generalised M-estimator
GMM: Generalised Methods of Moments
GPU: Graphics Processing Unit
GRNN: Generalised Regression Neural Network
HAR: Heterogeneous AutoRegressive (model)
HDFS: Hadoop Distributed File System
HMD: Human Mortality Database
HP: Hodrick-Prescott
HPU: House Price Uncertainty
HVAC: Heating, Ventilation, and Air Conditioning (system)
HAR: Heterogeneous AutoRegressive (model)
HQ: Hannan-Quinn
IEA: International Energy Agency
IG: Interaction Groups
iid: independent and identically distributed
IIS: Impulse Indicator Saturation
IO: Innovation Outlier
IT: Information Technology
KBKD: Krishnan-Bass-Kummar Diachronic (model)
KISS: Keep It Simple, Stupid (principle)
kNN: k Nearest Neighbours
KPSS: Kwiatkowski–Phillips–Schmidt–Shin
L-IVaR: Liquidity-adjusted Intraday Value-at-Risk
LASSO: Least Absolute Shrinkage and Selection Operator
LH: Low and High
LLN: Law of Large Numbers
LN-CASS: Logit-Normal Continuous Analogue of the Spike-and-Slab
LS (or LPS): Logarithmic (Predictive) Score (log-score)
LSTAR: Logistic STAR
LSTM: Long Short-Term Memory Networks
LV: Lotka-Volterra model
LVac: Lotka-Volterra with asymmetric churn (model)
LVch: Lotka-Volterra with churn (model)
MAE: Mean Absolute Error
MAPE: Mean Absolute Percentage Error
MASE: Mean Absolute Scaled Error
MFI: Marginal Forecast Interval
MIDAS: MIxed DAta Sampling
MJO: Madden Julian Oscillation
ML: Machine Learning
MLP: MultiLayer forward Perceptron
MLR: Multiple Linear Regression
MS VAR: Markov Switching VAR
MSARIMA: Multiple/Multiplicative Seasonal ARIMA
MSC: Multiple Seasonal Cycles
MSE: Mean Squared Error
MSM: Markov Switching Model
MSRB: Markov-Switching Range-Based
MTA: Multiple Temporal Aggregation
NAO: North Atlantic Oscillation
NLS: Nonlinear Least Squares
NLTK: Natural Language Toolkit
NMAE: Normalised Mean Absolute Error
NN: Neural Network
NNAR: Neural Network AutoRegressive
NOB: Non-Overlapping Blocks
NWP: Numerical Weather Prediction
OBR: Office for Budget Responsibility
OB: Overlapping Blocks
OLS: Ordinary Least Squares
OWA: Overall Weighted Average
PAR: Periodic AutoRegressive (model)
PCA: Principal Components Analysis
pdf: probability density function
PdM: Predictive Maintenance
PFEM: Point Forecast Error Measure
PHANN: Physical Hybrid Artificial Neural Network
pHDR: predictive Highest Density Region
PI: Prediction Interval
PIT: Probability Integral Transform
PL: Product Level
PLS: Partial Least Squares
PM: Particulate Matter
POT: Peak Over Threshold
PPP: Purchasing Power Parity
PSO: Particle Swarm Intelligence
PV: PhotoVoltaic
RAF: Royal Air Force (UK)
RB: Range-Based
RB-copula: Range-Based copula
RB-DCC: Range-Based DCC
RB-MS-DCC: Range-Based Markov-Switching DCC
RBF: Radial Basis Function
REGARCH: Range-Based Exponential GARCH
RET: Renewable Energy Technology
RGARCH: Range GARCH
RMSE: Root Mean Squared Error
RNN: Recurrent Neural Network
RR-HGADCC: Return and Range Heterogeneous General Asymmetric DCC
RTV: Real Time Vintage
SA: Structured Analogies
SARIMA: Seasonal AutoRegressive Integrated Moving Average (model)
SARIMAX: Seasonal AutoRegressive Integrated Moving Average with eXogenous variables
SARMA: Seasonal AutoRegressive Moving Average (model)
SARMAX: Seasonal AutoRegressive Moving Average with eXogenous variables
SBA: Syntetos-Boylan Approximation
SBC: Syntetos-Boylan-Croston (classification)
SEATS: Seasonal Extraction in ARIMA Time Series
SES: Simple (or Single) Exponential Smoothing
SETAR: Self-Exciting Threshold AutoRegressive (model)
SFI: Simultaneous Forecast Interval
SKU: Stock Keeping Unit
SGD: Stochastic Gradient Descent
SIS: Step Indicator Saturation
SL: Serial number Level
SMA: Simple Moving Average
SOM: Self-Organising Map
SS: State Space
sSA: semi-Structured Analogies
SSARIMA: Several Seasonalities (or State Space) ARIMA
STAR: Smooth Transition AutoRegressive (model)
STARR: Smooth Transition conditional AutoRegressive Range (model)
STL: Seasonal Trend decomposition using Loess
STLF: Short-Term Load Forecasting
STR: Seasonal-Trend decomposition based on Regression
SV: Stochastic Volatility
SVA: Stochastic Value Added
SVD: Singular Value Decomposition
SVM: Support Vector Machine
SWAN: Simulating WAves Nearshore
S&OP: Sales and Operations Planning
S&P: Standard & Poor’s
TAR: Threshold AutoRegressive (model)
TARMA: Threshold AutoRegressive Moving Average (model) TARMASE: Threshold AutoRegressive Moving Average (model)
TARR: Range-Based Threshold conditional AutoRegressive (model)
TBATS: Exponential Smoothing state space model with Box-Cox transformation, ARMA errors, Trend and
Seasonal components
TGARCH: Threshold GARCH
TMA: Threshold Moving Average (model)
TPU: Tensor Processing Unit
TRAMO: Time series Regression with ARIMA noise, Missing values and Outliers
TSB: Teunter-Syntetos-Babai (method)
UCRCD: Unbalanced Competition and Regime Change Diachronic (model)
UIP: Uncovered Interest Party
VaR: Value at Risk
VAR: Vector AutoRegressive (model)
VARX: VAR with eXogenous variables (model)
VARMA: Vector AutoRegressive Moving Average (model)
VAT: Value Added Tax
VARIMAX: Vector AutoRegressive Integrated Moving Average with eXogenous variables (model)
VECM (or VEC): Vector Error Correction Model
VEqCM: Vector Equilibrium-Correction Model
WLS: Weighted Least Squares
WNN: Wavelet Neural Network
WOM: Word-Of-Mouth
WW2: World War 1
WW2: World War 2
WW3: World War 3
XGBoost: eXtreme Gradient Boosting
```

# Appendix B Software

# Appendix C Data sets