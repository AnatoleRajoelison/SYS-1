# SYS-1

										Installation serveur NGINX

                                        
1- Se connecter en tant que super utilisateur (root)
2- installer NGINX (apt-get install nginx -y)
3- verifions si c'est bien installer (nginx -v)
4- on va creer un dossier dans le www du nginx (mkdir /var/www/nom du domaine du site) ce dossier va nous permettre de stocker les fichier de notre site qui est notre racine
5- determination du proprieter du dossier du l'utilisateur de nginx (chown -R www-data:www-data /var/www/nom du site/)
6- apppliquer les droits (chmod 755 /var/www/nom du site/)
7- création d'une page index.html pour la racine (nano /var/www/nom du site/index.html)
8- création du fichier de configuration (nano /etc/nginx/sites-available/appellation du site):
exemple: server{
	listen 80;
	listen [::]:80;

	root/var/www/nom du site;

	index index.html;
	server_name nom du site www nom du site;

	location / {
		try_files $uri $uri/ =404;
}
}
9- mettre la configuration permanente (ln -s /etc/nginx/site-available/nom du site /etc/nginx/sites-enabled/nom du site)
10- verifions la configuration de notre nginx avec la commande (nginx -t)
11- redémarrer le nginx (systemctl restart nginx)
	
