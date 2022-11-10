# Predictive-maintenance

Предсказание выхода из строя датчиков в реактивном двигателе от NASA

Для предсказание использовался метод решающих деревьев, такие как от [XGBoost](https://xgboost.readthedocs.io/en/latest/), [CatBoost](https://catboost.ai/) и [Random Forest](https://en.wikipedia.org/wiki/Random_forest)

## DATA 
Dataset from [Kaggle](https://www.kaggle.com/code/darkside92/nasa-turbofan-engine-rul-predictive-maintenance/data)

![Screenshot 2022-11-10 at 18 59 40](https://user-images.githubusercontent.com/11818964/201152820-63a1761e-3dcc-433b-a2bf-6e6bc70ff5b3.png)

## The result of experiments
В качестве проверки работы моделей используется cреднеквадратичная ошибка (RMSE) и коэффициент детерминации ($R^2$)

![Screenshot 2022-11-10 at 19 20 02](https://user-images.githubusercontent.com/11818964/201153042-5ba1e2e3-31d5-45a8-b91c-b082fafc3893.png)

## Conclusion
- Ограничение показателя оставшийся срок полезного использования(RUL) до 115, то методы решающих деревьев справлются с предсказанием лучше 
- Примение фильтра [Savitzky-Golay](https://en.wikipedia.org/wiki/Savitzky%E2%80%93Golay_filter) три раза тоже дает прирост в качестве
- Лучший результат показал классический метод решаюших деревьев 
- Поиск гипер-параметров с помощью Optuna не дает значимого прироста, был использоват только для Random Forest  метода

## References
1. https://gallery.azure.ai/Experiment/Predictive-Maintenance-Template-2
2. https://neptune.ai/blog/anomaly-detection-in-time-series
