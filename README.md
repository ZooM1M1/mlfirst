# 🧠 ML Foundations & Production Engineering (mlfirst)

Репозиторий практических работ двухнедельного интенсивного погружения в классическое машинное обучение: от базового исследовательского анализа (EDA) до промышленных бустингов, оптимизации бизнес-порога и деплоя микросервисов.

---

## 🗺️ Структура репозитория

| Ноутбук | Тема | Ключевые концепции | Главный результат / Инсайт |
| :--- | :--- | :--- | :--- |
| [`day1.ipynb`](./day1.ipynb) | Введение в tabular data | Pandas (`head`, `describe`, `info`), Seaborn | Первичная интуиция по факторам выживания на Titanic |
| [`day3.ipynb`](./day3.ipynb) | Первая модель (Iris) | `LogisticRegression`, `DecisionTreeClassifier` | Разница между линейной гиперплоскостью и ступенчатыми правилами |
| [`day4.ipynb`](./day4.ipynb) | Предобработка Titanic | Импьютинг медианой/модой, `pd.get_dummies`, веса LR | `Sex_female` (+), `Sex_male` (-), интерпретация коэффициентов |
| [`day5.ipynb`](./day5.ipynb) | Feature Engineering & Scaling | `Title` regex, `FamilySize`, `IsAlone`, `StandardScaler` | Защита от Data Leakage: `fit_transform` строго на train! |
| [`day6.ipynb`](./day6.ipynb) | Валидация & Bias-Variance | `StratifiedKFold`, `cross_val_score`, `GridSearchCV` | Одиночный сплит обманывает; разница $< \sigma$ — это статистический шум |
| [`day7.ipynb`](./day7.ipynb) | Ансамбли & Пайплайн | `RandomForest`, `GradientBoosting`, `Pipeline` | Бэггинг vs Бустинг; на Титанике ансамбли эквивалентны LR |
| [`day8.ipynb`](./day8.ipynb) | Промышленные бустинги | `XGBoost`, `LightGBM`, Precision, Recall, F1, ROC-AUC | Порог 0.5 не священен: тюнинг порога максимизирует F1 |
| [`day 9.ipynb`](./day%209.ipynb) | Отбор признаков (Feature Selection) | `RFE`, полиномиальные фичи, биннинг | Новые фичи не всегда полезны: избыточные признаки внесли шум |
| [`day11.ipynb`](./day11.ipynb) | Промышленный Pipeline | `ColumnTransformer`, `SimpleImputer`, `OneHotEncoder` | Защита от утечки на фолдах; совместный тюнинг препроцессинга и модели |
| [`day12.ipynb`](./day12.ipynb) | **Итоговая контрольная (Telco Churn)** | 7043 строки, 46 фичей, LR vs RF vs LGBM vs CatBoost | CatBoost (**0.8506** ROC-AUC); сдвиг порога до 0.35 поднял Recall с 53% до 76% (пик F1 0.6357) |

---

## 💡 Фундаментальные инженерные принципы (ML Mindset)

1. **Один `train_test_split` обманывает**: честная оценка устойчивости модели возможна только через K-Fold кросс-валидацию и multi-seed прогоны.
2. **Бритва Оккама в продакшне**: если сложный ансамбль опережает простую линейную модель на величину, меньшую $\sigma$ — в продакшн идёт линейная модель (дешевле, быстрее, интерпретируема).
3. **Ловушка порога 0.5**: при дисбалансе классов (например, отток 27%) дефолтный порог 0.5 слеп к половине уходящих клиентов. Сдвиг порога под бизнес-метрики спасает выручку компании.
4. **Data Leakage — грех №1**: скейлеры, импьютеры и кодировщики должны настраиваться строго на тренировочных фолдах. Инструмент спасения — `Pipeline` + `ColumnTransformer`.
5. **Деревья и One-Hot Encoding**: раздувание категорий на 40+ бинарных колонок вредит решающим деревьям (требуется мелкая глубина `max_depth=3` или нативные категории в CatBoost).

---

## 🛠️ Стек технологий
- **Язык**: Python 3.14
- **Обработка и визуализация**: Pandas, NumPy, Matplotlib, Seaborn
- **Моделирование**: Scikit-Learn, LightGBM, XGBoost, CatBoost
- **Валидация и отбор**: StratifiedKFold, GridSearchCV, RFE
- **Деплой**: см. соседний репозиторий [titanic-api](https://github.com/ZooM1M1/titanic-api) (FastAPI + Uvicorn)
