# Описание проекта
Проект посвящен решеню задачи предсказания цен на машины
https://www.kaggle.com/datasets/vijayaadithyanvg/car-price-predictionused-cars?resource=download

# Запуск
Для запуска проекта необходимо выполнить команды:
```
git clone https://github.com/Egor14112001/IIS_Lr_1
cd IIS_Lr_1
установка окружения - python -m venv .venv_proj
активация окружения - .venv_proj/scripts/Activate
установка зависимостей - pip install -r requirements.txt
```

# Исследование данных
В ходе исследования были проведены действия:
 * Очистка данных не производилась, так как после проверки все данные оказались валидын
 * Был создан новый признак - 'Driven_run' - уровень пробега автомобиля
 * Для столбцов 'Driven_kms', 'Year' изменен тип данных на int32
Закономерности, выявлены по графикам, которые могут быть полезны в дальнейшем для решния задачи:
 * В основном машины меньшего года выпуска стоят дешевле.
 * Дизельные автомобили стоят в основном дороже, что соответсвует правде.
 * Были продемонстрированы более дорогие модели машин.
 * Был сделан вывод, что машины с салона стоят дороже, чем с рук.
 * Стоимосить машины больше всего коррелирует с годом выпуска.

Обработанная выборка сохранена в файл `./data/clean_data.pkl`

# Запуск MLFlow
* Перейти в директорию mlflow
```
cd mlflow
```
* Выполинть в терминале следующую команду
```
source start_mlflow.sh
```
Или выполнить команду
```
mlflow server --backend-store-uri sqlite:///mlruns.db
```
После чего можно проверить, что фреймворк успешно запустился, пройдя в браузере на http://localhost:5000/
# Результаты исследования
Лучший результат показала модель на основе fe_sklearn:
Метрики полученные при обучении модели следующие:
* mae: 0.16
* mape: 0.05
* mse: 0.08
Параметры модели:
* depth: 8
* max_features: 0.5052449805697352
* n_estimators': 3
RunID финальной модели: 496c3d1f8a4a4fbf8569b37b3f73211c