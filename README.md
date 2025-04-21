#Projet Sherlock 13

Compilation du projet

Prérequis

Installer les bibliothèques SDL2 et extensions :

sudo apt update
sudo apt install libsdl2-dev libsdl2-image-dev libsdl2-ttf-dev

Commande de compilation

Pour compiler le client SDL :

gcc -o sh13 sh13.c `sdl2-config --cflags --libs` -lSDL2_image -lSDL2_ttf

Pour compiler le serveur :

gcc -o server server.c

Lancer une partie

1. Lancer le serveur

./server 2000

2. Lancer les clients

Lancer 4 clients dans des terminaux séparés :

./sh13 127.0.0.1 2000 127.0.0.1 5001 Player1
./sh13 127.0.0.1 2000 127.0.0.1 5002 Player2
./sh13 127.0.0.1 2000 127.0.0.1 5003 Player3
./sh13 127.0.0.1 2000 127.0.0.1 5004 Player4

Une fois connectés, cliquez sur le bouton "Connect" dans l'interface SDL pour rejoindre officiellement la partie.

Règles du jeu

Il y a 13 cartes personnage, 12 sont distribuées (3 par joueur), 1 est le coupable à deviner.

Chaque personnage possède 2 ou 3 objets caractéristiques.

Le but est de deviner qui est le coupable en posant des questions aux autres joueurs.

Actions possibles :

Poser une question à tous : "Qui a au moins un objet [X] ?"

Poser une question ciblée : "Combien de [X] as-tu ?"

Accuser un personnage si vous pensez avoir trouvé le coupable.

Fin du jeu :

Si un joueur accuse correctement → il gagne la partie.

S'il se trompe → il est éliminé.