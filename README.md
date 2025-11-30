# Simulation Réseau

# Images
<div align="center">
  <img width="956" height="470" alt="image" src="https://github.com/user-attachments/assets/a2cbcbb0-5e9b-45b8-819b-621655b69383" />
</div>

# Description
Simulation d’un réseau informatique avec stations et switches en C.
Le projet permet de :
Créer un réseau à partir d’un fichier de configuration (mylan ou mylan_nocycle).
Simuler le protocole STP (Spanning Tree Protocol) pour éviter les boucles.
Envoyer des trames Ethernet entre stations, avec apprentissage automatique des adresses MAC par les switches.
Afficher l’état complet du réseau (stations, switches, liens, ports, tables de commutation).
Ce projet est entièrement développé en C et fonctionne en console.
L'état actuel du projet permet de créer un réseau sans boucle et d'envoyer et afficher des trames, le protocole STP n'est pas très fonctionnel.

# Technologies utilisées
Le jeu est codé en C sur VSCodium. Compilé avec gcc et fourni un Makefile pour la compilation automatique. Un fichier est utilisé pour créer le réseau.
# Guide d'installation
Cloner le dépôt :
```bash
git clone https://gitlab.com/Brioche67/simulation-reseau.git
cd simulation-reseau
```
Dans main.c modifié le chemin du fichier pour créer le réseau :
```bash
creer_reseau("CHEMIN_ABSOLU_FICHIER", &reseau);
```
Compiler le projet avec Make :
```bash
make
```
Le binaire main sera généré dans le dossier bin/.
Lancer le projet :
```bash
./bin/main
```
Le programme utilise le fichier mylan_nocycle par défaut pour générer le réseau.

# Fonctionnalités
###Création du réseau :
Lecture des fichiers mylan et mylan_nocycle.
Initialisation des stations et des switches avec leurs adresses MAC/IP.
Allocation dynamique des liens et des tables de commutation.
###Affichage du réseau :
Détails des stations et switches.
Table de commutation et état des ports (ACTIF, BLOQUE, DESACTIVE).
Liens et ports associés.
###Transmission de trames :
Création de trames depuis les noms des stations.
Transmission entre stations via les switches.
Apprentissage dynamique des adresses MAC dans les switches.
Gestion de la diffusion et des ports d’entrée pour éviter les boucles.
###Protocole STP :
Calcul des ports racines et désignés pour chaque switch.
Convergence automatique jusqu’à ce que tous les switches aient trouvé l’arbre couvrant.
Mise à jour de l’état des ports pour éviter les boucles.
