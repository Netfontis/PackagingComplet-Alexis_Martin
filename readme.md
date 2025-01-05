# 1 - Docker compose
## Chargez l’image Docker webapp-1.tar et créez un fichier compose.yaml avec un service mongodb/mongodb-community-server pour la démarrer. (images sur le Moodle)
- Charger l'image avec : docker load -i webapp-1.tar
- Créer le compose.yaml

## Essayer d’ajouter un utilisateur.


## Il est possible que Lucas n’aie pas bien testé. Quel est le problème ? Comment le voyez-vous ?


## « Faut qu’ça tourne! » Redémarrez le conteneur webapp et connectez-y vous pour le faire fonctionner tout de même.


## Quelle ligne Lucas pourrait-il rajouter à son Dockerfile pour le résoudre ?


## Remplacer l’image de la webapp par celle de webapp-2.tar et testez que l’ajoutd’utilisateur soit fonctionnel.

# 2 - Kubernetes

## Installez et démarrez Minikube ( minikube start --driver=docker )


## Monitorez l’état de votre cluster Minikube avec kubectl get all .


## Utilisez l’utilitaire kompose pour convertir votre compose.yaml en configurations K8s.


## Appliquez les configurations. Quelles corrections avez-vous dû leur apporter ? Dans quel ordre les appliquez-vous, et pourquoi ? Utilisez les attributs readinessProbe sur les pods MongoDB et webapp.


## Pourquoi la webapp n’a pas été déployée ? Corrigez cela avec minikube docker-env .


## Paramétrez le déploiement de la webapp pour avoir deux répliques. Testez la redondance en tuant un des pods de la webapp

