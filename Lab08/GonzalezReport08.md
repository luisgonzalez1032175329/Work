---
# Front matter
title: "Отчёт по лабораторной работе №8"
subtitle: "Целочисленная арифметика многократной точности"
author: 
- "Студент: Гонсалес Ананина Луис Антонио, 1032175329"
- "Группа: НФИмд-02-21"
- "Преподаватель: Кулябов Дмитрий Сергеевич,"
- "д-р.ф.-м.н., проф."
date: "Москва 2021"

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
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
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Цель данной лабораторной работы- изучить теорию и реализовать рассмотренные алгоритмы программно.

# Теоретические сведения

**Целочисленная арифметика многократной точности**

Мы считаем, что числа записаны в *b*-ичной системе счисления, где *b* — фиксированное натуральное число, *b* 2. При этом натуральное число, записываемое не более чем *n* цифрами в *b*-ичной системе счисления, мы обозначаем *u*1 *. . . u**n* (допуская, что несколько старших разрядов *u*1, *. . .* , *u**k* могут равняться нулю). Основание *b* не всегда равно 2; иногда оно соответствует размеру машинного слова, отведенному под запись обычных целых чисел. В этом случае мы работаем с массивом, содержащим большое целое число[@Algoritm].

При работе с большими целыми числами удобно хранить знак такого числа в отдельной ячейке или переменной. Если мы хотим, например, перемножить два числа, то знак произведения мы вычисляем отдельно.

**Алгоритм А (сложение неотрицательных целых чисел).**

Для двух неотрицательных чисел *u*1 *. . . u**n* и *v*1 *. . . v**n* вычисляется их сумма *w*0 *. . . w**n*; при этом *w*0 — цифра переноса — всегда равна 0 или 1.

**Алгоритм S (вычитание неотрицательных целых чисел).**

По двум *n*-разрядным неотрицательным целым числам *u*= *u*1 *. . . u**n**v* = *v*1 *. . . v**n* 0 вычисляется их разность *w* = *w*1 *. . . w**n* = *u − v*.

**Замечание:** Для того, чтобы в общем случае установить, что *u*1 *. . . u**n* *v*1 *. . . v**n*, надо пройти по цифрам, вычисляя *u**j* *− v**j*. Это простая проверка; с ее помощью находится знак разности *u − v* в общем случае.

**Алгоритм M (умножение неотрицательных целых чисел столбиком).**

Для чисел *u* = *u*1 *. . . u**n* и *v* = *v*1 *. . . v**m* в системе счисления с основанием *b* мы находим их произведение *w* = *uv* = *w*1 *. . . w**m*+*n*.

**Алгоритм FM («быстрый столбик»)**

| 1    | шаг. *t* := 0.                                               |
| ---- | ------------------------------------------------------------ |
| 2    | **шаг.** (цикл) Для *s* от 0 до *m* + *n −* 1 с шагом 1 выполнить шаги 3 и |
|      |                                                              |
| 3    | **шаг.** Для *i* от 0 до *s* с шагом 1 выполнить присвоение  |
|      | t := t + u*n−i* · v*m−s*+*i*.                                |
| 4    | **шаг.** Присвоить *w**m*+*n−s* := *t* (mod *b*) — наименьший неотрицательный вычет по модулю *b* (опять-таки, это не деление, а чтение записи памяти, если *b* = 2 или *b* — размер машинного слова); *t* := [*t*/*b*]. |



# Выполнение работы

![Алгоритм1](images\Алгоритм1.JPG)

![Алгоритм2](images\Алгоритм2.JPG)

![Алгоритм3](images\Алгоритм3.JPG)

![Алгоритм4](images\Алгоритм4.JPG)

![Алгоритм5](images\Алгоритм5.JPG)

# Выводы

В итоге в данной лабораторной работы я изучил теорию и реализовал рассмотренные алгоритмы программно.

# Список литературы{.unnumbered}

:::{#refs}

:::







