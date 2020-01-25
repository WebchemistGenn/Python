# Django

## Django 설치

```bash
python3 -m pip install django
```

## Django 프로젝트 설치

```bash
django-admin startproject [project-name]
```

```bash
project-name/
  manage.py
  mysite/
    __init__.py
    settings.py
    urls.py
    asgi.py
    wsgi.py
```

## Django 프로젝트 동작

```bash
cd project-name

python3 manage.py runserver

open http://localhost:8000
```

## Django 마이그레이션 파일 생성

```bash
python3 manage.py migrate
```

## Django Admin 계정생성

```bash
python3 manage.py createsuperuser --username=name
```

## 사이트 만들기

```bash
python3 manage.py startapp [app-name]
```

```bash
app-name/
  __init__.py
  admin.py
  apps.py
  migrations/
      __init__.py
  models.py
  tests.py
  urls.py
  views.py
```

## app-name/views.py 수정

```python
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. You're at the polls index.")
```

## app-name/urls.py 생성

```python
from django.urls import path
from . import views

urlpatterns = [
  path('', views.index, name='index'),
]
```

## project-name/urls.py 수정

```python
from django.urls import include, path

urlpatterns = [
  path('[app-name]/', include('[app-name].urls')),
  path('admin/', admin.site.urls),
]
```

재실행 후에 open http://localhost:8000/app-name/ 으로 접근하면 "Hello, world. You're at the polls index."가 출력됩니다.
