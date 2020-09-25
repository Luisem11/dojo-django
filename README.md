#  Dojo Django 

  - [X] Paso 1: Configurar Django 
  - [X] Paso 2: Crear un modelo en la base de datos
  - [X] Paso 3: Configurar Django REST Framework
  - [ ] Paso 4: Serializar el modelo
  - [ ] Paso 5: Visualizar los datos


## Paso 4: Serializar el modelo
Creamos un nuevo archivo en *myapi/serializers.py*. En este archivo vamos a importar el modelo, importar REST Framework serializer y crea una nueva clase que apunte hacia el modelo.

    from rest_framework import serializers
    from .models import Hero
    
    class  HeroSerializer(serializers.HyperlinkedModelSerializer):    
	    class  Meta:    
		    model = Hero    
		    fields = ('name', 'alias')
