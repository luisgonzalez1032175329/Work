---
## Front matter
lang: ru-RU
title: | 
    Дискретное логарифмирование в конечном поле
author: |
    *Дисциплина: Математические основы защиты информации*  
    *и информационной безопасности*  
    \vspace{2pt}  
    **Студент:** Гонсалес Ананина Луис Антонио, 1032175329  
		**Группа:** НФИмд-02-21  
		**Преподаватель:** д-р.ф.-м.н., проф. Кулябов Дмитрий Сергеевич  
    \vspace{2pt}
date: 25 декабря, 2021, Москва

## Formatting
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true

---

# Цели и задачи

## Цель лабораторной работы

Цель данной лабораторной работы- изучить теорию и реализовать рассмотренный алгоритм программно.

# Выполнение лабораторной работы

**Дискретное логарифмирование в конечном поле**

Пусть р — небольшое простое число, п> l,q = р' GF(q) — конечное поле из q элементов, g — примитивный элемент поля GF(q), h е GF(q) Требуется найти решение уравнения g* = h относительно х при известных g и h. Решение данной задачи существенно зависит от способа представления элементов поля. В данном параграфе мы познакомимся с алгоритмами логарифмирования в GF(q), использующими изученные в курсе алгебры способы задания конечных полей.

Поле GF(q) может быть задано в виде GF(p)[y]/f(y), где f(y) — неприводимый многочлен над GF(p) степени п (см. [ГЕН2, утверждение 17, с. 181]). Поэтому можно считать, что поле GF(q) состоит из многочленов над GF(p) степени не более п - 1, в частности g = g(y). Операции в этом поле выполняются по модулю многочлена f(y).



## Выполнение лабораторной работы 2

**Алгоритм полларда для дискретного логарифмирования**

р-метод Полларда для дискретного логарифмирования (p-метод) — алгоритм дискретного логарифмирования в кольце вычетов по простому модулю, имеющий экспоненциальную сложность. Предложен британским математиком Джоном Поллардом (англ. John Pollard) в 1978 году, основные идеи алгоритма очень похожи на идеи ро-алгоритма Полларда для факторизации чисел. Данный метод рассматривается для группы ненулевых вычетов по модулю p, где p — простое число, большее 3.

Для заданного простого числа p и двух целых чисел a и b требуется найти целое число x, удовлетворяющее сравнению:

![Метод Полларда](images\Полларда.JPG)

где b  является элементом циклической группыG, порожденной элементом a.

## Результат выполнения работы 1

![Выполнение1](images\Выполнение1.JPG)

## Результат выполнения работы 2

![Выполнение2](images\Выполнение2.JPG)

## Результат выполнения работы 3

![Выполнение3](images\Выполнение3.JPG)

#### Выводы

В ходе данной лабораторной работы была изучена теория и реализован рассмотренный алгоритм программно.