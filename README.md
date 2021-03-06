
# MusicGeneration

[![Build Status](https://travis-ci.com/n4mespace/MusicGenerationWebService.svg?token=BH7x1GyGU7Wzay5sJ8QA&branch=master)](https://travis-ci.com/n4mespace/MusicGenerationWebService)

## Пояснювальна записка


# Зміст

1. [Вступ](#introduction)
2. [Технічне завдання](#techtask)
3. [Проектування програмного додатку](#design)
4. [Розробка програмного додатку](#development)
5. [Тестування програмного додатку](#test)
6. [Висновки](#conclusion)


##  1. Вступ <a name="introduction"></a>
### 1.1 Ціль проєкту


MusicGeneration - веб сервіс, на якому користувач може прослуховувати музику згенеровану глубокою нейронною мережею типу "трансформер". Детальніше в цьому [ноутбуці](https://colab.research.google.com/drive/1C1bIClVhXkXy3mRwl3ozXImdYvRgGcwz?usp=sharing). Данні використані для "тюнингу" моделі можна скачати за [посиланням](https://drive.google.com/open?id=1Hbn8jQKIyJtHIbhGbQ0DrbAMha6OFWdM)


### 1.2 Реалізація

Для вебсервісу використовувалися такі фреймворки:

1. Серверна частина (python3):
* [Quart](https://pgjones.gitlab.io/quart/)

2. Клієнтська частина (js):
*  [React](https://ru.reactjs.org/docs/getting-started.html)

3. Нейронна мережа (python3):
* [gpt-2-simple](https://github.com/minimaxir/gpt-2-simple)


## 2. Технічне завдання <a name="techtask"></a>

### 2.1 Загальне завдання

Розробити вебсервіс, на якому користувач може слухати згенеровану нейронною мережею музику.

### 2.2 Функціональність

 - кілька жанрів музики на вибір.
 - можливість отримання згенерованої музики сторонніми сервісами через REST API:

1. GET api/generate
2. POST api/generate

Ендпоінт приймає такі параметри:
- temperature -- чим більше temperature, тим більш різноманітний результат
- top_k -- вибрати краций результат з top_k разів
- include_prefix -- чи включити у результат сам префікс
- prefix -- початкова точка генерації

### 2.3 Документація

 - JsDoc
```bash
>> cd client
>> npm run docs
```
 - PythonDoc
```bash
>> cd docs/PythonDoc
>> make html
>> sphinx-build -b rinoh source _build/rinoh
```

## 3. Проектування програмного додатку  <a name="design"></a>

### Проєктування графічного інтерфейсу користувача

Веб-сервіс побудований як SPA, зразок головної сторінки

![SPA Example page](docs/img/page_image.png)

## 4. Розробка програмного додатку  <a name="development"></a>
 ### TODO: 
 * // що залишилося реалізувати
 
## 5. Тестування програмного додатку <a name="test"></a> 

За допомогою бібліотеки [pytest](https://docs.pytest.org/en/latest/) та [pytest-asyncio](https://github.com/pytest-dev/pytest-asyncio) запускаємо тести командою:
```bash
>> pytest tests.py
```
Також автоматично тестування запускається після кожного коміту за допомогою інтеграції з [Travis-ci](https://docs.travis-ci.com/)

## 6. Висновки  <a name="conclusion"></a> 

За допомогою розробки цього проекту я покращила не тільки теоретичні знання в сфері програмування на python3 та js, але й набула нових навичок у використанні різних бібліотек для побудови веб-сервісу, також поглибила знання у сфері NLP.
