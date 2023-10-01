---
title: "Instruccione de Dockerfile"
linkTitle: "Dockerfile"
weight: 20
menu:
  main:
    weight: 20
icon: fa-regular fa-file-code
draft: true    
---

{{% pageinfo %}}
### __:star: Comandos__  
 Repaso de __comandos__ usados en __docker__ en __línea de comados__
{{% /pageinfo %}}



{{% pageinfo %}}
### Descargando imágenes
#### Obtener en local una imagen llamad __ubuntu:latest__::
```bash
    docker pull ubunut:latest
```
#### Visualizar imágenes en local
```bash
    docker images
```
#### Buscar todas las imágenes que contengan ubuntu cuya distribución empiece por 1
```bash
    docker search ubuntu:1
```


### Creare un contenedor
```bash
    docker create ubuntu:latest
```
#### Crearlo vinculándolo al terminal
```bash
    docker create -t ubuntu:latest
```
#### Crear un contenedor llamada web a partir de la imagen ubuntu:latest __create --name__
```bash
    docker create --name web ubuntu:latest
```
### Arrancar el contenedor web __start__
```bash
    docker start web
```
### Ejecutar un comando en un contenedor __exec__
 Tiene que estar arrancado

```bash
    docker exec -ti  web bash
```
En este caso no funcionará ya que el contenedor creado no está asociad a un terminal y trabajar de forma interactiva
#### Crear un contenedor llamada web para interactuar  __create --name -t -i__
 Antes de crearlo tendrás que borrar el que había 
```bash
    docker rm web
    docker create --name web -t -i ubuntu:latest
```
```bash
    docker start web
```

```bash
    docker exec -ti web bash
```

Ahora ya puedes arrancarlo e interactuar con él
***
#### Listar todos los contenedors __docker ps -a__
> Listar todos los contenedores
```bash
    docker ps -a
```

> Solo aquellos que están arrancados (en estado __Up__)
```bash
    docker ps 
```
#### Crear un contenedor y dejar arrancado y ejecuta una instrucción __docker run__
> a partir de la imagen __ubuntu_latest__.  
> ejecutando el comando __bash__.   
> __-ti__ es para que se quede abierta una terminal y podamos interactuar.
```bash
    docker run -ti ubuntu:latest bash 
```

> Que se llame __web__
> Previamente borramos
```bash
    docker rm web 
    docker run -ti --name web ubuntu:latest bash    
```

> Mapeando el puerto 8000 del anfitrión en el 80 del contenedor
> Previamente borramos
```bash
    docker rm web 
    docker run -ti --name web ubuntu:latest -p 8000:80 bash    
```
> Compartiendo carpetas, la carpeta local llamada app con /var/www/html del contenedor
> Previamente borramos
```bash
    docker rm web 
    docker run -ti --name web -p 8000:80 ubuntu:latest  bash    
```


{{%  /pageinfo %}}