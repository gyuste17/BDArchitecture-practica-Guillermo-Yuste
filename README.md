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


[ENLACE AL VIDEO ]

### Perfilado de los datos

Uso Trifacta para hacer una limpieza y perfilado de los datasets de Airbnb y Turismo-activo.net
Creamos una nueva “Recipe” y un “new job” para limpiar los datos, especialmente los dedicados a la localización, que es lo que usaremos.



### Cloud

Utilizar un proveedor de Cloud para montar un cluster de al menos 3 contenedores configurados correctamente o hacerlo en el cluster local
Usaré Google Cloud Storage para almacenar los datos en un cluster de 3 segmentos
gy-airbnb1, local, nearline
Gy-turismo-activo1

### Hadoop

Subiríamos los datos al cluster de Hadoop mediante Google storage connectore insertarlos en el HDFS.
Indicar pasos necesarios para realizar esto, dependiendo de la opción elegida en el Sprint 3
Realizar la tarea de procesamiento de datos sobre los datos extraídos utilizando WordCount.


### Operaciones de datos

Utilizar HIVE/Elastic/Kafka/Mongo para insertar los datos extraídos durante el Sprint 2 y realizar operaciones con los mismos.
Indicar los pasos y las decisiones de diseño respecto a cómo organizar los datos.

