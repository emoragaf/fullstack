# Test Fullstack Teck-K

## Objetivo
---
Por medio de este test se evaluarán algunos de tus conocimientos que nos interesan como desarrollador.

## Instrucciones de uso
---
1. Hacer un fork del proyecto
2. Instalar cliente de [Docker](https://www.docker.com/)
3. Instalar [Docker Compose](https://docs.docker.com/compose/)
4. Levantar el proyecto:
    * `cd path/to/project/fullstack`
    * `$ docker-compose up`
    * Verificar correcto funcionamiento en [http://localhost:8000/](http://localhost:8000/)
5. Desarrollar lo que se indica. Si existen supuestos, estos deben definirse claramente
6. Entregar desarrollo por medio de un pull-request y notificar envío por email


## Instrucciones de desarrollo
---
Desarrollar un scraper que permita obtener información de [esta página web](http://books.toscrape.com/index.html), almacenarla en BBDD y luego visualizarla en una interaz web. 

Lo anterior será bajo el uso del framework [Django 2.0.5](https://www.djangoproject.com/).

### *Web Scraping*

Se requiere obtener del [sitio web](http://books.toscrape.com/index.html) la siguiente información:

* Listado de categorías (travel, mystery, etc.)
* Información de cada libro:
  * Category
  * Title
  * Thumbnail
  * Price
  * Stock
  * Product Description
  * UPC


### *Backend*

La información obtenida por el scraper (en la sección anterior) debe ser almacenada en una BBDD sqlite. Para ello se debe modelar la BBDD, crear los modelos de Django y sus respectivas migraciones.

### *Frontend*

La información ontenida por el scraper debe ser presentada en forma de tabla. El diseño queda a libre elección del desarrollador.

¿Qué considera?
* Un botón que inicie/ejecute el scraper para obtner los datos del sitio web(*)
* Un listado de Categorías obtenidas por el scrapers.
* Al seleccionar una categoría, la tabla sólo mostrará libros de esa categoría
* La tabla debe tener un buscador por los atributos que posee
* Se debe poder eliminar registros de la tabla que se presente

Notas:
(*): Si no se dispone de los datos obtenidos por el scraper, debido a la no realización de esta etapa, los datos deben ser ser cargados desde un archivo en formato json. Este archivo debe contener la informaci´ón minima para la interfaz web funciona correctamente, es decir:
* Al menos 3 categorías
* Al menos 5 libros por categoría
* Estructura del archivo JSON es de la siguiente forma:
```
[{
    "categories": [
        {
            "id": 1,
            "name": "Travel"
        }, {
            "id": 2,
            "name": "Mystery"
        }, {
            "id": 3,
            "name": "Historical Fiction"
        }
    ],
    "books": [
        {
            "id": 1;
            "category_id": 1,
            "title": "It's Only the Himalayas",
            "thumbnail_url": "http://books.toscrape.com/media/cache/6d/41/6d418a73cc7d4ecfd75ca11d854041db.jpg",
            "price": "£45.17",
            "stock": True,
            "product_description": "Wherever you go, whatever you do, just ...",
            "upc": "a22124811bfa8350"
        },
        ...
    ]
}]
```

## Restricciones
---
* No se debe usar el Admin de Django
* Usar ORM de Django (no row queries)


## Bonus
---
* Uso de alguna librería en el frontend. Ideal React
* Webscraping usando la librería Requests y BeautifulSoup
* Uso Django Rest Framework para la comunicación entre frontend y backend
* Uso de test (unittest)


## En qué nos fijaremos 
---
* Correcto uso del ORM
* Correcto modelamiento la BBDD
* Correcto uso de GIT
* Patrones de diseño
* Orden del código

