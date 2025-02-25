# Instalación de Wordpress en instancia Debian(o Ubuntu) EC2 con soporte de base de datos RDS y EFS

## 1. Creación de Instancia
Para comenzar esta práctica tendremos que tener nuestra VPC ya creada la cual en mi caso se llama proyecto

![image](https://github.com/user-attachments/assets/21960531-c5cc-467a-be8a-9dfa248228fe)
![image](https://github.com/user-attachments/assets/bdf84643-f1f6-47ee-8ebe-ea91641d5606)
![image](https://github.com/user-attachments/assets/1f95dab9-d862-4bc6-ad12-8422771a16d4)
![image](https://github.com/user-attachments/assets/b8af525e-4a0a-4b16-b48e-0def70a37da1)

tras esto crearemos la instancia dentro de la subred pública, la llamaremos
servidorwordpress y al grupo de seguridad lo llamaremos seguridadwordpress (En origen ponemos 0.0.0.0/24)

![Screenshot_1](https://github.com/user-attachments/assets/086a172f-6c6e-4edb-adf8-dfb2c4a4cf18)

Tras esto le daremos a crear instancia 

![image](https://github.com/user-attachments/assets/284efca8-acd9-41f2-aa7c-517aca719b45)

Luego de crearla comprobaremos si las IPs estan asignadas correctamente

![image](https://github.com/user-attachments/assets/ee8bc258-2aa3-443a-a7d9-ec2cd5951df6)

Tras esto nos conectaremos a la instancia

![image](https://github.com/user-attachments/assets/3ba39a22-2f40-416e-b7b8-5cbddff8b88a)

## 2. Instalación de Apache y PHP

Tras esto instalaremos el servidor apache
```bash
sudo apt update
sudo apt install apache2
sudo systemctl start apache2
sudo systemctl enable apache2
```

![image](https://github.com/user-attachments/assets/415f3c82-e15a-435c-91da-6ba40f5bb74f)
![image](https://github.com/user-attachments/assets/2e29945b-4ebe-4a1f-9106-4a490975bbbe)
![image](https://github.com/user-attachments/assets/5dc1e462-1ee6-43f4-8a6c-2d81b5211418)

Una vez instalado Apache si accedemos a la IP pública de nuestra instancia podremos ver la página de inicio de apache

![image](https://github.com/user-attachments/assets/fa499098-2100-4c36-a2a2-f38e6988373f)

A continuación instalaremos PHP, primero confirmaremos que el paquete amazon-linux-extras está instalado en nuestro servidor, tras esto
instalaremos php como módulo de Apache e instalaremos también MySQL

```bash
sudo apt -y update && sudo apt upgrade

```

![image](https://github.com/user-attachments/assets/bfb08385-9e91-4da3-a508-3976663300b0)
![image](https://github.com/user-attachments/assets/659e2763-7df6-48b7-8647-36f52917da90)
![image](https://github.com/user-attachments/assets/981b4500-6943-4ab0-ba75-6f3342ded276)

Comprobamos a continuación si PHP se ha instalado correctamente

![image](https://github.com/user-attachments/assets/7e0711df-5be3-4e69-8669-7e0bffa76e76)

## 3. Creación de la Base de Datos

Tras instalar PHP y MySql crearemos la base de datos

![image](https://github.com/user-attachments/assets/e55e768f-48e3-475d-b8b3-bf2f9fc747ca)
![image](https://github.com/user-attachments/assets/ea86709a-cf8f-432f-9782-5d9b52011c09)
![image](https://github.com/user-attachments/assets/95d34c37-5c26-48c0-886e-c6828a05493a)
![image](https://github.com/user-attachments/assets/f9dc437a-a671-46a8-96e1-fb1cc9ca3118)
![image](https://github.com/user-attachments/assets/bdb404f0-82ea-4ec0-b982-512c95682411)

Tras todos estos pasos crearemos a la base de datos

![image](https://github.com/user-attachments/assets/ec5f9563-f468-4043-87b7-27c582cb185a)
![image](https://github.com/user-attachments/assets/f61d64b6-8a27-4b1d-bbc1-d14040ff8528)

Una vez creada esta, podremos su punto de enlace en los detalles de la propia base de datos

![image](https://github.com/user-attachments/assets/b892f5be-7ca1-46f5-8b7e-f101e4235bca)

# 4. Elastic File System.

Buscamos el apartado EFS y clicamos en crear un sistema de archivos

![image](https://github.com/user-attachments/assets/71b226ee-3ddb-4d09-ad09-d2c4d16f4034)

Le pondremos el nombre de almacenwordpress y elegiremos la vpc que estamos utilizando en la práctica

![image](https://github.com/user-attachments/assets/9a4ae6e7-ffad-4f62-87d4-de28d543e83f)

Una vez hecho esto le damos a crear, esta deberia de haberse creado y se veria asi

![image](https://github.com/user-attachments/assets/a586ad52-f7f2-4cc6-bd6b-b61716850ee0)

Si clicamos en nuestro sistema de archivos veremos un botoón que pone Asociar, el cual clicaremos
para asociar nuestra instancia al EFS 

![image](https://github.com/user-attachments/assets/8d34eec8-4f70-4bf1-91b6-ed8c32fb9fa4)

Al darle a asociar nos aparecerá esto en pantalla, de las opciones que nos proporciona elegiremos la que pone mediante NFS

![image](https://github.com/user-attachments/assets/0a3360ee-62ba-4add-b9fa-3aafafc0047f)

Antes de aplicar ese comando tendremos que ejecutar el comando nfs-common y crearlo dentro de una carpeta efs 

![image](https://github.com/user-attachments/assets/ee550754-cc93-4a89-ae08-ac9c4cb8daa7)

Una vez hecho esto ejecutaremos el comando que nos habian proporcionado anteriormente y ya tendríamos todo para instalar Wordpress

![image](https://github.com/user-attachments/assets/43c051c3-f371-44b6-ace5-14cfc1c771fc)

# 5. Instalación Wordpress

Accedemos al directory /var/www/html y metemos el siguiente comando

```bash
sudo wget http://wordpress.org/latest.tar.gz
```

![image](https://github.com/user-attachments/assets/e1222d47-e458-4df9-a287-eeff9d325887)

A continuación descomprimimos el archivo que acabamos de descargar con el siguiente comando y revisamos que se haya descomprimido

```bash
tar -xf latest.tar.gz
```

![image](https://github.com/user-attachments/assets/6a54b460-9840-4105-a232-68ca71c1c22f)

Tras esto tendremos que crear unas credenciales, nos conectaremos a la instancia de la base de datos
mediante el punto de acceso de nuestra propia base de datos y poniendo nuestra contraseña

```bash
sudo apt install default-mysql-client
sudo mysql -u admin -h bdwordpress.cztaa9wgx9dy.us-east-1.rds.amazonaws.com -p
```

![image](https://github.com/user-attachments/assets/cc27b875-f408-4384-8f55-892314f041cf)
![image](https://github.com/user-attachments/assets/c103bf89-b283-4862-8c7c-e40d5963ecaa)

Creamos la base de datos, el usuario y la contraseña

```bash
CREATE DATABASE wordpress; 
CREATE USER 'usuario' IDENTIFIED BY 'usuario'; 
GRANT ALL PRIVILEGES ON wordpress.* TO 'usuario'; 
FLUSH PRIVILEGES;
```

Tras introducir estas lineas, si buscamos en el buscador nuestra IP publica mas /wordpress nos aparecerá esto en pantalla

![image](https://github.com/user-attachments/assets/53b2eaa1-4bc1-4b70-b5a9-c9ef6458220b)

Para continuar le daremos al botón de Let's go y rellenaremos los campos

![image](https://github.com/user-attachments/assets/c03d149b-c988-4921-864d-f8107be3c77c)

Una vez rellenados ya accederiamos a la base de datos y tendriamos wordpress listo para usar

















