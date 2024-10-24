---
layout: post
title: Demo Django
description: This project demo a backend RESTful API use Django framework.
date: 2020-01-10 10:59:00 +0700
categories: demo
thumbnail: [https://camo.githubusercontent.com/b287b1801494552afe94376f70b06ce03d341e2baf2fbfdc2a6664ccc1c7508f/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3730302f312a4d512d4c6638746d7466612d70756d4e3253683063772e706e67](https://camo.githubusercontent.com/c5c14948d100ccce18abaac423617583d5203678b3b8396675017c162444d0f9/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3730302f312a4d512d4c6638746d7466612d70756d4e3253683063772e706e67)
---

![](https://miro.medium.com/max/700/1*MQ-Lf8tmtfa-pumN2Sh0cw.png)

### Criteria
This project demo a backend RESTful API use Django framework

### Source 
[https://github.com/duycs/demo-django](https://github.com/duycs/demo-django){:.link-text}

### Keywords
- Python
- Django
- RESTAPI
- Authentication with JWT
- MySQL

### Installation
- Install Python 3.6.x
- Install Django 2.x
```
python -m pip install Django
```
- Install Mysql
- Create/update *DATABASES* variables at *apps/settings.py* file to correct your local Mysql

### Stpes
1. Clone this repository
2. Open terminal
3. Go to root folder `demo-django`
4. Install some libs
```
pip install -r requirements.txt
```
5. Migrate
```
python manage.py makemigrations
```
```
python manage.py migrate
```
5.1 Some exception case when migration
- https://simpleisbetterthancomplex.com/tutorial/2016/07/26/how-to-reset-migrations.html

6. Run at local
```
python manage.py runserver
```

### Create new app
1. Create folder where create app
```
mkdir ./demo/apps/app-names
```
2. Generate app-names
```
django-admin.py startapp app-name ./demo/apps/app-names
```
3. Add config app to settings
```
INSTALLED_APPS = [
....
    'demo.apps.app-names',
]
```

### TODO
- Refresh-token
- Logout will add token to black list
- Modeling with domain
- Aggregate relations
- Serializers
- Enpoints API for bussiness
- Containerization
- Authorization

### Bugs
- Swagger doc don't show if require authentication
- Swagger exception at Django 3
- Expired token time

---
### References
- https://docs.djangoproject.com/en/3.0/
- https://www.django-rest-framework.org/tutorial/
- https://thinkster.io/tutorials/django-json-api/
- https://github.com/gothinkster/conduit-django
- https://django-rest-swagger.readthedocs.io/en/latest/
- https://github.com/axios/axios
- https://simpleisbetterthancomplex.com/tutorial/2016/07/26/how-to-reset-migrations.html
