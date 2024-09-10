---
## Front matter
lang: ru-RU
title: Лабораторная работы №4
subtitle: Информационная безопасность
author:
  - Махорин И. С.
institute:
  - Российский университет дружбы народов имени Патриса Лумумбы, Москва, Россия
date: 2024

## i18n babel
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

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
  - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
  - '\makeatletter'
  - '\beamer@ignorenonframefalse'
  - '\makeatother'
---

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Махорин Иван Сергеевич
  * Студент группы НПИбд-02-21
  * Студ. билет 1032211221
  * Российский университет дружбы народов имени Патриса Лумумбы

:::
::: {.column width="30%"}

![](./image/0.jpg)

:::
::::::::::::::


## Цель лабораторной работы

- Получить практические навыки работы в консоли с расширенными атрибутами файлов.

## Теоретическая справка (1)

**Права доступа** определяют, какие действия конкретный пользователь может или не может совершать с определенным 
файлами и каталогами. С помощью разрешений можно создать надежную среду — такую, в которой никто не может поменять 
содержимое ваших документов или повредить системные файлы [1].

## Теоретическая справка (2)

**Расширенные атрибуты файлов Linux** представляют собой пары имя: значение, которые постоянно связаны с файлами 
и каталогами, подобно тому как строки окружения связаны с процессом. Атрибут может быть определён или не определён. 
Если он определён, то его значение может быть или пустым, или не пустым [2].

## Виды расширенных атрибутов

- chattr +a # только добавление, удаление и переименование запрещено

- chattr +A # не фиксировать данные об обращении к файлу

- chattr +c # сжатый файл

- chattr +d # неархивируемый файл

- chattr +i # неизменяемый файл

- chattr +S # синхронное обновление

- chattr +s # безопасное удаление

- chattr +u # неудаляемый файл

- chattr -R # рекурсия

# Ход выполнения лабораторной работы

## Определение расширенных атрибутов файла

![lsattr /home/guest/dir1/file1](image/1.PNG){ #fig:001 width=100% height=100% }

## Установка на файл прав (разрешающие чтение и запись)

![chmod 600 /home/guest/dir1/file1](image/2.PNG){ #fig:002 width=100% height=100% }

## Попытка установить на файл расширенный атрибут «a»

![chattr +a /home/guest/dir1/file1](image/3.PNG){ #fig:003 width=100% height=100% }

## Повышение своих прав и установка расширенного атрибута «a»

![chattr +a /home/guest/dir1/file1](image/4.PNG){ #fig:004 width=100% height=100% }

## Проверка правильности установки атрибута

![lsattr /home/guest/dir1/file1](image/5.PNG){ #fig:005 width=100% height=100% }

## Выполнение дозаписи в файл слова

![echo "test" /home/guest/dir1/file1](image/6.PNG){ #fig:006 width=100% height=100% }

## Выполнение чтения файла

![cat /home/guest/dir1/file1](image/7.PNG){ #fig:007 width=100% height=100% }

## Попытка стереть имеющуюся в файле информацию

![echo "abcd" > /home/guest/dirl/file1](image/8.PNG){ #fig:008 width=100% height=100% }

## Попытка установить на файл права (запрещающие чтение и запись)

![chmod 000 file1](image/9.PNG){ #fig:009 width=100% height=100% }

## Снятие расширенного атрибут «a», повторение операций

![chattr -a /home/guest/dir1/file1](image/10.PNG){ #fig:010 width=80% height=80% }

## Повторение действий с атрибутом «i»

![Повторение действий по шагам с атрибутом «i»](image/11.PNG){ #fig:011 width=80% height=80% }

# Вывод

## Вывод

- В ходе выполнения лабораторной работы были получены практические навыки работы в консоли с расширенными атрибутами файлов.

# Список литературы. Библиография

[[1] Права доступа: https://codechick.io/tutorials/unix-linux/unix-linux-permissions

[2] Расширенные атрибуты: https://ru.manpages.org/xattr/7

[3] Операции с расширенными атрибутами: https://p-n-z-8-8.livejournal.com/64493.html