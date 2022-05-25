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

# **[ÍNDEX]** 

**ACTIVITAT 1. REALITZA I/O RESPON ELS SEGÜENTS APARTATS (obligatòria)
(1 punts)**

1\. Indica quins són els motors d'emmagatzematge que pots utilitzar
(quins estan actius)? Mostra al comanda utilitzada i el resultat
d'aquesta

![](./images/media/image1.png)Per poder veure els motors d'
emmagatzematge que estan actius utilitzarem la sentencia show engines
per veure els que estan activats i com veiem en la captura estan tots
activats menys el FEDERATED.

2\. Com puc saber quin és el motor d'emmagatzematge per defecte. Mostra
com canviar aquest paràmetre de tal manera que les noves taules que
creem a la BD per defecte utilitzin el motor MyISAM?

Per saber quin es el motor d'emmagatzematge per defecte tenim que
utilitzar la sentencia show engines i es veu en la captura que el InnoDB
es el motor de emmagatzematge ![Texto Descripción generada
automáticamente](./images/media/image2.png)

Per poder canviar el motor de emmagatzematge y passi al myISAM tenim que
primer anar a la ruta següent i editar el arxiu my.cnf

![](./images/media/image3.png)

Una vegada a dins de el arxiu my.cnf hem de posar el seguit paràmetre
per poder canviar el motor de emmagatzematge una vegada fet això guardem
y sortim.

![Texto Descripción generada
automáticamente](./images/media/image4.png)

Tornem al mysql i introduïm la sentencia SHOW ENGINES i es veu que
MyISAM a passat per defecte com motor de emmagatzematge.

![Texto Descripción generada
automáticamente](./images/media/image5.png)

3\. Com podem saber quin és el motor d'emmagatzematge per defecte?

**Per saber quin es el motor de emmagatzematge per defecte tenim que
utilitzar la següent sentencia mysql.**

![Escala de tiempo Descripción generada
automáticamente](./images/media/image6.png)

4\. Explica els passos per instal·lar i activar l'ENGINE MyRocks.
MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD
incrustat de tipus clau-valor). Aquest tipus d'emmagatzematge està
optimitzat per ser molt eficient en les escriptures amb lectures
acceptables.

## Per poder instal·lar el MyRocks i activar-ho tenim que fer els següents passos

**Primer de tot utilitzem la comanda següent per instal·lar el MyRocks i
li donarem que si per iniciar la instal·lació.**

![Texto Descripción generada
automáticamente](./images/media/image7.png)

### Sortirà el següent missatge que ja esta instal·lat el RocksDB.

![Interfaz de usuario gráfica Descripción generada automáticamente con
confianza media](./images/media/image8.png)

**Per poder activar-ho en el mysql tenim que utilitzar la següent
comanda i instal·larà el pulgin engine de RocksDB**

![Texto Descripción generada
automáticamente](./images/media/image9.png)

**Per assegurar que esta activat utilitzarem la següent sentencia i
veiem que el RocksDB esta activat.**

![Texto Descripción generada
automáticamente](./images/media/image10.png)

#### ACTIVITAT 2 -- STORAGE ENGINE CSV

## Per utilitzar el CSV. Primer creem una base de dades amb las següent sentencia.

![](./images/media/image11.png)

### Ara utilitzarem la següent sentencia per utilitzar la base de dades 

![](./images/media/image12.png)

Una vegada fet això creem una taula amb el seus camps que tenen que ser
NOT NULL i utilitzant el engine CSV

![Texto Descripción generada
automáticamente](./images/media/image13.png)

### Introduirem dades amb la següent sentencia

![Texto Descripción generada
automáticamente](./images/media/image14.png)

### Ara fem una SELECT per ve ure la taula

![Texto Descripción generada
automáticamente](./images/media/image15.png)

Per veure on esta el arxiu CSV tenim que anar a la ruta següent i com es
veu esta el arxiu albums.CSV

![Texto Descripción generada automáticamente con confianza
media](./images/media/image16.png)

Ara fem un nano per veure el seu contingut

![Texto Descripción generada
automáticamente](./images/media/image17.png)

EXERCICI 3

![Texto Descripción generada
automáticamente](./images/media/image18.png)

![Texto Descripción generada
automáticamente](./images/media/image19.png)

3\. A quin directori es guarden els fitxers de dades? Fes un llistat de
a on són els fitxers i què ocupen

El directori on es guarden els fitxers de dades es en el /var/lib/mysql

![Interfaz de usuario gráfica Descripción generada automáticamente con
confianza media](./images/media/image20.png)

Quina és la compressió per defecte que utilitza per les taules? Com ho
faries per canviarlo. Per exemple utilitza Zlib o ZSTD o sense
compressió.

Per defecte la compressio de taules son les tres

![Texto Descripción generada
automáticamente](./images/media/image21.png)

SI volem cambiar ho per un sol en especific tendriem que fer las seguent
sentencia mysql

![](./images/media/image22.png)

I com es veu se ha canviat la compressio

