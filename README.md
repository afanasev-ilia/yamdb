# api_yamdb

api_yamdb

## Описание

Проект YaMDb собирает отзывы пользователей на произведения

### Технологии

Python 3.7 Django 3.2 Gunicorn 20.0.4 Docker

#### Как запустить проект

Клонируем репозиторий и переходим в него в командной строке:

```bash
git clone https://github.com/LihieTapki/infra_sp2.git
```

```bash
cd infra_sp2/infra
```

Запускаем docker-compose:

```bash
docker-compose up -d --build
```

Выполняем миграции:

```bash
docker-compose exec web python manage.py migrate
```

Создаем суперппользователя:

```bash
docker-compose exec web python manage.py createsuperuser
```

Собираем статику проекта:

```bash
docker-compose exec web python manage.py collectstatic --no-input
```

Загружаем данные из файла фикстур:

```bash
python manage.py loaddata dump.json
```

Останавливаем собранные контейнеры:

```bash
docker-compose down -v 
```

Документация в формате Redoc:

```HTTP
http://127.0.0.1:8000/redoc/
```

##### Шаблон наполнения .env

```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД 
```

###### Авторы

Архипов Владимир
Афанасьев Илья
Гринчар Николай
