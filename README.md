# Kittygram - социальная сеть для размещения фотографий домашних животных.
## Описание проекта
Проект, где пользователи могут регистрироваться, загружать фотографии котиков (не только) с описанием их достижений, а также любоваться на других котов.

## Технологии
•	Python-3.9  
•	Django-3.2.3  
•	djangorestframework-3.12.4  
•	nginx  
•	gunicorn-20.1.0  
•   djoser-2.1.0  

## Автор
[@shintsujin](https://github.com/shintsujin)

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/ShintsuJin/kittygram_final.git 
```

Перейти в корневую директорию
```
cd kittygram_final
```

Создать файл .evn для хранения ключей:

```
SECRET_KEY='указать секретный ключ'
ALLOWED_HOSTS='указать имя или IP хоста'
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DB_PORT=5432
```

Запустить docker-compose.production:

```
docker compose -f docker-compose.production.yml up
```

Выполнить миграции, сбор статики:

```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/

```

Создать суперпользователя, ввести почту, логин, пароль:

```
docker compose -f docker-compose.production.yml exec backend python manage.py createsuperuser
```

Готово, теперь можно похвастаться своим Котиком!
