# DJANGO Girls tutorial

https://tutorial.djangogirls.org/en/django_start_project/


# TO DO
https://ctrlzblog.com/to-do-list-part-1-installing-django/


This repository contains the source code for two tutorials from the CTRL+Z blog.

These tutorials will show you how to create and login users with the least custom code.

### 1. Basic user registration
https://ctrlzblog.com/basic-user-registration-with-django/

### 2. User login and logout
https://ctrlzblog.com/django-login-logout-tutorial/

### How to use this repository

1. **Create a virtual environment**

```
python -m venv venv

```
__>>S1.pentru selectare interpreter
     (Ctrl+Shift+P)) 
__>>S2.0 Run Terminal: Create New Integrated Terminal 
      (Ctrl+Shift+`))

__>>S3.upgrade pip:
```
  python -m pip install -U pip
```

Activate environment
```
source venv/bin/activate
```

2. **Install requirements**


 pip install pip-tools

 Create requirements.in

django==4.1
django-environ


```
pip-compile --output-file=requirements.txt requirements.in
pip install -r requirements.txt
```

3. **Create a .env file in mysite directory**

Add the following code:
```
__>>S.Secure your secret key 

Create a file called 
        .env 
which will store the secret key. 
Our settings.py file will import the secret key from that file.
django-environ, is a package that will help us read environment variables from .env.

A....Create the .env file
Create a file called .env in the same directory as settings.py.

Add the following code, but with your own secret key:

SECRET_KEY=yourchosensecretkeywhichwillbealotmoresecurethanthisone

new secret key:

SECRET_KEY=(j%6^8_+1#j!p1sb+(f!)az*ar((5fod6x@3oqvl57ch)2v!+h
``````````````````````
Generating a Django SECRET_KEY

# importing the function from utils
from django.core.management.utils import get_random_secret_key

# generating and printing the SECRET_KEY
print(get_random_secret_key())
`````````````````````````````
Make sure there are no quotations around the key.

Don’t commit .env!
Add .env to your gitignore.

Update settings
Go to settings.py, add import environ:

# settings.py

import environ
After your imports, add the following line. This will read the values in the .env file.

# settings.py

env = environ.Env()
environ.Env.read_env()

SECRET_KEY = env(‘SECRET_KEY’)
```

4. **Test the server runs**
```
python manage.py runserver
```

5. **Migrate**
```
python manage.py migrate
```

6. **Create a superuser**
```
python manage.py createsuperuser
```

7. **Function definition**

def index(request: HttpRequest) -> HttpResponse:

I have included type-hints here to help explain how the view works. Leave them out (e.g. def index(request):) if you prefer.

The input to a view is a request, which is an instance of the HttpRequest class. The view is a function that returns an instance of the HttpResponse class.
