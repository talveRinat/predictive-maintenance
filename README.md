# Predictive-maintenance

Предсказание выхода из строя датчиков в реактивном двигателе от NASA

Для предсказание использовался метод решающих деревьев, такие как от [XGBoost](https://xgboost.readthedocs.io/en/latest/), [CatBoost](https://catboost.ai/) и [Random Forest](https://en.wikipedia.org/wiki/Random_forest)

## DATA 
Dataset from [Kaggle](https://www.kaggle.com/code/darkside92/nasa-turbofan-engine-rul-predictive-maintenance/data)

![Screenshot 2022-11-10 at 18 59 40](https://user-images.githubusercontent.com/11818964/201152820-63a1761e-3dcc-433b-a2bf-6e6bc70ff5b3.png)

## The result of experiments
В качестве проверки работы моделей используется cреднеквадратичная ошибка (RMSE) и коэффициент детерминации ($R^2$)

![Screenshot 2022-11-10 at 19 20 02](https://user-images.githubusercontent.com/11818964/201153042-5ba1e2e3-31d5-45a8-b91c-b082fafc3893.png)

## ML model performance 
![Screenshot 2022-11-11 at 15 29 48](https://user-images.githubusercontent.com/11818964/201340811-0fd5023f-5378-481d-91b8-833a425e5b86.png)

## Conclusion
- Если установить показателя срок службы датчика(RUL) до 115 циклов, то методы решающих деревьев справлются с предсказанием лучше 
- Если применить фильтра [Savitzky-Golay](https://en.wikipedia.org/wiki/Savitzky%E2%80%93Golay_filter) три раза тоже получим прирост в качестве
- Лучший результат показал классический метод решаюших деревьев 
- Поиск гипер-параметров с помощью Optuna не дает значимого прироста, поиск параметров занимает ~50 минут плюс обучения с лучшими параметрами занимает 14 минут, поэтому поиск был только использоват для Random Forest метода
- Производительность RandomForest с лучшими параметрами увеличилась в три раза 

## References
1. https://gallery.azure.ai/Experiment/Predictive-Maintenance-Template-2
2. https://neptune.ai/blog/anomaly-detection-in-time-series
3. https://github.com/optuna/optuna-examples/blob/main/quickstart.ipynb
