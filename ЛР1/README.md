<a href=\"https://colab.research.google.com/github/huksleva/DataScience/blob/main/%D0%9B%D0%A01/notebooks/LR1_Ames_SelfStudy.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>

# ЛР1 — Ames Housing

Лабораторная работа №1 по дисциплине **«Основы Data Science»**.

Проект выполнен по методичке с использованием датасета **Ames Housing** и включает основную часть лабораторной работы и все 4 задания для самостоятельной работы:

1. Дополнительный Feature Engineering:
   - `PricePerSqFt`
   - `AgeCategory`
   - `HasGarage`
2. Улучшение обработки пропусков с помощью `KNNImputer` и сравнение с текущим методом.
3. Анализ остатков:
   - residuals vs predicted;
   - Q-Q plot;
   - поиск паттернов в остатках.
4. 10-fold кросс-валидация всех моделей и сравнение с train/test.

## Структура проекта

```text
LR1_Ames/
├── data/
│   └── ames_demo.csv
├── notebooks/
│   └── LR1_Ames_SelfStudy.ipynb
├── .gitignore
├── pyproject.toml
└── README.md
```

## Установка

Рекомендуется Python 3.10+.

### Через venv

Windows PowerShell:

```powershell
cd ЛР1
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -e .
```

Linux/macOS:

```bash
cd ЛР1
python3 -m venv .venv
source .venv/bin/activate
pip install -e .
```

## Запуск Jupyter Notebook

```bash
jupyter notebook
```

или:

```bash
jupyter lab
```

После запуска открыть:

```text
notebooks/LR1_Ames_SelfStudy.ipynb
```

И выполнить ячейки сверху вниз.

## Данные

В проект добавлен небольшой демонстрационный вариант Ames Housing из методички (`data/ames_demo.csv`), поэтому notebook можно запустить сразу.

Если используется полный Kaggle Ames Housing Dataset, положите `train.csv` в каталог `data/`. Notebook автоматически выберет полный датасет, если он найден:

```text
data/train.csv
```

В методичке демонстрационный набор содержит 20 наблюдений; полный Ames Housing Dataset значительно больше.

## Модели

В работе сравниваются:

- Linear Regression;
- Ridge Regression;
- Lasso Regression.

Для Ridge и Lasso используется подбор `alpha` через `GridSearchCV`.

## Важное замечание по PricePerSqFt

`PricePerSqFt` рассчитывается через `SalePrice`, поэтому это **целевая утечка**, если использовать его непосредственно как признак для прогнозирования цены.

Поэтому в notebook признак создаётся и анализируется в рамках задания 1, но не передаётся в модель как входной predictor.

## Воспроизводимость

Для разбиения train/test используется:

```python
random_state=42
```

Параметры моделей и диапазоны `alpha` соответствуют методичке.

## Результат

После выполнения notebook будут получены:

- таблицы качества моделей;
- графики сравнения моделей;
- анализ дополнительных признаков;
- сравнение Median/текущего метода и KNNImputer;
- графики остатков;
- Q-Q plots;
- результаты 10-fold CV;
- итоговые выводы по всем заданиям.
