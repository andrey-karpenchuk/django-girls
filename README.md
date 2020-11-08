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

manage gjango
```
python manage.py migrate
python3 manage.py startapp blog
python3 manage.py makemigrations blog
python3 manage.py migrate blog
python3 manage.py runserver
python manage.py createsuperuser  (admin/1)
```
ORM==> python manage.py shell
```
from blog.models import Post
Post.objects.all()

from django.contrib.auth.models import User
me = User.objects.get(username='admin')
Post.objects.create(author=me, title='Sample title', text='Test')
Post.objects.filter(title__contains='title')
Post.objects.all()

Post.objects.filter(author=admin)
from django.utils import timezone
Post.objects.filter(published_date__lte=timezone.now())

post = Post.objects.get(title="Sample title")
post.publish()
Post.objects.filter(published_date__lte=timezone.now())

#sorted
Post.objects.order_by('created_date')
Post.objects.order_by('-created_date')

Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
```