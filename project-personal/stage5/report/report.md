---
## Front matter
title: "Пятый этап персонального проекта. Добавить к сайту все остальные элементы."
subtitle: "Операционные системы"
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

Добавить к сайту все остальные элементы.

# Задание

1. Сделать записи для персональных проектов.
2. Сделать пост по прошедшей неделе.
3. Добавить пост на тему по выбору. Языки научного программирования.
4. Добавить с сайту все остальные элементы.

	
# Теоретическое введение

**Заголовок веб-страницы**

Как правило большая полоса сверху с большим заголовком и / или логотипом. Именно здесь обычно размещаетсябазовая информация о веб-сайте.

**Панель навигации сайта - хедер**

Ссылки на разделы сайта: обычно представлены кнопками меню, ссылками или вкладками. Как и заголовок, этот контент обычно остается неизменнымпри переходе с одной веб-страницы на другую - несогласованная навигация на вашем веб-сайте просто приведет к растерянности и разочарованию пользователей. Многие веб-дизайнеры считают панель навигации частью заголовка, а не отдельным компонентом, но это не является обязательным требованием; на самом деле некоторые также утверждают, что реализация этих двух составляющих по отдельности лучше для доступности, так как программы чтения с экрана лучше читают две функции, если они разделены.

**Основное содержание веб-страницы**

Большая область в центре, которая содержит большую часть уникального контента данной веб-страницы, например, видео, которое вы хотите посмотреть, или рассказ, который вы читаете, или карту, которую вы хотите просмотреть, заголовки новостей и т. д. Это та часть сайта, которая определенно будет меняться от страницы к странице!

**Боковая панель страницы**

Тут размещается периферийная информация, ссылки, цитаты, реклама и т. д. Обычно это контекстно к тому, что содержится в основном контенте (например, на странице новостной статьи, боковая панель может содержать биографию автора или ссылки на связанные статьи), но есть также случаи, когда можно найти повторяющиеся элементы, такие как вторичная навигационная система.

**Нижний колонтитул - футер**

Полоса в нижней части страницы, которая зачастую содержит мелкий шрифт, уведомления об авторских правах или контактную информацию. Это место для размещения общей информации, но как правило эта информация не является критичной по отношению к самому сайту. Нижний колонтитул также иногда используется в целях SEO, предоставляя ссылки для быстрого доступа к популярному контенту.

# Выполнение лабораторной работы

1. Сделать записи для персональных проектов (рис. @fig:001, @fig:002, @fig:003).

![Папка с одним из проектов](image/6.png){#fig:001 width=70%}

![Изменяю документ markdown](image/5.png){#fig:002 width=70%}

![Изменяю документ markdown](image/7.png){#fig:003 width=70%}


2. Сделать пост по прошедшей неделе (рис. @fig:004).

Теперь необходимо было зайти в папку blog_ganina/content/post. 

![Изменяю документ markdown](image/1.png){#fig:004 width=70%}

3. Добавить пост на тему по выбору. Языки научного программирования (рис. @fig:005).

![Изменяю документ markdown](image/4.png){#fig:005 width=70%}

4. Добавить с сайту все остальные элементы (рис. @fig:006, @fig:007)

![Делаю featured публикации](image/2.png){#fig:006 width=70%}

![Галерея](image/3.png){#fig:007 width=70%}

5. Результаты (рис. @fig:008, @fig:009, @fig:010, @fig:011, @fig:012, @fig:013)

![Результаты](image/8.png){#fig:008 width=70%}

![Результаты](image/9.png){#fig:009 width=70%}

![Результаты](image/10.png){#fig:010 width=70%}

![Результаты](image/11.png){#fig:011 width=70%}

![Результаты](image/12.png){#fig:012 width=70%}

![Результаты](image/13.png){#fig:013 width=70%}


# Выводы

Я разобралась как работать с блоками на сайте и усовершенствовала свои навыки в написании постов.

# Список литературы{.unnumbered}

1. [Создание сайта](https://создание-сайта.net/news-new/structura-web-stranicy.html)
2. [Hugo docs](https://wowchemy.com/docs/)

::: {#refs}
:::
