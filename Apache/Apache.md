# Installation serveur APACHE

## I/ En résumer qu’est-ce qu’un serveur Web Apache? <br>

<p>
Apache est le serveur Web le plus utilisé au niveau du marcher et sur les systèmes Linux, elles sont utilisés pour servir les pages Web demandées à la demande du clients. Cette configuration est appelée LAMP (Linux, Apache, MySQL et Perl/Python/PHP) qui forme un plate-forme assez puissante et robuste pour le développement et le déploiement d’applications Web<a href="https://www.lojiciels.com/reponse-rapide-comment-configurer-le-serveur-web-apache-sous-linux-etape-par-etape/">LOJICIELS.Com</a>
</p> 
<br><p>
Mais encore,Apache est un logiciel de serveur web gratuit et open-source qui alimente environ 46% des sites web à travers le monde.
Il est maintenu et développé par Apache Software Foundation.
</p><br>

## II/ Comment installer le serveur Apache et la configurer

<h4> Étape 1 — Installation d’Apache </h4>

1-Tout d'abord il faut se connecter en tant que super utilisateur (Root)

2-Mettre à jour votre index local des packages :

		apt update

3-Il faut installé maintenant les packages, pour installer il faut entré la ligne de commande apt-get install apache2

4-Une fois installer il y a un dossier qui s'est créer qui est dans "var" et qui est nommé "www"

<h4> Étape 2 — Configuration</h4>

1-Configurons maintenant alors taper la commande:
			
		cd /var/etc/html/ 

2-Puis si on tape la commande "ls" on peut constater qu'il y a un fichier index.html

3-Alors tapons la commande (cp index.html index.html.bak)

4-Apres la commande (rm index.html)

5-Ouvrons index.html dans nano maintenant (nano index.html) ensuite ecriver quelque chose pour tester votre serveur

6-Configurons maintenant notre machine local en allons dans wifi/proprieter/internet protocole version... une fois dedans changer l'adresse ecrite qui est sur DNS server par l'adresse du serveur de votre apache.




										 


