django-girls https://tutorial.djangogirls.org/ru

----------------------------------

`django-admin startproject mysite .`

mysite/settings.py
``` 
TIME_ZONE = 'Europe/Moscow'
LANGUAGE_CODE = 'ru-ru'
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']
```
python manage.py migrate

python3 manage.py startapp blog

python3 manage.py makemigrations blog

python3 manage.py migrate blog