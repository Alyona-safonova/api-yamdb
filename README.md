# YaMDb API
Описание проекта:

Проект YaMDb собирает отзывы пользователей на произведения, позволяет ставить произведениям оценку и комментировать чужие отзывы.

Произведения делятся на категории, и на жанры. Список произведений, категорий и жанров может быть расширен администратором.

Сами произведения в YaMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.

Доступ к БД проекта осуществляется через Api.

Полный список запросов и эндпоинтов описан в документации ReDoc, доступна после запуска проекта по адресу:

``` http://127.0.0.1:8000/redoc/ ```

Как запустить проект на тестовом сервере:

Клонировать репозиторий, перейти в директорию с проектом.

``` https://github.com/olrogachev/api_yamdb.git ```

Cоздать и активировать виртуальное окружение:

``` python -m venv venv ```

``` source venv/Scripts/activate ```

Установить зависимости из файла requirements.txt:

``` pip install -r requirements.txt ```

Выполнить миграции:

``` python manage.py makemigrations ```

``` python manage.py migrate ```

Импортировать тестовые данные:

``` python manage.py loadfixtures```

Запустить проект:

``` python manage.py runserver ```

Авторизация пользователей:

Для получения доступа необходимо создать пользователя отправив POST запрос на эндпоинт /api/v1/auth/signup/ username и email

Запрос:

{

"email": "string",

"username": "string"

}

После этого на email придет код подтверждения, который вместе с username необходимо отправить POST запросом на эндпоинт/api/v1/auth/token/

Запрос:

{

"username": "string",

"confirmation_code": "string"

}

Ответ:

{

"access": "string"

}

Полученный токен используется для авторизации

Для просмотра и изменения своих данных используйте эндпоинт /api/v1/users/me/

Примеры запросов к API:

Получение списка всех категорий:

``` http://127.0.0.1:8000/api/v1/categories/ ```

Получение списка всех жанров:

``` http://127.0.0.1:8000/api/v1/genres/ ```

Получение списка всех произведений:

``` http://127.0.0.1:8000/api/v1/titles/ ```

### Документация к API доступна после запуска
http://127.0.0.1/redoc/

Работа выполнялась в клманде.
## Авторы:
[Сафонова Алена](https://github.com/Alyona-safonova)

[Рогачева Ольга](https://github.com/olrogachev)

[Нижник Михаил](https://github.com/Hituzip?tab=overview&from=2023-03-01&to=2023-03-30)
