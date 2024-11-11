# Alfa Hack 2024

> Кейс "Отток юридических лиц из расчетно-кассового обслуживания"

Leaderboard ROC-AUC: `0.817764`

## Решение:

1. [AutoGluon](1.%20AutoGluon.ipynb) - запускать на CPU

```python
Ensemble Weights: {
  'LightGBMXT_BAG_L2': 0.48,
  'LightGBM_BAG_L2': 0.2,
  'XGBoost_BAG_L2': 0.2,
  'CatBoost_BAG_L1': 0.04,
  'CatBoost_BAG_L2': 0.04,
  'LightGBMLarge_BAG_L2': 0.04
}
```

- val: 0.8145
- lb: 0.817466

2. [LightAutoML](2.%20LightAutoML.ipynb) - запускать на CPU

```python
Final prediction for new objects (level 0) =
   0.17114 * (7 averaged models Lvl_0_Pipe_1_Mod_0_LightGBM) +
   0.65639 * (7 averaged models Lvl_0_Pipe_1_Mod_1_Tuned_LightGBM) +
   0.11405 * (7 averaged models Lvl_0_Pipe_1_Mod_2_CatBoost) +
   0.05842 * (7 averaged models Lvl_0_Pipe_1_Mod_3_Tuned_CatBoost)
```

- val: 0.8141
- lb: 0.817412

3. [Blending](3.%20Blending.ipynb)

```python
Result = 0.6 * LightAutoML + 0.4 * AutoGluon
```

- lb: 0.817764
