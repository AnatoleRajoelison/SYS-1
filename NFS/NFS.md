# Installation serveur NFS

## I/ En resumé qu’est-ce qu'un serveur NFS ? <br>
<p>
Le serveur NFS (Network File System) ,qui est un protocole permettant à un ordinateur d'accéder à des fichiers extérieurs via un réseau.
</p> 
<br>

## II/ Comment installer et configurer le serveur NFS?

<h4> Etape 1: Configuration de l'adresse IP et le ping entre les deux serveurs</h4>

1-Attribution de noms Clt_ NFS et Srv_NFS

2-Configuration IP: 

	a. Clt_Srv: 192.168.10.10/24

	b. Srv_NFS: 192.168.10.250/24

<h4> Etape 2: Sur le serveur NFS</h4>

1- apt-get install nfs-common nfs-kernel serveur portmap

2- préparation des dossier a partager /home/user/data_ro/ et /home/user/data_rw

3- partage des deux dossier avec le client Clt_NFS en ajoutant les deux lignes dans le fichier

4- ajouter les partages dans le fichiers /etc/exports/ :

	/home/user/data_ro 192.168.10.10 (ro)

	/home/user/data_rw 192.168.10.10 (rw)

5- redémarrer le service NFS:

	/etc/init.d/nfs-kernel-server restart

<h4> Etape 3: Sur le client Clt_NFS<h4> 

1- apt-get install nfs-common 

2- créer deux dossier pour le montage des dossiers distants

	/home/user/nfs_data_ro

	/home/user/nfs_data_rw

3- puis monter les deux dossiers partagés sur le serveurs dans les dossiers  locaux

mount -t nfs 192.168.10.250 : /home/user/data_ro /home/user/nfs_data_ro

mount -t nfs 192.168.10.250 : /home/user/data_ro /home/user/nfs_data_rw

4- tester l'accès aux dossiers partagé a partir du clients

<h4> Etape 4: Montage permanent de partage NFS</h4> 

1- redémarrer le client et essayer a nouveau l'accès aux dossiers partagés.

2- monter les deux dossier d'une facon permanente dans les fichiers /etc/fstab

192.168.10.250: /home/user/data_ro /home/user/nfs_data_ro nfs _netdev,nodev,noexec 0 0

192.168.10.250: /home/user/data_rw /home/user/nfs_data_rw nfs _netdev,nodev,noexec 0 0

3- redémarrer le client et réessayer l'accès aux dossier partagés