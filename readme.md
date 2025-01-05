Le dossier K8s n'est pas utile, il représente une version anterieure de la partie 2, non fonctionelle.

# 1 - Docker compose
## Chargez l’image Docker webapp-1.tar et créez un fichier compose.yaml avec un service mongodb/mongodb-community-server pour la démarrer. (images sur le Moodle)
- Charger l'image avec : docker load -i webapp-1.tar
- Créer le compose.yaml

![lqsdml](https://github.com/user-attachments/assets/dda36c8e-b816-4219-8cb0-a98a284eff30)

## Essayer d’ajouter un utilisateur.
La page renvoie une erreur. On ne peut pas ajouter d'utilisateur.

![lugigyg](https://github.com/user-attachments/assets/40a2af54-13d0-4d01-b1ea-c2162ffcc82f)

![kgjhgj](https://github.com/user-attachments/assets/07199db6-effb-442a-a205-a0c07f49ffe3)

## Il est possible que Lucas n’aie pas bien testé. Quel est le problème ? Comment le voyez-vous ?
Il manque un fichier, l'erreur suivante est retournée :
[ERROR] unable to create /var/log/webapp/webapp.log (No such file or directory (os error 2)), exiting)
Il faut donc le créer manuellement pour corriger l'erreur.

## « Faut qu’ça tourne! » Redémarrez le conteneur webapp et connectez-y vous pour le faire fonctionner tout de même.
En créant le fichier
![qmsldkm](https://github.com/user-attachments/assets/47d4e252-fba3-4485-917d-6969a82345fc)


## Quelle ligne Lucas pourrait-il rajouter à son Dockerfile pour le résoudre ?
RUN mkdir /var/log/webapp && touch /var/log/webapp/webapp.log

## Remplacer l’image de la webapp par celle de webapp-2.tar et testez que l’ajoutd’utilisateur soit fonctionnel.
Dans le compose.yaml on modifie la ligne suivante :
  webapp:
    image: webapp-1:latest
Par :
  webapp:
    image: webapp-2:latest

# 2 - Kubernetes

## Installez et démarrez Minikube ( minikube start --driver=docker )
![qksfjlkfqj](https://github.com/user-attachments/assets/dd927a4b-bf5e-421f-84a2-3a74a7f59183)


## Monitorez l’état de votre cluster Minikube avec kubectl get all .
![qskjdlkj](https://github.com/user-attachments/assets/93f65e8a-31b1-41f8-8201-234a0764ee3f)


## Utilisez l’utilitaire kompose pour convertir votre compose.yaml en configurations K8s.


## Appliquez les configurations. Quelles corrections avez-vous dû leur apporter ? Dans quel ordre les appliquez-vous, et pourquoi ? Utilisez les attributs readinessProbe sur les pods MongoDB et webapp.


## Pourquoi la webapp n’a pas été déployée ? Corrigez cela avec minikube docker-env .


## Paramétrez le déploiement de la webapp pour avoir deux répliques. Testez la redondance en tuant un des pods de la webapp

