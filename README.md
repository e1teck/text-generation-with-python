# Text generation approaches using python
---
## Table of contents

- [Описание выбранных корпусов](#Описание%20выбранных%20корпусов)
  * [Reviews](#reviews)
  * [News](#news)
    + [Lenta](#lenta)
    + [КП](#КП)
    + [Интерфакс](#интерфакс)
    + [N+1](#N+1)
  * [Literature](#literature)
    + [Проза](#проза)
    + [Поэзия](#поэзия)
  * [Social Networks](#socialnets)

- [Генерация текстов](#Генерация%20текстов)
  * [Препроцессинг](#препроцессинг)
  * [N-граммная модель](#N-граммная%20модель)
  * [Генерация](#Генерация)

- [Эксперименты](#Эксперименты)

---


<!-- toc -->

## Описание выбранных корпусов
Для данной работы я собрал 4 разных корпуса. Один из них на английском языке, остальные на русском. Русскоязычные тексты были взяты из корпуса [TAIGA](https://tatianashavrina.github.io/taiga_site/).

### Отзывы

В данный корпус входят отзывы пользователей с сайта IMDB. Корпус содержит 50000 отзывов, которые в сумме дают 14 млн. слов, а так же 146 тыс. уникальных слов.

### Новости
В данный корпус входят новости из 4х новостных изданий (Lenta, КП, Интерфакс и N+1).

#### Lenta
- 9.5 млн. слов
- 291 тыс. уникальных слов
#### КП
- 6.3 млн. слов
- 216 тыс. уникальных слов
#### Интерфакс
- 7.8 млн. слов
- 217 тыс. уникальных слов
#### N+1
- 2.2 млн. слов
- 137 тыс. уникальных слов

### Литература
В данный корпус входят тексты из художественной литературы, а так же тексты стихотворений.
#### Проза
- 9.1 млн. слов
- 341 тыс. уникальных слов
#### Поэзия
- 1.2 млн. слов
- 127 тыс. уникальных слов

### Социальные сети
Сюда входят сообщения и посты с сайта LiveJournal. В будущем, надеюсь, смогу распарсить Vk и Twitter.
- 40.0 млн. слов
- 752 тыс. уникальных слов

---

## Генерация текстов
Для генерации текстов был написан класс `TextGenerator(method, analyzer)`, который содержит три метода, о которых подробнее будет написано ниже.

### Препроцессинг
Предварительую обработку текстов я решил сделать минимальную, ведь задача в том, чтобы генерировать максимально похожий на настоящий текст. За подготовку текста отвечает метод `prepare_for_generation(...)`, который принимает путь на папку содержащую .txt файлы и возвращает список токенов текста. В качестве токенизатора я использовал TweetTokenizer() из nltk, но в `prepare_for_generation(...)` можно передать любой токенизатор.

### N-граммная модель
Подробнее о данной модели вы можете прочитать по этой ссылке: [Speech and Language Processing. Daniel Jurafsky & James H. Martin](https://web.stanford.edu/~jurafsky/slp3/3.pdf). Метод `fit(...)` считает вероятности для данной модели.

### Генерация
Для генерации используется метод `generate(...)`.

---

## Эксперименты
Ниже представленны короткие куски сгенерированного текста. Большие фрагменты вы можете найти в .ipynb ноутбуках, которые находятся в папке `experiments`.


