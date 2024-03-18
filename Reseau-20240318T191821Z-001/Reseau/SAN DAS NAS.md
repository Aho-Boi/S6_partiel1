---
tags : GAILLARD
---


# `SAN` `DAS` `NAS`


## `SAN`, Storage Area Network

### Description general : 

![](https://i.imgur.com/f3pwk82.png)


* Un reseau SAN = 2 Fabric independante en parallele => haute disponnibilite => tolerance au panne + maintenance transparente au applications.
* Une FABRIC est compose d'un ensemble de switch SAN connecte.
* Achemine les donnees a stocker depuis les serveurs jusqu'a la baie de stockage.

### Donnees Qui Transitent : 

#### Par Bloc : 



* Les donnees qui transitent a travers le SAN sont regroupees en bloc de donnees => le File System du serveur peut acceder directement en mode bloc aux donnees dans un SAN => Chaque serveurs voit l'espace disque du baie de stockage auquel il a acces comme son propre disque dur => ces stockages peuevent etre partager simultanement entre plusieurs serveur.

****

#### Requete `SCSI`, Small Computer System Interface, et `FC` Fiber Channel : 

![](https://i.imgur.com/rCFBDsB.png)

* Le SAN transite les requetes SCSI = standar definissant un bus en informatique reliant des machines.
* Ces requetes SCSI sont transporte par les `FC`, Fiber Channel.
* Le `FCP`, Fiber Channel Protocol permet le transport a haut de debit entre serveurs et espace de stockage.
* Carte `HBA`, sur la fibre optique, permet de faire l'interface entre serveurs et un reseau.
* Canal I/O:
    * Peu d’appareils
    * Statique
    * Faible temps d’attente
    * Courtes distances
    * Gestion de la livraison basée sur matériel

****

#### Requete `SCSI`, Small Computer System Interface, et le `iSCSI`, internet ... :


![](https://i.imgur.com/4J97HF8.png)


* Les paquets peuvent etre router sur internet => utiliser Ethernet moins couteux.
* Reseau Ethernet : 
    * Nombreux appareils
    * Dynamique
    * Long temps d’attente
    * Longues distances
    * Gestion de la livraison
    * basée sur logiciel

*****

### Fonctionnalites clees : 


#### Le Zonning : 

![](https://i.imgur.com/XPTFyvI.png)

* Permet de cloisiner les espaces de stockages equivaleent d'un VLAN 

****

#### Le `LUN`, Logical Unit Number : 
 
 
![](https://i.imgur.com/skbNJsz.png)
![](https://i.imgur.com/aeUHjXW.png)

* Creation de plusieures `LUN`.
* Decoupage dui stacokgae en plusieursd unite logqiuuye => gestion plus efficace du sstockage.
* Replication synchrone / asynchrone : 

****

#### Le Thin Provisionning :

![](https://i.imgur.com/XJQrasQ.png)

****

#### Le Tierring : 

![](https://i.imgur.com/YTPI8o6.png)

****

## `DAS`, Direct Attached Storage ;

![](https://i.imgur.com/QBPCqj4.png)

* Disque de stockage directement relier au serveur.
* Echange de donne entree serveur et disque en mode block.
* Oas possible de relier simultanementn avec d'autre sedrveur. 
* Allocation espace disque peut optimise.

****

## `NAS`, Network Attached System : 


![](https://i.imgur.com/EElUgDD.png)




* Baie de stockage qui possede a la fois son propre systeme d'exploitation dedier a la gestion des donmnees, d'un logiciel de config de son propre filesystem et un ensemble de disque independant.
* Il est attache au reseau de l'entreprise => il deviens comme un serveur de fichier, les harddrive sont relier au nas et pas au serveur + acces client au donnees sans passer par un serveur.
* Il partgae les donnees sous forme de fichiers pas bloc + un meme fichier peut etre partage simultanement