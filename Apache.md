# SYS-1

										Installation serveur APACHE

1-Tout d'abord il faut se connecter en tant que super utilisateur (Root)
2-Pour installer il faut entré la ligne de commande apt-get install apache2
3-Une fois installer il y a un dossier qui s'est créer qui est dans "var" et qui est nommé "www"
4-Configurons maintenant alors taper la commande (cd /var/etc/html/ )
5-Puis si on tape la commande "ls" on peut constater qu'il y a un fichier index.html
6-Alors tapons la commande (cp index.html index.html.bak)
7-Apres la commande (rm index.html)
8-Ouvrons index.html dans nano maintenant (nano index.html) ensuite ecriver quelque chose pour tester votre serveur
9-Configurons maintenant notre machine local en allons dans wifi/proprieter/internet protocole version... une fois dedans changer l'adresse ecrite qui est sur DNS server par l'adresse du serveur de votre apache
