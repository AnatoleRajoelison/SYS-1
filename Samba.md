# SYS-1

								Installation serveur SAMBA 

1- Il faut se connecter en tant que super utilisateur (root)
2- Installer SAMBA pour ca il faut taper la commande (apt -get install samba)
3- Une fois installer passons a la configuration 
4- Entrons dans le home pour ça il faut taper la commande ( cd /home/ )
5- Une fois dans home créons un dossier exemple:(mkdir data)
6- Changeons le droit de ce dossier (chmod 777 data/ )
7- Puis créons un utilisateur comme (useradd dea)
8- Ensuite entrons la ligne de commande (smbpasswd -a dea)
9- Une fois que c'est fait configurons maintenant (nano /etc/samba/smb.conf)
10- Après avoir fait cette commande et qu'on est entré dans nano écrivons maintenant: 
	[data]
	path - /home/data
	valid users = dea
	browseable = yes
	writeable = yes
11- Une fois fini tapons la commande /etc/init.d/samba restart
12- Après avoir fini tout ca configurons maintenant notre ordinateur local 
13- Entrons dans la panneau de configuration de notre ordinateur puis Connexion Network 
14- Une fois entrer , entrons dans ethernet puis entrons tous les adresse du serveur
