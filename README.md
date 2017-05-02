## Create virtual environment
    - Python 2.7
    $ python --version
    $ pip install virtualenv
    $ pip install --upgrade pip
    $ virtualenv venv
    $ . venv/bin/activate
    
    - Python 3.5
    $ brew install python3
    $ pyvenv venv3      # install virtual machine
    $ . venv3/bin/activate
    
## Install dependencies
    (venv3) pip install django
    
## Create Project
    $ cd django-pgsql-noobpost
    $ django-admin.py startproject post
    
## Run App
    $ cd post
    $ python manager.py runserver
    Django use sqlite by default
    
## Run PostgreSql in Docker
    $ docker run --name mypgsql -e POSTGRES_PASSWORD=abc123 -d postgres
    
## Install driver
    (venv3) pip install psycopg2
    
## Change db to postgreSQL
    In settings.py, change database from  
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    to
        'ENGINE': 'django.db.backends.postgresql_psycopg2',
        'NAME': 'noobpost',
        'USER': 'postgres',
        'PASSWORD': 'abc123'
    
    
## Create admin user for application
    (venv3) python manage.py migrate
    (venv3) python manage.py createsuperuser  sa/Ben12345
    login as admin
    localhost:8000/admin
    
## Use bootstrap
    Create post/static
    Copy bootsrap css, js into post/static
    
    set static and template in settings.py