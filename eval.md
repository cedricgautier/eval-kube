# Évaluation Kubernetes

## 🎯 Objectif
Évaluer le niveau des étudiants en Kubernetes à travers **quiz** et **ateliers pratiques**.

---

# PARTIE 1 : Évaluation pratique


## Atelier 1 : Déploiement d’une application web

### Contexte professionnel
Votre entreprise souhaite tester rapidement une application web dans un cluster Kubernetes.
Pour que l’équipe puisse valider l’installation, l’application doit être accessible via un Service stable.

### Objectif de la mission

#### 1. Rédiger un fichier YAML clair, bien indenté et soigneusement commenté qui contient :

- La creation d'un namespace nommé `production`

- Un Deployment nommé `web-app-deploy` dans le namespace `production` :
  - Utilisant l’image `nginx:1.28.0` avec un conteneur nommé `web-app`. 
  - Avec un Pod unique
  - les bons labels : `app=web-app` et `env=<VOTRE_PRENOM>`

- Un Service nommé `web-app-svc` exposant le port de votre choix et redirigeant vers le port 80 du conteneur.

#### 2. Vérifier attentivement que :

- Le Pod est bien créé dans le bon namespace et en cours d'execution.

- Le Service est correctement lié au Pod grâce aux labels et selectors.

- L’accessibilité de l'application.


### Livrables attendus
- Fichier YAML contenant à la fois le Namespace, Deployment et le Service.
- Une démonstration avec les ressources en Running/Active.
- Un test d’accès à l'app.

### Vérification par l’enseignant
L’enseignant vérifiera attentivement :
- La qualité syntaxique et la lisibilité du YAML.
- L’existence d’un  Namespace, Deployment, Pod en cous d'execution et un Service actif. 
- La présence des labels cohérents, selector correct, ports alignés.
- La possibilité d’accéder réellement au contenu de la page web.

---

##  Atelier 2 : Déploiement évolutif et résilient

### Contexte professionnel
`Web-app-deploy` est une application critique. Elle doit être scalable, tolérante aux pannes et exposée via un Ingress.  

### Objectif de la mission
- Adaptez `Web-app-deploy`
- Mettre en place un Horizontal Pod Autoscaler (HPA) pour adapter automatiquement la charge en surveillant le déploiement et ajuste le nombre de Pods entre 1 à 5 pour maintenir l’utilisation CPU moyenne autour de 50 %. 
- Créer un Ingress pour exposer l'application critique.  

### Livrables attendus
- Pods déployés et accessibles via Ingress.  
- HPA fonctionnel (scaling en fonction de la charge).  

### Vérification par l’enseignant
- Manifestes YAML (Namespace, Deployment, Service, HPA, Ingress).  
- Demo de fonctionnement

---

##  Atelier 3 : Déployer une application avec réplication et persistance

### Contexte professionnel

Une PME veut déployer une base de données `MySQL` et stocker les données même si un Pod redémarre en `production`.

### Objectif de la mission
- Créez un Deployment nommé `mysql-deploy` avec `2 réplicas`, utilisant l'image `mysql:8.4.6`.

- Utilisez un `PersistentVolumeClaim` de 1Gi pour stocker les données.

- Passez la variable d’environnement `MYSQL_ROOT_PASSWORD=admin123` dans un  `ConfigMap`.

- Exposez MySQL via un `Service` de type ClusterIP (`msql-service`).

- Vérifiez que les Pods se connectent bien au volume et au Service.

### Livrables attendus
- Le Deployment gère 2 Pods en Running en production.
- Les Pods utilisent le PVC.
- presence de ConfigMap
- Connexion possible au MySQL avec un client (`mysql -h mysql-service -p`) pour verifier la version. (BONUS)

### Vérification par l’enseignant
- Manifestes YAML contenant l'ensemble des ressources.  
- Demo de fonctionnement

---

# PARTIE 2 : Évaluation théorique

**Quiz de 40 questions** couvrant les domaines de kubernetes ci-dessous :
- Architecture du cluster, Installation et Configuration.
- Charges de travail et Ordonnancement.
- Stockage
- Services et Réseau.  
- Dépannage

Le quiz est accessible sur [https://forms.office.com/e/yWqURdEmnY](https://forms.office.com/e/yWqURdEmnY).

