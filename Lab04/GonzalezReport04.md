---
# Front matter
title: "Отчёт по лабораторной работе №4"
subtitle: "Алгоритмы вычисления наибольшего общего делителя"
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

Цель данной лабораторной работы- изучить теорию и реализовать все рассмотренные алгоритмы программно.

# Теоретические сведения

**Алгоритм Евклида** – это алгоритм нахождения наибольшего общего делителя (НОД) пары целых чисел.

Наибольший общий делитель (НОД) – это число, которое делит без остатка два числа и делится само без остатка на любой другой делитель данных двух чисел. Проще говоря, это самое большое число, на которое можно без остатка разделить два числа, для которых ищется НОД[@AlgoritmEvklida].

**Алгоритм нахождения НОД делением**
Большее число делим на меньшее.
Если делится без остатка, то меньшее число и есть НОД (следует выйти из цикла).
Если есть остаток, то большее число заменяем на остаток от деления.
Переходим к пункту 1.

**Бинарный алгоритм Евклида**

Бинарный алгоритм вычисления НОД, как понятно из названия, находит наибольший общий делитель, а именно НОД двух целых чисел. В эффективности данный алгоритм превосходит метод Евклида, что связано с использованием сдвигов, то есть операций деления на степень 2-ки, в нашем случае на 2.

![Бинарный алгоритм](images\Бинарный_алгоритм.JPG)

Теперь рассмотрим этапы работы алгоритма. Они основываются на приведенных свойствах наибольшего общего делителя.

1) инициализируем переменную k значением 1. Ее задача – подсчитывать «несоразмерность», полученную в результате деления. В то время как A и Bсокращаются вдвое, она будет увеличиваться вдвое;

2) пока A и B одновременно не равны нулю, выполняем
   a.если A и B – четные числа, то делим надвое каждое из них: A<-A/2, B<-B/2, а k увеличивать вдвое: k<-k*2, до тех пор, пока хотя бы одно из чисел A или B не станет нечетным;
   b. если A – четное, а B – нечетное, то делим A, пока возможно деление без остатка;
   c. если B – четное, а A – нечетное, то делим B, пока возможно деление без остатка;
   d. если A≥B, то заменим A разностью A и B, иначе B заменим разностью Bи A.*

3) после выхода из 2-ого пункта, остается вернуть в качестве результата произведение B и k: НОД(A, B)=B*k[@Binar].

   **Расширенный алгоритм Эвклида**

   В то время как "обычный" алгоритм Евклида просто находит наибольший общий делитель двух чисел a и b, расширенный алгоритм Евклида находит помимо НОД также коэффициенты x и y такие, что:

   

   ![Расширенный алгоритм](images\Расширенный_алгоритм.JPG)

   Т.е. он находит коэффициенты, с помощью которых НОД двух чисел выражается через сами эти числа[@ExtendedAlgoritm].

# Выполнение работы

![Работа1](images\Работа1.JPG)

![Работа2](images\Работа2.JPG)

![Работа3](images\Работа3.JPG)

# Выводы

В итоге в данной лабораторной работы я изучил теорию и реализовал все рассмотренные алгоритмы программно.

# Список литературы{.unnumbered}

:::{#refs}

:::







