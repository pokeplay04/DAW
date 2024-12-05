Comenzamos instalando apache2

![image](https://github.com/user-attachments/assets/8be1d4fb-47f6-4139-a6c1-a8ffb5082479)

Seguimos configurando los dominios, agregando los dominios de departamentos.centro.intranet y centro.intranet

![image](https://github.com/user-attachments/assets/92b6cd5c-9201-49b5-923e-dfb3f048f604)

![image](https://github.com/user-attachments/assets/9e78ee9c-4576-4879-b868-26614082bb23)

Configuraremos el VirtualHost

![image](https://github.com/user-attachments/assets/6ee94dcf-fef4-4134-8f52-74466fb331dd)
![image](https://github.com/user-attachments/assets/c32c208d-9f1c-49c9-a2de-bc36784c0b91)
![image](https://github.com/user-attachments/assets/8c25d12c-a51c-40da-84d5-44afafb970cb)
![image](https://github.com/user-attachments/assets/cba842ed-be7e-4135-a4e4-340d3fd1b1fc)

# INTSTALACIÓN WORDPRESS

Áhora instalaremos tanto las dependencias como el mismo wordpress
```bash
sudo apt install php libapache2-mod-php php-mysql mariadb-server -y
```

Aquí las dependencias

![image](https://github.com/user-attachments/assets/b9cf3cba-d573-40c1-bd93-0936863219f7)

Y aqui el mismo wordpress

```bash
wget https://wordpress.org/latest.tar.gz
tar -xvzf latest.tar.gz
```

Movemos el wordpress a la carpeta centro.intranet y cambiamos el propietario de la carpeta para tener los permisos necesarios

![image](https://github.com/user-attachments/assets/c469aa5f-6ae7-4e77-b070-6cd86a70aceb)

A continuación configuraremos la base de datos
```bash
sudo mysql -u root -p
```
Tras entrar a esta, le cambiaremos la contraseña a "contraseñaproyecto"

![image](https://github.com/user-attachments/assets/9b6185da-5694-4dac-b460-163fdf6ca49d)

Una vez cambiada esta, crearemos tanto la base de datos, como el usuario que se utilizará en la base de datos

![image](https://github.com/user-attachments/assets/7563673e-65c0-40b1-aa6d-d6d596559cc4)
![image](https://github.com/user-attachments/assets/b29bedbd-5c96-40ac-b676-499d55e6c8ee)

Hecho esto, saldremos de mysql
```bash
mysql> exit
```
Una vez hecho esto activamos el módulo rewrite, aunque este nos pedirá que reiniciemos apache

![image](https://github.com/user-attachments/assets/1ce091da-c5c9-455a-99e9-c5be6e6132b1)

Tras reiniciar apache introduciremos en la configuración de apache nuestra ip quedando tal que asi
```bash
ServerName 10.0.2.15
```
Una vez hecho eso accedemos a WordPress e introducimos los datos de la base de datos

![image](https://github.com/user-attachments/assets/bb00c9f5-48ea-4632-ba85-3030287927dd)

Tras hacer lo anterior, nos pedirá información para rellenar, ya podríamos iniciar sesión en WordPress con los datos.

# INSTALACIÓN PYTHON
Para comenzar en esta instalación activamos el modulo wsgi medianto el siguiente comando
```bash
sudo apt-get install libapache2-mod-wsgi-py3
```
A continuación creamos las siguientes carpetas

![image](https://github.com/user-attachments/assets/26ed6044-f187-4b87-b1d3-feb1bfa1bab9)

Accedemos al controlador de la carpeta mypythonapp y añadimos lo siguiente

![image](https://github.com/user-attachments/assets/0c7e3ab1-db54-466c-bf47-7761bfb2c862)

Tras todo esto editaremos otro archivo el cual el nombre se ve arriba, y añadimos esto:

![image](https://github.com/user-attachments/assets/ba77131c-46ad-4e0f-ba8d-430452236330)

Activamos el sitio web y volvemos a reiniciar apache

![image](https://github.com/user-attachments/assets/59fe9e8f-a936-46f8-8f82-e26859cc6509)

Creamos el siguiente script, el cual será lo que veamos en la página

![image](https://github.com/user-attachments/assets/8a1ce5f3-bb25-4730-acb4-a57943b59c00)

Accedemos a la página

![image](https://github.com/user-attachments/assets/f668d955-4080-4b57-9f71-31325b41498a)

A continuación instalamos htpasswd para proteger la aplicación
```bash
sudo apt install apache2-utils
```
Añadimos un usuario y su debida contraseña

![image](https://github.com/user-attachments/assets/50455af2-88e0-42a7-91dc-694dfd353a8c)

Tras esto añadimos las lineas al archivo de configuración ya modificado anteriormente

![image](https://github.com/user-attachments/assets/b5613e9b-d0d4-4fa0-b503-e31b5608a01c)

Reiniciamos apache tras guardar el archivo de configuración
```bash
systemctl restart apache2
```

Y volvemos a entrar en la página web, tras entrar veremos que nos salta la alerta en la que nos pide tanto como el usuario y la contraseña, tras introducir estos datos poddremos acceder sin ningún problema

![Captura de pantalla 2024-12-05 210241](https://github.com/user-attachments/assets/fa324da2-8ffc-4220-868e-7a2f7ea5e630)

A continuación instalaremos awstat
```bash
sudo apt install awstats
```

Entramos al mismo archivo de configuración y modificamos las lineas de SiteDomain y HostAliases

![image](https://github.com/user-attachments/assets/427949bd-aee8-46ff-9f27-054d7573e059)

Tras esto habrá que crear unas estadísticas iniciales con el siguiente comando

![image](https://github.com/user-attachments/assets/c234024c-1b37-494e-8772-19e1905ca718)

Creamos un alias para poder acceder a AWStats y no tener que complicarnos con la dirección 
```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```

![image](https://github.com/user-attachments/assets/2dde6882-9683-4ba5-aba3-27ef19e3b59c)

Accedemos a la página web añadiendo el enlace que se ve en la url de la página

![Captura de pantalla 2024-12-05 a las 22 07 54_d700f93b](https://github.com/user-attachments/assets/e5830997-0fc4-43d8-9488-9a94934d1978)

Instalamos el NGINX y creamos un segundo servidor, tras esto crearemos el archivo de configuración  y añadiremos lo mostrado en la siguiente imagen

```bash
sudo apt install nginx
sudo nano /etc/nginx/sites-available/servidorNginx.centro.intranet
```

![image](https://github.com/user-attachments/assets/e299732b-d3f9-4eef-b863-3f45cf15ebc6)

A continuación creamos el directorio para el dominio

```bash
sudo mkdir -p /var/www/servidorNginx.centro.intranet
```

Tras crear el directorio activamos la configuración de Nginx

![image](https://github.com/user-attachments/assets/27683f2d-c65a-4b97-9673-85f942ffdfb7)

Hacemos que el servidor funcione por el puerto 8080 mediante el siguiente comando 

```bash
sudo nano /etc/nginx/sites-available/default
```

![image](https://github.com/user-attachments/assets/70523851-fabc-4bab-b515-62bae5c322f0)

Ahora procederemos a crear el archivo index.php en el mismo directorio del servidor

![image](https://github.com/user-attachments/assets/f1aa5eee-2b29-47c9-9a55-4af3c30f4325)
![image](https://github.com/user-attachments/assets/f76ec07a-16be-4ea0-adcb-3f02cebb5d61)

Tras esto editamos el host y añadiremos la linea que se mostrará en la imagen

![image](https://github.com/user-attachments/assets/3fc04f0c-4667-4efd-b2a4-9be5861361d8)

Entramos a la página y podremos ver en la URL el archivo agregado anteriormente

![image](https://github.com/user-attachments/assets/6b2ac68a-228e-4b71-a860-a6e8c724b307)

A contoinuación instalaremos phpmyadmin, ya que ya tenemos el servidor Nginx con php

```bash
sudo apt install phpmyadmin -y
```

Al iniciar este comando, tras darle comenzará la instalación y al completarse aparecerá esta ventana, en la que elegiremos apache2

![image](https://github.com/user-attachments/assets/0f429278-5d06-44c7-8e9b-3dd6628bf17d)

Una vez elegido volverá a seguir descargandose y aparecerá esta ventana, en la que elegiremos si

![image](https://github.com/user-attachments/assets/849d6c4f-ca9d-4c65-b6fe-2c2eced4ff1b)

Tras esto pedirá que tengamos una contraseña, la cual introduciremos

![image](https://github.com/user-attachments/assets/174cbceb-34cd-415c-aa42-dd4e309c7325)

Una vez puesta y confirmada, ya habría terminado de instalarse, y ahora crearemos el enlace simbólico para phpmyadmin

![image](https://github.com/user-attachments/assets/c01fb8ff-73e2-430a-9223-b3840e21b944)

Y por último accedemos al dominio, tras esto, podríamos concluir, ya que phpmyadmin ya está instalada, y así terminaría esta práctica

![image](https://github.com/user-attachments/assets/ce00ec93-2461-4988-9a02-732476b1f003)
