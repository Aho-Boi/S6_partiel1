---
tags: GAILLARD
---

# `TCP`/`UDP`



:::info
* Dans le teams de ce cours 5 juin, fichier word contenant le sujet des exams.
:::


## `TCP`, Transmission Control Protocol : 


* ![](https://i.imgur.com/pzoRxoW.jpg)
* ![](https://i.imgur.com/BX7pSI0.png)


* `TCP` : 
    * L4.
    * Protocol fiable.
    * En mode connecte / interconnexion.
    * Mecanismes : d'acquitement, de tranmission, de gestion de flux, de reprise sur erreur.
    * Full Duplex : 
    * Gestion de Buffer au extremite de la connexion.
    * 
    * TCP control Block = une informatuion construite en memoire de chaque cote et on y trouve une socket TCP qui contient ip sources/dst les ports src/dst.
    * `TCB` = cree a l'ouverture d'une connexion et detruit a la fermeture.
    * ![](https://i.imgur.com/N3E9rjb.png)
    * ![](https://i.imgur.com/yioYjTh.png)

    * Lors d'une ttransmission entre A et B tcp de B envoie info aux couches au-dsessus <=> le flag Push est actionne sinon il buffurise inbformatrion.

## `UDP`, User Datagram Protocol : 

* `UDP` : Peut fiable, Ne sait pas si paquet est arrive a destination => on doit utiliser accuse de reception.


## `TCP` et `UDP` : 

* Leur point commun est qu'ils utilisent des mecanismes de ports : 
    * Ports codes sur 16 bits.
    * ![](https://i.imgur.com/g60hdJw.png)
    * Well Know Port : port specifique connue comme 80 sur UDP pour http en mode Serveur.
 
 
 
 
 ## Three Way And Check : 
 
 
![](https://i.imgur.com/4DyL298.png)

![](https://i.imgur.com/QIlb4Dg.png)

![](https://i.imgur.com/6RRVrsw.jpg)

![](https://i.imgur.com/V2noa42.jpg)

![](https://i.imgur.com/upeIGu5.png)


![](https://i.imgur.com/dxEY34E.png) 



* Sequence d'ouverture/fermeture  de connexion entre deux TCP.





* Le TCP receveur fixe la taille de la fenetre (Ici c'est m).






