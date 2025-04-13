### Описание

   Проект Yatube API позволяет пользователям публиковать посты.<br/>
   Пользователи могут оставлять комментарии к постам.<br/>
   Реализован функционал подписки пользователй друг на друга.<br/>
   Создавать посты, комментарии и подписываться могут только аутентифицированные пользователи.<br/>
   

### Используемые пакеты:
    asgiref==3.8.1
    atomicwrites==1.4.1
    attrs==25.3.0
    certifi==2025.1.31
    cffi==1.17.1
    charset-normalizer==2.0.12
    colorama==0.4.6
    coreapi==2.3.3
    coreschema==0.0.4
    cryptography==41.0.7
    defusedxml==0.7.1
    Django==3.2.16
    django-templated-mail==1.1.1
    djangorestframework==3.12.4
    djangorestframework-simplejwt==4.7.2
    djoser==2.1.0
    idna==3.10
    iniconfig==2.0.0
    itypes==1.2.0
    Jinja2==3.1.6
    MarkupSafe==3.0.2
    oauthlib==3.2.2
    packaging==24.2
    Pillow==9.3.0
    pluggy==0.13.1
    py==1.11.0
    pycparser==2.22
    PyJWT==2.10.1
    pytest==6.2.4
    pytest-django==4.4.0
    pytest-pythonpath==0.7.3
    python3-openid==3.2.0
    pytz==2025.1
    requests==2.26.0
    requests-oauthlib==2.0.0
    six==1.17.0
    social-auth-app-django==4.0.0
    social-auth-core==4.5.6
    sqlparse==0.5.3
    toml==0.10.2
    typing_extensions==4.12.2
    tzdata==2025.1
    uritemplate==4.1.1
    urllib3==1.26.20

### Установка

1. Клонировать репозиторий:

   ```python
   git clone https://github.com/71R4N/api_final_yatube.git
   ```

2. Перейти в папку с проектом:

   ```python
   cd yatube_api
   ```

3. Установить виртуальное окружение для проекта:

   ```python
   python -m venv venv
   ```

4. Активировать виртуальное окружение для проекта:

   ```python
   # для OS Lunix и MacOS
   source venv/bin/activate
   # для OS Windows
   venv/Scripts/activate
   ```

5. Установить зависимости:

   ```python
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

6. Выполнить миграции на уровне проекта:

   ```python
   cd yatube_api
   python manage.py migrate
   ```

7. Запустить проект:
   ```python
   python manage.py runserver
   ```

### Примеры запросов  
* Запрос на получение JWT-токена.  
    `POST http://127.0.0.1:8000/api/v1/jwt/create/`
    ```json
    {
        "username": "string",
        "password": "string"
    }
    ```
* Ответ:
    ```json
    {
        "refresh": "string",
        "access": "string"
    }
    ```
* GET-запрос к ресурсу posts.
   Получение списка всех постов. Доступно без токена.
   `GET http://127.0.0.1:8000/api/v1/posts/`
* Пример ответа:
   ```json
    {
       "count": 1,
       "next": null,
       "previous": null,
       "results": [
           {
               "id": 1,
               "author": "User",
               "text": "string",
               "pub_date": "2025-03-10T19:56:01.961065Z",
               "image": null,
               "group": null
           }
       ]
    }
   ```
* POST-запрос к ресурсу posts.
   Добавление нового блога. Необходим токен.  
   `GET http://127.0.0.1:8000/api/v1/posts/`
   ```json
    {
      "text": "string",
      "image": "string",
      "group": 0
    }
   ```
* Пример ответа:
   ```json
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2025-05-14T14:15:22Z",
      "image": "string",
      "group": 0
    }
   ```
  
Более подробное описание эндпоинтов с примерами доступно по адресу: http://127.0.0.1:8000/redoc/


