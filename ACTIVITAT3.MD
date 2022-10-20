# Activitat 1 

Per fer aquesta activitat comptem amb que ja s'ha configurat el servei Owncloud a una Màquina Virtual (MV).

### 3.1. - Llista els Virtual Hosts d'Apache per tal de veure si owncloud.XYZ.com està habilitat amb la comanda:

```
apache2ctl -s
```

##### Resposta

![Activitat3 1](https://user-images.githubusercontent.com/114162326/195608192-68113e8c-0892-497a-857d-0253fcce7a02.png)

### 3.2.- A Owncloud podem veure que hi ha una serie de carpetes per defecte, mostra la ruta real a les tres carpetes dins de la teva MV.

![Activitat3 2](https://user-images.githubusercontent.com/114162326/195608915-15533d3c-1fe5-46fa-b92f-91f4f6600c5a.png)

##### Resposta
Des de l'arrel del S.O.
```
/var/www/html/owncloud/core/skeleton
```
![Activitat3 3](https://user-images.githubusercontent.com/114162326/195615261-5ff912eb-9c24-4d41-a8d7-5f69667f4d53.png)

### 3.3.- Al directori Learn more about owncloud hi ha informació en forma de fitxers pdf. Consulta'ls i respon aquestes preguntes:

##### Quin són els tres tipus de protecció de dades que ofereix Owncloud?

**1-** Encryption in Transit 

**2-** Encryption at Rest

**3-** End-to-End Encryption

##### Fes una petita descripció de cada un d'ells.

**1- Encryption in Transit** Vol dir que les dades es xifren abans de ser enviats i es desxifren quan arriben al seu lloc de destí.

**2- Encryption at Res** Aquesta manera de xifratge vol dir que el xifratge està fet inclòs quan estan dintre del disc dur, llavor si l'ataca'n no té cap clau de desxifrat no podrà accedir-hi a les dades.

**3- End-to-End Encryption** Vol dir que està xifrat d'extrem a extrem, i només es pot accedir amb una clau de xifratge.

##### Per quina raó ens recomana utilitzar Owncloud per als documents de Microsoft Office de la nostra empresa?

Es bo utilitzar Ownclowd ja que aixi tenim les nostres dades guardades en un lloc segur. 

##### Això passa a tots els països?

No en tots ja que no tots els paisos utilitzen els mateixos protocols, pero són semblans.

##### Quina és la llicència d'OWncloud Enterprise?

És una opció que te Owncloud, i es pot adquirir per 12 euros.

##### I la d'Owncloud Standard?

Es pot conseguir per 5 euros.

##### Es poden veure videos en Streaming directament des de Owncloud?

Si que es pot.

##### Es poden connectar directoris de Google Drive a Owncloud?

Si que es pot.

##### I Dropbox?

També es pot.

##### Compta Owncloud amb antivirus? En cas afirmatiu com es diu?

Nomes si instal·les l'extenció

### 3.4.- Mostra els següents canvis de paràmetres d'usuari:

##### Posa't una imatge d'usuari.

![image](https://user-images.githubusercontent.com/114162326/196968095-ddbd59fc-72a3-4f93-81b2-b52de7f7d18c.png)

##### Afegeix el teu mail de l'Institut.

![image](https://user-images.githubusercontent.com/114162326/196968182-5c5fac41-8bd9-4e5c-b24f-2a690e078d33.png)

##### Canvia l'idioma a català.

![image](https://user-images.githubusercontent.com/114162326/196968768-1144ce94-e666-42cd-aafa-272d08b7b667.png)

##### Mostra la versió d'Owncloud instal·lada.

![image](https://user-images.githubusercontent.com/114162326/196968882-e96ccd1a-578b-407e-9236-cc3775eaa500.png)
