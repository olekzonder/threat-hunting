# Получение сведений о системе

## Цель работы

Получить сведения об используемой системе

## Исходные данные

1. Ноутбук ASUS X554Lj

2. ОС OpenSUSE Tumbleweed

3. Интерпретатор командной оболочки bash 5.2.15

4. Эмулятор терминала Konsole

## План

1. Ввод команд в эмулятор терминала

2. Анализ данных

## Ход работы

1. Для начала получим сведения об используемом дистрибутиве:

```bash
olekzonder@snusbook:~> lsb_release -a
LSB Version:    n/a
Distributor ID: openSUSE
Description:    openSUSE Tumbleweed
Release:        20230227
Codename:       n/a
```

В результате выполнения данной команды было определён используемый дистрибутив - openSUSE Tumbleweed версии 20230227.

2. Затем получим сведения о версии ядра:

```bash
olekzonder@snusbook:~> uname -a
Linux snusbook 6.1.12-1-default #1 SMP PREEMPT_DYNAMIC Wed Feb 15 05:31:41 UTC 2023 (373f017) x86_64 x86_64 x86_64 GNU/Linux
```

В результате выполнения данной команды была получена версия ядра - 6.1.12-1, дата компиляции ядра - 15 февраля 2023 года.

3. Далее можно получить сведения о процессоре:

```bash
olekzonder@snusbook:~> cat /proc/cpuinfo | grep "model name"
model name      : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz
model name      : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz
model name      : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz
model name      : Intel(R) Core(TM) i3-4005U CPU @ 1.70GHz
```

Было определено, что используемый процессор - четырёхпоточный Intel Core i3-4005U с тактовой частотой 1.7 ГГц.

4. Далее получим последние 30 строк логов системы:

```bash
olekzonder@snusbook:~> journalctl -q -b | tail -n 30
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Daemon changed
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net mobile: false
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Is net online: true
мар 01 10:42:26 snusbook plasmashell[1997]: plasma-pk-updates: Daemon changed
мар 01 10:42:29 snusbook kwin_x11[1964]: kwin_core: XCB error: 152 (BadDamage), sequence: 919, resource id: 11661625, major code: 143 (DAMAGE), minor code: 3 (Subtract)
мар 01 10:45:14 snusbook akonadi_imap_resource[2269]: org.kde.pim.kimap: Connection to server lost  QAbstractSocket::RemoteHostClosedError
мар 01 10:45:14 snusbook akonadi_imap_resource[2269]: org.kde.pim.kimap: Connection to server lost  QAbstractSocket::RemoteHostClosedError
мар 01 10:46:13 snusbook plasmashell[2833]: [main 2023-03-01T07:46:13.253Z] [UtilityProcess id: 4, type: extensionHost, pid: 8397]: received exit event with code 0
мар 01 10:46:13 snusbook plasmashell[2833]: [main 2023-03-01T07:46:13.255Z] Extension host with pid 8397 exited with code: 0, signal: unknown.
мар 01 10:46:15 snusbook plasmashell[2833]: [main 2023-03-01T07:46:15.277Z] [UtilityProcess id: 6, type: extensionHost, pid: <none>]: creating new...
мар 01 10:46:15 snusbook plasmashell[2833]: [main 2023-03-01T07:46:15.293Z] [UtilityProcess id: 6, type: extensionHost, pid: 17198]: successfully created
мар 01 10:48:25 snusbook kwin_x11[1964]: kwin_core: XCB error: 3 (BadWindow), sequence: 28076, resource id: 11665941, major code: 129 (SHAPE), minor code: 6 (Input)
мар 01 10:50:15 snusbook plasmashell[2581]: [2582:2582:0301/105015.459326:ERROR:brave_new_tab_message_handler.cc(160)] Ads service is not initialized!
мар 01 10:50:19 snusbook akonadi_imap_resource[2269]: org.kde.pim.kimap: Connection to server lost  QAbstractSocket::RemoteHostClosedError
мар 01 10:50:22 snusbook akonadi_imap_resource[2269]: org.kde.pim.kimap: Connection to server lost  QAbstractSocket::RemoteHostClosedError
мар 01 10:55:03 snusbook plasmashell[2833]: [main 2023-03-01T07:55:03.180Z] [UtilityProcess id: 6, type: extensionHost, pid: 17198]: received exit event with code 0
мар 01 10:55:03 snusbook plasmashell[2833]: [main 2023-03-01T07:55:03.181Z] Extension host with pid 17198 exited with code: 0, signal: unknown.
мар 01 10:55:04 snusbook plasmashell[2833]: [main 2023-03-01T07:55:04.959Z] [UtilityProcess id: 7, type: extensionHost, pid: <none>]: creating new...
мар 01 10:55:04 snusbook plasmashell[2833]: [main 2023-03-01T07:55:04.973Z] [UtilityProcess id: 7, type: extensionHost, pid: 18454]: successfully created
мар 01 10:55:19 snusbook akonadi_imap_resource[2269]: org.kde.pim.kimap: Connection to server lost  QAbstractSocket::RemoteHostClosedError
мар 01 10:55:19 snusbook akonadi_imap_resource[2269]: org.kde.pim.kimap: Connection to server lost  QAbstractSocket::RemoteHostClosedError
```

## Оценка результата

В результате лабораторной работы была получена базовая информация об используемой системе.

## Вывод

Таким образом. мы научились, используя команды Linux, получать сведения о системе.
