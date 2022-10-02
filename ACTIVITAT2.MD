# Instal·lació owncloud

## Guia instal·lació
### Requeriments 

 - Linux: Ubuntu 22.04LTS

 - Servidor web: Apache

 - Base de dades: MariaDB

 - PHP (versio 7.3 o 7.4)

### Instal·lació Apache

He instal·lat el servidor Apache .

```
sudo apt install apache2
```

![Install apache 1](https://user-images.githubusercontent.com/114162326/193453650-84c72e8e-32f8-4845-ae40-f7d53f49273d.png)

 Tot seguit he desactivat el llistat de directoris del servidor.
'''  
 sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/apache2/apache2.conf
'''
 
 
