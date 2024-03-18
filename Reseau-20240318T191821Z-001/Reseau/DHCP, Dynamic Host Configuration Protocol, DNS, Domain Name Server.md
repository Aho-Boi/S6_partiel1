---
tags : GAILLARD
---



# `DHCP`, Dynamic Host Configuration Protocol, `DNS`, Domain Name Server


:::info
* Avant de laisser place au `DHCP` pour obtenir une adresse IP, plusieurs protocoles etaient utilises.
:::

## `RARP` (ReverseARP)
 - jusqu'en 1985
 - un serveur RARP qui a un fichier d'association `MAC -> IP`
 - RARP fonctionne comme ARP donc sur L2 -> ne traverse pas les routeurs

## `BOOTP`
 - de 1985 à 1993 mais peut toujours etre utilisé
 - Utilise UDP => IP => traverse routeur.
 - requête `BOOTP` en broadcast sur 255.255.255.255
 - Probleme : pas de notion de `lease` donc pas de mise a jour de la conf périodiquement => c'est-a-dire qu'on peut garder une adresse IP tant qu'on a pas eteint la machine en question. + IP unique.
 - Statique
 
## `DHCP`
 - depuis 1993
 - le DHCP introduit la notion de `lease` ou `baille` qui indique la durée de vie pour la configuration envoyée par le DHCP.
 - simple paquet IP/UDP donc cela peut passer les routeurs étant donné que c'est du L3
 - Donne adresse  IP + adresse Gateway + DNS ...
 - Statique / Dynamique.
 - Etape : DHCP discover - DHCP Offer - DHCP Request - DHCP Hack / Nack
 - Pour le renouvellemnt : 
     - a 50% du temps avant la fin du bail :  clien dhcp demande au serveur dhcp fait une request pour savoir s'il peut cvontinuer a utiliser plus => soit HACK => oui soit il repond pas => il peut utiliser jusqu'a la fin
     - a 87,5 % : Nouvelle demande de renouvellemtn => soit le serveur repond : accept/refuse soit repond pas.
- pour requets en brodcast il faut gerer les routeurs pour donner autorisation.


## `DNS` : 

- Voir HackMd partage.

## TD RXAN 2019 : 

- Voir fichier Exercice.