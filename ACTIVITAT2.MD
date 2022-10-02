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

Després he configurat la instal·lació amb la següent comanda:

```
sudo mysql_secure_installation
```

Y amb els següents paràmetres:
- Deshabilitar usuaris anònims.
- Deshabilitar l'accés remot com ara root.
- Eliminar les bases de dades de test y l'accés a les mateixes.
- Actualitzar les taules de privilegis.
 
![install mariadb 2](https://user-images.githubusercontent.com/114162326/193454168-9bcf9ab2-1288-43b8-8fcf-55dd7cfe949f.png)

Per últim he reiniciat el servidor mariadb:

```
sudo systemctl restart mariadb.service
```

![Install owncloud 1](https://user-images.githubusercontent.com/114162326/193454209-22d2ff3e-0748-4442-af94-9ea9152cbeec.png)

### Crear la base de dades de owncloud

He entrat dintre de MariaDB

```
sudo mysql -u root -p
```

![Create bd 1](https://user-images.githubusercontent.com/114162326/193454244-947eb227-fef8-4d68-a121-c75377e0538e.png)

Tot seguit he creat la base de dades:

```
CREATE DATABASE owncloud
```

![Create bd 2](https://user-images.githubusercontent.com/114162326/193454284-78be1675-e910-43c4-9d2e-875c8714cb81.png)

Una vegada la base de dades creada, el que he fet a sigut crear un usuari amb el nom “owntclouduser” i la contraseña “Admin 1234”:

```
CREATE USER ‘ownclouduser’@’localhost’ IDENTIFIED BY ‘Admin1234’ WITH
```

![Create bd user 1](https://user-images.githubusercontent.com/114162326/193454297-6257b227-e6ea-4871-8875-f90a32431c33.png)

Tot seguit li he donat al usuari accés a la base de dades:

```
GRANT ALL ON owncloud.* TO 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin1234' WITH GRANT OPTION;
```

![Create bd user 2](https://user-images.githubusercontent.com/114162326/193454318-351c8c88-52e7-44e3-9116-98a6a3e8c6f0.png)

### Instalar PHP i els seus mòduls

```
sudo apt-get install software-properties-common -y
```

![install PHP 1](https://user-images.githubusercontent.com/114162326/193454343-91cb1798-0973-4d0f-9852-e0b5530e030e.png)

```
sudo add-apt-repository ppa:ondrej/php
```

![Install PHP 2](https://user-images.githubusercontent.com/114162326/193454356-985e7ed3-5a81-412d-ac61-ecc03a545d44.png)




