# DOCKER-CASSANDRA

En este repositorio se muestara como consruir y correr el motor de base de datos CASSANDRA desde docker

## Dockerfile
Se crea el dockerfile con el siguiente contenido

```
FROM cassandra:4.1
EXPOSE 9042
```

### Construir la imagen

```
 docker build -t mi-cassandra .
```

### Se crea el contenedor
```
docker run --name cassandra-contenedor -d -p 9042:9042 mi-cassandra
```
Utilicé el mismo puerto del contenedor en el host (9042) para ser más intuitivo y recordar fácilmente el puerto en el que se expone en mi maquina

### Entrar a casandra
```
docker exec -it cassandra-contenedor bash
```
luego
```
cqlsh
```
docker exec: Decirle a docker que ejecute un comando dentro de un contenedor en ejecución

-it:
-i: modo interactivo (mantener la entrada estándar abierta) para poder escribir comandos
-t: asignar una terminal virtual para que se vea como una consola normal (colores,formato,etc).

cqlsh (Cassandra Query Language Shell): Consola oficial de Cassandra para ejecutar comandos.

