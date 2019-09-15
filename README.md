## BIG DATA ARCHITECTURE
 
Práctica Guillermo Yuste - Big Data Architecture

## Idea General

Usar el [dataset de Airbnb](https://public.opendatasoft.com/explore/dataset/airbnb-listings/export/?disjunctive.host_verifications&disjunctive.amenities&disjunctive.features&q=Madrid&dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7InR5cGUiOiJjb2x1bW4iLCJmdW5jIjoiQ09VTlQiLCJ5QXhpcyI6Imhvc3RfbGlzdGluZ3NfY291bnQiLCJzY2llbnRpZmljRGlzcGxheSI6dHJ1ZSwiY29sb3IiOiJyYW5nZS1jdXN0b20ifV0sInhBeGlzIjoiY2l0eSIsIm1heHBvaW50cyI6IiIsInRpbWVzY2FsZSI6IiIsInNvcnQiOiIiLCJzZXJpZXNCcmVha2Rvd24iOiJyb29tX3R5cGUiLCJjb25maWciOnsiZGF0YXNldCI6ImFpcmJuYi1saXN0aW5ncyIsIm9wdGlvbnMiOnsiZGlzanVuY3RpdmUuaG9zdF92ZXJpZmljYXRpb25zIjp0cnVlLCJkaXNqdW5jdGl2ZS5hbWVuaXRpZXMiOnRydWUsImRpc2p1bmN0aXZlLmZlYXR1cmVzIjp0cnVlfX19XSwidGltZXNjYWxlIjoiIiwiZGlzcGxheUxlZ2VuZCI6dHJ1ZSwiYWxpZ25Nb250aCI6dHJ1ZX0%3D&location=16,41.38377,2.15774&basemap=jawg.streets), para simular la intención de buscar un lugar óptimo para montar una empresa de turismo  de aventura.

## Diagrama

[Enlace al Diagrama](https://docs.google.com/drawings/d/1gXVE_xu6VsjlSTch8qfKb0Nv3GazjpoLwMiL8eNrCrw/edit?usp=sharing)

## Guía de ejecución de los pasos

### Scraping

Queremos enriquecer los datos de Airbnb con otro dataset extraido de turismo-activo.net, que nos dará información muy valiosa de las empresas de turismo de aventura por localización en España.
Este scraping elijo hacerlo desde la herramienta Import.io en vez de por scripts de scrapy.org.


[Enlace a la captura](https://drive.google.com/drive/folders/1I5RVYGOO8FNP8Vkwq6MnBB3OgTmtFktY?usp=sharing)


### Perfilado de los datos

Uso Trifacta para hacer una limpieza y perfilado de los datasets de Airbnb y Turismo-activo.net
Creamos una nueva “Recipe” y un “new job” para limpiar los datos, especialmente los dedicados a la localización, que es lo que usaremos.

[Enlace a la captura](https://drive.google.com/drive/folders/1vcI3BldqSBUdDYyCYTOSeLYwHbGL5TFm?usp=sharing)

### Cloud

Usaré Google Cloud Storage para almacenar los datos en un cluster con los siguientes segmentos contenedores
gy-airbnb1
gy-turismo-activo1

### Hadoop

Subiríamos los datos al cluster de Hadoop mediante Google storage connector para insertarlos en el HDFS.

Para ello descargaríamos el conector de Hadoop copiaríamos el archivo jar a nuestro directorio de Hadoop.
Tras lo cual, habríamos habilitado la API de computer engine en nuestro proyecto


### Operaciones de datos

Utilizaríamos PostreSQL / Cloud SQL para insertar los datos extraídos realizar operaciones aunando ambos datasets.
Para la configuración usaríamos el marketplace de Google Cloud.
Elegiría SQL frente a NoSQL debido a la calidad estructurada de los datos con los que trabajamos.


### Visualización de datos

Para presentación de gráficos y resultados finales lo haríamos tanto en excel, como en herramientas integradas en cloud marketplace como CanvasJS

