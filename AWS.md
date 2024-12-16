Abrimos la terminal 
```bash
ssh -i tu-clave.pem ubuntu@172.31.27.246
```

![image](https://github.com/user-attachments/assets/a8d002e4-0e9d-4a1b-b6b3-69b989d4469e)

A continuación actualizaremos los paquetes del sistema con
```bash
sudo apt update
sudo apt upgrade -y
```

Tras esto instalaremos apache y los módulos necesarios para la autenticación MySQL y SSL
```bash
sudo apt install apache2 -y
```
Y verificamos para saber si Apache está funcionando
```bash
sudo systemctl status apache2
```

![image](https://github.com/user-attachments/assets/e3630c49-0272-46aa-b2e1-9143a3d92f4e)

Instalamos MySQL server con el siguiente comando
```bash
sudo apt install mysql-server -y
```
Y procedemos a comprobar si está activo

![image](https://github.com/user-attachments/assets/50cdc775-100a-4200-867a-921ed4e66765)

Accedemos a MySQL
```bash
sudo mysql -u root
```
Y a continuación creamos la base de datos y un usuario

![image](https://github.com/user-attachments/assets/27f945a1-f22d-483b-95e8-ecce309c580b)

Y a continuación una tabla para los usuarios

![image](https://github.com/user-attachments/assets/aa460da1-e261-4a72-bbf2-35c015709784)

Editaremos el archivo de configuración de apache
```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```
Y agregaremos esto al directorio
```bash
<Directory "/var/www/html/secure">
    AuthType Basic
    AuthName "Área Restringida"
    AuthBasicProvider dbd
    AuthDBDUserPWQuery "SELECT password FROM users WHERE username = %s"
    Require valid-user
</Directory>
```
Habilitamos los módulos

![image](https://github.com/user-attachments/assets/fe44bdf3-7969-4699-87da-30d86b047298)

Habilitamos el módulo ssl
```bash
sudo a2enmod ssl
```  

A continuación crearemos el certificado autofirmado

![image](https://github.com/user-attachments/assets/54247526-1854-4bbf-905e-f9d18e74b5d6)

Tras esto editaremos el archivo SSL por defecto, añadiremos esto
```bash
SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
```

Por último habilitaremos el sitio mediante el comando
```bash
sudo a2ensite default-ssl.conf
```
Y reiniciamos apache
```bash
sudo systemctl restart apache2
```




