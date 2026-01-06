Amsellem Alan 

EN utilisant les worklofws j"ai detecte plusieurs vulnerabilitées : 

Trivy_scan : 


🚨 Problème N°1 : Une fuite de secret 
-> Dans la section private-node.pem (secrets).
        Ce que Trivy a trouvé : Un fichier nommé private-node.pem qui contient une clé privée SSH.
-> Pourquoi c'est grave ? 
        C'est Une clé privée. Si ce fichier se retrouve sur GitHub, n'importe qui         peut se connecter au serveur, voler les données ou prendre le contrôle de la machine.
        Trivy te montre même les lignes concernées (lignes 2 à 4) qui commencent par BEGIN OPENSSH PRIVATE KEY.

-> Ce que je fais :
        Supprimer ce fichier du projet.