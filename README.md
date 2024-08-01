# Приложение знакомств

## Описание

Это приложение знакомств позволяет пользователям просматривать анкеты друг друга и ставить лайки или дизлайки. Если два пользователя ставят друг другу лайк, это называется "мэтч", и у них появляется возможность познакомиться. 

В рамках проекта был разработан новый алгоритм для поиска наиболее подходящих анкет. Для проверки его эффективности был проведен A/B-тест, в котором пользователи были разделены на две группы:

- **Группа 0**: пользователи, использующие старый алгоритм.
- **Группа 1**: пользователи, использующие новый алгоритм.

## Задача

Ваша задача заключается в оценке эффективности нового алгоритма. Для этого необходимо выбрать метрики, которые отражают качество сервиса, и провести статистическое сравнение этих метрик между двумя группами.

## Данные

Данные представляют собой выгрузку логов взаимодействия пользователей, содержащую следующие столбцы:

- `user_id_1`: ID первого пользователя
- `user_id_2`: ID второго пользователя
- `group`: группа A/B-теста (0 или 1)
- `is_match`: бинарная переменная, указывающая, произошел ли мэтч (1) или нет (0)

## Анализ

Анализ включает в себя:

1. Импорт данных и предварительная обработка.
2. Вычисление общего числа кликов для каждого пользователя.
3. Определение среднего числа мэтчей на пользователя (конверсия в мэтч).
4. Проведение статистических тестов (тест Хи-квадрат и t-тест) для сравнения метрик между группами.
5. Проверка результатов с использованием метода Монте-Карло.

## Результаты

В результате проведенных тестов было установлено, что:

- Количество кликов у пользователей, использующих новый алгоритм, значительно выше.
- Количество мэтчей и конверсия в мэтч также увеличились.

Все тесты показали значимое отличие между группами, что подтверждает эффективность нового алгоритма. 

## Вывод

Новый алгоритм улучшает качество сервиса, и его можно внедрить для всех пользователей. В среднем, изменения увеличивают количество кликов на 9.57 - 10.29, число мэтчей на 5.73 - 6.21 и конверсию в мэтч на 0.19 - 0.22%.

## Установка

Для запуска приложения вам потребуется установить необходимые библиотеки:

```bash
pip install pandas seaborn statsmodels scipy pingouin matplotlib
```

## Использование

1. Импортируйте данные из CSV-файла.
2. Запустите анализ, используя предоставленный код.
3. Интерпретируйте результаты и делайте выводы о целесообразности внедрения нового алгоритма.
