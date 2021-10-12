# READMME TP1

## Config de Base Apache et GIT
1. Installer Apache: sudo apt-get install apache2
2. Modifier le fichier: sudo vim /var/www/html/index.html
3. Redémarrer le service: Sudo systemctl restart apache2
4. Créer un dossier pour git: sudo mkdir TP1
5. Copier la config de base de apache: sudo cp 000-default.conf /home/utilisateur/TP1/
6. Copier la config de base de apache (index html): sudo cp /var/www/html/index.html ~/TP1

## Création du Git

1. Initialiser le git: sudo git init
2. Ajouter les fichiers: sudo git add index.html && 000 && README.md
3. Créer un commit: sudo git commit -m "config de base"
4. Créer la branche master: sudo git branch -M master
5. Le lien vers le git: sudo git remote add origin https://github.com/KhDerbel/TP1-KJ.git
6. Push les fichiers vers le git: sudo git push -u origin master

## Création de la branche modif

1. Créer la branche: sudo git branch "modif"
2. Aller sur la branche: sudo git checkout modif

## Création du docker

1. Créer un dossier: sudo mkdir dockerTP1
2. Créer le Dockerfile: sudo vim Dockerfile
3. Écrire ca dedans

FROM ubuntu:20.04  
WORKDIR /mydir  
RUN apt-get -y update && DEBIAN_FRONTEND=noninteractiveapt-get -y install apache2  
COPY 000-default.conf .  
COPY index.html .  
CMD ["/bin/bash"]  

4. Créer le docker sudo docker build .
5. Copier les fichiers apache2 pour le docker: sudo cp 000-default.conf /home/utilisateur/dockerTP1/ .
6. Copier les fichiers apache2 pour le docker: sudo cp /var/www/html/index.html  .
7. Executer l'image du docker: sudo docker run -it *nom image*
8. Trouver le conteneur: sudo docker containers ls -a
9. Exécuter le conteneur: sudo docker exec -it *nom conteneur* bash

