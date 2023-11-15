---
## Front matter
title: "Отчёт по лабораторной работе №6"
subtitle: "Дисциплина: архитектура компьютера"
author: "Швецов Михаил Романович"

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

Цель данной лабораторной работы - приобретение практических навыков
работы в Midnight Commander и освоение инструкций языка ассемблера mov и
int

# Задание

Здесь приводится описание задания в соответствии с рекомендациями
методического пособия и выданным вариантом.

# Теоретическое введение

Здесь описываются теоретические аспекты, связанные с выполнением работы.

Например, в табл. @tbl:std-dir приведено краткое описание стандартных каталогов Unix.

: Описание некоторых каталогов файловой системы GNU Linux {#tbl:std-dir}

| Имя каталога | Описание каталога                                                                                                          |
|--------------|----------------------------------------------------------------------------------------------------------------------------|
| `/`          | Корневая директория, содержащая всю файловую                                                                               |
| `/bin `      | Основные системные утилиты, необходимые как в однопользовательском режиме, так и при обычной работе всем пользователям     |
| `/etc`       | Общесистемные конфигурационные файлы и файлы конфигурации установленных программ                                           |
| `/home`      | Содержит домашние директории пользователей, которые, в свою очередь, содержат персональные настройки и данные пользователя |
| `/media`     | Точки монтирования для сменных носителей                                                                                   |
| `/root`      | Домашняя директория пользователя  `root`                                                                                   |
| `/tmp`       | Временные файлы                                                                                                            |
| `/usr`       | Вторичная иерархия для данных пользователя                                                                                 |

Более подробно об Unix см. в [@gnu-doc:bash;@newham:2005:bash;@zarrelli:2017:bash;@robbins:2013:bash;@tannenbaum:arch-pc:ru;@tannenbaum:modern-os:ru].

# Выполнение лабораторной работы

Я открыл  Midnight Commander и перешел в каталог arch-pc, далее создал каталог lab05.

![Создание каталога lab05](image/1.jpeg){#fig:001 width=70%}

Перещел в созданную директорию и создал файл lab5-1.asm

![Создал файл lab05-1.asm](image/2.jpeg){#fig:001 width=70%}

Открыл данный файл в редакторе nano для редактирования 

![Открыл файл для редактирования](image/3.jpeg){#fig:001 width=70%}

Редактирую файл

![Редактирование файла](image/4.jpeg){#fig:001 width=70%}

Сохранил файл

![Сохранение файла](image/5.jpeg){#fig:001 width=70%}

Создал объектный файл lab5-1.o, выполнил компоновку объектного файла и
запускаю исполняемый файл 

![Запуск программы](image/6.jpeg){#fig:001 width=70%}

Скачал файл in_out.asm 

![Скачивание in_out.asm](image/7.jpeg){#fig:001 width=70%}

Переместил данный файл в директорию lab05

![Перемещение файла](image/8.jpeg){#fig:001 width=70%}

Скопировал файл lab5-1.asm с новым именем lab5-2.asm и изменил текст программы lab5-2.asm, чтобы в ней использовались функции
из подключаемого файла, далее выполнил компановку и создал исполняемый файл и запустил его

![Запуск lab5-2](image/9.jpeg){#fig:001 width=70%}

В тексте программы lab5-2.asm заменил sprintLF на sprint, далее создаю объектный файл lab5-2.o, выполняю компоновку объектного файла
и запускаю исполняемый файл (рис. 2.13). Теперь ввод производится на той же
строке, что и вывод, убран символ перевода строки после вывода.

![Запуск измененной программы](image/10.jpeg){#fig:001 width=70%}

Скопировал файл lab5-1.asm с именем lab5-3.asm

![Копирование файла](image/11.jpeg){#fig:001 width=70%}

Изменил код программы, добавляя вывод введеннной строки

![Изменение кода программы](image/12.jpeg){#fig:001 width=70%}

Создал объектный файл lab5-3.o,скомпоновал его в исполняемый файл, запускаю
исполняемый файл

![Запуск новой программы](image/13.jpeg){#fig:001 width=70%}

Программа из пункта 1:

;------------------- Объявление переменных ----------------
SECTION .data ; Секция инициированных данных
msg: DB 'Введите строку:',10 ; сообщение плюс
; символ перевода строки
msgLen: EQU $-msg ; Длина переменной 'msg'
SECTION .bss ; Секция не инициированных данных
buf1: RESB 80 ; Буфер размером 80 байт
;------------------- Текст программы -----------------
SECTION .text ; Код программы
GLOBAL _start ; Начало программы
_start: ; Точка входа в программу
mov eax,4 ; Системный вызов для записи (sys_write)
mov ebx,1 ; Описатель файла 1 - стандартный вывод
mov ecx,msg ; Адрес строки 'msg' в 'ecx'
mov edx,msgLen ; Размер строки 'msg' в 'edx'
int 80h ; Вызов ядра
mov eax, 3 ; Системный вызов для чтения (sys_read)
mov ebx, 0 ; Дескриптор файла 0 - стандартный ввод
mov ecx, buf1 ; Адрес буфера под вводимую строку
mov edx, 80 ; Длина вводимой строки
int 80h ; Вызов ядра
mov eax,4 ; Системный вызов для записи (sys_write)
mov ebx,1 ; Описатель файла '1' - стандартный вывод
mov ecx,buf1 ; Адрес строки buf1 в ecx
mov edx,buf1 ; Размер строки buf1
int 80h ; Вызов ядра
mov eax,1 ; Системный вызов для выхода (sys_exit)
mov ebx,0 ; Выход с кодом возврата 0 (без ошибок)
int 80h ; Вызов ядра

Скопировал файл lab5-2.asm с именем lab5-4.asm

![Копирование файла](image/13.jpeg){#fig:001 width=70%}

Изменил код программы, добавляя вывод введенной строки, создал объектный файл lab5-3.o, скомпоновал его в исполняемый файл, запускаю
исполняемый файл

![Запуск программы](image/14.jpeg){#fig:001 width=70%}

Программа из пункта 2:

;--------------------------------------------------------------------
; Программа вывода сообщения на экран и ввода строки с клавиатуры
;---------------------------------------------------------------------
%include 'in_out.asm' ; подключение внешнего файла
SECTION .data ; Секция инициированных данных
msg: DB 'Введите строку: ',0h ; сообщение
SECTION .bss ; Секция не инициированных данных
buf1: RESB 80 ; Буфер размером 80 байт
SECTION .text ; Код программы
GLOBAL _start ; Начало программы
_start: ; Точка входа в программу
mov eax, msg ; запись адреса выводимого сообщения в `EAX`
call sprint ; вызов подпрограммы печати сообщения
mov ecx, buf1 ; запись адреса переменной в `EAX`
mov edx, 80 ; запись длины вводимого сообщения в `EBX`
call sread ; вызов подпрограммы ввода сообщения
mov eax,4 ; Системный вызов для записи (sys_write)
mov ebx,1 ; Описатель файла '1' - стандартный вывод
mov ecx,buf1 ; Адрес строки buf1 в ecx
int 80h ; Вызов ядра
call quit ; вызов подпрограммы завершения

# Выполнение самостоятельной работы


# Выводы

Я приобрел практические навыки работы в Midnight Commander и освоил
инструкции языка ассемблера mov и int.

# Список литературы{.unnumbered}

::: {#refs}
:::
