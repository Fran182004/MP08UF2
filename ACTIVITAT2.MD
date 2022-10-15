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

Tot seguit he actualitzat els paquets amb el repositori anyadit.

```
sudo apt update
```

![Install PHP 3](https://user-images.githubusercontent.com/114162326/193454398-080d6d60-c3ec-4ff5-8a5f-42f0256b68a1.png)

Una vegada actualizat el que he fet a sigut instala el PHP amb els mòduls necessaris 

```
sudo apt install php7.4 libapache2-mod-php7.4 php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-apcu php7.4-smbclient php7.4-ldap php7.4-redis php7.4-gd php7.4-xml php7.4-intl php7.4-json php7.4-imagick php7.4-mysql php7.4-cli php7.4-mcrypt php7.4-ldap php7.4-zip php7.4-curl -y
```

“No tinc captura”

Tot seguit he editat el document php.ini.

```
sudo nano /etc/php/7.4/apache2/php.ini
```

![Install PHP 4](https://user-images.githubusercontent.com/114162326/193454450-9659f688-e369-476c-b035-a3be56a8d325.png)

I he canviat els següents paràmetres.

```
file_uploads = On allow_url_fopen = On memory_limit = 256M upload_max_filesize = 100M display_errors = Off date.timezone = Europe/Madrid
```

![Install PHP 5](https://user-images.githubusercontent.com/114162326/193454467-7bd6a9af-de34-46f4-8201-68efd03359e5.png)

### Instal·lació Owncloud

Primer que tot m’he descarregat la última versió del programa.

```
cd /tmp && wget https://download.owncloud.com/server/stable/owncloud-complete-latest.zip
```
![Install owncloud 1](https://user-images.githubusercontent.com/114162326/193454556-3c51f77f-45e5-4aaf-86d3-55718efddcb3.png)

Tot seguit he descomprimit els arxius.

```
unzip owncloud-10.0.8.zip
```

![Install owncloud 2](https://user-images.githubusercontent.com/114162326/193454561-bee02b0e-5540-4c2a-9ef5-9e9aba6eb2a3.png)

Una vegada d’escomprimit el que he fet a sigut moure els arxius de Owncloud a “/var/www/html/owncloud”.

```
sudo mv owncloud /var/www/html/owncloud/
```

![Install owncloud 3](https://user-images.githubusercontent.com/114162326/193454574-efb27164-c06e-44f9-b2fa-3c95fd54d78a.png)

Tot seguit he canviat el propietari i els permisos del directorio de Owncloud www-data per a que els pugi usar Apache, 755 per a que els pugui executar i llegir qualsevol usuari de Linux.

```
sudo chown -R www-data:www-data /var/www/html/owncloud/
```

![Install owncloud 4](https://user-images.githubusercontent.com/114162326/193454607-10cb899a-fc0d-443e-97ec-4f4a371d6d51.png)

```
sudo chmod -R 755 /var/www/html/owncloud/
```

![Install owncloud 5](https://user-images.githubusercontent.com/114162326/193454628-96ddd4ea-7a91-45e5-b03a-89bece7c4552.png)

Ja ho tendriem instal·lat

![Instalast 1](https://user-images.githubusercontent.com/114162326/193454670-761ebf88-02e0-4e52-a981-e2f9a182ae87.png)

Expliqueu:

Què signifiquen a Apache les línies de configuració del fitxer owncloud.conf.

![195784901-1d83f3c1-ee2d-46f1-b432-a27156d55f50](https://user-images.githubusercontent.com/114162326/196010277-f936855f-eef3-41d1-94bd-5bd34fc200c5.jpg)

ServerAdmin admin@exemple.com:

DocumentRoot /var/www/html/owncloud/:

ServerName dungeonfbits.com:

ServerAlias www.dungeonfbits.com

Alias /owncloud "/var/www/html/ owncloud/"

<Directory /var/www/html/owncloud/>

options +FollowSymlinks

AllowOverride All

Require all granted

</IfModule>

SetEnv HOME /var/www/html/owncloud

SetEnv HTTP_HOME /var/www/html/owncloud

</Directory>

ErrorLog ${APACHE_LOG_DIR}/error.log

CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>

Què fa la comanda a2ensite?
-Activa una pagina web

I la comando a2dissite?
-Desactiva la pagina web

Què significa la línia de /etc/hosts
127.0.0.1 owncloud.XYZ.com

Es per a fer una conecsio entre la ip una direcció

