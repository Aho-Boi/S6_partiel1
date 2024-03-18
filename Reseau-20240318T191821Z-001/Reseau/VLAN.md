---
tags: GAILLARD
---

# VLAN 


# VLAN :

![](https://i.imgur.com/FYFXAnJ.png)

## VLAN type 1 par PORT : 


![](https://i.imgur.com/1w2oJ9F.png)


* Creation VLAn : fonction 802.1Q.

* Pour inter connecter deux VLAN : fonction de bridging.

* Pas mal utilise.

* Probleme : on ne peut pas manipuler d'IP.


## VLAN type 2 par MAC address : 



![](https://i.imgur.com/ixejr0z.png)


* Pb : doit connaitre MAC des machines.

## VLAN type 3 par SubNet IP : 


![](https://i.imgur.com/0aRNBUh.png)
![](https://i.imgur.com/TQWWkGW.png)



* Tres utilise.


* Utilise info de niveau 3 popur creer reseau de niv 3.

* Les switchs de base ne peuevnt router deux reseaux different => on doit faire appel a une fonction de routage pour inter connecter deux VLAN de type 3.


## Comment utiliser VLAN entre differents Switch : 

![](https://i.imgur.com/HgneOyP.png)


* On a donc diff switchs, la trame qui part de A est sans TAG 802.1Q.

![](https://i.imgur.com/i08yTif.png)
![](https://i.imgur.com/IN8MULn.png)
![](https://i.imgur.com/FaPsYlB.jpg)
![](https://i.imgur.com/IpzbJ9v.png)




* Arrivee dans S1, la trame va etre modifie pour devenir TAGUE.
* Dans la trame on ajoute un champ de 4 octets divise en plusieurs champs.
* Le champs TPID a ete mit pour respecter la structure de la trame car apres un champs Souce il faut Type.
* Ici on observe les etapes pour enbvoyer une trame de A vers C. Une fois arrivee a C le switch S2 retire le tag rajoute par S1.
* Les TAGS sont utilise uniquement par les switchs.

## Quel est l'impact de l'activation du VLAN : 802.1Q : 


![](https://i.imgur.com/Z5DJq3x.png)


* Rajoute 4 octet.
* Trame ethernet : Payload min 46o max 1500o; CRC 4o => avec VLAN : on passe a 1522 => si un switch n'est pas en mode VLAN gros pb.



