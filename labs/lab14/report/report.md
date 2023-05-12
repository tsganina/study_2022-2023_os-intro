---
## Front matter
title: "Отчёт по лабораторной работе №14"
subtitle: "Именованные каналы"
author: "Ганина Таисия Сергеевна, НКАбд-01-22"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение практических навыков работы с именованными каналами.

# Задачи

Изучите приведённые в тексте программы server.c и client.c. Взяв данные примеры за образец, напишите аналогичные программы, внеся следующие изменения:

1. Работает не 1 клиент, а несколько (например, два).

2. Клиенты передают текущее время с некоторой периодичностью (например, раз в пять секунд). Используйте функцию sleep() для приостановки работы клиента.

3. Сервер работает не бесконечно, а прекращает работу через некоторое время (например, 30 сек). Используйте функцию clock() для определения времени работы сервера.
Что будет в случае, если сервер завершит работу, не закрыв канал?

# Ход работы

1. Я создала файлы *common.h*, *server.c*, *client.c*, *client2.c*. Скопировала основной код из теоретической части лабораторной работы и немного подкорректировала его.(рис. @fig:001, @fig:002, @fig:003, @fig:004)

![Файл common.h](image/5.png){#fig:001 width=70%}

![Файл server.c](image/3.png){#fig:002 width=70%}

![Файл client.c](image/2.png){#fig:003 width=70%}

![Файл client2.c](image/1.png){#fig:004 width=70%}

2. Создала *makefile*.(рис. @fig:005)

![makefile](image/4.png){#fig:005 width=70%}

3.  Запустила *makefile*. Затем запустила *server*. (рис. @fig:006, @fig:007)

![Запуск makefile и server](image/6.png){#fig:006 width=70%}

![Запуск makefile и server](image/7.png){#fig:007 width=70%}

4. Запустила client (рис. @fig:008)

![Запуск client](image/7.png){ #fig:008 width=70% }

# Вывод

Мы научились пользоваться именованными каналами.

# Контрольные вопросы.

1.	Именованные каналы отличаются от неименованных наличием идентификатора канала, который представлен как специальный файл (соответственно имя именованного канала — это имя файла).

2.	Создание неименованного канала из командной строки возможно командой pipe.

3.	Создание именованного канала из командной строки возможно с помощью mkfifo.

4.	Функция языка С, создающая неименованный канал:
int read(int pipe_fd, void *area, int cnt); int write(int pipe_fd, void *area, int cnt);
Первый аргумент этих вызовов - дескриптор канала, второй - указатель на область памяти, с которой происходит обмен, третий - количество байт. Оба вызова возвращают число переданных байт (или -1 - при ошибке).

5.	Функция языка С, создающая именованный канал:
int mkfifo (const char *pathname, mode_t mode);
Первый параметр — имя файла, идентифицирующего канал, второй параметр маска прав доступа к файлу. Вызов функции mkfifo() создаёт файл канала (с именем, заданным макросом FIFO_NAME):
mkfifo(FIFO_NAME, 0600);

6.	При чтении меньшего числа байтов, возвращается требуемое число байтов, остаток сохраняется для следующих чтений.
При чтении большего числа байтов, возвращается доступное число байтов 7. Запись числа байтов, меньшего емкости канала или FIFO, гарантированно
атомарно. Это означает, что в случае, когда несколько процессов одновременно записывают в канал, порции данных от этих процессов не перемешиваются.
При записи большего числа байтов, чем это позволяет канал или FIFO, вызов write(2) блокируется до освобождения требуемого места. При этом атомарность операции не гарантируется. Если процесс пытается записать данные в канал, не открытый ни одним процессом на чтение, процессу генерируется сигнал SIGPIPE, а вызов write(2) возвращает 0 с установкой ошибки (errno=ЕР1РЕ) (если процесс не установил обработки сигнала SIGPIPE, производится обработка по умолчанию -- процесс завершается).

8.	Два и более процессов могут читать и записывать в канал.

9.	Функция write записывает length байтов из буфера buffer в файл, определенный дескриптором файла fd. Эта операция чисто 'двоичная' и без буферизации. При единице возвращает действительное число байтов.
Функция write возвращает число действительно записанных в файл байтов или -1 при ошибке, устанавливая при этом errno.

10.	Строковая функция strerror - функция языков C/C++, транслирующая код ошибки, который обычно хранится в глобальной переменной errno, в сообщение об ошибке, понятном человеку.

# Список литературы{.unnumbered}

1. Руководство к лабораторной работе №14.

::: {#refs}
:::
