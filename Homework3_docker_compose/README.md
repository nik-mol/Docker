# Homework3_Docker_Compose

### Создаем проект (django - это обращение к сервису)
```
docker-compose run django django-admin startproject new_progect .
```
### Собираем образ
```
docker-compose build
```
### Запускаем контейнер
```
docker-compose up
```
### Запускаем миграции
```
docker-compose run django python manage.py migrate
```
### Создание суперпользователя
```
docker-compose run django python manage.py createsuperuser
```
### Остановка контейнера
```
docker-compose down
```

