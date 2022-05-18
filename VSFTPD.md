# SYS-1

									Installation serveur VSFTPD

                                    
1-Se connecter en tant que super utilisateur (root)
2-installer VSFTPD (apt-get install vsftpd)
3-configurons maintenant (/etc/vsftpd.conf)
4-enlevons le # du 31ème ligne de commentaire pour qu'elle ne le soit plus (write_enable=yes) et du 99 eme ligne qui est (ascii_upload_enable=yes) et du 100 eme qui est
(ascii_download_enable=yes) et du 122 eme ,123,125,131 puis sur la 157 eme qui est vide ecrivons( local_root=public_html )et sur 158 eme (seccomp_sandbox=NO)
5-taper la commande suivante /usr/sbin/adduser ibra
6-puis /etc/vsftpd.chroot_list
7-redémarrer le serveurs (systemctl restart vsftpd)
8-modifier le reseaux de votre ordinateur virtuel en réseau interne mais plus en NAT
9-apres (resolve /etc/resolv.conf) pour configurer les adresse ip