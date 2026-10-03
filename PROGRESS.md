# 📊 Журнал прогресса обучения (14-дневный интенсив)

| День | Тема | Статус | Основные результаты и метрики |
| :---: | :--- | :---: | :--- |
| **1** | Окружение + Titanic EDA | ✅ | Настройка окружения, pandas, sns.countplot по полу и выживаемости |
| **2** | Углубленный EDA | ✅ | Гистограммы Age/Fare, тепловая карта корреляций, стратегия по пропускам |
| **3** | Датасет Iris + Первая модель | ✅ | LogisticRegression vs DecisionTree, accuracy, confusion matrix |
| **4** | Подготовка признаков Titanic | ✅ | Базовый fillna, get_dummies, stratify=y, интерпретация весов LR (acc ~0.80) |
| **5** | Feature Engineering & Scaling | ✅ | Title regex, FamilySize, IsAlone, StandardScaler без утечки (acc ~0.81) |
| **6** | Кросс-валидация + GridSearch | ✅ | StratifiedKFold (5 фолдов), Bias-Variance tradeoff, max_depth=4 оптимум |
| **7** | Ансамбли + Pipeline | ✅ | RandomForest vs GradientBoosting в Pipeline, multi-seed (LR 0.834 эквивалентна) |
| **8** | Промышленные бустинги | ✅ | XGBoost, LightGBM, ROC-AUC, Precision, Recall, F1, зависимость от порога |
| **9** | Отбор признаков (RFE) | ✅ | Новые фичи (22) vs 10 отобранных через RFE (компактный набор устойчивее) |
| **10** | Деплой модели в FastAPI | ✅ | Создан репозиторий titanic-api, Pydantic v2, Swagger UI, тест requests |
| **11** | ColumnTransformer & Pipeline | ✅ | Промышленный Pipeline (Imputer + OneHot + Scaler), multi-seed (0.832) |
| **12** | **Итоговая контрольная (Telco Churn)** | ✅ | Telco 7043 строки: CatBoost (0.8506 ROC-AUC), сдвиг порога до 0.35 (F1 0.6357, Recall 76%) |
| **13** | Рефакторинг titanic-api | ✅ | Перевод FastAPI на монолитный Pipeline, удаление columns.joblib, тесты пройдены |
| **14** | Финальный аудит и стратегия | ✅ | Оформление репозиториев, фиксация побед, переход к Блоку 2 |
