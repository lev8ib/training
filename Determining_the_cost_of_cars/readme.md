# Предсказание цены автомобиля

## Цель проекта
На основании анализа объявлений о продаже автомобиля построить модель, определяющую рыночную стоимость авто. Модель в дальнейшем будет использоваться в мобильном приложении.

## Общий вывод
По результатам исследований моделей для поставленной задачи наиболее оптимальными являются:

- CatBoostRegressor
- LGBMRegressor
- CatBoostRegressor показывает хорошие показатели метрик и скорости обучения и предсказания, интуитивно понятная документация с широкими возможностями реализации
- LGBMRegressor демонстрирует невероятную скорость обучения и высокое качество, достаточно информативная документация.
- У XGBoost превосходное качество, но очень долгое обучение модели и он не может работать с категориальными данными напрямую, как два его конкурента.

Для данной задачи лучшая для заказчика в плане качества предсказания, скорости предсказания, времени обучения - LGBMRegressor. Т.к. лучше всего справляется с поставленной задачей и имеет огромный потенциал для дальнейшего тюнинга модели.

## Используемые библиотеки
- Python
- Pandas
- Matplotlib
- Seaborn
- Pandas_profiling
- Sklearn
- CatBoost
- LightGBM
