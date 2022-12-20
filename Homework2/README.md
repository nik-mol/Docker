# Docker homework№2

## Команды для запуска приложения:

1. docker build .
2. python manage.py migrate
3. docker run -dp 7000:6060 --name new_name_container id_image

## Типовые команды для запуска контейнера c backend-сервером:
```
@baseUrl = http://localhost:8000/api/v1
```
### создание продукта
```
POST {{baseUrl}}/products/
Content-Type: application/json

{
  "title": "Помидор",
  "description": "Лучшие помидоры на рынке"
}
```
### получение продуктов
```
GET {{baseUrl}}/products/
Content-Type: application/json
```
### обновление продукта
```
PATCH {{baseUrl}}/products/1/
Content-Type: application/json

{
  "description": "Самые сочные и ароматные помидорки"
}
```
### удаление продукта
```
DELETE {{baseUrl}}/products/3/
Content-Type: application/json
```
### поиск продуктов по названию и описанию
```
GET {{baseUrl}}/products/?search=помидор
Content-Type: application/json
```
### создание склада
```
POST {{baseUrl}}/stocks/
Content-Type: application/json

{
  "address": "адрес не дом и не улица, мой адрес сегодня такой: www.ленинград-спб.ru3",
  "positions": [
    {
      "product": 2,
      "quantity": 250,
      "price": 120.50
    },
    {
      "product": 3,
      "quantity": 100,
      "price": 180
    }
  ]
}
```
### обновляем записи на складе
```
PATCH {{baseUrl}}/stocks/4/
Content-Type: application/json

{
  "positions": [
    {
      "product": 2,
      "quantity": 100,
      "price": 130.80
    },
    {
      "product": 3,
      "quantity": 243,
      "price": 145
    }
  ]
}
```

### поиск складов, где есть определенный продукт по параметру
```
GET {{baseUrl}}/stocks/?products=2
Content-Type: application/json
```
### поиск складов, где есть определенный продукт по названию (описанию)
```
GET {{baseUrl}}/stocks/?search=дыня
Content-Type: application/json
```