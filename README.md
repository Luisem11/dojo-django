#  Dojo Django 

  - [X] Paso 1: Configurar Django 
  - [ ] Paso 2: Crear un modelo en la base de datos
  - [ ] Paso 3: Configurar Django REST Framework
  - [ ] Paso 4: Serializar el modelo
  - [ ] Paso 5: Visualizar los datos


## Paso 2: Crear un modelo en la base de datos
Inicialmente debemos editar el archivo llamado */models.py * en la carpeta *myapp*.

    from django.db import models
    
    class  Hero(models.Model):
	    name = models.CharField(max_length=60)
		alias = models.CharField(max_length=60)
		
		def  __str__(self):
			return  self.name
**name** y **alias** serán los atributos que componer el modelo **Hero**, el método __ str __   le indica a Django que imprimir cuando necesite imprimir una instancia de este modelo.

Indicamos a Django que actualice estos cambios en la base de datos.

    $ py manage.py migrate
Como último, registramos el modelo para que sea accedido desde el panel de administración. Accedemos al archivo *myapp/admin.py*

    from django.contrib import admin
    from .models import Hero
    
    admin.site.register(Hero)
Para verificar que funcionó ejecutamos `py manage.py runserver` y nos debería dejar agregar elementos a la base de datos.

