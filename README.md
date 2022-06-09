### Что это за проект:

```
Проект api_yatube позволяет пользователям получать интерисующую информацию (о постах, пользователях и группах)
из БД проекта yatube. Также есть возможность публиковать собственные посты, оставлять комментарии к постам.
```

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/yandex-praktikum/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```

### Некоторые примеры запросов к API:

#### Получить список всех публикаций.

Пример запроса:

```
GET http://127.0.0.1:8000/api/v1/posts/ 
```

Пример ответа:
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```

#### Добавление новой публикации в коллекцию публикаций. Анонимные запросы запрещены.

Пример запроса:

```
POST http://127.0.0.1:8000/api/v1/posts/ 
```

Пример ответа:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
