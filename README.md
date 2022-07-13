# Социальная сеть Yatube API
Социальная сеть, в которой реализованы следующие возможности: публикация новых записей, комментирование, исправление и их удаление, получение списка сообществ, отдельные сообщества. Также реализована возможность подписываться и отписываться от авторов, получение, обновление и проверка токенов для доступа к сервису.

## Технологии
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/P?color=brightgreen&label=Pyton)
![PyPI - Python Version](https://img.shields.io/badge/Django-3.2-brightgreen)
![PyPI - Python Version](https://img.shields.io/badge/Django%20Rest%20Framework-brightgreen)
![DWT](https://img.shields.io/badge/JWT-%20brightgreen)
![Djoser](https://img.shields.io/badge/Djoser-%20brightgreen)


## Установка и запуск проекта

+ Клонировать репозиторий.
```bash
git clone git@github.com:Alex-Kirma/api_final_yatube.git
```
+ Установить и активировать виртуальное окружение(версия python 3.7).
```bash
python3 -3.7 -m venv venv
. venv/scripts/activate
```
+ Обновить менеджер пакетов pip.
```bash
python -m pip install --upgrade pip
```
+ Установить зависимости из файла requirements.txt.
```bash
pip install -r requirements.txt
```
+ Сделать миграции.
```bash
python manage.py migrate
```
+ Создать суперпользователя.
```bash
python manage.py createsuperuser
```
+ Запустить проект:
```bash
python manage.py runserver
```
## Примеры работы с API сервиса для всех пользователей.
Для неавторизованных пользователей работа с API доступна в режиме только для чтения.
```
GET api/v1/posts/ - получить список всех публикаций.

GET api/v1/posts/{id}/ - получение публикации по id

GET api/v1/groups/ - получение списка доступных сообществ

GET api/v1/groups/{id}/ - получение информации о сообществе по id

GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации

GET api/v1/{post_id}/comments/{id}/ - Получение комментария к публикации по id
```
## Примеры работы с API для авторизованных пользователей
Создание публикации:
```
POST /api/v1/posts/
```
в body { "text": "string", "image": "string", "group": 0 }

Обновление публикации:
```
PUT /api/v1/posts/{id}/
```
PATCH /api/v1/posts/{id}/

Частичное обновление публикации:

```
PATCH /api/v1/posts/{id}/
```
в body { "text": "string", "image": "string", "group": 0 }

Удаление публикации:
```
DEL /api/v1/posts/{id}/
```
Доступ авторизованным пользователем доступен по JWT-токену (Joser), который можно получить выполнив POST запрос по адресу:
```
POST /api/v1/jwt/create/
```
в body:

{
"username": "string",
"password": "string"
}

Полученный токен добавляем в headers (postman), после чего буду доступны все функции проекта:

```
Authorization: Bearer {your_token}
```
Обновление JWT-токена:

```
POST /api/v1/jwt/refresh/ - обновление JWT-токена
```
Все виды запросов достуны в документации по эндпоинту: /redoc

## Автор: Кырма Алексей.
