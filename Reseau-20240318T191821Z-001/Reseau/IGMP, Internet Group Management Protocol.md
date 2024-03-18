---
tags: GAILLARD
---

# `IGMP`, Internet Group Management Protocol


 
# Rappel `IGMP` : 
 
 * ![](https://i.imgur.com/nKIeZx0.jpg)
 
 * Protocol obligatoire d'implemnetation + il permet l'echange d'info entre l'abonnee et le routeur R1 isi dansd notre schema.
 * Routeuter IGMP gere une tables des groupes actifs.

# `IGMP`, v1 : 



* ![](https://i.imgur.com/q1auqZ6.png)

* ![](https://i.imgur.com/ZCLqv19.png)

* On observe un abonnement.

* ![](https://i.imgur.com/o7qp4V9.jpg)



* ![](https://i.imgur.com/VNPxAgY.png)


* Desabonnement.


* ![](https://i.imgur.com/L2nWit7.png)

* Le routeur envoie un deux types de Query : Explicit et general.
* Explicit lorsque il sait qu'il a des abonnees et veut savoir s'ils sont toujours actifs ou non.
* General : quand il ne sait pas s'il y a des hosts multicast => la Querry est envoyee a l'adresse des hosts multicast : 224.0.0.1 



* ![](https://i.imgur.com/Dz1WPWY.png)



# `IGMP` v2 : 


* ![](https://i.imgur.com/TbxVbvv.png)



# `IGMP` v3 : 



![](https://i.imgur.com/R4kM2OZ.jpg)
![](https://i.imgur.com/mcKqGwg.png)
![](https://i.imgur.com/KWfWydV.jpg)


# `IGMP` Snooping



