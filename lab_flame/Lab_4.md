# Цель работы

Цель - разработка тест-кейсов для тестирования функциональности нашей социальной сети на основе анализа входной информации. Нужно обеспечить, чтобы количество тестов было оптимизировано, избегая избыточности.

# Процесс расчета количества тестов

В нашем случае мы будем тестировать отдельные функции социальной сети, например, функцию поиска пользователей, публикацию постов, отправку личных сообщений и т.д.  Рассмотрим, например, функцию поиска пользователей.

Функция поиска пользователей может иметь несколько возможных результатов (классов):

1. Поиск возвращает одного и более пользователя (Первый класс)
2. Поиск возвращает ровно одного пользователя (Второй класс)
3. Поиск не возвращает никаких пользователей (Третий класс)

# Наборы данных

Предположим, в нашей социальной сети зарегистрированы пользователи с именами: "Алексей", "Александра", "Алексей М", "Мария", "Иван", "Иван М".

## Набор 1: 

Поиск "Алексей". Ожидаемые результаты: "Алексей", "Алексей М".

## Набор 2:

Поиск "Иван М". Ожидаемый результат: "Иван М".

## Набор 3: 

Поиск "Сергей". Ожидаемый результат: Ни одного пользователя не найдено.

# Шаги

Следуем аналогичной логике для каждого набора:

- Ввести строку поиска в приложение.
- Запустить функцию поиска.
- Сравнить результаты поиска с ожидаемыми.
- Записать результаты тестирования для каждого случая.

# Ожидаемые результаты

- Для запросов с несколькими возвращаемыми пользователями, приложение должно вернуть всех соответствующих пользователей.
- Для запросов с одним найденным пользователем, приложение должно вернуть только этого пользователя.
- Для запросов без результатов, приложение должно выводить сообщение, что ни одного пользователя не найдено.

Мы можем также протестировать обработку некорректного ввода, например, символы, которые не являются кириллическими буквами или пробельными символами. Но учитывая, что цель нашей работы - нахождение минимального количества тестов, мы можем предположить, что ввод будет всегда корректным.

# Заключение

Мы разработали набор тест-кейсов для тестирования функциональности поиска в нашей социальной сети, основываясь на анализе входных данных и логики работы этой функциональности. Это помогло нам определить минимальное количество тестов, которые необходимо выполнить для обеспечения качества функции.