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

Tras instalar PHP y MySql crearemos la base de datos

![image](https://github.com/user-attachments/assets/e55e768f-48e3-475d-b8b3-bf2f9fc747ca)
![image](https://github.com/user-attachments/assets/ea86709a-cf8f-432f-9782-5d9b52011c09)
![image](https://github.com/user-attachments/assets/95d34c37-5c26-48c0-886e-c6828a05493a)
![image](https://github.com/user-attachments/assets/f9dc437a-a671-46a8-96e1-fb1cc9ca3118)
![image](https://github.com/user-attachments/assets/bdb404f0-82ea-4ec0-b982-512c95682411)

Tras todos estos pasos crearemos a la base de datos

![image](https://github.com/user-attachments/assets/ec5f9563-f468-4043-87b7-27c582cb185a)
![image](https://github.com/user-attachments/assets/f61d64b6-8a27-4b1d-bbc1-d14040ff8528)










