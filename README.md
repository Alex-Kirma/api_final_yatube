# api_final
Данный проект api final yatube предназначен для работы с апи сервиса. При запросе через через программу Postman можно добавлять новые посты и комментарии, исправлять, удалять их. Получать список сообществ, отдельные сообщества. Также с помощью данного програмного обеспечения можно получить, обновить и проверить токен для доступа к сервису. По мере улучшения работы сервиса будут добавляться новые возможности и функции.
Для разворачивания проекта на локальной машине необходимо: Скачать ссылку репозитория на проект, с помощью команды git clone <ссылка> склонировать проект. Далее необходимо создать и активировать виртуальное окружение: 
python3 -m venv env. 
source env/bin/activate
Установить зависимости из файла requirements.txt:
python3 -m pip install --upgrade pip
pip install -r requirements.txt
Выполнить миграции:
python3 manage.py migrate
Установить необходимые библиотеки:
pip install djangorestframework
pip install djoser djangorestframework_simplejwt.
Запустить сервер python manage.py runserver
Примеры запросов к api сервиса:
Get запрос по этому адресу http://127.0.0.1:8000/api/v1/posts/ выдаст 
{
"count": 123,
"next": "http://api.example.org/accounts/?offset=400&limit=100",
"previous": "http://api.example.org/accounts/?offset=200&limit=100",
"results": [
{}
]
}
Post запрос 
{
"text": "string",
"image": "string",
"group": 0
}
выдаст ответ 
{
"id": 0,
"author": "string",
"text": "string",
"pub_date": "2019-08-24T14:15:22Z",
"image": "string",
"group": 0
}
