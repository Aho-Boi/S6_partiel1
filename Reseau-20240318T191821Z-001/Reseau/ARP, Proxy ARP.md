---
tags: GAILLARD
---


# `ARP`, Proxy `ARP`


## `ARP` (Address Resolution Protocol), Rappels :

* Layer 3 devices need ARP to map IP network addresses to MAC hardware addresses so that IP packets can be sent across networks. Before a device sends a datagram to another device, it looks in its ARP cache to see if there is a MAC address and corresponding IP address for the destination device. 
* If there is no entry, the source device sends a broadcast message to every device on the network. Each device compares the IP address to its own. Only the device with the matching IP address replies to the sending device with a packet containing the MAC address for the device (except in the case of “proxy ARP”). 
* The source device adds the destination device MAC address to its ARP table for future reference, creates a data-link header and trailer that encapsulates the packet, and proceeds to transfer the data. The figure below illustrates the ARP broadcast and response process.


* When the destination device lies on a remote network, one beyond another Layer 3 device, the process is the same except that the sending device sends an ARP request for the MAC address of the default gateway. 

* After the address is resolved and the default gateway receives the packet, the default gateway broadcasts the destination IP address over the networks connected to it. The Layer 3 device on the destination device network uses ARP to obtain the MAC address of the destination device and delivers the packet.




## Proxy `ARP` : 


### Def : 

* Enable devices that are separated into physical network segments connected by a router in the same IP network or subnetwork to resolve IP-to-MAC addresses. When devices are not in the same data link layer network but are in the same IP network, they try to transmit data to each other as if they were on the local network. However, the router that separates the devices will not send a broadcast message because routers do not pass hardware-layer broadcasts. Therefore, the addresses cannot be resolved.

* Proxy ARP is enabled by default so the “proxy router” that resides between the local networks responds with its MAC address as if it were the router to which the broadcast is addressed. When the sending device receives the MAC address of the proxy router, it sends the datagram to the proxy router, which in turns sends the datagram to the designated device.

### Exemple : 



* ![](https://i.imgur.com/iFp1B7R.png)


* The Host A (172.16.10.100) on Subnet A needs to send packets to Host D (172.16.20.200) on Subnet B. As shown in the diagram, Host A has a /16 subnet mask. What this means is that Host A believes that it is directly connected to all of network 172.16.0.0. When Host A needs to communicate with any devices it believes are directly connected, it sends an ARP request to the destination. Therefore, when Host A needs to send a packet to Host D, Host A believes that Host D is directly connected, so it sends an ARP request to Host D. In order to reach Host D (172.16.20.200), Host A needs the MAC address of Host D. Therefore, Host A broadcasts an ARP request on Subnet A, as shown:

  

    | Sender's MAC Address | Sender's IP Address | Target MAC Address | Target IP Address    |
    | -------------------- | ------------------- | ------------------ | ---                  |
    | 00-00-0c-94-36-aa    | 172.16.10.100       | 00-00-00-00-00-00  |172.16.20.200         |


* In this ARP request, Host A (172.16.10.100) requests that Host D (172.16.20.200) send its MAC address. The ARP request packet is then encapsulated in an Ethernet frame with the MAC address of Host A as the source address and a broadcast (FFFF.FFFF.FFFF) as the destination address. Since the ARP request is a broadcast, it reaches all the nodes in the Subnet A, which includes the e0 interface of the router, but does not reach Host D. The broadcast does not reach Host D because routers, by default, do not forward broadcasts.

* Since the router knows that the target address (172.16.20.200) is on another subnet and can reach Host D, it replies with its own MAC address to Host A.


     | Sender's MAC Address | Sender's IP Address | Target MAC Address | Target IP Address    |
     | -------------------- | ------------------- | ------------------ | ---                  |
     | 00-00-0c-94-36-ab	| 172.16.20.200	      | 00-00-0c-94-36-aa  |172.16.10.100         |

* This is the Proxy ARP reply that the router sends to Host A. The proxy ARP reply packet is encapsulated in an Ethernet frame with MAC address of the router as the source address and the MAC address of Host A as the destination address. The ARP replies are always unicast to the original requester.
* Upon receipt of this ARP reply, Host A updates its ARP table, as shown:
    

    | IP Address | MAC Address 
    | -------- | -------- 
    | 172.16.20.200     | 00-00-0c-94-36-ab
    
    

* From now on, Host A forwards all the packets that it wants to reach 172.16.20.200 (Host D) to the MAC address 00-00-0c-94-36-ab (router). Since the router knows how to reach Host D, the router forwards the packet to Host D. 
* The ARP cache on the hosts in Subnet A is populated with the MAC address of the router for all the hosts on Subnet B. Hence, all packets destined to Subnet B are sent to the router. The router forwards those packets to the hosts in Subnet B.

* The ARP cache of Host A is shown in this table:


    | IP Address    | MAC Address       |
    | ------------- | ----------------- |
    | 172.16.20.100	              |   00-00-0c-94-36-ab                |
    |       172.16.10.99	       |         00-00-0c-94-36-ab           |
    |            172.16.10.200	   |          00-00-0c-94-36-bb         |
    | 172.16.20.200 | 00-00-0c-94-36-ab |
    