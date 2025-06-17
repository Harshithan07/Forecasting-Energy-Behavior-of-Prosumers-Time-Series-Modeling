# Forecasting Energy Behavior of Prosumers – Time Series Modeling for Enefit Kaggle Challenge


## ABOUT THE PROJECT:
This project aimed to predict the future electricity consumption and production behavior of prosumers (households that both consume and produce energy) using multivariate time-series data. It was part of a Kaggle competition hosted by Enefit, an energy company. The goal was to build accurate, efficient, and robust models to forecast future values for energy planning and grid optimization.

## USE CASE EXPLANATION:
Accurate forecasting of prosumer energy behavior is crucial in smart grid management, demand-response systems, and energy trading. This project falls within energy analytics and time-series forecasting, helping utility providers and policymakers optimize resource distribution and reduce operational inefficiencies.


## HOW IT IS BUILT AND FULL WORKING:

1. Data Used:

- Household-level energy usage/production data

- xternal weather features, pricing, and PV (photovoltaic) capacity

- Multiple time-series grouped by id (household) (21Million Records)

2. Preprocessing & Feature Engineering:

- Timestamp parsing and feature extraction (hour, day, month, etc.)

- Missing value imputation and smoothing

- Lag features, rolling window statistics, and group-wise transformations

3. Modeling Approaches:

   1. LightGBM:

      - Tree-based boosting model with strong performance

      - Tuned with early stopping and feature importance analysis

   2. CatBoost:

      - Gradient boosting with categorical handling

      - Robust to overfitting on long sequences

   3. GRU (Gated Recurrent Unit):

      - Deep learning model for time series

      - Implemented with TensorFlow/Keras, struggled with overfitting and variance

   4. Ensemble (CatBoost + LightGBM):

      - Averaging predictions; performed poorly due to divergence in error patterns

   5. Voting Regressor:

      - Combined outputs of CatBoost and LightGBM with better averaging

      - Produced best overall performance on leaderboard


## OUTPUT AND RESULTS OR BENCHMARKS:

Model	MAE	Kaggle Score
LightGBM	58	87.5
CatBoost	61	88.06
Ensemble (LGB + CB)	95	133.8
GRU	47	411.7
Voting Regressor	41	68.5

- Voting Regressor achieved the best MAE of 41 and leaderboard score of 0.68.5

- GRU had the lowest MAE offline but failed to generalize on leaderboard test set.

- Ensemble model (unweighted average) amplified errors instead of balancing them.


## SKILLS, TOOLS:
Python, Pandas, LightGBM, CatBoost, TensorFlow/Keras (GRU), Sklearn, Time-series preprocessing, Feature engineering, VotingRegressor, MAE scoring, Kaggle submission pipeline


## KEYWORDS:
Time series forecasting, energy analytics, smart grid, LightGBM, CatBoost, GRU, ensemble learning, MAE, Kaggle competition, demand prediction, multivariate forecasting

