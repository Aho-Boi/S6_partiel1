---
tags: GAILLARD
---

# Multicast IP 

![](https://i.imgur.com/KLuz6qI.png)



* Privilegier le flux Multicast que le fulx Unicast car en UNicast on doit faire n * flux alors qu'en mulit c'est 1 * flux.



![](https://i.imgur.com/szqeD3j.png)



* Le flux multicast est toujours sur UDP + unilateral ( flux aller,  pas aller-retour)


![](https://i.imgur.com/4C1qq6P.png)


* En multicast les abonnee partage la meme adrs de groupe IP = adrs multicast = adrs de classe D.
* Mais chacun possede sa propre adrs unicast


![](https://i.imgur.com/uTVgcTq.png)


* Les abonnees partage le meme groupe ID.


![](https://i.imgur.com/Z6fxsUg.png)



* Pour connaitre l'adresse de classe D, les appli au-dessus de la couche 4 vont lance un truc qui va faire remonte cette adresse et qui sera connu par les abonnees.


![](https://i.imgur.com/uY3gVTw.png)




![](https://i.imgur.com/OVTjqhN.jpg)



* Routeur echange table de routage qui contiennent que des adresse Unicast => certains flux multiat ne peut pas passer par routeur.
* Meme sans activier lecteur applicatif, les hosts TCP/IP possedent sur leur couche 4 un protocol : `IGMP`, Internet Group Management Protocol.
* Ce protocol est obligatoire dans les piles tcp/ip. 
* Il permet de faire abonnement/desab d'un host au pres de son plus proches routeurs multicast.
* Les paquet IP contewntn IGMP sont echange entre les hosts multicast et les routeurs multicast de proximi, le paquet IP a un TTl de 1 => ces paquets ne traverse pas les deux routeurs R6 et R7.
* Les routeurs R6 et R7 vont ensuite communiqwuer leurs infos aux autres routeurs qui vont pouvoir s'activer en mode multicast et construire un arbre de distribution : multicast tree.
* la racine de cette arbre est situe la ou le flux entre

![](https://i.imgur.com/jBd3z5u.jpg)


* Exemple : lorsqu'on active A il passe d'uni a multi + il devient membre du groupe 228.0.0.1 + le protocol IGMP s'active + va envoyer  IGMP report(contenant l'adresse 228.0.0.1) + le routeur R6 recoit le report => va enregistrer un nouvel abonne dans le groupe 228.0.0.1.
* On peut s'ernregiostrer de diff maniere au presa d'un routeur soit direcxtemnt avec un report soit request puis report.



 


![](https://i.imgur.com/XUG3xFx.jpg)

* Desabonnemnt de A.



![](https://i.imgur.com/tAXcNxv.jpg)




* pb overlapping : diffeerente IP mais mm MAC multicast


## Determiner l'adresse MAC multicast : 
![](https://i.imgur.com/OF7q1fm.jpg)
![](https://i.imgur.com/ozZoqDl.jpg)

* Les 24 premiers bits ont tjr cette valeure : 01 00 5E
* Le 25eme toujours a : 0.
* Les 23 bits restants : prendres les 23 bits de poids faible du Groupe ID dans l'adresse IP multicast.
* le bit tjr a 0 remplace le dernier bit de poids faible du group ID.

## Les Problemes des adresses MAC multicast : 

![](https://i.imgur.com/9CwZmDs.jpg)

* Plusieurs adresses ip multicast peuvent avoir la meme Mac multicast. 
* On a 5 bits qui ne sont pas pris en compte dans l'adresse IP pour l'adresse MAC => on aura 2 puissance 5 adresse ip  qui auront la meme MAC.


![](https://i.imgur.com/vyyzidQ.png)

* Ici A et D ont deux adresses IP multicast differentes mais la meme adresse MAC => on a un pb car B et C vont recevoir une info en plus.
* Le switch en unicast utilise sa table d'auto aprentissage pour savoir a qui envoyer la trame mais cette table ne fonctionne qu'en unicast.
* Differentes solution pour ce pb : 
    * le switch renvoie le flux sur tout les ports.
    * Mettre un truc sur un poirt genre le port ethernet en bleu : le flux multicast il achemenie manumiliatri sur ce port la.
     
     ![](https://i.imgur.com/moxxaHl.png)

    * Lw swtich possed une fonction de haut niveau : IGMP Snooping : C est abbonne a A => il envoi un IGMP report : Le switch va identifier cette IGMP report qui sera envoyer a tout les routeur (multicast) : adresse 224.0.0.2 (adresse multicast reservee) = 01 00 5E 00 00 02  => dans le msg IGMP l'IMGM Snooping va determiner l'adresse de C.
