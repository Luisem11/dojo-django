#  Dojo Django 

  - [ ] Paso 1: Configurar Django 
  - [ ] Paso 2: Crear un modelo en la base de datos
  - [ ] Paso 3: Configurar Django REST Framework
  - [ ] Paso 4: Serializar el modelo
  - [ ] Paso 5: Visualizar los datos


Antes de comenzar se debe asegurar de haber completado la [guía de instalación de Python y creación del entorno virtual.](https://github.com/andrespinov/guia-dojo-django)
## Paso 1: Configurar Django 
### Creación de proyecto de Django
Iniciamos el entorno virtual de python

    $ .\ambiente-dojo\Scripts\activate

Creamos un proyecto de django

    $ cd ambiente-dojo
    $ django-admin startproject mysite

Para probar que el proyecto ha sido creado exitosamente

    $ cd mysite
    $ python manage.py runserver
    Watching for file changes with StatReloader
    Performing system checks...
    
    System check identified no issues (0 silenced).
    September 24, 2020 - 18:51:06
    Django version 3.1.1, using settings 'mysite.settings'
    Starting development server at http://127.0.0.1:8000/
    Quit the server with CTRL-BREAK.
Luego de correr el comando de debe comprobar que esté la plantilla por defecto de django en http://127.0.0.1:8000/. Con CTRL+C se termina la ejecución de este servidor.

### Creación de app para el API 
Creamos un app con el siguiente comando

    $ py manage.py startapp myapi
Django creará por defecto una base de datos simple en SQLite.

Para que django reconozca nuetra app debemos registrarla, para esto editamos mysite/settings.py

    INSTALLED_APPS = [
	     'myapi.apps.MyapiConfig',
	     ...    
    ]
Cada que cambiamos algo en el modelo, debemos hacer que Django actualice estos cambios en la base de datos.

    $ py manage.py migrate
Como último debemos crear un usuario para  administrar la base de datos

    $ py manage.py createsuperuser
>Luego de este comando se deben ingresar las credenciales

Si accedemos a http://127.0.0.1:8000/admin ahora podemos ingresar con estas credenciales.
