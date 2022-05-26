# Storage-Engine
**CFGS Administració de Sistemes Informàtics a la Xarxa**

**Mòdul 10:** Administració de sistemes gestors de base de dades (ASIX)

**UF 3:** Llenguatges SQL: DCL i extensió procedimental SGBD corporatiu


***


**Activitat 3: Storage Engine**


***

**Gaurav Pal**

**Ahmed Belhadi**

**ASIX**

**26/05/2022**
***

# **ACTIVITAT 1 -- REALITZA I/O RESPON ELS SEGÜENTS APARTATS**

**1\. Indica quins són els motors d'emmagatzematge que pots utilitzar
(quins estan actius)? Mostra al comanda utilitzada i el resultat
d'aquesta**

Per poder veure els motors d'
emmagatzematge que estan actius utilitzarem la sentencia ***show engines***
per veure els que estan activats, tal com veiem en la captura estan tots
activats menys el **FEDERATED**.![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image1.png)

**2\. Com puc saber quin és el motor d'emmagatzematge per defecte. Mostra
com canviar aquest paràmetre de tal manera que les noves taules que
creem a la BD per defecte utilitzin el motor MyISAM?**

Per saber quin es el motor d'emmagatzematge per defecte tenim que
utilitzar la sentencia ***show engines*** i tal com es veu en la captura que el InnoDB
es el motor d'emmagatzematge ![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image2.png)

Per poder canviar el motor de emmagatzematge i aquest passi al myISAM hem de anar a la ruta següent i editar l'arxiu "my.cnf"


![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image3.png)


Una vegada a dins de l'arxiu "my.cnf" hem de posar el següentt paràmetre
per tal de poder canviar el motor d'emmagatzematge. Una vegada fet, guardem
i sortim!


![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image4.png)


Ara hem de tornar al mysql aquesta vegada introduïm la sentencia **"SHOW ENGINES"** i es veu que
MyISAM a passat per defecte com motor de emmagatzematge.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image5.png)

**3\. Com podem saber quin és el motor d'emmagatzematge per defecte?**

Per saber quin es el motor de emmagatzematge per defecte hem d'utilitzar la següent sentencia mysql.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image6.png)

**4\. Explica els passos per instal·lar i activar l'ENGINE MyRocks.
MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD
incrustat de tipus clau-valor). Aquest tipus d'emmagatzematge està
optimitzat per ser molt eficient en les escriptures amb lectures
acceptables.**

Per poder instal·lar el MyRocks i activar-ho, principalment hem d'utilitzar la comanda següent per tal d'instal·lar el MyRocks i
li donarem que si quan ens demani si estem d'accors per iniciar la instal·lació.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image7.png)

Sortirà el següent missatge que ja esta instal·lat el RocksDB.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image8.png)

Per poder activar-ho en el mysql hem d'utilitzar la següent
comanda i instal·larà el plugin engine de RocksDB

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image9.png)

Per assegurar que esta activat utilitzarem la següent sentencia i
tal com es veu RocksDB esta activat.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image10.png)

# **ACTIVITAT 2 -- STORAGE ENGINE CSV** 

Per utilitzar el **CSV**, primer creem una base de dades amb las següent sentencia.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image11.png)

Ara utilitzarem la següent sentencia per utilitzar la base de dades 

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image12.png)

Una vegada fet això creem una taula amb el seus camps que tenen que ser
***NOT NULL*** i utilitzant el engine CSV

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image13.png)

Introduirem dades amb la següent sentencia

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image14.png)

Ara fem una ***SELECT*** per ve ure la taula

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image15.png)

Per veure on esta l'arxiu CSV hem d'anar a la ruta següent i com es
veu esta l'arxiu albums.CSV

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image16.png)

Ara fem un **"cat"** per veure el contingut de l'arxiu

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image17.png)

# **EXERCICI 3 -- STORAGE ENGINE MyRocks**

**1. Crea una Base de dades amb 2 o 3 taules i insereix-hi contingut.**

Primer creem una base de dades l'anomenem *"rocksdb"*

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image18.png)

Seguidament utilitzem la base de dades amb la sentència **"USE"**, i creem 2 taules 

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image19.png)

**2. A quin directori es guarden els fitxers de dades? Fes un llistat de
a on són els fitxers i què ocupen**

El directori on es guarden els fitxers de dades es en el ***"/var/lib/mysql"***

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image20.png)

**3. Quina és la compressió per defecte que utilitza per les taules? Com ho
faries per canviarlo. Per exemple utilitza Zlib o ZSTD o sense
compressió.**

Per defecte venen 3 compressions de taules i són  les que es mostren en la captura d'imatge

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image21.png)

SI volem cambiar-ho per un sol en específic, tendriem que fer la següent
sentencia mysql

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image22.png)

I com es veu se ha canviat la compressio a una sola.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image23.png)

# **ACTIVITAT 4 -- INNODB part I**

**1. Desactiva l’opció que ve per defecte de innodb_file_per_table**

Per tal de desactivar l'opcio que ve per defecte de innodb_file_per_table nomes hem de fer un OFF mitjançant un **SET**

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image24.png)

