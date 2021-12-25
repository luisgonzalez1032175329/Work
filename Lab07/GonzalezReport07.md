---
# Front matter
title: "Отчёт по лабораторной работе №7"
subtitle: "Дискретное логарифмирование в конечном поле"
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

Цель данной лабораторной работы- изучить теорию и реализовать рассмотренный алгоритм программно.

# Теоретические сведения

**Дискретное логарифмирование в конечном поле**

Пусть р — небольшое простое число, п> l,q = р' GF(q) — конечное поле из q элементов, g — примитивный элемент поля GF(q), h е GF(q) Требуется найти решение уравнения g* = h относительно х при известных g и h. Решение данной задачи существенно зависит от способа представления элементов поля. В данном параграфе мы познакомимся с алгоритмами логарифмирования в GF(q), использующими изученные в курсе алгебры способы задания конечных полей.

Поле GF(q) может быть задано в виде GF(p)[y]/f(y), где f(y) — неприводимый многочлен над GF(p) степени п (см. [ГЕН2, утверждение 17, с. 181]). Поэтому можно считать, что поле GF(q) состоит из многочленов над GF(p) степени не более п - 1, в частности g = g(y). Операции в этом поле выполняются по модулю многочлена f(y)[@Logaritm].

**Алгоритм полларда для дискретного логарифмирования**

р-метод Полларда для дискретного логарифмирования (p-метод) — алгоритм дискретного логарифмирования в кольце вычетов по простому модулю, имеющий экспоненциальную сложность. Предложен британским математиком Джоном Поллардом (англ. John Pollard) в 1978 году, основные идеи алгоритма очень похожи на идеи ро-алгоритма Полларда для факторизации чисел. Данный метод рассматривается для группы ненулевых вычетов по модулю p, где p — простое число, большее 3[@Pollard].

Для заданного простого числа p и двух целых чисел a и b требуется найти целое число x, удовлетворяющее сравнению:

![Поллард](images\Полларда.JPG)

где b  является элементом циклической группыG, порожденной элементом a.

# Выполнение работы

![Выполнение1](images\Выполнение1.JPG)

![Выполнение2](images\Выполнение2.JPG)

![Выполнение3](images\Выполнение3.JPG)

# Выводы

В итоге в данной лабораторной работы я изучил теорию и реализовал рассмотренный алгоритм программно.

# Список литературы{.unnumbered}

:::{#refs}

:::







