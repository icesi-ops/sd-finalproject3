# PROCESO Y CONFIGURACION
Inicialmente se procede a escribir los Dockerfile tanto de frontend como de backend, se buildean y publican estas imagenes en Dockerhub. Luego empeze a escribir los archivos .yml para el despliegue con kubernetes. Primero hice el de la base de datos, luego el backend y por ultimo el frontend, todos con su respectivo deploy y servicio (en el caso del front, LoadBalancer). Opte por crear cada uno en un pod por separado.

# RETROSPECTIVA
Hubo que cambiar muchas cosas de las app en si, y revisar que variables van y donde consumio algo de tiempo. Db y front estan arriba pero no pude conectar el backend a la base de datos por problemas de conexion debido a la url que no llegaba bien. Fue un buen ejercicio que me ayudo a afianzar mucho la teoria y practicas que tuvimos durante el curso.
