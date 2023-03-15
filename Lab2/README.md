Сбор и аналитическая обработка информации о сетевом трафике
================
olekzonder@outlook.com

## Цель работы

1.  Развить практические навыки использования современного стека
    инструментов сбора и аналитической обработки информации о сетвом
    трафике

2.  Освоить базовые подходы блокировки нежелательного сетевого трафика

3.  Закрепить знания о современных сетевых протоколах прикладного уровня

## Ход выполнения практической работы

1.  Был собран сетевой трафик объёмом 800 Мб с помощью Wireshark.

2.  С помощью утилиты Zeek была выделена метаинформация сетевого трафика
    (файлы http.log и dns.log)

3.  Сбор данных об источниках нежелательного трафика

    Скачаем файлы с источниками нежелательного трафика:

``` bash
mkdir hosts
cd hosts
wget -q https://github.com/StevenBlack/hosts/raw/master/data/add.2o7Net/hosts
wget -q https://raw.githubusercontent.com/StevenBlack/hosts/master/data/Adguard-cname/hosts
wget -q https://raw.githubusercontent.com/StevenBlack/hosts/master/data/mvps.org/hosts 1
sort hosts* | uniq > final_hosts
mv final_hosts ../hosts.txt
cd ..
rm -rf hosts
```

    Был получен файл hosts.txt.

1.  Проанализируем полученный трафик

    Установим библиотеку Zeek Analysis Toolkit для преобразоваия
    log-файлов в датафрейм Pandas:

``` bash
pip install zat > /dev/null
```

``` python
import pandas as pd
from zat.log_to_dataframe import LogToDataFrame
df = LogToDataFrame()
zeek_df = df.create_dataframe('dns.log')
```

    /home/olekzonder/.local/lib/python3.10/site-packages/pandas/core/arrays/timedeltas.py:908: RuntimeWarning: invalid value encountered in cast
      base = data.astype(np.int64)
    /home/olekzonder/.local/lib/python3.10/site-packages/pandas/core/arrays/timedeltas.py:912: RuntimeWarning: invalid value encountered in cast
      data = (base * m + (frac * m).astype(np.int64)).view("timedelta64[ns]")

``` python
pd.set_option('display.max_columns', None)
```
