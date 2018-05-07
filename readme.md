# Pythononly

This project has two parts.

* [Backend](backend)
* [Frontend](frontend)

* URLs:
    * Admin Panel: [http://localhost:8000/admin](http://localhost:8000/admin)
    * Frontend Application: [http://localhost:3000](http://localhost:3000)
    * API: [http://localhost:8000/api/](http://localhost:8000/api/)

## Local development
### [Backend](backend):
The following environment is used to develop the backend application:
- **OS** : Ubuntu 16.04 LTS (64 bit)
- **IDE** : PyCharm Professional (Version: 2018.1)
- **Python** : 3.5.2 (64 bit)
- **MySQL** : 
```
mysql --version
mysql  Ver 14.14 Distrib 5.7.22, for Linux (x86_64) using  EditLine wrapper
``` 
Python packages:
* `Django`: 2.0.5
* `djangorestframework`: 3.8.2
* `mysqlclient`: 1.3.12

### Install required packages:

* Create a virtual environment: 
    ```
    python3 -m virtualenv venv --no-site-packages
    ```
* Activate the virtual environment: 
    ```
    source venv/bin/activate
    ```
* Install required packages: 
    ```
    pip -r install requirements.txt
    ```
### Local Settings 
Place it in `backend/local_settings.py`
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'pythononly_db',
        'USER': 'your_mysqluser',
        'PASSWORD': 'your_mysqluser_password',
        'HOST': 'localhost',
        'PORT': '3306',
    },
}
CORS_ORIGIN_WHITELIST = (
    'localhost:3000',
    '127.0.0.1:3000',
    '127.0.0.1:3013'
)
# SECURITY WARNING: don't run with debug turned on in production!
DEBUG = True
ALLOWED_HOSTS = ['*']
```
### Necessary Django commands
#### Migrate the models
```
python manage.py migrate
```

#### Run Project
```
python manage.py runserver
```

#### Make Migrations of Models and Reflect them in Database
```
python manage.py makemigrations api
python manage.py migrate
```

#### Open Python Shell Around Django API	
```
python manage.py shell
```

#### Create Super User
```
python manage.py createsuperuser
username: 
Email address: 
Password: 
```

#### How the Backend is created?

* Create a virtual environment: 
    ```
    python3 -m virtualenv venv --no-site-packages
    ```
* Activate the virtual environment: 
    ```
    source venv/bin/activate
    ```
* Install required packages: 
    ```
    pip -r install requirements.txt
    ```
* Start a project called `backend`: 
    ```
    django-admin startproject backend
    ```
* Start an app called `api`: 
    ```
    cd backend
    python manage.py startapp api
    ```
* Start an app called `api`: 
    ```
    cd backend
    python manage.py startapp api
    ```
* Create a database in MySQL called `pythononly_db`
* Place `local_settings.py` in `backend`
* Update the database configuration in `local_settings.py`
* Migrate the models: 
    ```
    cd backend
    python manage.py migrate
    ```
* Create super user: 
    ```
    python manage.py createsuperuser
    ```
* Run server: 
    ```
    python manage.py runserver
    ```

#### Instruction to run API Test (Django): 

* In `root` directory: 
    ```
    make django-test
    ```
* Check the `backend\cover\index.html` file to check the coverage report.

#### Instruction to run the Backend: 

* In root directory: 
    ```
    make django
    ```

### [Frontend](frontend):

Frontend is developed using the following libraries:

* React (version: 16.2.0)
* React DOM (version: 16.2.0)
* Font awesome (version: 4.7.0)

#### Install required packages for Frontend:

* Install all packages listed in `package.json`: 
    ```
    yarn
    ```

#### Instruction to run the Frontend: 

* In root directory: 
    ```
    make react
    ```