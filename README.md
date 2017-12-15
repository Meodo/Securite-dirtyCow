# Securite-dirtyCow

Projet de sécurité du groupe : Zitouni Hedi, Follet Nicolas et Gérigné Antoine.



#------------------------------------------------
#--------------DirtyCowHere.sh-------------------
#------------------------------------------------

Ce script va préparer l'environement dans le répertoire DirtyCowHere pour pouvoir tester la faille dirty cow dans votre environnement actuel.
Rendez vous dans le repertoire DirtyCowHere et executez le script init.sh
Un fichier foo est créé, accessibe en lecture seule et un executable dirtyc0w est créé.

lorsque vous executez le script exec.sh, le programme dirtyc0w vas utiliser la faille décrite dans notre rapport pour écrire le "text" en debut de foo.
Cette faille marche que pour des versions du kernel inferieure à 4.8.3, en particulier, si vous l'executez sur les machine Centos 7 de l'ensimag, il ne va pas fonctionner.

#------------------------------------------------
#-----------DirtyCowDeb-8-0-0.sh-----------------
#------------------------------------------------

Ce script va telecharger une image de Debian8.0.0 qui contient deja tout le nécessaire, cette version de Debian utilise le kernel 3.16
Aussi la faille fonctionne dans cet environnement.

pour lancer la machine virtuelle, lancez la commade suivante dans le répertoire DirtyCowDeb-8-0-0:

'virtualbox Debian-8-0-0.ova'

VirtualBox va s'ouvrir et vous proposer d'importer l'appareil virtuel. Cliquez sur Importez puis lancez la machine virtuelle.

Les logins de cette machien virtuelle sont:
login : ensimag
mdp : root


Le code de la faille est présent dans le répertoire Documents/dirtycow/ de la machine virtuelle.

Pour initialiser le fichier foo accessible en lecture seule, et pour créer l'exécutable dirtyc0w, lancez:

'sh init.sh'

puis lancez le script exec.sh

Le programme dirtyc0w va utiliser la faille décrite dans notre rapport pour écrire le "text" en debut de foo.