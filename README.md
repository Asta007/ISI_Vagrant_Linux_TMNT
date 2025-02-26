# Vagrant - Linux TMNT  

Ce projet Vagrant configure une machine virtuelle Ubuntu 22.04 avec un serveur web **Nginx** et une base de données **MySQL**, accessibles via une IP privée et un port redirigé.

## Installation & Démarrage  

1. **Cloner ce dépôt** :  
   ```sh
   git clone <URL_DU_DEPOT>
   cd <NOM_DU_PROJET>
   ```

2. **Démarrer la machine virtuelle** :  
   ```sh
   vagrant up
   ```

3. **Se connecter en SSH** :  
   ```sh
   vagrant ssh
   ```

## Accès  

- **Serveur Nginx** : [http://192.168.33.3](http://192.168.33.3)  
- **Base de données MySQL** :  
  - Hôte : `192.168.33.3` ou `localhost` (via Vagrant)  
  - Port : `3306`  
  - Utilisateur : `iamroot`  
  - Mot de passe : `root123`  

## Détails de la configuration  

- **OS** : Ubuntu 22.04 (bento)  
- **CPU** : 1  
- **RAM** : 1 Go  
- **IP privée** : `192.168.33.3`  
- **Dossier synchronisé** :  
  - Local : `./web/`  
  - VM : `/var/www/html/`  

## Commandes utiles  

- **Redémarrer la VM** :  
  ```sh
  vagrant reload
  ```

- **Arrêter la VM** :  
  ```sh
  vagrant halt
  ```

- **Détruire la VM** (⚠ supprime toutes les données) :  
  ```sh
  vagrant destroy
  ```


- **Ababacar Asta**  