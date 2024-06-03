# Прогресс выполнения лабораторной работы №2

## Выбранный для разработки программный продукт 
Представляет собой мобильное приложение для создания заметок.

## Цель исследования
Основная цель работы - практическое изучение классификации и типов тестирования.

## Описание программного проекта
В рамках рабочего проекта была выполнена работа с темой "Социальная сеть". Для реализации проекта были применены такие технологии как Express и Prisma, в качестве решения для базы данных.

Среди функций программного решения: создание текстовых заметок с поддержкой Markdown, просмотр, редактирование и удаление заметок, а также окно просмотра всех существующих заметок с возможностью перехода к каждой из них. Соответствующий скриншот программы представлен ниже.

## Возможные тесты для этого проекта 
Из-за сложности мобильного приложения, включающего как пользовательский интерфейс, так и логику обработки данных пользователей, можно рассматривать множество возможных тестов. 

Тестирование на уровне компонентов особенно важно при использовании React Native из-за возможности повторного использования компонентов. Интеграционное тестирование также обязательно, чтобы удостовериться, что все части программы работают вместе должным образом. Системное тестирование проводилось после каждой новой сборки для проверки полноты выполнения функций. 

Применяемые для проекта виды тестирования включают функциональное, нагрузочное, ресурсное, юзабилити/ UI/ GUI, конфигурационное и прототипирование.

## Обнаруженные ошибки
Было обнаружено, что приложение может терять доступ к базе данных из-за неправильно реализованной логики открытия базы данных. Это было исправлено после функционального тестирования.

<h2 align="center">Картикнка 1 "Отбражение баг репорта <h2>

!['Баг репорт'](/img/1.png)

## Итоги работы
Успешно освоили классификацию и различные виды тестирования на практике, обнаружили и исправили основные ошибки в приложении с помощью этих тестов.