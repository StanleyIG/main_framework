## Кастомный web фреймворк

### Небольшой какстомный фреймворк по созданию web приложений который работает поверх интефейса web сервера WSGI.
### Ядро фреймворка:
- всё что свзяано с обработкой GET, POST запросов находится в дирректории ```main_fraimwork```
- в ```main.py``` происходит обработка поступающих запросов, так-же и запросов с параметрами
- в фреймворке поддерживается любая статика ```css```, ```JavaScript```, для наглядности вся статика добавлена в папку ```staticfiles```
- для демонстрации работы есть 1 простой ```JavaScript```. Подробное описание его работы можете найти в ```staticfiles/js/test.js```
### Контроллеры и маршрутизаторы:
- Маршрутизаторы работают по принципу декоратора поверх основных контроллеров и загружают все "пути" в переменную routes которая обрабатывается самим ядром фреймворка
- Контроллеры реализованы на основе классов, есть небольшая схожеть с Django.
### ORM
- ORM реализован с помощью моделей, при помощи фабричного паттерна, паттерна unit of work для синхронизации и атомарности добавления и изменения данных, а так-же универсального маппера (базовый класс для всех мапперов) в которром реализованы сами запросы на чтение и запись, а так-же мапирование запросов на чтение в объекты Python
- всего реализовано 5 CRUD запросов на изменение и чтение: добавить, обновить, удалить запись, а также получение всех записей и получение записей по id

### Запуск:
- для запуска необходимо пройти в корень проекта и установить все зависимости из файла: ```pip install -r requirements.txt```
- при необходимости запустить скрипт ```python create_db.py```
- запустить фреймворк ```python run.py```