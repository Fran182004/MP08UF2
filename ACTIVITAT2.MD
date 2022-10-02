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

```
 sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/apache2/apache2.conf
```
 
 ![Install apache 2](https://user-images.githubusercontent.com/114162326/193454049-5b3b1ebc-3672-4884-856d-2faf938c73e7.png)

### Instal·lació del servidor Mariadb

He instal·lat el servidor MariaDB

```
sudo apt-get install mariadb-server mariadb-client -y
```

![Install mariadb 1](https://user-images.githubusercontent.com/114162326/193454117-220baec1-8fc6-401b-bd3e-6472f28d887b.png)

 
