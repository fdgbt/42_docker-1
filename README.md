# 42_docker-1
First project to discover Docker's ecosystem and to create first containers using Dockerfiles.  
It is part of the Admin-Sys / DevOps branch with "init" and "roger-skyline-1" projects.  

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
### Summary of document
### Introduction
### Summary of Docker commands
### 00_how_to_docker

01 Create a virtual machine with docker-machine using the virtualbox driver, and named Char  
02 Get the IP address of the Char virtual machine  
03 Define the variables needed by your virtual machine Char in the general env of your terminal, so that you can run the docker ps command without errors  
   You have to fix all four environment variables with one command, and you are not allowed to use your shell’s builtin to set these variables by hand  
04 Get the hello-world container from the Docker Hub, where it’s available  
05 Launch the hello-world container, and make sure that it prints its welcome message, then leaves it  
06 Launch an nginx container, available on Docker Hub, as a background task  
   It should be named overlord, be able to restart on its own, and have its 80 port attached to the 5000 port of Char  
   You can check that your container functions properly by visiting http://<ip-de-char>:5000 on your web browser  
07 Get the internal IP address of the overlord container without starting its shell and in one command  
08 Launch a shell from an alpine container, and make sure that you can interact directly with the container via your terminal, and that the container deletes itself once the shell’s execution is done  
09 From the shell of a debian container, install via the container’s package manager everything you need to compile C source code and push it onto a git repo  
   Of course, make sure before that the package manager and the packages already in the container are updated  
   For this exercise, you should only specify the commands to be run directly in the container  
10 Create a volume named hatchery  
11 List all the Docker volumes created on the machine, remember, VOLUMES  
12 Launch a mysql container as a background task  
   It should be able to restart on its own in case of error, and the root password of the database should be Kerrigan  
   You will also make sure that the database is stored in the hatchery volume, that the container directly creates a database named zerglings, and that the container itself is named spawning-pool  
13 Print the environment variables of the spawning-pool container in one command, to be sure that you have configured your container properly  
14 Launch a wordpress container as a background task, just for fun  
   The container should be named lair, its 80 port should be bound to the 8080 port of the virtual machine, and it should be able to use the spawning-pool container as a database service  
   You can try to access lair on your machine via a web browser, with the IP address of the virtual machine as a URL  
   Congratulations, you just deployed a functional Wordpress website in two commands!  
15 Launch a phpmyadmin container as a background task  
   It should be named roach-warden, its 80 port should be bound to the 8081 port of the virtual machine and it should be able to explore the database stored in the spawning-pool container  
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
The document of 45 pages is available in French only and can be shared upon request.

# Keywords
Unix  
Docker  
Containers  
Micro services  
DevOps  
