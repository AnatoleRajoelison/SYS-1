# Installation serveur SAMBA 

## I/ En résumer qu’est-ce que SAMBA ? <br>

<p>
Samba est une réimplémentation gratuite et open-source du protocole de partage de 
fichiers réseau SMB / CIFS qui permet aux utilisateurs finaux d'accéder aux fichiers, imprimantes et autres ressources partagées.

Elle est aussi un logiciel d'interopérabilité qui implémente le protocole propriétaire SMB/CIFS de Microsoft Windows dans les ordinateurs tournant sous le système d'exploitation Unix et ses dérivés de
manière à partager des imprimantes et des fichiers dans un réseau informatique.

C'est un ensemble d'outils permettant de partager des ressources telles que des imprimantes
et des fichiers sur un réseau hétérogène. 
</p> 

## II/ Comment installer Samba ?

<h4> Étape 1 —  Installer SAMBA </h4>
       
1- Il faut se connecter en tant que super utilisateur (root)

2- Commencez par mettre à jour l'index des packages apt:

		 apt update

3- Installer SAMBA pour ca il faut taper la commande:

		 apt -get install samba

<h4> Étape 2 — Configuration globales de Samba </h4>

1- Entrons dans home pour ça il faut taper la commande:

		 cd /home/

2- Une fois dans home créons un dossier exemple:

		 mkdir data

3- Changeons le droit de ce dossier: 

		 chmod 777 data/ 

4- Puis créons un utilisateur:

		 useradd dea

5- Ensuite entrons la ligne de commande:

		 smbpasswd -a dea

6- Une fois que c'est fait configurons maintenant:

		 nano /etc/samba/smb.conf

7- Après avoir fait cette commande et qu'on est entré dans nano écrivons maintenant: 

	[data]

	path - /home/data

	valid users = dea

	browseable = yes

	writeable = yes

11- Une fois fini tapons la commande:

		 /etc/init.d/samba restart

12- Après avoir fini tout ca configurons maintenant notre ordinateur local 

13- Entrons dans la panneau de configuration de notre ordinateur puis Connexion Network 

14- Une fois entrer , entrons dans ethernet puis entrons tous les adresse du serveur
