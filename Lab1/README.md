# Получение сведений о системе
Александр Смирнов

## Цель работы

Получить сведения об используемой системе

## Исходные данные

1.  Ноутбук ASUS X554Lj

2.  ОС Kubuntu 22.10

3.  Интерпретатор командной оболочки bash 5.2.2

4.  Эмулятор терминала Konsole

## План

1.  Ввод команд в эмулятор терминала

2.  Анализ данных

## Ход работы

1.  Для начала получим сведения об используемом дистрибутиве:

``` bash
lsb_release -a
```

    No LSB modules are available.
    Distributor ID: Ubuntu
    Description:    Ubuntu 22.10
    Release:    22.10
    Codename:   kinetic

В результате выполнения данной команды было определён используемый
дистрибутив - Kubuntu 22.10

1.  Затем получим сведения о версии ядра:

``` bash
uname -a
```

    Linux X555LJ 5.19.0-38-generic #39-Ubuntu SMP PREEMPT_DYNAMIC Fri Mar 17 17:33:16 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux

В результате выполнения данной команды была получена версия ядра -
5.19.0-38, дата компиляции ядра - 17 марта 2023 года.

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
journalctl -q -b | tail -n 30
```

    мар 27 10:01:55 X555LJ plasmashell[6136]: qrc:/qml/ApplicationPage.qml:353:41: Unable to assign [undefined] to QString
    мар 27 10:01:56 X555LJ kwin_x11[2782]: qt.qpa.xcb: QXcbConnection: XCB error: 3 (BadWindow), sequence: 3650, resource id: 96469040, major code: 18 (ChangeProperty), minor code: 0
    мар 27 10:01:56 X555LJ kwin_x11[2782]: qt.qpa.xcb: QXcbConnection: XCB error: 3 (BadWindow), sequence: 3654, resource id: 23069053, major code: 18 (ChangeProperty), minor code: 0
    мар 27 10:02:19 X555LJ wpa_supplicant[809]: wlp3s0: CTRL-EVENT-BEACON-LOSS
    мар 27 10:04:57 X555LJ plasmashell[3072]: [3073:3073:0327/100457.823281:ERROR:brave_new_tab_message_handler.cc(160)] Ads service is not initialized!
    мар 27 10:05:38 X555LJ wpa_supplicant[809]: wlp3s0: CTRL-EVENT-BEACON-LOSS
    мар 27 10:06:05 X555LJ kwin_x11[2782]: qt.qpa.xcb: QXcbConnection: XCB error: 3 (BadWindow), sequence: 27420, resource id: 48234553, major code: 18 (ChangeProperty), minor code: 0
    мар 27 10:06:05 X555LJ systemd[2518]: app-org.kde.dolphin-ff0392e7fb104ad1853d9150ba6ba1da.scope: Consumed 7.459s CPU time.
    мар 27 10:06:05 X555LJ kwin_x11[2782]: qt.qpa.xcb: QXcbConnection: XCB error: 3 (BadWindow), sequence: 27438, resource id: 14680073, major code: 18 (ChangeProperty), minor code: 0
    мар 27 10:06:40 X555LJ plasmashell[3072]: [3073:3073:0327/100640.728577:ERROR:brave_new_tab_message_handler.cc(160)] Ads service is not initialized!
    мар 27 10:08:35 X555LJ plasmashell[3072]: [3073:3073:0327/100835.077075:ERROR:brave_new_tab_message_handler.cc(160)] Ads service is not initialized!
    мар 27 10:09:58 X555LJ plasmashell[3072]: [3073:3073:0327/100958.879091:ERROR:brave_new_tab_message_handler.cc(160)] Ads service is not initialized!
    мар 27 10:11:04 X555LJ systemd[1]: Starting Refresh fwupd metadata and update motd...
    мар 27 10:11:04 X555LJ fwupd[6152]: 07:11:04:0660 FuPluginPciMei       ME family not supported for 0:10.0.38.1000
    мар 27 10:11:04 X555LJ systemd[1]: fwupd-refresh.service: Deactivated successfully.
    мар 27 10:11:04 X555LJ systemd[1]: Finished Refresh fwupd metadata and update motd.
    мар 27 10:12:17 X555LJ dbus-daemon[661]: [system] Activating service name='org.kde.powerdevil.backlighthelper' requested by ':1.56' (uid=1000 pid=2814 comm="/usr/lib/x86_64-linux-gnu/libexec/org_kde_powerdev" label="unconfined") (using servicehelper)
    мар 27 10:12:17 X555LJ dbus-daemon[661]: [system] Successfully activated service 'org.kde.powerdevil.backlighthelper'
    мар 27 10:12:32 X555LJ dbus-daemon[661]: [system] Activating service name='org.kde.powerdevil.backlighthelper' requested by ':1.56' (uid=1000 pid=2814 comm="/usr/lib/x86_64-linux-gnu/libexec/org_kde_powerdev" label="unconfined") (using servicehelper)
    мар 27 10:12:32 X555LJ dbus-daemon[661]: [system] Successfully activated service 'org.kde.powerdevil.backlighthelper'
    мар 27 10:13:37 X555LJ plasmashell[3072]: [3073:3073:0327/101337.558648:ERROR:brave_new_tab_message_handler.cc(160)] Ads service is not initialized!
    мар 27 10:15:34 X555LJ wpa_supplicant[809]: wlp3s0: CTRL-EVENT-BEACON-LOSS
    мар 27 10:16:21 X555LJ kwin_x11[2782]: qt.qpa.xcb: QXcbConnection: XCB error: 3 (BadWindow), sequence: 21204, resource id: 81788992, major code: 15 (QueryTree), minor code: 0
    мар 27 10:16:25 X555LJ kwin_x11[2782]: qt.qpa.xcb: QXcbConnection: XCB error: 3 (BadWindow), sequence: 22779, resource id: 81789017, major code: 15 (QueryTree), minor code: 0
    мар 27 10:17:01 X555LJ CRON[7566]: pam_unix(cron:session): session opened for user root(uid=0) by (uid=0)
    мар 27 10:17:01 X555LJ CRON[7567]: (root) CMD (   cd / && run-parts --report /etc/cron.hourly)
    мар 27 10:17:01 X555LJ CRON[7566]: pam_unix(cron:session): session closed for user root
    мар 27 10:17:18 X555LJ ksmserver[7594]: kf.kio.slaves.file: copy() QUrl("file:///tmp/tmp-4294-zSLT4SIm5YIH/sh/.intellisense.sh") to QUrl("file:///home/olekzonder/.local/share/Trash/files/.intellisense.sh (23)") mode= 436
    мар 27 10:17:18 X555LJ ksmserver[7594]: kf.kio.slaves.file: the file doesn't have any xattr
    мар 27 10:17:18 X555LJ kwin_x11[2782]: qt.qpa.xcb: QXcbConnection: XCB error: 3 (BadWindow), sequence: 34092, resource id: 48234502, major code: 18 (ChangeProperty), minor code: 0

## Оценка результата

В результате лабораторной работы была получена базовая информация об
используемой системе.

## Вывод

Таким образом, мы научились, используя команды Linux, получать сведения
о системе.
