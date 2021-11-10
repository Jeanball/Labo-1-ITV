# Laboratoire 01 - Procédure d'installation d'une application Web



**But :** le but de se laboratoire est documenter la procédure d'installation d'un site Web Wordpress dans votre environnement de test.



**Contexte :** Le laboratoire s'effectue en groupe de 2 personnes.


**Remise :** Vous devez déposer votre travail dans l'espace prévu sur LÉA au plus tard, le 13 novembre à 23h59.
Le temps alloué en classe est d'environ 3 heures.


## Voici les sections qui doivent être incluses dans votre procédure (document):



1. Caractérisation de la machine serveur :
   
   - Nom (FQDN) : 
   -            SrvDevOpsJSD
   - Addresses:
   -           IPv4: 10.100.2.15
   -           IPv6: fe80::250:56ff:fe9a:d501
   - Fichier Hosts (partie liée à l'installation), et serveur DNS
   - Port des services ouverts:
   -           Port 80 (Nginx)
   -           Port 53 (Systemd-resolved)
   -           Port 22 (SSH)
   -           Port 33060 (MySQL)
   -           Port 3306 (MySQL)
   - Usager utilisé pour l'installation
   -           Nom : jsdurette



2. Les mises à jour préalables à l'installation et ajout de composants externes si nécessaire.



3. Procédure d'installation détaillée des services :
   
   - Programmes : Nom, version, procédure d'installation.
   -              Git, 2.33.1, sudo add-apt-repository ppa:git-core/ppa, sudo apt update, sudo apt upgrade, sudo apt install git
   -              Nginx, 1.18.0, sudo apt install nginx
   -              MySQL, 8.0.27 , sudo apt install mysql-server-8.0
   -              PHP, 7.4.3, sudo apt install php-fpm php-cli php-mysql php-curl php-json -y
  
   - Répertoire utilisé pour le programme, ses fichiers de configuration, ses données.
   -              PHP : /etc/php/7.4/fpm, /etc/php/7.4/fpm/php.ini 
   - Espace espace utilisé et droits sur les répertoires.
   - Nom d'usager (UID) et groupe (GID) pour le programme au sein du système et dans l'application.
   - Liste des commandes nécessaires pouvant être exécutées par une tierce personne.
   -              sudo apt update
   -              sudo apt upgrade
   -              sudo systemctl restart nginx 
   -              sudo service mysql status



4. Prédure d'installation détaillée de WordPress :
   
   - Nom, version, procédure d'installation.
   - Espace utilisé.
   - Répertoire utilisé pour le programme, ses fichiers de configuration, ses données.
   - Espace espace utilisé et droits sur les répertoires.
   - Nom d'usager pour le programme au sein du système et dans l'application.
   - Liste des commandes nécessaires pouvant être exécutées par une tierce personne.



5. Procédure de validation de l'installation.



   Cette procédure doit démontrer le bon fonctionnement du site Web Wordpress.



## Vous devez fournir :



- Votre fichier avec toutes les parties demandées. Vous pouvez utiliser les formats suivant : Word (docx) ou Markdown (md).
- Ce fichier doit comprendre en plus des éléments nommés plus haut et les sections suivantes :
    - Page couverture selon les normes.
    - Introduction
    - Chacune des sections clairement identifiées.
    - Une conclusion
    - Bibliographie
- Un dessin qui illustre le poste client, le serveur, les services et ainsi que leurs relations au sein du réseau.



## Références à consulter :

- WordPress : https://fr-ca.wordpress.org/
- Installation de WordPress sur Ubuntu : https://www.linuxshelltips.com/install-wordpress-on-ubuntu/, attention il s'agit d'une installation sur Apache et non Nginx.
