#  Dojo Django 

  - [X] Paso 1: Configurar Django 
  - [X] Paso 2: Crear un modelo en la base de datos
  - [X] Paso 3: Configurar Django REST Framework
  - [X] Paso 4: Serializar el modelo
  - [ ] Paso 5: Visualizar los datos

## Paso 5: Visualizar los datos
Para renderizar los objetos en un JSON debemos obtener todos los objetos de la tabla y pasarlos a través del serializer.

    from rest_framework import viewsets
    from .serializers import HeroSerializer
    from .models import Hero  
    
    class  HeroViewSet(viewsets.ModelViewSet):
    queryset = Hero.objects.all().order_by('name')
    serializer_class = HeroSerializer
Agregamos los endpoints para la API

    from django.urls import include, path  
    from rest_framework import routers  
    from . import views  
      
    router = routers.DefaultRouter()  
    router.register(r'heroes', views.HeroViewSet)  
      
    urlpatterns = [  
    path('', include(router.urls)),  
    path('api-auth/',
	     include('rest_framework.urls',
	     namespace='rest_framework'))  
    ]

Agregamos el endpoint del sitio en *mysite/urls*

    from django.contrib import admin  
    from django.urls import path, include  
      
    urlpatterns = [  
	    path('admin/', admin.site.urls),  
	    path('', include('myapi.urls')),  
    ]
Por último, desplegamos el servidor y visitamos el endpoint que definimos http://localhost:8000/heroes/
