# Docker-compose WorPress  

----------------  

## Description :  


Environnement de développement local WordPress dockeriser  
Version : 1.0.0  
Date : 2020-06-07  
Responsable : HI  

----------------  

## Mise en oeuvre :  


* modifiez les valeurs des __variables d'environement__ avec vos propres données dans le fichier .env.  

* depuis un terminal, rendez-vous à la racine du repo (là où se trouve le fichier docker-compose.yml ) et lancer la ligne de commande suivante:   
    - ```$ docker-compose up -d```   

----------------

## Utilisation :  

Une fois les containers buildés l'application est visible à l'adresse suivante : http://localhost:8000/  (ou port personnalisé si modifié)   

Les fichiers WordPress sont accessibles depuis le dossier ./wordpress   

Les fichiers relatifs à la base de données sont stockés dans le dossier ./data   

----------------

## Rappel des principales commandes Docker :

* Noms des containers :  
    - wordpress : [project_name]_wordpress_[n] (n pour nombre incrémenté selon le nombre d'instance)   
    - mysql : [project_name]_db_[n] (n pour nombre incrémenté selon le nombre d'instance)   

* pour stopper les containers :  
    - ```$ docker-compose stop```  

* pour les relancer si déjà buildés :  
    - ```$ docker-compose start```   

* pour lister les containers qui tournent :  
    - ```$ docker-compose ps```  

* pour lister tous les containers :  
    - ```$ docker container ls -la```  

* pour inspecter les containers :  
    - ```$ docker container inspect [nom_du_container]```  

* pour exécuter des commandes arbitraires dans les services.  
    - ```$ docker-compose exec [nom_du_container] sh```   


* pour supprimer les containers et les volumes de données (Arrête les container et supprime les container, réseaux, volumes et images créés par up) : 
    - ```$ docker-compose down --rmi all --remove-orphans -v``` 

    * Par défaut, les seules choses supprimées sont :
        - Container pour les services définis dans le fichier docker-compose.yml  
        - Réseaux définis dans la section network du fichier docker-compose.yml  
        - Le réseau par défaut, s'il est utilisé  

Les réseaux et volumes définis comme externes ne sont jamais supprimés.  

* pour tout supprimer du système une fois les containers stoppés (**faire très attention**, **supprime** du système **TOUS** les container, réseaux, images, volumes inutilisés)  
    - ```$ docker system prune```  

    * Cela supprimera :  
        - tous les container arrêtés  
        - tous les réseaux non utilisés par au moins un conteneur  
        - toutes les images en suspend  
        - tout le cache de construction  

    - ```$ docker system prune -a --volumes```  

    * Cela supprimera :  
        - tous les container arrêtés  
        - tous les réseaux non utilisés par au moins un conteneur  
        - tous les volumes non utilisés par au moins un conteneur  
        - toutes les images sans au moins un conteneur qui leur est associé  
        - tout le cache de construction  


----------------

# Docker-compose WorPress  


----------------

## Description :  


Local development environment for WordPress dockeriser   
Version : 1.0.0  
Date : 2020-06-07  
Responsable : HI  

----------------

## Implementation :  


* modify the value of  __environment variables__ with your own data into the .env file.   

* from a terminal, go to the root of the repo / docker-amp (where the docker-compose.yml file is located) and launch the following command line :  
    - ```$ docker-compose up -d```  

----------------

## Utilisation :  


Once the containers have been built the application is visible at the following address: http://localhost:8000/    (or port customize if modified)  

The WordPress files are accessibles within the ./wordpress directory  

The database is store into ./data  

----------------

## Reminder of the main Docker commands:  

* containers names :   
    - wordpress : [project_name]_wordpress_[n]     
    - mysql : [project_name]_db_[n]    

* to stop the containers:  
    - ```$ docker-compose stop```  

* to relaunch them if already built:  
    - ```$ docker-compose start```  

* to list the running containers:  
    - ```$ docker-compose ps```  

* to list all of the containers :  
    - ```$ docker container ls -la```  

* to inspect all of the containers :  
    - ```$ docker inspect [nom_du_container]```  

* to delete containers, images and data volumes (Stops containers and removes containers, networks, volumes, and images created by up) :  
    - ```$ docker-compose down --rmi all --remove-orphans -v```  

    * By default, the only things removed are :  
        - Containers for services defined in the Compose file  
        - Networks defined in the networks section of the Compose file  
        - The default network, if one is used  

Networks and volumes defined as external are never removed.  

* to delete everything once the containers are stopped (whatch your steps, Remove all unused containers, networks, images (both dangling and unreferenced), and optionally, volumes)  
    - ```$ docker system prune```  

    * This will remove :  
        - all stopped containers  
        - all networks not used by at least one container  
        - all dangling images  
        - all build cache  

    - ```$ docker system prune -a --volumes```  

    * This will remove :  
        - all stopped containers  
        - all networks not used by at least one container  
        - all volumes not used by at least one container  
        - all images without at least one container associated to them  
        - all build cache  

----------------  