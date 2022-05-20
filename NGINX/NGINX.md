# Installation serveur NGINX

## I/ En résumé qu’est-ce qu'un serveur NGINX? <br>
<p>
Nginx a été créé à l’origine par Igor Sysoev,il est prononcé comme « engine-ex », est un serveur web open-source qui, depuis son succès initial en tant que serveur web, est maintenant 
aussi utilisé comme reverse proxy, cache HTTP, et load balancer.
</p> 

## II/ Comment installer et configurer NGINX?

<h4> Étape 1 — Installation de NGINX </h4>
                                   
1- Se connecter en tant que super utilisateur (root)

2- installer NGINX avec la ligne de commande:	 

		apt-get install nginx -y

3- Maintenant verifions si c'est bien installer avec la ligne de commande:

		nginx -v

<h4>Étape 2 — Configuration de NGINX</h4>

1- On va creer un dossier dans le www du nginx (mkdir /var/www/nom du domaine du site) ce dossier va nous permettre de stocker les fichier de notre site qui est notre racine.

2- Determination du proprieter du dossier du l'utilisateur de nginx:

		 chown -R www-data:www-data /var/www/nom du site/

3- Apppliquer les droits:

		 chmod 755 /var/www/nom du site/

4- Création d'une page index.html pour la racine:

		 nano /var/www/nom du site/index.html

8- Création du fichier de configuration (nano /etc/nginx/sites-available/appellation du site):

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

9- mettre la configuration permanente:

		 ln -s /etc/nginx/site-available/nom du site /etc/nginx/sites-enabled/nom du site

10- Verifions la configuration de notre nginx avec la commande:

		 nginx -t

11- Redémarrer le nginx:

		 systemctl restart nginx
	
