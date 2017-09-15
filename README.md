# hackathon.mvideo.ru
# Задание
Тестовое задание

Задача: разработка модели предсказания оценки по тексту отзыва.
Данные: отзывы о товарах с сайта mvideo.ru, оценки, которые поставлены авторами отзыва, категория и брэнд товара. 
Данные: скачать
Цель: Предсказание общей оценки товара
Формат предоставления решения: Ссылка на репозиторий на GitHub с исходным кодом программы, решающей поставленную задачу. На вход программа должна принимать данные в исходном виде (feedback), разбивать на train и test, обучать на train модель и демонстрировать ее качество на test. Репозиторий должен содержать проект для среды разработки и инструкцию по сборке и запуску. Рекомендуем использовать Jupyter Notebook, но окончательный выбор инструментария остаётся за вами.

                          ==============================================
# Описание решения
В ходе работыи спользовались следуюшие библиотеки
pandas, iimplicit, sklearn, pymorphy2, numpy, random, sys, re, math, xgboost, tqdm, matplotlib
Все вышеперечисленные библиотеки устаналиваются через pip 
(pip install %package_name%)

Задача достаточно корректно сводилась к классификации (Только 3% выборки были не целыми числами)
В исходных данных можно выделить два момента:
 - Текст комментария
 - Оценки пользователей для одного бренда или одной модели товара
 
Итоговая модель состояла из комбинации двух моделей
1) Градиеного бустинга (xgboost), обученного на суммарном тексте всех комментариев
2) Рекомендательного алгоритма iimplicit ALS

Для улучшения результата целесообразно
 - Изменить лемматизацию и токенизацию, добавить некоторые пунктуационнае знаки
 - Сделать стеккинг нескольких различных моделей (Линейная регрессия, Random Forest, K-means)
 - Применить лучшие рекомендательные метода (Например метод факторизационнах машин из пакета libFM)
 - Корректно настроить стеккинг нескольких моделей
