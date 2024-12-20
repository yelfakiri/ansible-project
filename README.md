# Projet Ansible : Déploiement de JuiceShop et Grafana avec Nginx

Ce projet Ansible a pour objectif de déployer des applications et de configurer un serveur **Nginx** sur deux environnements distincts : 

1. **VPS (sous CentOS)** : **JuiceShop**.
     
2. **Machine Vagrant (sous Ubuntu)** : **Grafana**.

## Fonctionnalités
- Installation automatisée de Docker et des dépendances nécessaires.
- Configuration de **Nginx** comme reverse proxy redirigeant le port 80 vers le port 3000 de Grafana et de JuiceShop, cela permet de contourner les limitations des iptables de Docker.
- Déploiement des applications JuiceShop et Grafana via Docker Compose.

## Prérequis
- **Ansible** installé sur la machine de contrôle.
- Accès SSH configuré pour les deux machines cibles (VPS et Vagrant).
- Clés SSH ajoutées aux machines distantes pour permettre une connexion sécurisée.

## Instructions
1. Mettre à jour le fichier `inventory.ini` pour inclure les adresses IP des machines cibles (VPS et Vagrant).
2. Lancer le playbook maître qui orchestre les différentes étapes :
   ```bash
   ansible-playbook -i inventory.ini master.yml
   ```
   
## Résultat attendu

- **JuiceShop** :  
  Accessible via l’adresse IP du **VPS** sur le port **80**.

- **Grafana** :  
  Accessible via l’adresse IP de la **machine Vagrant** sur le port **80**.
