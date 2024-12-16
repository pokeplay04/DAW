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
sudo apt install apache2 libapache2-mod-auth-mysql php-mysql openssl -y
```
Y verificamos para saber si Apache está funcionando
```bash
sudo systemctl status apache2
```









