# Actividades Docker

## Ejercicio 2

Para comenzar con este ejercicio ejecutaremos la imagen "hello world"

![image](https://github.com/user-attachments/assets/3776fda0-a5a6-45ea-9b29-d71acd2e8e45)
![image](https://github.com/user-attachments/assets/95d0ecba-2b7c-4ca5-8015-e8ae1f9b9f91)

Tras esto mostraremos las imágenes de docker

![image](https://github.com/user-attachments/assets/f4dfcb36-b66a-4228-abb6-8d27b21796b8)

Y por último mostramos los contenedores de docker

![image](https://github.com/user-attachments/assets/87837d85-7088-4806-a498-9cfbee508d0c)

Editamos el fichero dockerfile

![image](https://github.com/user-attachments/assets/3c0b9e1f-4f7a-44f7-9bb6-5758ea9913ed)

Construimos el contenedor 

![image](https://github.com/user-attachments/assets/5ab31c33-a433-4c78-b5f0-339476b663d2)

A continuación ejecutaremos el contenedor

![image](https://github.com/user-attachments/assets/076153b1-5379-46ba-8a89-bc466444798b)

Tras ejecutar el contenedor nos crearemos una cuenta en Docker Hub

![image](https://github.com/user-attachments/assets/6076f82f-b968-4798-9791-8eac559b6032)

Y por último publicaremos la imagen, comprabando si esta se ha subido

![image](https://github.com/user-attachments/assets/abc7220d-0906-4149-a352-a46f91f650ec)
![image](https://github.com/user-attachments/assets/68b8e25b-8fae-4b75-a56a-3040bf168e54)

## Ejercicio 3

Comenzaremos este ejercicio descargándonos las siguientes imágenes

![image](https://github.com/user-attachments/assets/a4ffa7cf-8617-46e5-bad3-15eebc007dd0)

Tras descargarlas las mostramos

![image](https://github.com/user-attachments/assets/eba28d9c-f967-45d2-85df-4c02523bdddf)

Tras mostrarlas ejecutaremos los contenedores de hello-world

![image](https://github.com/user-attachments/assets/1742e115-404b-431e-a825-b3e89b9f92f3)
![image](https://github.com/user-attachments/assets/da199e56-ce2d-444a-a2be-3f98b5cc9a94)
![image](https://github.com/user-attachments/assets/28812a08-2536-4d0d-a43f-6f24431ae2ec)

Una vez ejecutados los contenedores, mostramos los que se están ejecutando. Como se ve en la imagen no hay contenedores
ejecutados ya que tras buscar información he leído que los contenedores hello-world son efímeros (se ejecutan y detienen automáticamente)

![image](https://github.com/user-attachments/assets/f7b54a3a-dcb6-4191-afba-b68df5ff1b5e)

Tras esto pararemos los contenedores myhello1 y 2

![image](https://github.com/user-attachments/assets/d9b68af0-db98-4f88-b50e-76a7ac8e35d7)

A continuación borraremos el contenedor myhello1, como se aprecia en la imagen se ven el contenedor 2 y 3 pero no el 1

![image](https://github.com/user-attachments/assets/8ca6caa3-e1ea-4608-95f8-d603dcce7bad)

Si mostramos los contenedores en ejecución no habrá ninguno por lo que menionamos anteriormente

![image](https://github.com/user-attachments/assets/f7b54a3a-dcb6-4191-afba-b68df5ff1b5e)

Y por último borraremos todos los contenedores

```bash
docker rm $(docker ps -aq)
```

## Actividad 4

Clonamos el repositorio de git y accedemos a el

![image](https://github.com/user-attachments/assets/0dbbf80b-ce51-4db2-a0f2-f42cae504937)

Y tras clonarlo creamos la imagen Docker

![image](https://github.com/user-attachments/assets/4d344b4d-20bb-433b-8da1-501386f58041)

Una vez creada la imagen Docker, ejecutamos el contendor, el codigo que vemos es el ID

![image](https://github.com/user-attachments/assets/e2d28442-afd0-415c-9d18-833e390c41c0)

Comprobamos si se ha creado correctamente y miramos su ID

![image](https://github.com/user-attachments/assets/a7181cae-3605-40ea-9a44-be4b286db5d9)

Tras esto entramos a localhost:5000 para comprobar que funcione

![image](https://github.com/user-attachments/assets/54131f58-5440-4f16-96e1-93074f12adec)

Una vez terminado el ejemplo 1 continuaremos con el ejemplo 2 el cual sigue casi los mismos pasos, creamos la imagen

![image](https://github.com/user-attachments/assets/e070a61e-cc76-4ba1-8acb-1ee020921a86)

Tras crear la imagen ejecutamos el contenedor

![image](https://github.com/user-attachments/assets/30c390e3-2377-41cb-97cb-5010bb232a59)

Y accedemos a localhost:5001 para comprobar que este funcione

![image](https://github.com/user-attachments/assets/f191b4b8-cefb-450b-a38b-058b7038abd3)

Con esto concluye el ejemplo 2 y pasamos al tercero y último, creamos la carpeta docker_wordpress

```bash
C:\Users\petar>mkdir wordpress_docker
```

Una vez creada esta carpeta dentro creamos un archivo docker-compose.yml y ejecutamos ```bash docker-compose up -d ```

![image](https://github.com/user-attachments/assets/7d9c25b2-40e7-4138-aaa7-cb34e67bfd0c)

Entramos para comprobar el localhosst y vemos que aparece lo siguiente

![image](https://github.com/user-attachments/assets/a6769a4f-5914-4b2d-8ed2-961004ce29c8)

## ACTIVIDAD 5

Para comenzar este apartado crearemos la carpeta temperaturas y dentro crearemos el fichero docker-compose.yml y una carpeta que 
se llamará app y dentro tendrá el dockerfile y la app de python.
Tras esto nos ubicaremos en la carpeta de temperatura y utilizar el siguiente comando ```bash docker compose up -d ```

![image](https://github.com/user-attachments/assets/9d89cc71-23d9-4d47-b858-324a257fa600)

A continuación podemos listar los contenedores

![image](https://github.com/user-attachments/assets/c69aaebe-6913-4409-acf7-6e633ecc2a32)

Tras esto si accedemos a localhost:8081 nos aparecerá esto

![image](https://github.com/user-attachments/assets/693a1e67-fd9e-4fe0-888c-4d2ab0a17ba2)

El siguiente ejemplo que haremos será el de Wordpress, para comenzar editaremos el docker-compose como pone en la guía,
tras esto volveremos a utilizar el mismo comando pero esta vez en la carpeta que hayamos puesto el docker-compose.yaml ```bash docker compose up -d ```

![image](https://github.com/user-attachments/assets/800e8e71-28f2-4b83-897d-7dcae944cda3)

Una vez hecho podremos volver a listar los contenedores activos si queremos y acceder al localhost para comprobar si funciona

![image](https://github.com/user-attachments/assets/f38c5820-5698-4fe6-9fb3-0688ea64717c)

El último ejemplo que realizaremos de la actividad 5 será el guestbook, lo mismo, en la carpeta de guestbook pegamos el docker-compose que nos ofrece el ejercicio
y creamos el escenario con ```bash docker compose up -d ```

![image](https://github.com/user-attachments/assets/95cc2973-e8be-4160-850a-5cafbfc065a6)

Tras esto vemos si se han creado los contenedores y comprobaremos si se puede acceder correctamente al localhost

![image](https://github.com/user-attachments/assets/622e335e-eb8b-4dc5-9044-07362839825a)
![image](https://github.com/user-attachments/assets/9acdb443-b01e-494a-820b-d0885af1d412)

## ACTIVIDAD 6

### Ejemplo 1 página estática

Para comenzar con esta actividad creamos el dockerfile como está puesto en el ejemplo, y tras eso ejecutamos la imagen
con el siguiente comando ```bash docker build -t josedom24/ejemplo1:v1 . ```

![image](https://github.com/user-attachments/assets/c0041f14-99da-4b7c-8358-49221e45a486)

Tras esto entraremos en el localhost para comprobar que esta funcione correctamente, se debería de mostrar el texto que tenemos en el index.html
que en mi caso es Docker error wasaa

![image](https://github.com/user-attachments/assets/7b988254-a563-4576-ad84-e218fe21f4c8)

### Ejemplo 2 aplicación PHP

El siguiente ejemplo que haremos será el ejemplo 2 al cual yo llamaré ejemplo3, para comenzar crearemos la imagen

![image](https://github.com/user-attachments/assets/ec06b85f-14d1-4994-8879-1fff780da8ce)

Y tras crearlo comprobaremos que se haya creado

![image](https://github.com/user-attachments/assets/df361fb8-26e1-4a60-95b0-4d3860c1d4f8)

Una vez comprobado entraremos a la pagina y a su apartado phpinfo

![image](https://github.com/user-attachments/assets/cc24b284-c35e-4d3b-a65b-8459d3872af6)

En la version 2 cambiaremos el docker file y volveremos a crear la imagen y el contenedor

```bash
docker build -t josedom24/ejemplo2:v2 .
docker run -d -p 80:80 --name ejemplo2 josedom24/ejemplo2:v2
```
![image](https://github.com/user-attachments/assets/975b216d-ff85-470d-ab2e-9eee2be723a1)
![image](https://github.com/user-attachments/assets/e390a1a3-44fc-45ae-9971-965e9dfc2471)

Tras esto accedemos al localhost para comprobar que funcione correctamente

![image](https://github.com/user-attachments/assets/29b40f02-2964-4cc7-889b-f7657ae2455f)

### Ejemplo 3 aplicación Python

Comenzamos cambiando el contenido del dockerfile

```bash
# syntax=docker/dockerfile:1
FROM debian:12
RUN apt-get update && apt-get install -y python3-pip  && apt-get clean && rm -rf /var/lib/apt/lists/*
WORKDIR /usr/share/app
COPY app .
RUN pip3 install --no-cache-dir --break-system-packages -r requirements.txt
EXPOSE 3000
CMD python3 app.py
```

Comenzamos creando la imagen y comprobando que se haya creado

```bash
docker build -t josedom24/ejemplo3:v1 .
docker images
```

![image](https://github.com/user-attachments/assets/70ce9cf9-90b0-4952-a109-ea66200f6a2c)
![image](https://github.com/user-attachments/assets/eedef5bb-8324-414d-980f-b6a0b11ea83e)

Una vez creada la imgagen crearemos el contenedor

![image](https://github.com/user-attachments/assets/80a8c462-65a1-4781-891c-0c5666093e83)

Accedemos al localhost para comprobar de que funcione

![image](https://github.com/user-attachments/assets/aeb8e8b0-f8e3-4517-98a6-79837b5f3418)

En la versión cambiamos el dockerfile que nos facilita la guía

```bash
# syntax=docker/dockerfile:1
FROM python:3.12.1-bookworm
WORKDIR /usr/share/app
COPY app .
RUN pip install --no-cache-dir -r requirements.txt
EXPOSE 3000
CMD python app.py
```

Tras esto volveremos a crear la imagen y el contenedor 

![image](https://github.com/user-attachments/assets/58bb7db1-a65e-4deb-ae0b-f633a4d8cb7b)
![image](https://github.com/user-attachments/assets/bfc0a6d9-8de3-4bf7-bb72-355eb38e5c9e)

Tras cambiar el dockerfile veremos que el unico cambio visible sería el hostname ya que
no hemos cambiado nada del contenido 

![image](https://github.com/user-attachments/assets/0d798d38-d615-4bb9-976e-c15c23598269)

