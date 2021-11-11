Jean-Sébastien Durette
Yann Martel
Groupe 10037





<center>Procédure d’installation d’une application web</center>

<center>Travail présenté à monsieur Jean-Pierre Duchesneau</center>

<center>Infrastructure technologique et virtualisation</center>
<center>420-W44-SF</center>







<center>Département d’informatique</center>
<center>Programme programmation et base de données</center>
<center>Cégep de Sainte-Foy</center>
<center>14 novembre 2021</center>


# Laboratoire 01 - Procédure d'installation d'une application Web


Dans ce document nous allons détailler l’installation d’un site internet wordpress dans un environnement de test, ainsi que les configuration  des composantes nécessaire afin de procéder à la dite installation.


## Voici les sections qui sont incluses dans la procédure:



### 1. Caractérisation de la machine serveur :
   
   ####  Nom (FQDN) : 
   - jsdurette@srvdevopsjsd
   ####  Addresses:
   - IPv4: 10.100.2.15
   - IPv6: fe80::250:56ff:fe9a:d501
   ####  Fichier Hosts (partie liée à l'installation), et serveur DNS
   - Localhost : 127.0.0.1
   - srvdevops_jsd : 127.0.1.1
   - DNS : 199.202.105.108
   - 199.202.105.1
   - Domaine DNS : csfoy.ca
   
   ####  Port des services ouverts:
   - Port 80 (Nginx)
   - Port 53 (Systemd-resolved)
   - Port 22 (SSH)
   - Port 33060 (MySQL)
   - Port 3306 (MySQL)
   ####  Usager utilisé pour l'installation
   - Nom : jsdurette



### 2. Les mises à jour préalables à l'installation et ajout de composants externes si nécessaire.
   -  sudo apt update -y (Télécharger et mettre à jour les informations de paquets via la configuration /etc/apt/source.list)
   -  sudo apt upgrade -y (Applique la dernière version de la mise à jour à tous les paquets installés)



### 3. Procédure d'installation détaillée des services :
   
   ####  Programmes : Nom, version, procédure d'installation.
   - Git, 2.33.1, sudo add-apt-repository ppa:git-core/ppa, sudo apt update, sudo apt upgrade, sudo apt install git
   - Nginx, 1.18.0, sudo apt install nginx
   - MySQL, 8.0.27 , sudo apt install mysql-server-8.0
   - PHP, 7.4.3, sudo apt install php-fpm php-cli php-mysql php-curl php-json -y
  
   #### Répertoire utilisé pour le programme, ses fichiers de configuration, ses données.
   - PHP : /etc/php/7.4/fpm, /etc/php/7.4/fpm/php.ini 
   - NGINX : /etc/nginx
   - MySQL : /etc/mysql
   - Git : /usr/bin/git
                     
   #### Espace espace utilisé et droits sur les répertoires.
   - Git : 3.3 Mo
   - PHP : 300 Ko
   - Nginx : 92 Ko
   - MySQL : 44 Ko                           
   - Nom d'usager (UID) : jsdurette (1000) groupe (GID): jsdurette (1000) 
   #### Liste des commandes nécessaires pouvant être exécutées par une tierce personne.
   - sudo apt update
   - sudo apt upgrade
   - sudo systemctl restart nginx 
   - sudo systemctl status nginx
   - sudo service mysql status
   - sudo systemctl status php7.4-fpm


### 4. Prédure d'installation détaillée de WordPress :
   
   #### Nom : 
   - Wordpress
   #### Version :
   - 5.8.2 
   #### Procédure d'installation :
   - sudo mkdir -p /var/www/html/wpress, wget https://wordpress.org/latest.tar.gz , tar xfvz latest.tar.gz
   - sudo cp -r wordpress/* /var/www/html/wpress, sudo chown -R www-data /var/www/html/wpress, sudo chmod -R                                 
   - 755 /var/www/html/wpress
   #### Espace utilisé : 
   - 46,38 Mo
   #### Répertoire utilisé pour le programme, ses fichiers de configuration, ses données :
   - Répertoire Wordpress : /var/www/html/wpress
   - Répertoire des téléversements : /var/www/html/wpress/wp-content/uploads
   - Répertoire des thèmes : /var/www/html/wpress/wp-content/themes
   - Répertoire des extensions : /var/www/html/wpress/wp-content/plugins
   - Fichier Virtual Host Nginx pour Wordpress : /etc/nginx/conf.d/wpress.conf
   #### Espace espace utilisé et droits sur les répertoires :
   - Répertoire Wordpress : 46,38 Mo : Accessible en écriture
   - Répertoire des téléversements : 0 Octet : Accessible en écriture
   - Répertoire des thèmes : 6,47 Mo : Accessible en écriture
   - Répertoire des extensions : 251,25 Ko : Accessible en écriture
   - Taille de la base de donnée : 688 Ko
   - Taille totale de l'installation : 53,77 Mo
   #### Nom d'usager pour le programme au sein du système et dans l'application : 
   - adminwp
   #### Liste des commandes nécessaires pouvant être exécutées par une tierce personne:
   - sudo systemctl restart nginx 
   - sudo systemctl status nginx
   - sudo service mysql status
   - sudo systemctl status php7.4-fpm
                                                        
                                                        
### 5. Procédure de validation de l'installation.



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
