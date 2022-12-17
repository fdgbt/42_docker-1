# 42_docker-1
First project to discover Docker's ecosystem and to create first containers using Dockerfiles.  
It is part of the admin-sys branch with "init" and "roger-skyline-1" projects.  

# Expected Result
All the commands and scripts (Dockerfiles) used in this project are uploaded in this repository.  
They are structured in two parts, following the subject structure: 00_how_to_docker and 01_dockerfiles.  
The complete process is described in a documentation that I initiated.  

# Special Doc
Following the great success of the initiative taken in the 'Init' and 'roger-skyline-1' projects, a unique document has been created for this project, starting from scratch.  
In this rare document you can follow the subject with a reminder for all notions learned, but also explanations for each script/command.  
It has been designed to be very complete in terms of informations, and represents dozens of hours of research and writing.  
It takes the form of a tutorial of 45 pages allowing you to be guided step by step and to complete the project from A to Z.  
It can be shared upon request.  

I would like to thanks a lot the 42 peers (and friends) who helped me to produce these documents: Julia A. and Radhoin H.  

Unfortunately only French is available for now, the content is organised as below:

### Thanks
### Versions of document
### Summary
### Introduction
### Summary of Docker commands
### 00_how_to_docker

Reminder  
01 Créer une machine virtuelle avec docker-machine utilisant le driver virtualbox et ayant pour nom Char  
02 Récupérer l’adresse IP de la machine virtuelle Char  
03 Assigner les variables spécifiques à la machine virtuelle Char dans l’env courant de votre terminal, de sorte que vous pouvez lancer la commande docker ps sans  erreurs   
- Une seule commande est attendue pour fixer les 4 variables d’environnement et il vous est interdit d’utiliser le builtin de votre shell pour set à la main ces variables  

04 Récupérer depuis le Docker Hub le container hello-world disponible sur le Docker Hub  
05 Lancer le container hello-world et faire en sorte que le container affiche bien son message d’accueil, puis le quitte  
06 Lancer un container nginx disponible sur le Docker Hub en tâche de fond  
- Le container lancé doit avoir pour nom overlord, doit pouvoir redémarrer de lui-même et doit avoir le port 80 du container rattaché au port 5000 de Char. Vous pouvez vérifier le fonctionnement de votre container en allant sur un http://<ip-de-char>:5000 comme URL sur votre navigateur internet  

07 Récupérer l’adresse IP interne du container overlord sans lancer son shell et en une commande  
08 Lancer un shell depuis un container alpine, en faisant en sorte que vous puissiez directement interagir avec le container via votre terminal et que le container se supprime à la fin de l’exécution du shell  
09 Depuis le shell d’un container debian, faire en sorte d’installer via le gestionnaire de paquets du container, de quoi compiler un code source en C et le pusher sur un repo git  
10 Créer un volume hatchery  
11 Lister les volumes Docker créés sur la machine... je dis bien VOLUMES  
12 Lancer un container mysql en tâche de fond  
- Il devra aussi pouvoir redémarrer de lui-même en cas d’erreur et faire en sorte que le mot de passe root de la base de données soit "Kerrigan". Vous ferez aussi en sorte que la base de données soit stockée dans le volume hatchery, que le conteneur crée directement une base de données qui aura comme nom zerglings et le container s’appellera spawning-pool  

13 Afficher les variables d’environnement du container spawning-pool en une seule commande, histoire d’être sûr que vous avez bien configuré votre container  
14 Lancer un container wordpress en tâche de fond  
- Le container doit avoir pour nom "lair", le port 80 du container doit être bindé au port 8080 de la machine virtuelle et doit pouvoir utiliser le container spawning-pool comme service de base de données. Vous pouvez tenter d’accéder à "lair" sur votre machine via un navigateur en rentrant l’adresse IP de la machine virtuelle comme URL. Bravo, vous venez de déployer un site Wordpress fonctionnel en 2 commandes !  

15 Lancer un container phpmyadmin en tâche de fond  
- Le container doit avoir pour nom roach-warden, le port 80 du container doit être bindé au port 8081 de la machine virtuelle et doit pouvoir faire en sorte d’aller explorer la base de données contenue dans le container spawning-pool  

16 Consulter les logs en temps réel du container spawning-pool sans exécuter son shell pour autant  
17 Afficher l’ensemble des containers actuellement actifs sur la machine virtuelle Char  
18 Relancer le container overlord  
19 Démarrer un container qui se nommera Abathur  
- Abathur sera un container Python en version 2-slim, qui aura son dossier /root bindé à un dossier du HOME de votre host, ainsi que le port 3000 bindé au port 3000 de votre machine virtuelle. Vous personnaliserez ce container de telle sorte que vous puissiez utiliser le micro-framework Flask dans sa dernière version. Vous devrez faire en sorte qu’une page html renvoyant un "Hello World" dans des balises < h1 >, soit servie par Flask. Vous testerez la bonne mise en place de votre container, en accédant via curl ou navigateur web, à l’adresse IP de votre machine virtuelle sur le port 3000  

