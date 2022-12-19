# api_yamdb

Проект **api_yamdb** собирает **отзывы (Review)** пользователей на  **произведения (Titles)** . Произведения делятся на категории: "Книги", "Фильмы", "Музыка". Список **категорий (Category)** может быть расширен администратором.

# Workflow badge status

```
https://github.com/draf-pick/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg
```

# Технологии

* Python
* Django
* Nginx
* Docker-compose

# Установка

Для запуска приложения проделайте следующие шаги:

1. Склонируйте репозиторий.

```
git clone https://github.com/draft-pick/infra_sp2.git
```

2. Перейдити в папку infra и запустите docker-compose.yaml (при установленном и запущенном Docker)

```
cd infra_sp2/infra
```

```
docker-compose up
```

3. Для пересборки контейнеров выполните команду:

```
docker-compose up -d --build
```

4. В контейнере web выполните миграции:

```
docker-compose exec web python manage.py migrate
```

5. Создатйте суперпользователя:

```
docker-compose exec web python manage.py createsuperuser
```

6. Соберите статику:

```
docker-compose exec web python manage.py collectstatic --no-input
```

Проект запущен и доступен по адресу: [localhost](http://localhost:81/admin/)
