### ЛАБОРАТОРНАЯ РАБОТА №4

#### Тема лабораторной работы: методы тест-дизайна

### Общие сведения по работе

Методы тест-дизайна упорядочивают деятельность по проектированию и созданию необходимых наборов тестов для контроля за качеством реализации программных продуктов. Основная задача при этом — минимизация количества тестов и их прогонов при максимизации контроля в условиях ограниченных временных, вычислительных и человеческих ресурсов. В данной лабораторной работе необходимо сосредоточиться на задаче проектирования необходимого набора тест-кейсов для тестирования отдельной функциональности приложений, основываясь на анализе входной информации.

### Цель работы

Цель данной лабораторной работы — применить методы тест-дизайна для проектирования набора тест-кейсов для тестирования отдельной функциональности приложения, выделить эквивалентные классы, минимизировать количество тестов и расчитать количество необходимых прогонов.

### 1. Выделение эквивалентных классов

Для примера возьмем форму авторизации на сайте Яндекс.Маркет. На форме авторизации присутствуют следующие поля и элементы:
1. Поле ввода email.
2. Поле ввода пароля.
3. Кнопка "Войти".

#### Поле ввода email
- Эквивалентный класс 1: Корректный email (формат "user@fa.ru").
- Эквивалентный класс 2: Некорректный email (без "@", без домена и т.д.).
- Эквивалентный класс 3: Пустое поле.

#### Поле ввода пароля
- Эквивалентный класс 1: Корректный пароль (длина от 6 до 20 символов).
- Эквивалентный класс 2: Некорректный пароль (длина менее 6 символов или более 20 символов).
- Эквивалентный класс 3: Пустое поле.

### 2. Расчет количества тестов

Для каждого поля можно выделить по 3 эквивалентных класса. Поле email имеет 3 эквивалентных класса, и поле пароля имеет также 3 эквивалентных класса. Следовательно, общее количество комбинаций будет:
\[ 3 \times 3 = 9 \]

### 3. Список используемых тест-кейсов

#### Тест-кейсы для поля email

| ID  | Описание тест-кейса                   | Входные данные        | Ожидаемый результат                         |
|-----|---------------------------------------|-----------------------|--------------------------------------------|
| 1.1 | Ввод корректного email                | user@fa.ru      | Поле проходит валидацию                    |
| 1.2 | Ввод некорректного email (без @)      | userfa.ru       | Поле не проходит валидацию, вывод ошибки   |
| 1.3 | Пустое поле email                     |                       | Поле не проходит валидацию, вывод ошибки   |

#### Тест-кейсы для поля пароля

| ID  | Описание тест-кейса                   | Входные данные        | Ожидаемый результат                         |
|-----|---------------------------------------|-----------------------|--------------------------------------------|
| 2.1 | Ввод корректного пароля               | password123           | Поле проходит валидацию                    |
| 2.2 | Ввод некорректного пароля (менее 6 символов) | pass                 | Поле не проходит валидацию, вывод ошибки   |
| 2.3 | Пустое поле пароля                    |                       | Поле не проходит валидацию, вывод ошибки   |

#### Комбинированные тест-кейсы

| ID  | Описание тест-кейса                                      | Email               | Пароль            | Ожидаемый результат                            |
|-----|----------------------------------------------------------|---------------------|-------------------|-----------------------------------------------|
| 3.1 | Корректный email и корректный пароль                     | user@fa.ru     | password123       | Успешная авторизация                          |
| 3.2 | Корректный email и некорректный пароль                   | user@fa.ru     | pass              | Поле пароля не проходит валидацию, вывод ошибки|
| 3.3 | Корректный email и пустое поле пароля                    | user@fa.ru     |                   | Поле пароля не проходит валидацию, вывод ошибки|
| 3.4 | Некорректный email и корректный пароль                   | userfa.ru     | password123       | Поле email не проходит валидацию, вывод ошибки|
| 3.5 | Некорректный email и некорректный пароль                 | userfa.ru     | pass              | Поля email и пароля не проходят валидацию, вывод ошибок |
| 3.6 | Некорректный email и пустое поле пароля                  | userfa.ru    |                   | Поля email и пароля не проходят валидацию, вывод ошибок |
| 3.7 | Пустое поле email и корректный пароль                    |                     | password123       | Поле email не проходит валидацию, вывод ошибки|
| 3.8 | Пустое поле email и некорректный пароль                  |                     | pass              | Поля email и пароля не проходят валидацию, вывод ошибок |
| 3.9 | Пустое поле email и пустое поле пароля                   |                     |                   | Поля email и пароля не проходят валидацию, вывод ошибок |

### 4. Расчет количества тестов

Для минимизации количества тестов можно выбрать по одному представителю из каждого эквивалентного класса, что уже было сделано в списке тест-кейсов выше. Общее количество тестов составляет 9.

### 5. Выводы по работе

В данной лабораторной работе были применены методы тест-дизайна, такие как анализ эквивалентных классов и тестирование граничных значений, для проектирования набора тест-кейсов для тестирования формы авторизации на сайте Яндекс.Маркет. Были выделены эквивалентные классы для каждого поля ввода, минимизировано количество тестов и рассчитано общее количество необходимых прогонов. Работа показала важность применения методик тест-дизайна для эффективного и качественного тестирования программных продуктов.

### 6. Список использованных источников

1. ГОСТ Р 56922-2016/ISO/IEC/IEEE 29119-3:2013. Информационная технология. Процессы, методы и жизненный цикл программных средств. Методы тестирования программного обеспечения.
2. Официальный сайт Яндекс.Маркет: https://market.yandex.ru/
