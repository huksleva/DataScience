# Data card: Bike Sharing Dataset

## Назначение в работе

Локальная фиксированная копия используется только для офлайн-выполнения двух
практических частей. `hour.csv` применяется в вероятностной части, а
`day.csv` — в части описательной статистики и статистического вывода.

## Происхождение и лицензия

- Набор: UCI Machine Learning Repository, Bike Sharing Dataset.
- Постоянный идентификатор: DOI [10.24432/C5W894](https://doi.org/10.24432/C5W894).
- Исходная страница: <https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset>.
- Лицензия: CC BY 4.0.
- Получено: 2026-10-06 из фиксированного архива
  `https://archive.ics.uci.edu/static/public/275/bike+sharing+dataset.zip`.
- Рекомендуемая атрибуция: H. Fanaee-T, *Bike Sharing*, UCI Machine Learning
  Repository, 2013.

## Состав и схема

- `hour.csv`: 17 379 почасовых наблюдений за 2011–2012 годы, 17 столбцов.
  Цель/счётчик `cnt` — число аренд за час. Ключевые признаки: `dteday`,
  `yr`, `mnth`, `hr`, `workingday`, `weathersit`, `temp`, `hum`, `windspeed`.
- `day.csv`: 731 дневное наблюдение, 16 столбцов. `cnt` — число аренд за
  день; `casual` и `registered` — компоненты этого счётчика.
- `Readme.txt`: исходное описание кодов, единиц и полей.
- `Bike-Sharing-Dataset.zip`: неизменённая локальная копия исходного архива.

В обеих таблицах `season`, `weathersit`, `yr`, `mnth`, `weekday`, `holiday` и
`workingday` закодированы числами. Они не являются непрерывными измерениями;
их расшифровку следует смотреть в локальном `Readme.txt`. Набор наблюдательный:
статистические ассоциации не доказывают причинность.

## Контрольные суммы SHA-256

| Файл | SHA-256 |
|---|---|
| `Bike-Sharing-Dataset.zip` | `b70182d0d0508e9abbb79306ce5c0cec34869000f8220175ac83d11dbe845401` |
| `hour.csv` | `e03de4ee4ef4dc376ac6e04bf829673c6269e8eba5c60fa121640fa2f829504f` |
| `day.csv` | `a6bcf826782d3c0fbfdcbeead17cd0884185a0dafe8ff10cd48a874ee7ba18be` |
| `Readme.txt` | `b92c8628622948bf0828c43a1b315d1517c3d7fd63654730d0dea379b8e88175` |

Git нормализует окончания строк CSV с CRLF на LF при публикации. В Colab
ноутбуки восстанавливают CRLF перед сверкой с этими суммами из исходного архива.