20 Créer un swarm local où la machine virtuelle Char en est le manager  
21 Créer une autre machine virtuelle avec docker-machine utilisant le driver virtualbox et ayant pour nom Aiur  
22 Basculer Aiur comme esclave du swarm local où Char est leader  
23 Créer un réseau interne de type overlay que vous nommerez overmind  
24 Lancer un SERVICE rabbitmq qui aura pour nom orbital-command  
- Vous devrez définir un user et un mot de passe spécifiques à l’utilisation du service RabbitMQ, et ceux-ci seront à votre libre convenance. Ce service sera sur le réseau overmind  

25 Lister l’ensemble des services du swarm local  
26 Lancer un service 42school/engineering-bay en 2 répliques et faire en sorte que le service fonctionne  
- Ce service s’appellera engineering-bay et sera sur le réseau overmind  

27 Récuperer les logs  en continu d’une des tasks du service engineering-bay  
28 ... Damn, des zergs sont en train d’attaquer orbital-command et couper le service engineering-bay ne servira à rien…  
- Vous devez envoyer des Marines pour les éliminer… Lancer un service 42school/marine-squad en 2 répliques, et faites en sorte que le service fonctionne. Ce service s’appellera … marines et sera sur le réseau overmind  

29 Afficher l’ensemble des tâches du service marines  
30 Mettre à jour le nombre de répliques du service marines à 20, car on n’a jamais assez de Marines pour annihiler du Zerg  
31 Forcer l’arrêt et supprimer l’ensemble des services sur le swarm local, en une seule commande  
32 Forcer l’arrêt et supprimer l’ensemble des containers (tous états confondus), en une seule commande  
33 Supprimer l’ensemble des images de containers stocké sur la machine virtuelle Char, en une seule commande aussi  
34 Supprimer la machine virtuelle Aiur autrement qu’avec un rm -rf  
    
### 01_dockerfiles

ex00 - vim/emacs  
- Depuis une image alpine, vous ajouterez à votre container l’éditeur de texte de votre choix entre vim ou emacs, qui se lancera au démarrage de votre container.  

ex01 - BYOTSS  
- Depuis une image debian, vous ajouterez les sources adéquates pour créer un serveur TeamSpeak, serveur qui se lancera au démarrage de votre container. Celui-ci est considéré comme valide si au moins un utilisateur peut se connecter dessus et discuter normalement (pas de configuration hasardeuse), donc créez votre Dockerfile avec les options adéquates.
Vous devez faire en sorte que les sources soient récupérées au build, elles ne doivent pas être présentes dans le dépôt.
Pour les petits malins, l’utilisation de l’image officielle TeamSpeak de docker est INTERDITE et sera sanctionné par la note de -42.  

ex02 - Dockerfile in a Dockerfile... in a Dockerfile ?
- Vous allez créer votre premier Dockerfile containerisateur d’application Rails.
Ce Dockerfile sera un peu spécial car il sera générique et devra être appelé dans un autre Dockerfile, qui devrait ressembler un peu à ça :
```
FROM        ft-rails:on-build
EXPOSE    3000
CMD        ["rails", "s", "-b", "0.0.0.0", "-p" ,"3000"]
```
- Votre container générique devra, depuis un container ruby, installer toutes les dépendances nécessaires, puis copier votre application rails dans le dossier /opt/app de votre container. 
Au build, Docker doit faire l’installation des gems spécifiques, ainsi que les migrations et la population de la db de votre application. 
Le Dockerfile-fils devra exposer les bons ports et lancer le serveur de rails (voir exemple ci-dessus). 
Si vous ne connaissez pas les commandes, il est temps de faire un tour sur la doc de Ruby on Rails.  

ex03 - What does the Fox say ?
- Docker peut etre pratique pour pouvoir tester une application encore en développement sans créer de la pollution dans vos fichiers. 
Vous allez par ailleurs, devoir concevoir un Dockerfile qui, au build, récupère la version actuelle de Gitlab - Community  Edition, l’installe avec toutes les dépendances et les configurations nécessaires et lance l’application (HTTPS et SSH). 
Le container est jugé valide, si vous pouvez accéder au client web, et si vous êtes capables d’utiliser correctement avec Gitlab et d’interagir via GIT avec ce container. Bien sur, vous ne devrez pas utiliser le container officiel de Gitlab, ce serait un peu tricher...

### Conclusion
    
# Reminder
This document of 45 pages is available in French only and can be shared upon request.

# Keywords
Unix  
Docker  
Containers  
Micro services  
DevOps  
