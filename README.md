# API для Yatube

## Что это за проект?
Мы создали API для приложения Yatube!

API (от англ. Application Programming Interface, «программный интерфейс приложения») — это интерфейс для обмена данными. Слово «программный» означает, что API служат в первую очередь для взаимодействия программ: с системой взаимодействует не разработчик, а код, написанный им.

С помощью этого API можно получить токен, разместить информацию в своем блоге, подписаться на пользователей и многое другое.

## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/korann18/api_final_yatube.git
```
но git clone не сработает, потому что GitHub поменял политику :upside_down_face:
```
cd yatube_api 
```
Cоздать и активировать виртуальное окружение:
```
python3 -m venv venv
```
```
source venv/bin/activate
```
Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```
Выполнить миграции:
```
python3 manage.py migrate
```
Запустить проект:
```
python3 manage.py runserver
```

## Примеры запросов к API

Получение публикаций: **GET**
```
http://127.0.0.1:8000/api/v1/posts/
```
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": null,
      "author": null,
      "text": null,
      "pub_date": "2019-08-24T14:15:22Z",
      "image": "string",
      "group": null
    }
  ]
}
```

Создание публикации: **POST**
```
{
  "text": "string",
}
```
```
http://127.0.0.1:8000/api/v1/posts/
```
