---
tags: GAILLARD
---


# `MPLS`, MultiProtocol Label Switch 

* ![](https://i.imgur.com/MoqBHzp.png)
* ![](https://i.imgur.com/SosRlME.jpg)



## Sans `MPLS` : 

* ![](https://i.imgur.com/fRw32nU.jpg)


## Avec `MPLS` : 

* On utilise le principe de bout en bout avec entree et sortie.

* Sans `MPLS` on a uniquement le plan de routage, avec `MPLS` on a un plan de commutation.
* Gain de perfomrance avec QoS.
* ![](https://i.imgur.com/XZLme9g.jpg)


## Description : 


* ![](https://i.imgur.com/slPmcwr.png)
* ![](https://i.imgur.com/HQ0D9uI.png)
* ![](https://i.imgur.com/ZWBU23I.png)


* Flux = ip s/d + port s/d + protocol couche 4.
* Label = Champ essentiel qui est attribue en focntion du flux auquel le paquet ip appartient.
* `LDP` = Protocol qui construit les label
* Le paquet ne sera plus router mais plustot commuter par rapport a son header MPLS(label), on supperpose le routage IP avec commutation.


![](https://i.imgur.com/QjmcD0N.png)


* Une fois `MPLS` activer, tout les routeurs deviennent des `LSR`, Label Switch Routeur.
* Ingress/Egress LSR = Entree/Sortie routeurs Flux.
* Les autres routeurs sont des Transit LSR.
* Pour un flux dfonnee on va determiner un `LSP`, Label Switch Path, un chemin de commutation de label de bout en bout.


![](https://i.imgur.com/Fdp7ks6.png)


* Les routeurs `MPLS` , ou plustot le plan de commutation `MPLS` utilises les tables de routage pour construire les meilleurs chemins.

![](https://i.imgur.com/QSreOEp.jpg)

![](https://i.imgur.com/r0sywcc.jpg)


* `FEC`, Forwarding Equivalence Class = relier au flux d'entree. 
* Le label est determiner en fonction du `FEC`, chaque FEC attribuer a un Label.


* La table de commutation se construit grace au `LDP`, Label Distribution Protocol.
* En gros le routeur de sortie, Egress, va dire, grace au `LDP`, au routeur intern que pour un flux donnee il veut un label precis => le rotueur inter dans sa table de commutation va speicifie pour ce flux donnee le label demande par le Egress routeur. Cette information va jusqu'a la source Ingress.

:::success
* Pourquoi le Egress routeurs a-t-il choisit pour un flux donnee, un label et une interface precise ?
    *  car grace a sa table de routage il va pouvoir determiner le meilleur chemin donne pour ce flux a partir de la source de ce flux.
:::

:::warning
* Les labels ne sont pas uniques, ils sont utilises de proche en proche pas de bout en bout.
:::

:::info
* On garde tjr le plan de routage qui determinent les plus cours chemnin entre uyn routeur et une source de flux donnee => a partir de cette table on va pouvoir determikner le meilleure chemin `MPLS`.
* La plan de commutation MPLS tire profit de cellui de routage.
:::
![](https://i.imgur.com/JXVmBrH.jpg)

![](https://i.imgur.com/pzmINlH.png)

![](https://i.imgur.com/3KmiJme.png)

![](https://i.imgur.com/PAtsghl.png)
 

## Label Stacking : 

* On veut un chemin de bout en bout en utilisant MPLs au pres d'un operateur, lew pb c'est que ce n'est pas toujours possible : 
    
    * ![](https://i.imgur.com/VSH8weC.png)
    * Ici les Telco1 sont pareils et les Telco2 idem.

* Une des solutions est de faire appel au stack bit sur le header MPLS : on maintient le header et le label a la sortie d'un MPLS, avant ca on doit meetre d'accord les differents MPLS avec le peering MPLS : 
    
    * ![](https://i.imgur.com/rpgOKnh.png)

    * ![](https://i.imgur.com/oT4CCgN.png)


    * On observe un empillage des headers, s= 0 puis 1.
    * Ici les Telco1 sont pareils et les Telco2 idem.


    * ![](https://i.imgur.com/HjgwjOH.png)


    