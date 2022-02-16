# Instalacio_SGBD
Practica 1 MP10 UF2

Taula de continguts:

* Instal·lació Server SGBD
* Instal·lació SGBD MySQL 8.0
* Instal·lació SGBD MongoDB
* Instal·lació SGBD SQLServer



#### Abans de començar haurem de tenir les nostres màquines actualitzades.
Farem un `sudo yum update`. <br>
I una vegada hi hagi acabat farem el nostre `sudo yum upgrade`.
#

## [Instal·lació server SGBD (percona server)]()

1.  Primerament, actualitzem l’equip de manera que tindrem el sistema actualitzat.

![image](https://user-images.githubusercontent.com/80846119/153273479-fe2dc02c-7518-4df3-a5bb-5148f4306be8.png)
#

2.  Afegirem el repositori yum de percona per després procedir amb la instal·lació del nostre SGBD.

![image](https://user-images.githubusercontent.com/80846119/153273560-2b2809cc-62b6-4b2b-a3e9-917faa338fa3.png)
#

3.  Seguidament, comprovarem que la instal·lació ha sigut un èxit.

![image](https://user-images.githubusercontent.com/80846119/153273986-c9364685-6f4a-433a-b8ad-dde949fbb935.png)
#

4.  Ara habilitarem el repositori de percona

![image](https://user-images.githubusercontent.com/80846119/153274028-e212e111-c477-43cd-a2b9-3d678850bf79.png)
#

5.  Finalment instal·larem el nostre percona server per mysql 8.0. Per fer aquesta acció, necessitarem executar un seguit de tres comandes.

![image](https://user-images.githubusercontent.com/80846119/153274141-6d0593db-a143-4b59-88c8-170b93a0523a.png)

![image](https://user-images.githubusercontent.com/80846119/153274115-9f9ae37c-0dfe-4dbb-b66c-4676f1d7f2b4.png)

![image](https://user-images.githubusercontent.com/80846119/153274159-f2718f0d-24ed-4153-9226-0b405483fcf4.png)
#

6.  Comprovarem la instal·lació del nostre percona server amb mysql 8.0.

![image](https://user-images.githubusercontent.com/80846119/153274214-5c754001-260a-4745-bd9c-41b26dbb7881.png)
#

7.  Ara initcialitzarem el servei mysql.

![image](https://user-images.githubusercontent.com/80846119/153274348-cc653d43-fcb9-42f2-b877-ec135d162252.png)
#

8.  Farem la comprovació que el servei mysql està corrent.

![image](https://user-images.githubusercontent.com/80846119/153274419-73cd3cbf-3e39-44a0-addd-15a3b5d5c094.png)
#

9.  Ara que finalment tenim el nostre servei operatiu, copiarem la contrasenya temporal i executarem l’script d’instal·lació segura.

![image](https://user-images.githubusercontent.com/80846119/153274673-2babc6cf-9d1b-46ba-980b-62b4500d482a.png)

![image](https://user-images.githubusercontent.com/80846119/153274684-ae143ba1-329d-432b-82a6-935a494b390f.png)

![image](https://user-images.githubusercontent.com/80846119/153274725-0a8d858e-8f14-4283-8a1a-42d7da4d54fb.png)

![image](https://user-images.githubusercontent.com/80846119/153274692-581dbed7-05fb-4a1c-8137-fe885b09762f.png)

![image](https://user-images.githubusercontent.com/80846119/153274714-df52c751-f951-40b3-9f6f-5ff71ca08ba1.png)
#
#

## RESPON O COMPROVA ELS SEGÜENTS APARTATS

#### Un cop realitzada la instal·lació realitza una securització de la mateixa. Quin programa realitza aquesta tasca? Realitza una securització de la instal·lació indicant que la contrasenya de root sigui patata.
A l'apartat 9, en les ultimes captures he fet el procediment per poder inserir la contrasenya patata.

#### Quines són les instruccions per arrancar / verificar status / apagar servei de la base de dades de Percona Server en el CentOS 7
Les instruccions per arrancar el servei és <br>
`sudo systemctl start mysql.service`

Les instruccions per aturar el servei és <br>
`sudo systemctl stop mysql.service`

Les instruccions per veure l'estat del servei és <br>
`sudo systemctl status mysql.service`


#### A on es troba i quin nom rep el fitxer de configuració del SGBD Percona Server?
El fitxer es el següent `/etc/my.cnf`.
![image](https://user-images.githubusercontent.com/80846119/154342730-b645bd6f-bdd2-4881-a3fa-673247b3ea72.png)


#### A on es troben físicament els fitxers de dades (per defecte). Com ho has sabut?
Els fitxers que hi han per defecte són els següents:<br>
![image](https://user-images.githubusercontent.com/80846119/154342921-4901db4a-cd57-4481-91d8-5ae4ef02bb75.png)


#### Crea un usuari anomenat asix en el sistema operatiu i en SGBD de tal manera que aquest usuari del sistema operatiu no hagi d'introduir l'usuari i password cada vegada que cridem al client mysql?

  1. https://dev.mysql.com/doc/refman/8.0/en/password-security-user.html
  2. Usuari SO-→ asix / patata
  3. Usuari MySQL → asix / patata
      - Crearem l'usuari al nostre sistema.
        ![image](https://user-images.githubusercontent.com/80846119/154343857-db7a5173-c381-4871-ab48-f1ab072ff123.png)
  
      - En el nostre Mysql farem les següents comandes, a part de les de creació del propi usuari.
        ![image](https://user-images.githubusercontent.com/80846119/154344681-a92ed103-742f-4ebf-a458-8c7ff08e1610.png)
        
      - Ara modificarem l'arxiu i afegirem 2 linies més.
      ![image](https://user-images.githubusercontent.com/80846119/154345263-cca11d0c-b3ca-4b85-9b54-26a30e1ba868.png)


#### El servei de MySQL (mysqld) escolta al port 3306. Quina modificació/passos caldrien fer per canviar aquest port a 33306 per exemple? 
Em de modificar el següent arxiu. <br>
![image](https://user-images.githubusercontent.com/80846119/154340108-1887257c-2635-4a5a-894e-0c0087b8d469.png)

#### Important: No realitzis els canvis. Només indica els passos que faries.

#### Ensenya al professor que us podeu connectar al SGBD.


INSTALAR MONGODB

1.  Primer em de crear un repositori, amb el següent contingut, la comanda ha de ser `sudo nano /etc/yum.repos.d/mongodb.org-4.4.repo`.
![image](https://user-images.githubusercontent.com/80846119/154326186-94d7f174-f747-44b7-aed4-b521aad33bc7.png)

2.  Ara intal·larem el servei del MongoDB amb la seguent comanda `sudo yum install mongodb-org`.
![image](https://user-images.githubusercontent.com/80846119/154327940-d4cc8687-2b10-461d-b09b-6738bb7c4bae.png)

3.  Una vegada intal·lat, iniciem el servei del nostre mongo db, i mirem el seu estat.
![image](https://user-images.githubusercontent.com/80846119/154328000-d0bde21c-83f3-40bf-b7e9-2da31efccf07.png)

4.  Ara ens podem conecta localment a MongoDB.
![image](https://user-images.githubusercontent.com/80846119/154328423-a50474a5-7317-4236-9c67-906ca739276b.png)




