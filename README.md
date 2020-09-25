#  Dojo Django 

  - [ ] Paso 1: Configurar Django 
  - [ ] Paso 2: Crear un modelo en la base de datos
  - [ ] Paso 3: Configurar Django REST Framework
  - [ ] Paso 4: Serializar el modelo
  - [ ] Paso 5: Visualizar los datos


## Paso 4: Serializar el modelo
Creamos un nuevo archivo en *myapi/serializers.py*. En este archivo vamos a importar el modelo, importar REST Framework serializer y crea una nueva clase que apunte hacia el modelo.


    $ pip install djangorestframework
Y la agregamos a las apps instaladas

    from rest_framework import serializers
    from .models import Hero
    
    class  HeroSerializer(serializers.HyperlinkedModelSerializer):    
	    class  Meta:    
		    model = Hero    
		    fields = ('name', 'alias')
