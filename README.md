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

![](./images/media/image1.png){width="5.905555555555556in"
height="1.1979166666666667in"}Per poder veure els motors d'
emmagatzematge que estan actius utilitzarem la sentencia show engines
per veure els que estan activats i com veiem en la captura estan tots
activats menys el FEDERATED.

2\. Com puc saber quin és el motor d'emmagatzematge per defecte. Mostra
com canviar aquest paràmetre de tal manera que les noves taules que
creem a la BD per defecte utilitzin el motor MyISAM?

Per saber quin es el motor d'emmagatzematge per defecte tenim que
utilitzar la sentencia show engines i es veu en la captura que el InnoDB
es el motor de emmagatzematge ![Texto Descripción generada
automáticamente](./images/media/image2.png){width="5.984633639545057in"
height="1.1266929133858268in"}

Per poder canviar el motor de emmagatzematge y passi al myISAM tenim que
primer anar a la ruta següent i editar el arxiu my.cnf

![](./images/media/image3.png){width="3.21875in"
height="0.3854166666666667in"}

Una vegada a dins de el arxiu my.cnf hem de posar el seguit paràmetre
per poder canviar el motor de emmagatzematge una vegada fet això guardem
y sortim.

![Texto Descripción generada
automáticamente](./images/media/image4.png){width="5.905555555555556in"
height="4.178472222222222in"}

Tornem al mysql i introduïm la sentencia SHOW ENGINES i es veu que
MyISAM a passat per defecte com motor de emmagatzematge.

![Texto Descripción generada
automáticamente](./images/media/image5.png){width="5.905555555555556in"
height="1.3965277777777778in"}

3\. Com podem saber quin és el motor d'emmagatzematge per defecte?

**Per saber quin es el motor de emmagatzematge per defecte tenim que
utilitzar la següent sentencia mysql.**

![Escala de tiempo Descripción generada
automáticamente](./images/media/image6.png){width="4.072916666666667in"
height="1.3125in"}

4\. Explica els passos per instal·lar i activar l'ENGINE MyRocks.
MyRocks és un motor d'emmagatzematge per MySQL basat en RocksDB (SGBD
incrustat de tipus clau-valor). Aquest tipus d'emmagatzematge està
optimitzat per ser molt eficient en les escriptures amb lectures
acceptables.

## Per poder instal·lar el MyRocks i activar-ho tenim que fer els següents passos

**Primer de tot utilitzem la comanda següent per instal·lar el MyRocks i
li donarem que si per iniciar la instal·lació.**

![Texto Descripción generada
automáticamente](./images/media/image7.png){width="5.905555555555556in"
height="2.3090277777777777in"}

### Sortirà el següent missatge que ja esta instal·lat el RocksDB.

![Interfaz de usuario gráfica Descripción generada automáticamente con
confianza media](./images/media/image8.png){width="5.905555555555556in"
height="0.7347222222222223in"}

**Per poder activar-ho en el mysql tenim que utilitzar la següent
comanda i instal·larà el pulgin engine de RocksDB**

![Texto Descripción generada
automáticamente](./images/media/image9.png){width="5.905555555555556in"
height="1.8618055555555555in"}

**Per assegurar que esta activat utilitzarem la següent sentencia i
veiem que el RocksDB esta activat.**

![Texto Descripción generada
automáticamente](./images/media/image10.png){width="5.905555555555556in"
height="1.3486111111111112in"}

#### ACTIVITAT 2 -- STORAGE ENGINE CSV

## Per utilitzar el CSV. Primer creem una base de dades amb las següent sentencia.

![](./images/media/image11.png){width="3.1145833333333335in"
height="0.4166666666666667in"}

### Ara utilitzarem la següent sentencia per utilitzar la base de dades 

![](./images/media/image12.png){width="2.125in"
height="0.3333333333333333in"}

Una vegada fet això creem una taula amb el seus camps que tenen que ser
NOT NULL i utilitzant el engine CSV

![Texto Descripción generada
automáticamente](./images/media/image13.png){width="4.041666666666667in"
height="1.1354166666666667in"}

### Introduirem dades amb la següent sentencia

![Texto Descripción generada
automáticamente](./images/media/image14.png){width="5.385416666666667in"
height="0.7708333333333334in"}

### Ara fem una SELECT per ve ure la taula

![Texto Descripción generada
automáticamente](./images/media/image15.png){width="4.052083333333333in"
height="1.3854166666666667in"}

Per veure on esta el arxiu CSV tenim que anar a la ruta següent i com es
veu esta el arxiu albums.CSV