![Texto Descripción generada
automáticamente](./images/media/image23.png)

ACTIVITAT 4. INNODB part I. REALITZA ELS SEGÜENTS APARTATS (obligatòria)
(2 pu

Exercici 1

![](./images/media/image24.png)

COm es veu esta desactivat

![Texto Descripción generada
automáticamente](./images/media/image25.png)

### Exercici 2

Els permisos de de la carpeta del directori que es el mysql els te mysql
tan el propietari y el grup.Els permisos que te el propietari son de
escritura de lectura i execucio que correspon els tres digits despres de
la d despres els seguents 3 digits son del grup que te lecura i execucio
i per ultim els ultims tres digits son altres ususaris que tenen nomes
execucio..

![Imagen que contiene Interfaz de usuario gráfica Descripción generada
automáticamente](./images/media/image26.png)

#### EXERCICI 3

Per veure la mida que te utilitzarem la seguent sentencia per veure
quant pesa i es veu en la image que pesa 12M

![Texto Descripción generada
automáticamente](./images/media/image27.png)

. Per què té aquesta mida inicial?

La mida es 12M perque com no hem configurat el arxhiu abans de iniciar
el msyql et crea un arxiu perdefecte que es diu ibdata1 amb una mida de
12M una mica superior.

EXERCICI4.

![Texto Descripción generada
automáticamente](./images/media/image28.png)

Com es veu al instalar Sakila el ibdata1 a pujat una mica la mida init 0

![](./images/media/image29.png)

EXERCICI 5.

Els fitxers de dades es troben anant a la ruta seguent /var/lib/mysql i
com es veu en la captura tenim un arxchiu anomennat ibdata1

![Texto Descripción generada
automáticamente](./images/media/image30.png)

y la seva mida son 12 M una mica mes

![Imagen que contiene texto, grande Descripción generada
automáticamente](./images/media/image31.png)

### EXERCICI 6

### 

### Per poder cambiar la localitzacio primer tenim que anar a la ruta seguent

![](./images/media/image32.png)

Una vegada a dins del arxiu my.cnf canviem la ruta del datadir a la
carpeta creada hd-mysql

![Texto Descripción generada
automáticamente](./images/media/image33.png)

I una vegada cambiat això creem els dos ibdatas a la ruta creada amb el
parametre seguent

![Texto Descripción generada
automáticamente](./images/media/image34.png)

### Despres de fer això reiniciem el mysql y no podrem entrar al mysql 

![](./images/media/image35.png)

### Tindrem que demanar la contrasenya provisional y fer un secure installation 

![](./images/media/image36.png)

Primer fer la comanda seguent per tenir una contrasenya provisional:

![](./images/media/image37.png)

Despres fer la securitzacio amb la comanda seguent:

![Texto Descripción generada
automáticamente](./images/media/image38.png)

Una vegada canviada la contrasenya ja podem anar al mysql y camviem la
contrasenya a patata

![Texto Descripción generada
automáticamente](./images/media/image39.png)

Ara li asignarem al autoextend que pugi 5M amb las seguent sentencia y
com es veu ja ha canviat a els 5 MB

![Texto Descripción generada
automáticamente](./images/media/image40.png)

![Texto Descripción generada
automáticamente](./images/media/image41.png)

![](./images/media/image42.png)

![Imagen que contiene Calendario Descripción generada
automáticamente](./images/media/image43.png)

![](./images/media/image44.png)

![](./images/media/image45.png)

![](./images/media/image46.png)

![Texto Descripción generada
automáticamente](./images/media/image47.png)

![Texto Descripción generada
automáticamente](./images/media/image48.png)

![Texto Descripción generada
automáticamente](./images/media/image49.png)

![](./images/media/image50.png)

Com es veu a generat els ibdata els disks

![Texto Descripción generada automáticamente con confianza
media](./images/media/image51.png)

![Interfaz de usuario gráfica, Texto Descripción generada
automáticamente](./images/media/image52.png)

ACTIVITAT 5. INNODB part II. REALITZA ELS SEGÜENTS APARTATS

![Texto Descripción generada automáticamente con confianza
baja](./images/media/image53.png)

![Texto Descripción generada
automáticamente](./images/media/image54.png)

ACTIVITAT 6. INNODB part III. REALITZA ELS SEGÜENTS APARTATS

![Texto Descripción generada
automáticamente](./images/media/image55.png)

![Texto Descripción generada
automáticamente](./images/media/image56.png)

![Imagen que contiene Texto Descripción generada
automáticamente](./images/media/image57.png)

Borrem per tbalespace 1

![](./images/media/image58.png)

Borrem per tbalespace 2

![](./images/media/image59.png)

![](./images/media/image60.png)
![](./images/media/image61.png)

![Texto Descripción generada
automáticamente](./images/media/image62.png)


![Interfaz de usuario gráfica Descripción generada
automáticamente](./images/media/image63.png)

![Texto Descripción generada
automáticamente](./images/media/image64.png)
