Получение сведений о системе
================
olekzonder@outlook.com

## Цель работы

Получить сведения об используемой системе

## Исходные данные

1.  Ноутбук ASUS X554Lj

2.  ОС OpenSUSE Tumbleweed

3.  Интерпретатор командной оболочки bash 5.2.15

4.  Эмулятор терминала Konsole

## План

1.  Ввод команд в эмулятор терминала

2.  Анализ данных

## Ход работы

1.  Для начала получим сведения об используемом дистрибутиве:

``` bash
lsb_release -a
```

    LSB Version:    n/a
    Distributor ID: openSUSE
    Description:    openSUSE Tumbleweed
    Release:    20230227
    Codename:   n/a

В результате выполнения данной команды было определён используемый
дистрибутив - openSUSE Tumbleweed версии 20230227.

1.  Затем получим сведения о версии ядра:

``` bash
uname -a
```

    Linux snusbook 6.1.12-1-default #1 SMP PREEMPT_DYNAMIC Wed Feb 15 05:31:41 UTC 2023 (373f017) x86_64 x86_64 x86_64 GNU/Linux

В результате выполнения данной команды была получена версия ядра -
6.1.12-1, дата компиляции ядра - 15 февраля 2023 года.

1.  Далее можно получить сведения о процессоре:

``` bash
cat /proc/cpuinfo | grep "model name"
```

    model name  : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz
    model name  : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz
    model name  : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz
    model name  : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz

Было определено, что используемый процессор - четырёхпоточный Intel Core
i3-4005U с тактовой частотой 1.7 ГГц.

1.  Далее получим последние 30 строк логов системы:

``` bash
dmesg | tail -n 30
```

    [ 3954.221445] wlp3s0: 80 MHz not supported, disabling VHT
    [ 3954.234219] wlp3s0: send auth to 36:a0:57:b5:e4:1a (try 1/3)
    [ 3954.238727] wlp3s0: authenticated
    [ 3954.241726] wlp3s0: associate with 36:a0:57:b5:e4:1a (try 1/3)
    [ 3954.249307] wlp3s0: RX AssocResp from 36:a0:57:b5:e4:1a (capab=0x431 status=0 aid=1)
    [ 3954.249485] wlp3s0: associated
    [ 3954.249725] ath: EEPROM regdomain: 0x8283
    [ 3954.249730] ath: EEPROM indicates we should expect a country code
    [ 3954.249733] ath: doing EEPROM country->regdmn map search
    [ 3954.249735] ath: country maps to regdmn code: 0x3d
    [ 3954.249737] ath: Country alpha2 being used: RU
    [ 3954.249739] ath: Regpair used: 0x3d
    [ 3954.249741] ath: regdomain 0x8283 dynamically updated by country element
    [ 3954.373849] wlp3s0: Limiting TX power to 0 (-128 - 0) dBm as advertised by 36:a0:57:b5:e4:1a
    [ 3954.397950] IPv6: ADDRCONF(NETDEV_CHANGE): wlp3s0: link becomes ready
    [ 5239.144114] wlp3s0: authenticate with 36:a0:57:b5:e4:1a
    [ 5239.144158] wlp3s0: 80 MHz not supported, disabling VHT
    [ 5239.157039] wlp3s0: send auth to 36:a0:57:b5:e4:1a (try 1/3)
    [ 5239.160732] wlp3s0: authenticated
    [ 5239.169136] wlp3s0: associate with 36:a0:57:b5:e4:1a (try 1/3)
    [ 5239.187045] wlp3s0: RX AssocResp from 36:a0:57:b5:e4:1a (capab=0x431 status=0 aid=1)
    [ 5239.187269] wlp3s0: associated
    [ 5239.187583] ath: EEPROM regdomain: 0x8283
    [ 5239.187591] ath: EEPROM indicates we should expect a country code
    [ 5239.187595] ath: doing EEPROM country->regdmn map search
    [ 5239.187599] ath: country maps to regdmn code: 0x3d
    [ 5239.187603] ath: Country alpha2 being used: RU
    [ 5239.187607] ath: Regpair used: 0x3d
    [ 5239.187611] ath: regdomain 0x8283 dynamically updated by country element
    [ 5239.252916] wlp3s0: Limiting TX power to 0 (-128 - 0) dBm as advertised by 36:a0:57:b5:e4:1a

## Оценка результата

В результате лабораторной работы была получена базовая информация об
используемой системе.

## Вывод

Таким образом. мы научились, используя команды Linux, получать сведения
о системе.