![Texto Descripción generada automáticamente con confianza
media](./images/media/image16.png){width="4.21875in"
height="0.6666666666666666in"}

Ara fem un nano per veure el seu contingut

![Texto Descripción generada
automáticamente](./images/media/image17.png){width="5.905555555555556in"
height="0.9118055555555555in"}

EXERCICI 3

![Texto Descripción generada
automáticamente](./images/media/image18.png){width="3.4583333333333335in"
height="0.5208333333333334in"}

![Texto Descripción generada
automáticamente](./images/media/image19.png){width="5.905555555555556in"
height="2.486111111111111in"}

3\. A quin directori es guarden els fitxers de dades? Fes un llistat de
a on són els fitxers i què ocupen

El directori on es guarden els fitxers de dades es en el /var/lib/mysql

![Interfaz de usuario gráfica Descripción generada automáticamente con
confianza media](./images/media/image20.png){width="5.905555555555556in"
height="5.625in"}

Quina és la compressió per defecte que utilitza per les taules? Com ho
faries per canviarlo. Per exemple utilitza Zlib o ZSTD o sense
compressió.

Per defecte la compressio de taules son les tres

![Texto Descripción generada
automáticamente](./images/media/image21.png){width="5.905555555555556in"
height="2.5965277777777778in"}

SI volem cambiar ho per un sol en especific tendriem que fer las seguent
sentencia mysql

![](./images/media/image22.png){width="5.416666666666667in"
height="0.5104166666666666in"}

I com es veu se ha canviat la compressio

![Texto Descripción generada
automáticamente](./images/media/image23.png){width="5.905555555555556in"
height="2.504861111111111in"}

