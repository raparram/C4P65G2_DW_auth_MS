# C4P65G2_DW_auth_MS

# Para ejecutar la app en local desde VS code

```
env\Scripts\activate
Python manage.py makemigrations
Python manage.py migrate
py manage.py runserver 8080
```

# Para desplegar la app en Heroku

```
python -m venv env
env\Scripts\activate
pip install -r Requirements.txt
```

NOTA: SÓLO en caso que no funcione, antes de subir a heroku, se debe ejecutar

```
docker build app_name .
```

NOTA: En caso que coloque algun problema debe ejecutar:

```
pip install django
pip install djangorestframework
```

```
heroku login
```

se inicia sesion en la web de heroku

```
heroku create app_name
```

En este punto se crea la base de datos postgresql en la pagina de heroku buscando la aplicacion app_name
Una vez teniendo las credenciales se configuran en setting.py

```
ALLOWED_HOSTS = ['localhost', '127.0.0.1', 'app_name', 'https://app_name.herokuapp.com']
```

```
Python manage.py makemigrations
Python manage.py migrate
heroku container:login
heroku container:push web -a app_name
heroku container:release web -a app_name
heroku open -a app_name
```

# Para verificar Endpoints

Para conocer y verificar los endpoints lo invitamos al siguiente link: ,dondese muestra un JSON con los endpoints listos para correr desde Postman.
