# Projet Ansible : Déploiement de JuiceShop et Grafana
## Objectif
Déployer JuiceShop sur un VPS (CentOS) et Grafana sur une machine Vagrant (Ubuntu), avec configuration automatique de Nginx comme reverse proxy.

## Étapes principales
1.	Installation des outils : Docker et dépendances.
2.	Déploiement : Applications via Docker Compose.
3.	Configuration de Nginx : Redirection du port 80 vers 3000 pour chaque machine.
4.	Inventaire dynamique : Utilisation de inventory.ini pour les noms d’hôtes.

## Prérequis
- **Ansible** installé sur la machine de contrôle.
- Accès SSH configuré pour les deux machines cibles (VPS et Vagrant).
- Clés SSH ajoutées aux machines distantes pour permettre une connexion sécurisée.

## Instructions
1. Mettre à jour le fichier `inventory.ini` pour inclure les adresses IPs des machines cibles.
2. Lancer le playbook maître qui orchestre les différentes étapes :
   ```bash
   ansible-playbook -i inventory.ini master.yml
   ```
   
## Résultat attendu
- JuiceShop : Accessible sur l’IP du VPS via le port 80.
     - http://<IP_du_VPS>
- Grafana : Accessible sur l’IP de la machine Vagrant via le port 80.
     - http://<IP_de_Vagrant> 