ACTIVITAT 4. INNODB part I. REALITZA ELS SEGÜENTS APARTATS (obligatòria)
(2 pu

Exercici 1

![](./images/media/image24.png){width="3.7708333333333335in"
height="0.4583333333333333in"}

COm es veu esta desactivat

![Texto Descripción generada
automáticamente](./images/media/image25.png){width="4.166666666666667in"
height="1.2708333333333333in"}

### Exercici 2

Els permisos de de la carpeta del directori que es el mysql els te mysql
tan el propietari y el grup.Els permisos que te el propietari son de
escritura de lectura i execucio que correspon els tres digits despres de
la d despres els seguents 3 digits son del grup que te lecura i execucio
i per ultim els ultims tres digits son altres ususaris que tenen nomes
execucio..

![Imagen que contiene Interfaz de usuario gráfica Descripción generada
automáticamente](./images/media/image26.png){width="5.905555555555556in"
height="5.676388888888889in"}

#### EXERCICI 3

Per veure la mida que te utilitzarem la seguent sentencia per veure
quant pesa i es veu en la image que pesa 12M

![Texto Descripción generada
automáticamente](./images/media/image27.png){width="4.447916666666667in"
height="1.3645833333333333in"}

. Per què té aquesta mida inicial?

La mida es 12M perque com no hem configurat el arxhiu abans de iniciar
el msyql et crea un arxiu perdefecte que es diu ibdata1 amb una mida de
12M una mica superior.

EXERCICI4.

![Texto Descripción generada
automáticamente](./images/media/image28.png){width="4.21875in"
height="1.84375in"}

Com es veu al instalar Sakila el ibdata1 a pujat una mica la mida init 0

![](./images/media/image29.png){width="5.905555555555556in"
height="0.4423611111111111in"}

EXERCICI 5.

Els fitxers de dades es troben anant a la ruta seguent /var/lib/mysql i
com es veu en la captura tenim un arxchiu anomennat ibdata1

![Texto Descripción generada
automáticamente](./images/media/image30.png){width="5.905555555555556in"
height="1.975in"}

y la seva mida son 12 M una mica mes

![Imagen que contiene texto, grande Descripción generada
automáticamente](./images/media/image31.png){width="5.677083333333333in"
height="3.3645833333333335in"}

### EXERCICI 6

### 

### Per poder cambiar la localitzacio primer tenim que anar a la ruta seguent

![](./images/media/image32.png){width="3.3541666666666665in"
height="0.3958333333333333in"}

Una vegada a dins del arxiu my.cnf canviem la ruta del datadir a la
carpeta creada hd-mysql

![Texto Descripción generada
automáticamente](./images/media/image33.png){width="5.905555555555556in"
height="1.9222222222222223in"}

I una vegada cambiat això creem els dos ibdatas a la ruta creada amb el
parametre seguent

![Texto Descripción generada
automáticamente](./images/media/image34.png){width="5.165193569553805in"
height="2.0025448381452318in"}

### Despres de fer això reiniciem el mysql y no podrem entrar al mysql 

![](./images/media/image35.png){width="3.8229166666666665in"
height="0.20833333333333334in"}

### Tindrem que demanar la contrasenya provisional y fer un secure installation 

![](./images/media/image36.png){width="5.905555555555556in"
height="0.4215277777777778in"}

Primer fer la comanda seguent per tenir una contrasenya provisional:

![](./images/media/image37.png){width="5.905555555555556in"
height="0.34375in"}

Despres fer la securitzacio amb la comanda seguent:

![Texto Descripción generada
automáticamente](./images/media/image38.png){width="4.635416666666667in"
height="0.9583333333333334in"}

Una vegada canviada la contrasenya ja podem anar al mysql y camviem la
contrasenya a patata

![Texto Descripción generada
automáticamente](./images/media/image39.png){width="4.333333333333333in"
height="4.979166666666667in"}

Ara li asignarem al autoextend que pugi 5M amb las seguent sentencia y
com es veu ja ha canviat a els 5 MB

![Texto Descripción generada
automáticamente](./images/media/image40.png){width="4.364583333333333in"
height="2.4895833333333335in"}

![Texto Descripción generada
automáticamente](./images/media/image41.png){width="5.905555555555556in"
height="3.984027777777778in"}

![](./images/media/image42.png){width="5.905555555555556in"
height="3.35625in"}

![Imagen que contiene Calendario Descripción generada
automáticamente](./images/media/image43.png){width="4.183590332458443in"
height="0.9427810586176728in"}

![](./images/media/image44.png){width="3.3020833333333335in"
height="0.375in"}

![](./images/media/image45.png){width="2.2395833333333335in"
height="0.40625in"}

![](./images/media/image46.png){width="4.104166666666667in"
height="0.3958333333333333in"}

![Texto Descripción generada
automáticamente](./images/media/image47.png){width="5.905555555555556in"
height="2.752083333333333in"}

![Texto Descripción generada
automáticamente](./images/media/image48.png){width="2.7604166666666665in"
height="0.6145833333333334in"}

![Texto Descripción generada
automáticamente](./images/media/image49.png){width="6.5395100612423445in"
height="3.967230971128609in"}

![](./images/media/image50.png){width="4.520833333333333in"
height="0.4375in"}

Com es veu a generat els ibdata els disks

![Texto Descripción generada automáticamente con confianza
media](./images/media/image51.png){width="2.5625in"
height="0.5729166666666666in"}

![Interfaz de usuario gráfica, Texto Descripción generada
automáticamente](./images/media/image52.png){width="2.7291666666666665in"
height="0.875in"}

ACTIVITAT 5. INNODB part II. REALITZA ELS SEGÜENTS APARTATS

![Texto Descripción generada automáticamente con confianza
baja](./images/media/image53.png){width="3.9166666666666665in"
height="0.9270833333333334in"}

![Texto Descripción generada
automáticamente](./images/media/image54.png){width="5.905555555555556in"
height="6.722916666666666in"}

ACTIVITAT 6. INNODB part III. REALITZA ELS SEGÜENTS APARTATS

![Texto Descripción generada
automáticamente](./images/media/image55.png){width="5.905555555555556in"
height="1.3166666666666667in"}

![Texto Descripción generada
automáticamente](./images/media/image56.png){width="3.9479166666666665in"
height="1.9166666666666667in"}

![Imagen que contiene Texto Descripción generada
automáticamente](./images/media/image57.png){width="6.285523840769904in"
height="0.8847331583552056in"}

Borrem per tbalespace 1

![](./images/media/image58.png){width="4.34375in"
height="0.3645833333333333in"}

Borrem per tbalespace 2

![](./images/media/image59.png){width="5.854166666666667in"
height="0.5in"}

![](./images/media/image60.png){width="3.5in" height="0.40625in"}

![](./images/media/image61.png){width="1.625in" height="0.25in"}

![Texto Descripción generada
automáticamente](./images/media/image62.png){width="2.6041666666666665in"
height="1.625in"}

![Interfaz de usuario gráfica Descripción generada
automáticamente](./images/media/image63.png){width="5.364583333333333in"
height="3.6770833333333335in"}

![Texto Descripción generada
automáticamente](./images/media/image64.png){width="5.905555555555556in"
height="1.9493055555555556in"}