Ara si fem un show  es veu que ja està desactivat

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image25.png)

**2. Quins són els permisos i l'usuari i grup de la carpeta que conté el directori de dades (datadir)**

Els permisos de la carpeta datadir els conté tant el propietari, com el del grup de mysql. Els permisos que te el propietari són d' escritura, de lectura i d'execució que correspon els tres digits despres de la ***"d"***. Els seguents 3 digits corresponen al grup que te el permís de lecura i el d'execucio i  els últims tres digits son dels altres ususaris (**OTHERS**), que tenen nomes d'execucio.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image26.png)

**3. Mostra quina és la mida del tablespace de sistema (System Tablespace)**

Per veure la mida que te el  utilitzarem la següent sentencia per veure
quant pesa i tal es veu en la image pesa 12M

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image27.png)

**Per què té aquesta mida inicial?**

La mida es 12M perque com no hem configurat el arxhiu abans de iniciar
el msyql et crea un arxiu perdefecte que es diu ibdata1 amb una mida de
12M una mica superior.

**4. Importa la BD Sakila com a taules InnoDB**

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image28.png)

Com es veu al instalar Sakila el ibdata1 a pujat una mica la mida init 0

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image29.png)

**5. Quin/quins són els fitxers de dades? A on es troben i quina és la seva mida?**

Els fitxers de dades es troben anant a la ruta seguent ***/var/lib/mysql*** i
com es veu en la captura tenim un arxiu anomenat ibdata1

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes//image30.png)

La seva mida son 12 MB i una mica mes

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image31.png)

**6. Canvia la configuració del MySQL per:**

  **1. Canviar la localització del directori de dades a /hd-mysql**

Per poder cambiar la localitzacio primer hem d'anar a la ruta següent ***"/etc/my.cnf"***

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image32.png)

Una vegada a dins del arxiu my.cnf canviem la ruta del datadir a la carpeta creada hd-mysql

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image33.png)

I una vegada cambiat això creem els dos ibdatas a la ruta creada amb el parametre següent

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image34.png)

Ara guardem, sortim del my.cnf i creem els discos. Li diem que sigui una particio primària, elegim en aquest cas que volem crear una partició de disc asignem el valor de +1024M per asignar que li volem donar 1GB de memoria a la partició. 

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image41.png)

Ara li hem de donar permisos a les particions creades i ho hem amb el ***CHMOD**** i el permis de **777** que aquest ens dona el permis de **RXW**(lectura, escriptura i execució). Seguidament utilizem el ***mkfs.ext4*** per tal de donar-li a les particions creades el format de extensió 4 (quatre sistemes d'arxius extessos).

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image42.png)

Arribant en aquest pas creem les carpetes que aquestes li assignarem amb el nom de **disk1** i **disk2** aquestes les col·locarem a l'arrel, i després aquestes les muntem en les particions que vam crear previament.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image43.png)

Donem permisos al  **lost+found** creat quan vam muntar la carpeta a la partició.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image44.png)

Canviem els usuari root de la carpeta /disk1 per un de mysql 

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image45.png)

Fem el mateix amb el /disk2, com també hem de canviar l'usuari de la carpeta /hd-mysql

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image46.png)

Segudament ens redirigim a l'arxiu ***/etc/fstab*** on en ella indicarem les particions el punt de muntatge i el sistema d'arxiu amb el que el fem.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image47.png)

Guardem i ara executem la següent comanda per tal de que es monti automàticament el que hem fet per tal que quan reiniciem la maquina i la tornem a engegar estigui ja tot muntat, que no haguem de fer tot els passos previs de nou.

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image48.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image49.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image50.png)

Com es veu a generat els ibdata els disks

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image51.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image52.png)

Després de comprovar que s'han generat els ibdates en els diskos tindrem que demanar la contrasenya provisional y fer un secure installation 

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image36.png)

Primer fer la comanda seguent per tenir una contrasenya provisional:

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image37.png)

Despres fer la securitzacio amb la comanda seguent:

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image38.png)

Una vegada canviada la contrasenya ja podem anar al mysql y camviem la
contrasenya a patata

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image39.png)

Ara li asignarem al autoextend que pugi 5M amb las seguent sentencia y
com es veu ja ha canviat a els 5 MB

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image40.png)

# **ACTIVITAT 5 -- INNODB part II**

**1.Partint de l'esquema anterior configura el Percona Server perquè cada taula generi el seu
propi tablespace en una carpeta anomenada tspaces**

Previament hem de crear la carpeta donarli permisos, i segudament assignar a la ruta el usuari que volem que fagi l'accio en aquest cas el de mysql

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image53.png)

Afegim una nova ruta per tal que innodb reconegui que a carpeta es seva

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image54.png)

# **ACTIVITAT 6 -- INNODB part III**

Primer creem els tablespaces afegim la ruta 


![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image55.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image56.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image57.png)

Borrem per tbalespace 1

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image58.png)

Borrem per tbalespace 2

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image59.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image60.png)
![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image61.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image62.png)


![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image63.png)

![](https://github.com/ahmedwaix/Storage-Engine/blob/main/Imagenes/image64.png)
