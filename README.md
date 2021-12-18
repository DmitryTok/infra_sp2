## Description of progect YaMDb
* User registration
* List of all titles
* List of all genres 
* List of all categories
* List of all rewiews
* List of all comments to rewiew
* List of all users

## Create and feel the .env file
```
DB_ENGINE=<...> # specify that we work with postgresql data base
DB_NAME=<...> # data base name
POSTGRES_USER=<...> # login for connecting to data base
POSTGRES_PASSWORD=<...> # password for connection to data base (create your own)
DB_HOST=<...> # name of the servise (container)
DB_PORT=<...> # port for conection to data base
SECRET_KEY=<...> # kay from settings.py
```

1.Assembly and run the container
```
docker-compose up -d --build
```
2.Migrations
```
docker-compose exec web python manage.py migrate
```
3.Create a Django superuser
```
docker-compose exec web python manage.py createsuperuser
```
4.Collect static
```
docker-compose exec web python manage.py collectstatic --no-input
```

Redoc:
http://127.0.0.1/redoc/
***
### Example of API request:

Request for a creation posts:
```python
import requests
from pprint import pprint
url = 'http://127.0.0.1/api/v1/categories/'
request = requests.get(url).json()
pprint(request)
```
Response from API:
```json
{"count": 3,
 "next": "None",
 "previous": "None",
 "results": [{"name": "Film", "slug": "movie"},
             {"name": "Booc", "slug": "book"},
             {"name": "Music", "slug": "music"}]}
```
***
## Progect author:
* https://www.linkedin.com/in/dmitry-tokariev-86b182157
***

## Technology

- Python 3
- Django
- Django REST Framework
- Simple JWT

## License

[MIT](http://opensource.org/licenses/MIT).
