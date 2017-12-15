# Securite-dirtyCow

Projet de sécurité du groupe : Zitouni Hedi, Follet Nicolas et Gérigné Antoine.



#------------------------------------------------
#--------------DirtyCowHere.sh-------------------
#------------------------------------------------

Ce script va préparer l'environement dans le répertoire DirtyCowHere pour pouvoir tester la faille dirty cow dans votre environnement actuel.
Rendez vous dans le repertoire DirtyCowHere et executez le script createfoo.sh
Un fichier foo est créé, accessibe en lecture seule, lorsque vous compiler le projet dirtyc0w.c grace a la commande suivante :

'gcc -pthread dirtyc0w.c o dirtyc0w'

et que vous executez la commande suivante :

'./dirtyc0w foo "text"'

Le programme dirtyc0w vas utiliser la faille décrite dans notre rapport pour écrire le "text" en debut de foo.
Cette faille marche que pour des versions du kernel inferieure à 4.8.3, en particulier, si vous l'executez sur les machine Centos 7 de l'ensimag, il ne va pas fonctionner.

#------------------------------------------------
#-----------DirtyCowDeb-8-0-0.sh-----------------
#------------------------------------------------

Ce script va telecharger une image de Debian8.0.0 qui contient deja tout le nécessaire, cette version de Debian utilise le kernel 3.16
Aussi la faille fonctionne dans cet environnement.

pour lancer la machine virtuelle, lancez la commade suivante dans le répertoire DirtyCowDeb-8-0-0:

'virtualbox Debian-8-0-0.ova'

VirtualBox va s'ouvrir et vous proposer d'importer l'appareil virtuel. Cliquez sur Importez puis lancez la machine virtuelle.

Le code de la faille est présent dans le répertoire Documents/dirtycow/ de la machine virtuelle.

Pour initialiser le fichier accessible en lecture seule, lancez:

'sh createFoo.sh'

Compilez dirtyc0w.c avec la commande :

'gcc -pthread dirtyc0w.c o dirtyc0w'

et executez la commande suivante :

'./dirtyc0w foo "text"'

Le programme dirtyc0w vas utiliser la faille decrite dans notre rapport pour ecrire le "text" en debut de foo.