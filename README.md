# mlfirst

Мой первый проект по машинному обучению. Учусь по двухнедельному плану: данные → EDA → модель → оценка.

## День 1 — Окружение и первый анализ

**Что сделал:**
- Настроил окружение (Python + venv + Jupyter)
- Установил pandas, numpy, scikit-learn, matplotlib, seaborn
- Загрузил датасет Titanic (встроен в seaborn)
- Посмотрел структуру: 891 строка, 15 колонок, есть пропуски в `age`, `embarked`, `deck`
- Построил два графика: распределение выживших и зависимость выживания от пола

**Главный вывод:** женщин выживало заметно больше, чем мужчин — классический признак для будущей модели.

## Инструменты

Python 3, pandas, seaborn, matplotlib, Jupyter Notebook.

## Файлы

- `day1.ipynb` — ноутбук первого дня

## День 2 — EDA

Гистограммы, groupby, корреляции. Сильные признаки: `sex`, `pclass`, `fare`.
План по пропускам: `age` → медиана, `embarked` → мода, `deck` → удалить.


## День 3 — ✅
- Iris, первая модель LogisticRegression
- train/test split, random_state=42
- accuracy, confusion matrix
- Сравнил с DecisionTree
- Понял fit/predict
