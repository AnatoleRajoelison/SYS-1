# Installation serveur VSFTPD

## I/ En résumer qu’est-ce qu’un serveur VSFTPD? <br>

VsFTPd est un serveur FTP(File Transfer Protocol) conçu avec la problématique d'une sécurité maximale. Contrairement aux autres serveurs FTP (ProFTPd, PureFTPd, etc.), aucune faille majeure de sécurité n'a jamais été décelée dans VsFTPd.

## II/ Comment installer VSFTPD?

1-Il faut se connecter en tant que super utilisateur (root)

2-Installer VSFTPD:

		 apt-get install vsftpd

## III/ Comment configurer VSFTPD?

1-Configurons maintenant entrons dans le dossier etc

		 /etc/vsftpd.conf

2-Enlevons les # maintenant, du 31ème ligne de commentaire:

		 write_enable=yes

 et du 99 eme ligne qui est:
 
 		 ascii_upload_enable=yes
 
 et du 100 eme qui est:

			ascii_download_enable=yes
			
 et du 122 eme ,123,125,131 puis sur la 157 eme qui est vide ecrivons:
 
 		 local_root=public_html 
		  
 et sur 158 eme:
 
 		 seccomp_sandbox=NO

3-Taper la commande suivante:

 		 /usr/sbin/adduser ibra

4-Puis:

		 /etc/vsftpd.chroot_list

5-Redémarrer le serveurs:

		 systemctl restart vsftpd

6-Modifier le reseaux de votre ordinateur virtuel en réseau interne mais plus en NAT

9-Apres:

		 resolve /etc/resolv.conf

 pour configurer les adresse ip