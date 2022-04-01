Le TP4 consiste à la mise en oeuvre d'un déploiement de pods via HELM CHART

Dans ce déploiement les chose suivante doivent être réalisé : 
  - Génération :
    - Un déploiement de serveur web
    - Un déploiement de serveur MariaDB
    - 2 PV et 2 PVC
    - Un service pour accéder serveur web
    - Un service pour que le serveur web puisse accéder à la base de données
  
  - Value modifiable (minimum) :
    - PV : name, size, path, persistentVolumeReclaimPolicy
    - PVC : name, size, volumeName
    - Serveur Web
        - volumeMount : name, mountPath
        - volumes : name, claimName
        - service : type, port, name
        - image : repository, pullPolicy, tag
        - replicaCount
    - MariaDB
        - rootPassword, user, password, database
        - image : repository, pullPolicy, tag
        - volumeMount : name, mountPath
        - volumes : name, claimName
        - service : name

 Pour qu'il fonctionne, il suffit de cloner le GIT, et de lancer la commande (Être dans le repertoire) :
  - helm install "nom" .
  !! Attention de bien avoir les addons de ingress, commande : - helm addons enable ingress
