# Операционные системы UNIX/Linux (Базовый).


## Содержание
- [Операционные системы UNIX/Linux (Базовый).](#операционные-системы-unixlinux-базовый)
	- [Содержание](#содержание)
	- [Part 1. Установка OC](#part-1-установка-oc)
	- [Part 2. Создание пользователя](#part-2-создание-пользователя)
	- [Part 3. Настройка сети ОС](#part-3-настройка-сети-ос)
	- [Part 4. Обновление ОС](#part-4-обновление-ос)
	- [Part 5. Использование команды **sudo**](#part-5-использование-команды-sudo)
	- [Part 6. Установка и настройка службы времени](#part-6-установка-и-настройка-службы-времени)
	- [Part 7. Установка и использование текстовых редакторов](#part-7-установка-и-использование-текстовых-редакторов)
	- [Part 8. Установка и базовая настройка сервиса **SSHD**](#part-8-установка-и-базовая-настройка-сервиса-sshd)
	- [Part 9. Установка и использование утилит **top**, **htop**](#part-9-установка-и-использование-утилит-top-htop)
	- [Part 10. Использование утилиты **fdisk**](#part-10-использование-утилиты-fdisk)
	- [Part 11. Использование утилиты **df**](#part-11-использование-утилиты-df)
	- [Part 12. Использование утилиты **du**](#part-12-использование-утилиты-du)
	- [Part 13. Установка и использование утилиты **ncdu**](#part-13-установка-и-использование-утилиты-ncdu)
	- [Part 14. Работа с системными журналами](#part-14-работа-с-системными-журналами)
	- [Part 15. Использование планировщика заданий **CRON**](#part-15-использование-планировщика-заданий-cron)

## Part 1. Установка OC

- Установка Ubuntu 20.04 Server LTS без графического интерфейса:

![](src/Screenshoots/Part_1.png "Вывод команды cat /etc/issue.")


## Part 2. Создание пользователя
- Выполнил команды для создания пользователя и добавления его в группу adm:

![a](src/Screenshoots/Part_2.png)

- Вывод команды cat /etc/issue:

![a](src/Screenshoots/Part_2_1.png)


## Part 3. Настройка сети ОС

- Выполнил команду для смены имени машины: sudo vi /etc/hostname - открыл в текстом редакторе vi с правами суперпользователя файл, хранящий название машины и заменил прежнее на aemmazub-1

- Скриншот с измененным именем пользователем на aemmazub-1:

![a](src/Screenshoots/Part_3.png)


- Просмотр текущей временной зоны

![a](src/Screenshoots/Part_3_1.png)


- Установка текущеней временной зоны: 

![a](src/Screenshoots/Part_3_2.png)

- Проверка, что зона установлена:

![a](src/Screenshoots/Part_3_3.png)

- Вызов команды ip -a link:

![a](src/Screenshoots/Part_3_4.png)


- lo (loopback device) – виртуальный интерфейс, присутствующий по умолчанию в любом Linux. Он используется для отладки сетевых программ и запуска серверных приложений на локальной машине.
  
- Вызов ip address, красным выделен ip адрес от DHCP

![a](src/Screenshoots/Part_3_5.png)


- DHCP (англ. Dynamic Host Configuration Protocol — протокол динамической настройки узла) — сетевой протокол, позволяющий сетевым устройствам автоматически получать IP-адрес и другие параметры, необходимые для работы в сети TCP/IP. 

## Part 4. Обновление ОС

- Прописал команды:
sudo apt update

![a](src/Screenshoots/Part_4.png)

## Part 5. Использование команды **sudo**

- sudo - консольная утиллита, позволяющая обычному пользователю дать возможность использовать root-права, не меняя текущего пользователя на root для выполнения каких-либо действий. Означает superuser do - суперпользователь делает.

- Убедился, что у user-1 есть права на выполнения sudo

![a](src/Screenshoots/Part_5.png)


- Изменил hostname с aemmazub-1 на aemmazub-1234, проверил что находился под нужным пользователем

![a](src/Screenshoots/Part_5_1.png)


## Part 6. Установка и настройка службы времени

- Использовал timedatectl вывел время своего часового пояса
  Вторая команда timedatectl show, включающая NTPSynchronized=yes

![a](src/Screenshoots/Part_6.png)

## Part 7. Установка и использование текстовых редакторов

1. Открыл файл text_vim.txt через команду: vim text_vim.txt
2. Закрыл с сохранениями: ESC + : + w + q
   
![a](src/Screenshoots/Part_7_vim_1.png)

1. Открыл файл text_vim.txt через команду: vim text_vim.txt
2. Прописал \:s/aemmazub/21 School 21, нажал Enter
3. Прописал для выхода без сохранения: :q!

![a](src/Screenshoots/Part_7_vim_2.png)


- Содержание text_vim.txt после выхода

![a](src/Screenshoots/Part_7_vim_3.png)

1. Команда для замены \:s/old_word/new_word
2. Команда для поиска /searded_word
   
![a](src/Screenshoots/Part_7_vim_4.png)

1. Открыл через nano test_nano.txt
2. ctrl+x, y, enter

![a](src/Screenshoots/Part_7_nano_1.png)


- Вывод test_nano.txt

![a](src/Screenshoots/Part_7_nano_2.png)


1. Стер aemmazub, написал 21 School 21
2. ctrl+x, n

![a](src/Screenshoots/Part_7_nano_3.png)

- Вывод test_nano

![a](src/Screenshoots/Part_7_nano_4.png)

- Открыл, нажал ctrl + x, вписал aemmazub, курсор перешел в начало искомой строки

![a](src/Screenshoots/Part_7_nano_5.png)

- Открыл, написал aemmazub, esc , выбрал yes

![a](src/Screenshoots/Part_7_mcedit_1.png)

- Открыл, написал aemmazub, esc , выбрал no

![a](src/Screenshoots/Part_7_mcedit_2.png)

- Вывод содержимого после выхода без сохранения

![a](src/Screenshoots/Part_7_mcedit_3.png)

- Нажал на f7, написал искомую строку aemmazub, содержимое подсветилось зеленым, где обнаружилась строка

![a](src/Screenshoots/Part_7_mcedit_4.png)

- Нажал на f4, первое поле для искомой строки, второе на какую будем менять

![a](src/Screenshoots/Part_7_mcedit_5.png)

## Part 8. Установка и базовая настройка сервиса **SSHD**

- Установил SSHd

![a](src/Screenshoots/Part_8_2.png)

- Добавил автостарт службы

![a](src/Screenshoots/Part_8_3.png)

- Изменил sshd_config, вписал Port2022

![a](src/Screenshoots/Part_8_4.png)

- ps -aux:
	a - вывод процессов всех пользователей
	u - более подробный отчет по процессам выводимым ps
	x - вывод процессов в фоне и во време загрузки

![a](src/Screenshoots/Part_8_6.png)

- Перезагрузка SSHd

![a](src/Screenshoots/Part_8_5.png)

- Вывод команды netstat -tan
	t - вывод процессов использующих TCP
	a - вывод всех процессов в том числе скрытых
	n - представить хостовые имена в виде чисел, а не в виде символов

![a](src/Screenshoots/Part_8_7.png)

1. proto - протокол, по которому осуществляется соедение

2. Recv-Q - количество байтов которые должны были полученны приложением, но помещены в буфер приема пакетов tcp/ip

3. Send-Q - количество байтов не отправленных или не подтверженных байтов, которые помещены в буфер отправки tcp/ip

4. Local address - локальный адрес и порт

5. Foreigh address - IP-адрес и номер порта удаленного компьютера, к которому подключен сокет.

6. State - состояние tcp-соединения

7. 0.0.0.0 - адрес, который позволяет получить службе все доступные ip-адреса доступные на компьютере 

## Part 9. Установка и использование утилит **top**, **htop**
- uptime: 55 min
количество авторизованных пользователей: 1
общую загрузку системы: 0.00 0.00 0.00
общее количество процессов: 101
загрузку cpu: 0.0 su, 0.0 sy, 0.0 ni, 100.0 id, 0.0 wa, 0.0 hi, 0.0 si, 0.0 st
загрузку памяти: 156.8 used
pid процесса занимающего больше всего памяти: 679
pid процесса, занимающего больше всего процессорного времени: 679

![a](src/Screenshoots/Part_9.png)

- Сортировка по PID

![a](src/Screenshoots/Part_9_2.png)

- Сортировка по CPU%

![a](src/Screenshoots/Part_9_4.png)

- Сортировка по MEM%

![a](src/Screenshoots/Part_9_5.png)

- Сортировка по TIME%

![a](src/Screenshoots/Part_9_6.png)

- Отфильтрованному для процесса sshd

![a](src/Screenshoots/Part_9_7.png)

- С процессом syslog, найденным, используя поиск

![a](src/Screenshoots/Part_9_8.png)

- Вывод с hostname, clock и uptime

![a](src/Screenshoots/Part_9_9.png)

## Part 10. Использование утилиты **fdisk**
- Запустил команду fdisk -l

![a](src/Screenshoots/Part_10.png)


## Part 11. Использование утилиты **df** 

![a](src/Screenshoots/Part_11.png)
![a](src/Screenshoots/Part_11_1.png)

Тип файловой системы ext4

## Part 12. Использование утилиты **du**
- Размер /home

![a](src/Screenshoots/Part_12.png)

- Размер /var

![a](src/Screenshoots/Part_12_1.png)

- Размер /var/log

![a](src/Screenshoots/Part_12_2.png)

- Размер всего содержимого в /var/log 

![a](src/Screenshoots/Part_12_3.png)



## Part 13. Установка и использование утилиты **ncdu**

- Размер папки /home

![a](src/Screenshoots/Part_13.png)

- Размер папки/var

![a](src/Screenshoots/Part_13_1.png)

- Размер папки /var/log

![a](src/Screenshoots/Part_13_2.png)

## Part 14. Работа с системными журналами
- Вывод лога dmesg

![a](src/Screenshoots/Part_14.png)

- Вывод лога syslog

![a](src/Screenshoots/Part_14_1.png)

- Вывод лога auth.log

![a](src/Screenshoots/Part_14_2.png)

- Вход через авторизацию(login), пользователь aemmazub, 20:42:58

![a](src/Screenshoots/Part_14_3.png)

- Вывод о перезапуске SSHd

![a](src/Screenshoots/Part_14_5.png)


## Part 15. Использование планировщика заданий **CRON**

- Вызвал crontab -e, прописал шаблон для выполнения планировщика заданий

![a](src/Screenshoots/Part_15.png)

- Содержание syslog

![a](src/Screenshoots/Part_15_1.png)

- Удаление журнала для планировщика заданий

![a](src/Screenshoots/Part_15_2.png)






