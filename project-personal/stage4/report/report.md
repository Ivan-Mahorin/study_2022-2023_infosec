---
## Front matter
title: "Отчёт по 4 этапу индивидуального проекта


Информационная безопасность"
subtitle: "Использование nikto"
author: "Выполнил: Махорин Иван Сергеевич, 


НПИбд-02-21, 1032211221"

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
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Научиться использовать nikto.


# Выполнение индивидуального проекта

## Работа с nikto

nikto — базовый сканер безопасности веб-сервера. Он сканирует и обнаруживает уязвимости в веб-приложениях, 
обычно вызванные неправильной конфигурацией на самом сервере, файлами, установленными по умолчанию, и небезопасными 
файлами, а также устаревшими серверными приложениями.

Целью сканирования приложением nikto будет локальная виртуальная машина OWASP BWA. 

OWASP BWA — это набор преднамеренно уязвимых веб-приложений, собранных на одной виртуальной машине на базе VMware.

![Скачивание OWASP BWA](image/1.png){ #fig:001 width=100% height=100% }

Через терминал запустим сканирование приложением nikto

![Запуск сканирования nikto](image/2.png){ #fig:002 width=100% height=100% }

Параметры, которые следует использовать при сканировании:

- Указав переключатель командной строки -T с отдельными номерами тестов,
можно настроить тестирование конкретных типов.
- Используя при тестировании параметр -t, вы можете установить значение
тайм-аута для каждого ответа.
- Параметр -D V управляет выводом на экран.
- Параметры -o и -F отвечают за выбор формата отчета сканирования.


Существуют и другие параметры, такие как -mutate (угадывать поддомены, файлы, каталоги и имена пользователей), 
-evasion (обходить фильтр идентификаторов) и -Single (для одиночного тестового режима), которые можно использовать 
для углубленной оценки цели.

# Вывод

В ходе выполнения индивидуального проекта были приобретены практические навыки использования базового сканера 
безопасности веб-сервера nikto.

# Список литературы. Библиография

[1] Документация по этапам индивидульного проекта:  Парасрам Шива, Замм Алекс, Хериянто Теди, Али Шакил, Буду Дамиан, 
Йохансен Джерард, Аллен Ли П18 Kali Linux. Тестирование на проникновение и безопасность. — СПб.: Питер, 2020. — 448 с.: 
ил. — (Серия «Для профессионалов»). ISBN 978-5-4461-1252-4
