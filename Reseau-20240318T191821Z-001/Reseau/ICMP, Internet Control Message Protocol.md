---
tags: GAILLARD
---

# `ICMP`, Internet Control Message Protocol


## `ICMP`

* Bien que le protocole IP ne soit pas un protocole fiable, la suite TCP/IP permet d'envoyer des messages si certaines erreurs se produisent. Ces messages sont envoyés via les services du protocole ICMP. Ces messages ont pour objectif de fournir des commentaires sur les problèmes liés au traitement de paquets IP dans certaines circonstances. Les messages ICMP ne sont pas obligatoires et sont souvent interdits au sein des réseaux pour des raisons de sécurité.

* Le protocole ICMP est disponible pour IPv4 et pour IPv6. ICMPv4 est le protocole de message des réseaux IPv4. L'ICMPv6 fournit ces mêmes services pour l'IPv6, mais inclut des fonctionnalités supplémentaires. Dans ce cours, le terme ICMP est utilisé pour faire référence à l'ICMPv4 et à l'ICMPv6.

* Il existe différents types de messages ICMP, et les raisons pour lesquelles ils sont envoyés sont très diverses. Nous décrirons les messages les plus courants.


* Les messages ICMP communs à ICMPv4 et à ICMPv6 sont notamment les suivants :

    * Host confirmation (Confirmation de l'hôte)
    * Destination or Service Unreachable (destination ou service inaccessible)
    * Time exceeded (Délai dépassé)
    * Route redirection (Redirection de la route)

* **ICMPv4/6 sont obligatoires**.




