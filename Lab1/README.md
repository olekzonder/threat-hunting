Получение сведений о системе
================
Александр Смирнов

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
    Release:    20230310
    Codename:   n/a

В результате выполнения данной команды было определён используемый
дистрибутив - openSUSE Tumbleweed версии 20230227.

1.  Затем получим сведения о версии ядра:

``` bash
uname -a
```

    Linux snuspc 6.2.2-1-default #1 SMP PREEMPT_DYNAMIC Thu Mar  9 06:06:13 UTC 2023 (44ca817) x86_64 x86_64 x86_64 GNU/Linux

В результате выполнения данной команды была получена версия ядра -
6.1.12-1, дата компиляции ядра - 15 февраля 2023 года.

1.  Далее можно получить сведения о процессоре:

``` bash
cat /proc/cpuinfo | grep "model name"
```

    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz
    model name  : Intel(R) Core(TM) i5-10400F CPU @ 2.90GHz

Было определено, что используемый процессор - четырёхпоточный Intel Core
i3-4005U с тактовой частотой 1.7 ГГц.

1.  Далее получим последние 30 строк логов системы:

``` bash
dmesg | tail -n 30
```

    [    6.391838] scsi 4:0:0:0: Direct-Access     SanDisk  Cruzer Blade     1.00 PQ: 0 ANSI: 6
    [    6.392992] sd 4:0:0:0: Attached scsi generic sg1 type 0
    [    6.393261] sd 4:0:0:0: [sdb] 60088320 512-byte logical blocks: (30.8 GB/28.7 GiB)
    [    6.394373] sd 4:0:0:0: [sdb] Write Protect is off
    [    6.394375] sd 4:0:0:0: [sdb] Mode Sense: 43 00 00 00
    [    6.394695] sd 4:0:0:0: [sdb] Write cache: disabled, read cache: enabled, doesn't support DPO or FUA
    [    6.398294]  sdb: sdb1 sdb2
    [    6.398345] sd 4:0:0:0: [sdb] Attached SCSI removable disk
    [    6.403232] r8169 0000:02:00.0 enp2s0: Link is Down
    [    6.838362] bridge: filtering via arp/ip/ip6tables is no longer available by default. Update your scripts to load br_netfilter if you need this.
    [    6.840554] Bridge firewalling registered
    [    6.938011] NET: Registered PF_PACKET protocol family
    [    7.019796] Initializing XFRM netlink socket
    [    7.113891] Bluetooth: hci0: Waiting for firmware download to complete
    [    7.114787] Bluetooth: hci0: Firmware loaded in 1575607 usecs
    [    7.114824] Bluetooth: hci0: Waiting for device to boot
    [    7.128790] Bluetooth: hci0: Device booted in 13659 usecs
    [    7.128795] Bluetooth: hci0: Malformed MSFT vendor event: 0x02
    [    7.131054] Bluetooth: hci0: Found Intel DDC parameters: intel/ibt-19-0-4.ddc
    [    7.132791] Bluetooth: hci0: Applying Intel DDC parameters completed
    [    7.133790] Bluetooth: hci0: Firmware revision 0.4 build 15 week 45 2022
    [    7.198855] Bluetooth: MGMT ver 1.22
    [    7.201780] NET: Registered PF_ALG protocol family
    [    8.734965] r8169 0000:02:00.0 enp2s0: Link is Up - 1Gbps/Full - flow control rx/tx
    [    8.734981] IPv6: ADDRCONF(NETDEV_CHANGE): enp2s0: link becomes ready
    [   10.824623] usblp0: removed
    [   10.828807] usblp 1-5:1.0: usblp0: USB Bidirectional printer dev 4 if 0 alt 0 proto 2 vid 0x03F0 pid 0x3817
    [   13.357913] Bluetooth: RFCOMM TTY layer initialized
    [   13.357919] Bluetooth: RFCOMM socket layer initialized
    [   13.357921] Bluetooth: RFCOMM ver 1.11

## Оценка результата

В результате лабораторной работы была получена базовая информация об
используемой системе.

## Вывод

Таким образом. мы научились, используя команды Linux, получать сведения
о системе.
