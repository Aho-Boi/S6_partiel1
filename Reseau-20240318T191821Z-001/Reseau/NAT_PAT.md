---
tags: GAILLARD
---

# NAT/PAT 

## `NAT` Network Address Translation

* Permet de « translater » une adresse IP en une autre. Il existe deux formes de NAT :

    * le « natage », la translation d’adresse source qui consiste à **modifier l’adresse source d’un paquet IP en une autre adresse**. En effet, tout paquet qui franchi l’équipement effectuant la NAT (routeur, FireWall ou Proxy) part avec une adresse source différente de la vraie adresse source de l’émetteur. Un observateur extérieur ne verra donc qu’une adresse affectée par translation ne correspondant pas à une réelle adresse de l’émetteur. Généralement l’adresse affectée est celle de l’interface de sortie de l’équipement qui assure la translation.
    * ![](https://i.imgur.com/nmUPuhe.png)



    * la translation d’adresse destination, moins courante, permet de **modifier l’adresse destination d’un paquet IP lorsque celui-ci demande une adresse spécifique**. Vous pouvez, de cette manière, masquer l’adresse réelle d’un serveur au monde extérieur ! Les internautes cherchent, par exemple, à contacter l’adresse 132.12.12.11 qui correspond en fait à votre adresse de FireWall (Pare-Feu). Le FireWall à réception des paquets va modifier l’adresse en 10.0.0.1 qui est l’adresse interne de votre serveur ! De cette façon on ne peut pas joindre votre serveur sans passer par votre FireWall ! Bien sûr, lors de la réponse du serveur, le FireWall modifiera l’adresse source de réponse !


* La N.A.T permet de n’utiliser qu’une seule adresse machine coté Internet. Cette adresse est affectée à l’interface de sortie de l’équipement réalisant la NAT. Tous les paquets, de tous les utilisateurs internes, partiront sur Internet avec cette adresse source. Mais bien sûr les réponses des serveurs sur Internet se feront toutes vers l’adresse source indiquée dans le paquet qu’ils reçoivent, c’est à dire celle de l’équipement qui assure la N.A.T !

* ![](https://i.imgur.com/qrg31ZH.png)


* Dans ce cas, comment faire pour que les réponses arrivent bien à chaque machine qui a émis initialement la requête ? C’est assez simple … L’équipement N.A.T va **maintenir une table de correspondance des translations en cours**.

* Lorsqu’une station envoie un paquet IP vers l’extérieur, il mémorise l’adresse source interne de la station et l’adresse destination externe demandée. Ce couple est insuffisant car lors des réponses l’équipement disposera toujours de la même adresse destination (la sienne !), il ne peut donc pas déterminer à qui il doit réémettre le paquet. De la même manière, s’il se base sur l’adresse source du paquet, il pourra retrouver la correspondance d’adresse de la station initiale mais seulement si une seule station discute avec le serveur ! Si plusieurs stations discutent avec le même serveur externe il ne peut pas savoir à laquelle retransmettre le paquet. Il doit donc **mémoriser des informations supplémentaires pour identifier de manière unique un couple** station_interne – serveur_externe de manière unique.

* Il **mémorise donc également les ports source et destination du segment TCP ou UDP** véhiculé par le paquet IP. Pour une machine IP donnée **le couple @IP-N° Port Source est toujours unique**

* L’équipement de NAT mémorise donc la correspondance :
    * **adresse source interne – port tcp source – adresse destination demandée – port tcp destination**.





# Architecture Reseau : ![](https://i.imgur.com/Vz5Kyy4.jpg)



* On a differentes vues d'architecture.
* architecture physique deploye = la plus detaille + trop complique a maintenir.
* Architecure logique = beaucoup moin precise + rapide a mettre en place.

# Exercice voir doc exercice.