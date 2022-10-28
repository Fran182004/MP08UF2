# Activitat 4:

## Gestió d'usuaris:

Hi ha dos tipus d'usuaris, els admins amb permissos per gestionar Owncloud i els usuaris normals.

On fica resposta afegeix una captura de pantalla on es vegi que has fet l'acció que es demana.

**Aquesta part de la pràctica la feu amb un company/a, li creeu un usuari i li doneu el vostre nom de domini d'Owncloud.**

Per a que pugui accedir necessitarà:

- La MV amb owncloud ha d'estar en mode "adaptador pont".
- El fitxer /etc/hosts del company ha de tenir la IP de la MV i el nom de domini de la MV del company/a.


**4.1.-** Crea un usuari admin que es digui adminXYZ, on XYZ són les inicials del teu nom:

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/196974328-6e5e3bd1-e0af-4730-9929-7d3446c75cf7.png)

**4.2.-** Inicia sessió com a l'usuari adminXYZ.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/196974859-cf56f97a-25c7-43db-be89-efb6d368af37.png)

**4.3.-** Crea un usuari XYZ on XYZ son les inicials del company/a i afegeix-lo al grup usuaris, aquest usuari tindrà una quota de 512 MB.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/196975560-df21bf52-06c6-4e33-97de-49db3ece70a4.png)

**4.4.-** Podem crear fitxers d'una mida determinada a Linux amb la comanda:

```
truncate -s 10M file.txt
```

A l'exemple es crea un fitxer de 10MB.

Crea 6 fitxers de 100MB i pujal's a Owncloud un per un.

![image](https://user-images.githubusercontent.com/114162326/196977516-774d6b97-9d62-4dd2-9556-40e64b55b12a.png)

**RESPOSTA**

**4.5.-** Mostra el missatge d'error per haver superat la quota d'usuari.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/196978920-bd4bab44-8e37-49b7-a239-1fb976802e1d.png)

**4.6.-** Busca al teu perfil quin percentatge de quota estas utilitzant.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/196979303-b6f2483e-ed4f-43c9-a21f-3cc9f6c29a44.png)

**4.7.-** Canvia la quota de l'usuari a 1GB i mostra tots els fitxers pujats.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/196983125-abfab00e-7872-4cc2-9eee-70b91d781303.png)

**4.8.-** Crea un usuari anomenat usuari2XYZ i fical al grup usuaris.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/198641126-9ce4da1c-560f-4ab3-8f26-48c918ef4c54.png)

**4.9.-** Comparteix un fitxer de usuariXYZ a usuari2XYZ i mostra com l'usuari2XYZ pot veure i descarregar el fitxer.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/198644364-01b9fa0c-c758-45f2-8be9-a5bd5d4d9e8c.png)

![image](https://user-images.githubusercontent.com/114162326/198645457-3551e2be-7482-4527-86ef-9400603d8d13.png)

**4.10.-** Esborra la carpeta Learn more about owncloud.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/198648979-8c4e73dd-38db-47f9-93e8-4dd90809029d.png)

**4.11.-** Recupera la carpeta Learn more about owncloud.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/198649268-d61229d4-5e98-4a13-a895-cc65c269431d.png)

**4.12.-** Com a usuariXYZ crea una carpeta nova anomenada shared i comparteix-la amb l'usuari usuari2XYZ.

**RESPOSTA**

![image](https://user-images.githubusercontent.com/114162326/198650013-b911301f-9565-4a11-94b5-30cba9e36604.png)

**4.13.-** Entra a Market instal·la dues aplicacions que no estiguin ja instal·lades i explica què fan i com funcionen.

![image](https://user-images.githubusercontent.com/110727546/196159706-705ff624-c409-4632-acb4-f43ffcc486d4.png)

**RESPOSTA PRIMERA APP**

**RESPOSTA SEGONA APP**

**4.14.-** Crearem una carpeta nova per emmagatzematge a Owncloud, la carpeta serà /media/publicXYZ on XYZ són les teves inicials i apareixerà amb el nom de public als usuaris.

Aquesta carpeta haurà de pertànyer a l'usuari www-data.

**RESPOSTA**

**4.15.-** Connectarem la carpeta publicXYZ com emmagatzematge local, tal i com s'indica [aquí](https://doc.owncloud.com/server/next/admin_manual/configuration/files/external_storage/local.html). Tots els usuaris tindran accés a la carpeta.

**RESPOSTA**

**4.16.-** Un usuari normal pujarà un fitxer a la carpeta public.

**RESPOSTA**

**OPCIONAL.-** Aquesta tasca és opcional.

Intenta connectar com a emmagatzematge extern el teu compte de Google Drive de l'Institut. Tens com fer-ho [aquí](https://doc.owncloud.com/server/next/admin_manual/configuration/files/external_storage/google.html).

**RESPOSTA**
