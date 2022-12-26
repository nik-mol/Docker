# Docker-Compose

### Собираем образ
```
docker-compose build
```
### Запускаем контейнер
```
docker-compose up
```


# Деплой в Docker Hub

### Собираем образ
```
docker build -t nikolay31/myphp ./php
```
nikolay31 - логин с Docker Hub
myphp - имя любое
./php - путь, откуда собираем образ

### Загружаем образ
```
docker push nikolay31/myphp
```
nikolay31/myphp - имя образа