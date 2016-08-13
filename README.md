# Spotify rpm pour Mageia
##### Comment installer Spotify(R) su Mageia?
- Pour débuter télécharger le fichier rpm depuis sourceforge.

[![chrome](https://img.shields.io/badge/T%C3%A9l%C3%A9charger rpm x86_64-V1.0.34.146-blue.svg)](https://sourceforge.net/projects/spotify-mageia/files/Spotify-1.0.34.146-mga6.1.x86_64.rpm/download)
[![chrome](https://img.shields.io/badge/T%C3%A9l%C3%A9charger rpm i386-V1.0.34.146-blue.svg)](https://sourceforge.net/projects/spotify-mageia/files/1.0.34.146/i386/Spotify-1.0.34.146-mga5.1.i386.rpm/download)

[![chrome](https://img.shields.io/badge/Sourceforge-V1.0.34.146-blue.svg)](https://sourceforge.net/projects/spotify-mageia/)

- Lancer le fichier rpm.

##### Comment refaire le packet?
- Télécharger le packet Debian sur le site de Spotify.

[![chrome](https://img.shields.io/badge/Liste-téléchargement-blue.svg)](http://repository.spotify.com/pool/non-free/s/spotify-client/)

- Décompresser le fichier
- Créer un dosier pour contenir votre projet
- Placer le dosier image (dans ce cas «usr») dans un sous-dosier nommé «root»
- Copier le fichier «Makefile» à la base de votre répertoire du projet
- Créer un fichier «name» qui contient le nom de votre application
- Créer un fichier «release» qui contient une chaine semblable à «mga5.1»
- Créer un fichier «version» contient le numéro de version du logiciel
- Créer un fichier «arc» contient l'architecture de la cible (32 bits: i386, 64 bits: x86_64)
- Ouvrir un terminal à la racine du projet et lancer la commande 
`make init`
- 
