# Examen FINAL¡

**Universidad ICESI**  
**Curso: Sistemas Distribuidos**  
**Docente: Joan S. Garcia D.**  
**Tema: Kubernetes**  
**Autor: Santiago Figueroa Aguirre**  

## Enunciado: ##

La empresa MyHealth nos ha contradatado para brindar un servicio de despliegue de infraestructura. Cabe resaltar que nos han brindado el frontend, backend y la base de datos a utilizar.  

Con todo esto se nos pide lo siguiente:  
  1. Despliegue del frontend:  
    -  El frontend es desplegado como deployment  
    -  El frontend es alcanzable desde internet mediante una IP publica  
  2. Despliegue del backend:  
    -  El backend es desplegado como deployment  
    -  El backend no es alcanzable desde internet  
    -  El backend se conecta con el front  
  3. Despliegue de la base de datos:  
    -  La BD es desplegada como deployment.  
    -  La BD ha sido inicializada con los datos entregados.  
    -  La BD no es alcanzable desde internet.  
    -  La BD se conecta con el backend.   

## Procedimiento: ##  
Primero se han de **crear las imagenes** de los componentes para poder ser desplegados en kubernetes.  
Para ello, se procede a crear los Dockerfiles para la creación de estas imagenes.  
Con el siguiente comando se crean las imagenes a partir de los Dockerfiles.  
 `sudo docker build . -t <Nombre de la imagen>:<tag>`  
Para "Subir" las imagenes y poderlas usar con microk8s se usa:  
 `sudo docker save <Nombre de la imagen> > <Nombre>.tar`  
Y para importarlas es:  
 `sudo microk8s ctr image import <Nombre>.tar`   
Con todo esto, se procede a crear los Pods, luego los ReplicaSets y finalmente los Deployments.   

Primero instalar docker, [Aquí está la información para hacerlo](https://github.com/icesi-ops/training_docker/blob/master/00_installAndBasicCommands/00_init.md)   
Despues, descargar las imagenes del [frontend](https://hub.docker.com/repository/docker/symghoul/midterm3front), [backend](https://hub.docker.com/repository/docker/symghoul/midterm3back) y la [base de datos](https://hub.docker.com/_/couchdb) del docker hub, corriendo el siguiente comando:  
`docker pull <Nombre de autor>/<imagen>`  
Luego, crear el deployment.yml  
Con esto y usando el comando:  
`sudo microk8s.kubectl create -f deployment.yml`  
Se obtiene la parte del front activo.  

El proceso con el back es un poco parecido, lo que hay de diferente son las imagenes.
  
## Retrospectiva: ##  
### **Aprendizajes principales:** ###    
  - Murphy puede joder como uno no se puede imaginar
  - El despliegue de infraestructura es un tema que cuando no lo dominas del todo te puede consumir todo el tiempo del mundo.  
  - El despliegue de infraestructura, cuando lo manejas puedes hacer maravillas.  
  - No subestimar tanto la entrega de una actividad que a priori se ve que no va a llevar mucho tiempo.   
### **Qué salió bien:** ###
  - La aplicación como tal no funcionaba, por lo que nada salió bien, pero en esqueleto estaba bien desplegada.  
### **Qué salió mal:** ###
  - Un error con el cluster no permitía el correcto despliegue de los Pods por lo que no permitía probar las funcionalidades, a pesar de que como se mencionó en terminos de estructura, estaba bien la declaración.  
