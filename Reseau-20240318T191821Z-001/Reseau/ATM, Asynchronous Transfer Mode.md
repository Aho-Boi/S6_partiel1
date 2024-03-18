---
tags : GAILLARD
---

# `ATM`, Asynchronous Transfer Mode

# Introduction

:::info
* **`ATM` = technologie récente + permet l’accès au réseau haut débit.** 
* **Réalise transmission des données + voix + vidéo, en garantissant une bande passante minimale à chaque connexion, notion de qualité de service.** 
* **S’applique au domaine des LAN, HSLAN, MAN et WAN.**
:::

# 1) Les cellules ATM
:::warning
* **Les cellules ATM sont de longueurs fixes ce qui facilite le multiplexage + permet d'obtenir des vitesses de commutation de plusieurs centaines de Méga bits.**
* ![](https://i.imgur.com/vkiptsu.png)
* **Taille = FIXE.**

:::

## a) Interface réseau

* 2 familles de trames, qui dépendent du type d'interface réseau utilisé : 
    *  **Interface réseau `UNI` ( User to Network Interface ):**
        * Prive : entre un équipement terminal privé et un commutateur ATM
        * Public : entre réseau privé ATM à un réseau public
    
    *  **Interface réseau `NNI` ( Network to Node Interface ):**
        * Prive : interface commutateur local d'une entreprise.
        * Public : interface entre deux commutateurs publics. 

## b) La cellule ATM

:::info
* **Deux types de cellules existent selon le type d'interface.**
:::

![](https://i.imgur.com/dDto6EB.png)



# 2) Les Liaisons 

* 2 types : 
    * **les liaisons point à point.** 
    * **les liaisons point à multipoint.** 

* Le réseau ATM est dit orienté connexion, à chaque demande de transmission un circuit virtuel est établit répondant à la qualité de service souhaité.


# 3) Les couches ATM

* ![](https://i.imgur.com/W9CjyaA.png)

## 3.1) La couche Physique

### a) Généralités



* La couche physique est chargée de fournir à la couche ATM un service de transport des cellules, elle est décomposée en deux sous couches:
    - **la sous-couche `TC` (Transmission Convergence).**
    - **La sous couche `PM` (Physical Medium).**

* L'ATM est une technique de multiplexage synchrone, trois modes de fonctionnement ont été définis:
    - **Le mode PDH (Plesiochronous Digital Hierarchy)** 
    - **Le mode SDH (Synchronous Digital Hierarchy)**
    - **Le mode cellule, où les cellules sont transmises directement sur le support.**
    * ![](https://i.imgur.com/Uw5HGax.png)



### b) La sous couche `TC`

* La sous couche `TC` assure:
    - **L'adaptation des débits.**
    - **Le contrôle des erreurs.**
    - **La délimitation des cellules (synchronisation).**
    - **L'adaptation des cellules au système de transmission.**


### c) La sous couche `PM`
* La couche `PM` est chargée de la transmission et de la réception du flot de bits sur le support.
*  Il réalise les fonctions suivantes:
    - **Le codage.**
    - **l'alignement.**
    - **la synchronisation bit.**
    - **l'adaptation électrique et photoélectrique au support.**


## 3.2) La couche ATM
### a) Généralités

* La couche ATM est chargé de:
    - **multiplexage et démultiplexage des cellules**
    - **L'acheminement des cellules dans le réseau.**
    - **L'ajout et du retrait des en-têtes.**
    - **Le contrôle de flux ( GFC ), à l'interface utilisateur, UNI.**
    - **L'adaptation du débit, insertion et retrait de cellules vides.**
    - **Le contrôle d'admission en fonction de la qualité de service requise.**
    - **Le lissage de trafic.**


### b) La fonction d'acheminement

* ATM établit une voie virtuelle entre les deux systèmes d'extrémité. La voie virtuel VCC ( Virtual Chanel Connection ) résulte de la concaténation des circuits virtuels.
* ATM introduit deux niveau de commutation:
    *  **la commutation des circuits virtuels (VCI).**
    *  **la commutation des conduits virtuels (VPI).**
 
* La commutation d'une cellule ATM s'effectue à l'aide de deux identifiant (étiquettes), le VCI et le VPI qui sont présent dans l'en-tête de la cellule.
* ![](https://i.imgur.com/G4fCs6x.png)


:::warning
* Un certain nombre de circuits virtuels, les 32 premiers VCI, sont toujours réservés.
:::

### c) Le contrôle de flux de congestion
* Un réseau ATM est un réseau de files d'attente, il peut donc être soumis à la congestion. 
* Trois mécanismes sont mis en œuvre pour prévenir ou guérir la congestion:
    - **L'élection de cellules à détruire.**
    - **Le contrôle d'admission d'une connexion.**
    - **Le contrôle du débit à la source.**

## 3.3) La couche `AAL`

### a) Généralité
 
* Garantit aux applications utilisateur la qualité de service requise par l'application.
* Cinq type d'adaptations spécifiques ont été définis:
    * ![](https://i.imgur.com/CvWVLlL.png)


### b) structure de la couche `AAL`

* La couche AAL est décomposée en deux sous couche : 

    - **La sous couche SAR (Segmentation And rassembly ) qui assure la segmentation et le réassemblage des données de la couche supérieure en cellules de 48 octets, et elle permet la compensation des délai de transmission, la récupération de l'horloge, ainsi que la détection des pertes de cellules ou leur insertion.**
    
    - **La sous couche CS ( Convergence Sublayer ) assure la transparence entre les applications est le mode de transfert ATM. Elle permet le multiplexage des connexions, la reprise des erreurs, la compensation de la gigue des cellules.**


# `ATM` QCM : 

	                                                                                
1. Les cellules ATM sont transmises à intervalle constant : 	 	
2. La taille des cellules ATM varie en fonction du type d ’interface (UNI, NNI)	:  	
4. La taille des cellules ATM n ’est pas fonction du débit des liens physiques	:
6. 	L ’architecture ATM spécifie les couches physiques	 :
8. Un commutateur ATM ne traite que le champ VP	 	:
10. Un commutateur ATM ne traite pas le champ le champ VC 	 	
12. Un brasseur ATM ne traite pas le champ le champ VC 	
14. Un brasseur ATM ne traite que le champ VC 	  	
16. Le champ VC est modifié dans chaque nœud ATM	 
18. Les cellules ATM erronées ne sont pas détectées au niveau AAL	  	
20.  La couche AAL assure un service de segmentation	  	
22. L ’AAL 1 est utilisée de manière privilégiée pour le transport de la voix	 	
24. L ’AAL 3/4 et l ’AAL 5 assurent des services analogues	 	
26. La classe de service UBR correspond à un service à bande passante réservée	  	
28. Toutes les classes de service ATM garantissent une qualité de service	  	 
30. La classe de service UBR correspond à un service de type « best effort »	 
32. La classe de service CBR garantie un délai d ’acheminement 	 
34. La classe de service CBR n ’offre pas de garantie sur la variation du délai d ’acheminement	
36. ATM n ’intègre pas de mécanisme de signalisation	 	
38. La signalisation ATM PNNI permet une configuration dynamique des équipements ATM	
